Zink driver allows you to run 3D graphics programs in Termux proot-distro with Android phone's GPU hardware acceleration. 

Vulkan API is required.  Mouse and keyabord are recommended.

**Please note that not all app would detect zink driver.**

Special thanks to [suhan-paradkar](https://github.com/suhan-paradkar) for his instructions and driver patches.

- Termux version: 0.118.0
- Android version: 12L
- Device: Sony Xperia 5 II 

## What can GPU Acceleration do?
Play 3D games, such as Minecraft, or editing videos.
![](https://i.imgur.com/3ZHpbjD.png)

## Can it run in a VNC server?
Probably not. TigerVNC only supports software rendering. You will need a Termux-x11 application for display.

## 1. Install Termux and Termux-x11
1. Install Termux from [F-Droid](https://f-droid.org/en/packages/com.termux/)

2. Launch Termux. Update Termux packages (Type `Y` if asking for a update). Exit.
```bash
pkg update
```

3. Install Termux-x11 apk from [Github repo](https://github.com/termux/termux-x11). You should get a archive which contains an apk and a .deb package.

4. Launch Termux, type in the following commands to grant permissions of accessing internal storage.
```bash
termux-setup-storage
```

5. Move .deb package to Termux's directory. Say your .deb is located at `Internal Storage/Downloads/termux-x11`, then type:
```bash
mv storage/shared/download/termux-x11/termux-x11.deb ~
```

6. Install dependencies
```bash
pkg install x11-repo termux-x11 xwayland -y
```

7. Install .deb package
```bash
dpkg -i termux-x11.deb
```

8. Edit Termux properties, make sure `allow-external-apps=yes` is uncommented.
```bash\
cd .termux
nano termux.properites
```

## 2. Install Termux proot-distro
Here I choose the pre-cionfigured "Udroid" distro, based on Ubuntu 20.04.

1. Install Udroid
```bash
#You can find more command usages at: https://udroid-rc.gitbook.io/udroid-wiki/udroid-landing/readme
curl -L -o install.sh https://git.io/hippo-installer
bash install.sh
udroid --install
```

2. Log into udroid and update packages.
```bash
proot-distro login udroid-focal-xfce4
apt updates
apt upgrades
```

3. Logout.
```bash
exit
```

## 3. Compile mesa drivers
**These steps are done in Termux, not in proot-distro!**

1. Download instructions.tar.gz from [suhan-paradkar's repo](https://github.com/suhan-paradkar/tewmux-disabled/releases).

2. Extract it. Copy `instructions-v2` to Termux's directory:
```bash
cp storage/shared/downloads/instructions-v2 ~
```
3. Then open the .txt file in the instructions-v2. Follow its directions to compile all drivers:
```bash
mkdir ~/dir
termux-setup-storage
echo Y | pkg upgrade -y
pkg install -y x11-repo
pkg install -y clang lld cmake autoconf automake libtool binutils '*ndk*' make python git libandroid-shmem-static 'vulkan*' ninja llvm bison flex libx11 libdrm libpixman libxfixes libjpeg-turbo xtrans libxxf86vm xorg-xrandr xorg-font-util xorg-util-macros libxfont2 libxkbfile libpciaccess xcb-util-renderutil xcb-util-image xcb-util-keysyms xcb-util-wm xorg-xkbcomp xkeyboard-config libxdamage libxinerama libepoxy
#Install old version
pip install meson mako=0.60.0
cd ~/dir

########################################
# get the sources of the programs/libs #
########################################

git clone --depth 1 https://gitlab.freedesktop.org/xorg/proto/xorgproto.git
git clone --depth 1 https://gitlab.freedesktop.org/wayland/wayland.git
git clone --depth 1 https://gitlab.freedesktop.org/wayland/wayland-protocols.git
git clone --depth 1 https://gitlab.freedesktop.org/xorg/lib/libxshmfence.git
git clone --single-branch --shallow-since 2022-02-01 https://gitlab.freedesktop.org/mesa/mesa.git
git clone --depth 1 https://github.com/dottedmag/libsha1.git
git clone --depth 1 https://github.com/anholt/libepoxy.git
git clone --depth 1 https://gitlab.freedesktop.org/xorg/xserver.git -b xorg-server-1.20.14 xorg-server-1.20.14
git clone --depth 1 https://github.com/glmark2/glmark2.git
curl -LO https://dri.freedesktop.org/libdrm/libdrm-2.4.109.tar.xz

#############################
# Compile the programs/libs #
#############################

#xorgproto
cd ~/dir/xorgproto
./autogen.sh --prefix=$PREFIX --with-xmlto=no --with-fop=no --with-xsltproc=no
make -j8 install

#libwayland 
cd ~/dir/wayland
mkdir build
cd build
meson -Dprefix=$PREFIX -Ddocumentation=false ..
ninja -j8 install

#wayland-protocols
cd ~/dir/wayland-protocols
mkdir build
cd build
meson -Dprefix=$PREFIX ..
ninja -j8 install 
#If the pkgconfig file was installed to $PREFIX/share/pkgconfig, try:
rm $PREFIX/lib/pkgconfig/wayland-protocols.pc
cp $PREFIX/share/pkgconfig/wayland-protocols.pc $PREFIX/lib/pkgconfig

#libxshmfence
cd ~/dir/libxshmfence
./autogen.sh --prefix=$PREFIX --with-shared-memory-dir=$TMPDIR
sed -i s/values.h/limits.h/ ./src/xshmfence_futex.h
make -j8 install CPPFLAGS=-DMAXINT=INT_MAX

#libdrm 
cd ~/dir
tar -xf libdrm-2.4.109.tar.xz
cd libdrm-2.4.109
mkdir build
cd build
meson -Dprefix=$PREFIX -Dintel=false -Dradeon=false -Damdgpu=false -Dnouveau=false -Dvmwgfx=false -Dvc4=false ..
ninja -j4 install

#mesa
cd ~/dir/mesa
git checkout 0d0ecbd987e7b37af9ea2c7dbf33bf91d018a603
git apply ~/instructions-v2/patches/mesa/mesa_main.patch
mkdir build
cd build
meson -Dcpp_rtti=false ..
ninja -j4 install

#libsha1
cd ~/dir/libsha1
#If failed, try again
./autogen.sh --prefix=$PREFIX
make -j8 install

#libepoxy
cd ~/dir/libepoxy
git apply ~/instructions-v2/patches/libepoxy/libepoxy.patch
mkdir build 
cd build
meson -Dprefix=$PREFIX -Degl=yes -Dglx=yes -Dx11=true -Dtests=false ..
ninja -j8 install

#xorg-server
cd ~/dir/xorg-server-1.20.14
git apply ~/instructions-v2/patches/xorg-server/xorg-server-1.20.14.patch
#If failed, try again
./autogen.sh --enable-mitshm --enable-xcsecurity --enable-xf86bigfont --enable-xwayland --enable-xorg --enable-xnest --enable-xvfb --disable-xwin --enable-xephyr --enable-kdrive --disable-devel-docs --disable-config-hal --disable-config-udev --disable-unit-tests --disable-selective-werror --disable-static --without-dtrace --disable-glamor --enable-dri --enable-dri2 --enable-dri3 --enable-glx --with-sha1=libsha1 --with-pic --prefix=$PREFIX
make install -j4 LDFLAGS=' -fuse-ld=lld /data/data/com.termux/files/usr/lib/libandroid-shmem.a -llog'

#glmark2
cd ~/dir/glmark2
mkdir build
cd build
meson -Dprefix=$PREFIX -Dflavors=x11-gl ..
ninja -j4 install
```

## 4. Check if the drivers are working

1. To login proot-distro with Termux-x11, type in:
```bash
termux-x11
# Swipe in from the left edge of the screen, launch another Termux session
proot-distro login udroid-focal-xfce4 --shared-tmp
export DISPLAY=:0
# You should see XFCE4 desktop in Termux-x11 app.
dbus-launch --exit-with-session startxfce4
```

2. If pulseaudio is not working, try:
```bash
# Swipe in from the left edge of the screen, launch another Termux session
pulseaudio --start --load="module-native-protocol-tcp auth-ip-acl=127.0.0.1 auth-anonymous=1" --exit-idle-time=-1
# Swipe in from the left edge of the screen, launch another Termux session
proot-distro login udroid-xfce4-focal
export PULSE_SERVER=127.0.0.1 && pulseaudio --start --disable-shm=1 --exit-idle-time=-1
exit
```

3. Run `glmark2` (pre-installed in udroid), you will see a series of 3D tests running. Next try to play some 1080p60fps videos in VLC.
![](https://i.imgur.com/vay4G2K.png)

4. To stop xfce4 session in Termux-x11, press `Ctrl + C` in Termux. Then logout.
```
exit
```