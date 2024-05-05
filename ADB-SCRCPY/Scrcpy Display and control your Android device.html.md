
# scrcpy (v1.16)

Read in another language

This application provides display and control of Android devices connected on
USB (or [over TCP/IP](https://www.genymotion.com/blog/open-source-project-
scrcpy-now-works-wirelessly/)). It does not require any _root_ access. It
works on _GNU/Linux_ , _Windows_ and _macOS_.

[![screenshot](](https://github.com/Genymobile/scrcpy/blob/master/assets/screenshot-debian-600.jpg)

It focuses on:

  * **lightness** (native, displays only the device screen)
  * **performance** (30~60fps)
  * **quality** (1920×1080 or above)
  * **low latency** ([35~70ms](https://github.com/Genymobile/scrcpy/pull/646))
  * **low startup time** (~1 second to display the first image)
  * **non-intrusiveness** (nothing is left installed on the device)

## Requirements

The Android device requires at least API 21 (Android 5.0).

Make sure you [enabled adb
debugging](https://developer.android.com/studio/command-
line/adb.html#Enabling) on your device(s).

On some devices, you also need to enable [an additional
option](https://github.com/Genymobile/scrcpy/issues/70#issuecomment-373286323)
to control it using keyboard and mouse.

## Get the app

[](https://repology.org/project/scrcpy/versions)

### Linux

On Debian ( _testing_ and _sid_ for now) and Ubuntu (20.04):

    
    
    apt install scrcpy
    

A [Snap](https://en.wikipedia.org/wiki/Snappy_\(package_manager\)) package is
available: [`scrcpy`](https://snapstats.org/snaps/scrcpy).

For Fedora, a [COPR](https://fedoraproject.org/wiki/Category:Copr) package is
available: [`scrcpy`](https://copr.fedorainfracloud.org/coprs/zeno/scrcpy/).

For Arch Linux, an
[AUR](https://wiki.archlinux.org/index.php/Arch_User_Repository) package is
available: [`scrcpy`](https://aur.archlinux.org/packages/scrcpy/).

For Gentoo, an [Ebuild](https://wiki.gentoo.org/wiki/Ebuild) is available:
[`scrcpy/`](https://github.com/maggu2810/maggu2810-overlay/tree/master/app-
mobilephone/scrcpy).

You could also [build the app
manually](https://github.com/Genymobile/scrcpy/blob/master/BUILD.md) (don't
worry, it's not that hard).

### Windows

For Windows, for simplicity, a prebuilt archive with all the dependencies
(including `adb`) is available:

  * [`scrcpy-win64-v1.16.zip`](https://github.com/Genymobile/scrcpy/releases/download/v1.16/scrcpy-win64-v1.16.zip)  
_(SHA-256: 3f30dc5db1a2f95c2b40a0f5de91ec1642d9f53799250a8c529bc882bc0918f0)_

It is also available in [Chocolatey](https://chocolatey.org/):

    
    
    choco install scrcpy
    choco install adb    # if you don't have it yet

And in [Scoop](https://scoop.sh):

    
    
    scoop install scrcpy
    scoop install adb    # if you don't have it yet

You can also [build the app
manually](https://github.com/Genymobile/scrcpy/blob/master/BUILD.md).

### macOS

The application is available in [Homebrew](https://brew.sh/). Just install it:

    
    
    brew install scrcpy

You need `adb`, accessible from your `PATH`. If you don't have it yet:

    
    
    brew cask install android-platform-tools

You can also [build the app
manually](https://github.com/Genymobile/scrcpy/blob/master/BUILD.md).

## Run

Plug an Android device, and execute:

    
    
    scrcpy

It accepts command-line arguments, listed by:

    
    
    scrcpy --help

## Features

### Capture configuration

#### Reduce size

Sometimes, it is useful to mirror an Android device at a lower definition to
increase performance.

To limit both the width and height to some value (e.g. 1024):

    
    
    scrcpy --max-size 1024
    scrcpy -m 1024  # short version

The other dimension is computed to that the device aspect ratio is preserved.
That way, a device in 1920×1080 will be mirrored at 1024×576.

#### Change bit-rate

The default bit-rate is 8 Mbps. To change the video bitrate (e.g. to 2 Mbps):

    
    
    scrcpy --bit-rate 2M
    scrcpy -b 2M  # short version

#### Limit frame rate

The capture frame rate can be limited:

    
    
    scrcpy --max-fps 15

This is officially supported since Android 10, but may work on earlier
versions.

#### Crop

The device screen may be cropped to mirror only part of the screen.

This is useful for example to mirror only one eye of the Oculus Go:

    
    
    scrcpy --crop 1224:1440:0:0   # 1224x1440 at offset (0,0)

If `--max-size` is also specified, resizing is applied after cropping.

#### Lock video orientation

To lock the orientation of the mirroring:

    
    
    scrcpy --lock-video-orientation 0   # natural orientation
    scrcpy --lock-video-orientation 1   # 90° counterclockwise
    scrcpy --lock-video-orientation 2   # 180°
    scrcpy --lock-video-orientation 3   # 90° clockwise

This affects recording orientation.

### Recording

It is possible to record the screen while mirroring:

    
    
    scrcpy --record file.mp4
    scrcpy -r file.mkv

To disable mirroring while recording:

    
    
    scrcpy --no-display --record file.mp4
    scrcpy -Nr file.mkv
    # interrupt recording with Ctrl+C

"Skipped frames" are recorded, even if they are not displayed in real time
(for performance reasons). Frames are _timestamped_ on the device, so [packet
delay variation](https://en.wikipedia.org/wiki/Packet_delay_variation) does
not impact the recorded file.

### Connection

#### Wireless

_Scrcpy_ uses `adb` to communicate with the device, and `adb` can
[connect](https://developer.android.com/studio/command-line/adb.html#wireless)
to a device over TCP/IP:

  1. Connect the device to the same Wi-Fi as your computer.
  2. Get your device IP address (in Settings → About phone → Status).
  3. Enable adb over TCP/IP on your device: `adb tcpip 5555`.
  4. Unplug your device.
  5. Connect to your device: `adb connect DEVICE_IP:5555` _(replace`DEVICE_IP`)_.
  6. Run `scrcpy` as usual.

It may be useful to decrease the bit-rate and the definition:

    
    
    scrcpy --bit-rate 2M --max-size 800
    scrcpy -b2M -m800  # short version

#### Multi-devices

If several devices are listed in `adb devices`, you must specify the _serial_
:

    
    
    scrcpy --serial 0123456789abcdef
    scrcpy -s 0123456789abcdef  # short version

If the device is connected over TCP/IP:

    
    
    scrcpy --serial 192.168.0.1:5555
    scrcpy -s 192.168.0.1:5555  # short version

You can start several instances of _scrcpy_ for several devices.

#### Autostart on device connection

You could use [AutoAdb](https://github.com/rom1v/autoadb):

    
    
    autoadb scrcpy -s '{}'

#### SSH tunnel

To connect to a remote device, it is possible to connect a local `adb` client
to a remote `adb` server (provided they use the same version of the _adb_
protocol):

    
    
    adb kill-server    # kill the local adb server on 5037
    ssh -CN -L5037:localhost:5037 -R27183:localhost:27183 your_remote_computer
    # keep this open

From another terminal:

    
    
    scrcpy

To avoid enabling remote port forwarding, you could force a forward connection
instead (notice the `-L` instead of `-R`):

    
    
    adb kill-server    # kill the local adb server on 5037
    ssh -CN -L5037:localhost:5037 -L27183:localhost:27183 your_remote_computer
    # keep this open

From another terminal:

    
    
    scrcpy --force-adb-forward

Like for wireless connections, it may be useful to reduce quality:

    
    
    scrcpy -b2M -m800 --max-fps 15
    

### Window configuration

#### Title

By default, the window title is the device model. It can be changed:

    
    
    scrcpy --window-title 'My device'

#### Position and size

The initial window position and size may be specified:

    
    
    scrcpy --window-x 100 --window-y 100 --window-width 800 --window-height 600

#### Borderless

To disable window decorations:

    
    
    scrcpy --window-borderless

#### Always on top

To keep the scrcpy window always on top:

    
    
    scrcpy --always-on-top

#### Fullscreen

The app may be started directly in fullscreen:

    
    
    scrcpy --fullscreen
    scrcpy -f  # short version

Fullscreen can then be toggled dynamically with `MOD`+`f`.

#### Rotation

The window may be rotated:

    
    
    scrcpy --rotation 1

Possibles values are:

  * `0`: no rotation
  * `1`: 90 degrees counterclockwise
  * `2`: 180 degrees
  * `3`: 90 degrees clockwise

The rotation can also be changed dynamically with `MOD`+`←` _(left)_ and
`MOD`+`→` _(right)_.

Note that _scrcpy_ manages 3 different rotations:

  * `MOD`+`r` requests the device to switch between portrait and landscape (the current running app may refuse, if it does support the requested orientation).
  * `--lock-video-orientation` changes the mirroring orientation (the orientation of the video sent from the device to the computer). This affects the recording.
  * `--rotation` (or `MOD`+`←`/`MOD`+`→`) rotates only the window content. This affects only the display, not the recording.

### Other mirroring options

#### Read-only

To disable controls (everything which can interact with the device: input
keys, mouse events, drag&drop files):

    
    
    scrcpy --no-control
    scrcpy -n

#### Display

If several displays are available, it is possible to select the display to
mirror:

    
    
    scrcpy --display 1

The list of display ids can be retrieved by:

    
    
    adb shell dumpsys display   # search "mDisplayId=" in the output
    

The secondary display may only be controlled if the device runs at least
Android 10 (otherwise it is mirrored in read-only).

#### Stay awake

To prevent the device to sleep after some delay when the device is plugged in:

    
    
    scrcpy --stay-awake
    scrcpy -w

The initial state is restored when scrcpy is closed.

#### Turn screen off

It is possible to turn the device screen off while mirroring on start with a
command-line option:

    
    
    scrcpy --turn-screen-off
    scrcpy -S

Or by pressing `MOD`+`o` at any time.

To turn it back on, press `MOD`+`Shift`+`o`.

On Android, the `POWER` button always turns the screen on. For convenience, if
`POWER` is sent via scrcpy (via right-click or `MOD`+`p`), it will force to
turn the screen off after a small delay (on a best effort basis). The physical
`POWER` button will still cause the screen to be turned on.

It can also be useful to prevent the device from sleeping:

    
    
    scrcpy --turn-screen-off --stay-awake
    scrcpy -Sw

#### Render expired frames

By default, to minimize latency, _scrcpy_ always renders the last decoded
frame available, and drops any previous one.

To force the rendering of all frames (at a cost of a possible increased
latency), use:

    
    
    scrcpy --render-expired-frames

#### Show touches

For presentations, it may be useful to show physical touches (on the physical
device).

Android provides this feature in _Developers options_.

_Scrcpy_ provides an option to enable this feature on start and restore the
initial value on exit:

    
    
    scrcpy --show-touches
    scrcpy -t

Note that it only shows _physical_ touches (with the finger on the device).

#### Disable screensaver

By default, scrcpy does not prevent the screensaver to run on the computer.

To disable it:

    
    
    scrcpy --disable-screensaver

### Input control

#### Rotate device screen

Press `MOD`+`r` to switch between portrait and landscape modes.

Note that it rotates only if the application in foreground supports the
requested orientation.

#### Copy-paste

Any time the Android clipboard changes, it is automatically synchronized to
the computer clipboard.

Any `Ctrl` shortcut is forwarded to the device. In particular:

  * `Ctrl`+`c` typically copies
  * `Ctrl`+`x` typically cuts
  * `Ctrl`+`v` typically pastes (after computer-to-device clipboard synchronization)

This typically works as you expect.

The actual behavior depends on the active application though. For example,
_Termux_ sends SIGINT on `Ctrl`+`c` instead, and _K-9 Mail_ composes a new
message.

To copy, cut and paste in such cases (but only supported on Android >= 7):

  * `MOD`+`c` injects `COPY`
  * `MOD`+`x` injects `CUT`
  * `MOD`+`v` injects `PASTE` (after computer-to-device clipboard synchronization)

In addition, `MOD`+`Shift`+`v` allows to inject the computer clipboard text as
a sequence of key events. This is useful when the component does not accept
text pasting (for example in _Termux_ ), but it can break non-ASCII content.

**WARNING:** Pasting the computer clipboard to the device (either via
`Ctrl`+`v` or `MOD`+`v`) copies the content into the device clipboard. As a
consequence, any Android application could read its content. You should avoid
to paste sensitive content (like passwords) that way.

#### Pinch-to-zoom

To simulate "pinch-to-zoom": `Ctrl`+ _click-and-move_.

More precisely, hold `Ctrl` while pressing the left-click button. Until the
left-click button is released, all mouse movements scale and rotate the
content (if supported by the app) relative to the center of the screen.

Concretely, scrcpy generates additional touch events from a "virtual finger"
at a location inverted through the center of the screen.

#### Text injection preference

There are two kinds of [events](https://blog.rom1v.com/2018/03/introducing-
scrcpy/#handle-text-input) generated when typing text:

  * _key events_ , signaling that a key is pressed or released;
  * _text events_ , signaling that a text has been entered.

By default, letters are injected using key events, so that the keyboard
behaves as expected in games (typically for WASD keys).

But this may [cause
issues](https://github.com/Genymobile/scrcpy/issues/650#issuecomment-512945343).
If you encounter such a problem, you can avoid it by:

    
    
    scrcpy --prefer-text

(but this will break keyboard behavior in games)

#### Key repeat

By default, holding a key down generates repeated key events. This can cause
performance problems in some games, where these events are useless anyway.

To avoid forwarding repeated key events:

    
    
    scrcpy --no-key-repeat

### File drop

#### Install APK

To install an APK, drag & drop an APK file (ending with `.apk`) to the
_scrcpy_ window.

There is no visual feedback, a log is printed to the console.

#### Push file to device

To push a file to `/sdcard/` on the device, drag & drop a (non-APK) file to
the _scrcpy_ window.

There is no visual feedback, a log is printed to the console.

The target directory can be changed on start:

    
    
    scrcpy --push-target /sdcard/foo/bar/

### Audio forwarding

Audio is not forwarded by _scrcpy_. Use
[sndcpy](https://github.com/rom1v/sndcpy).

Also see [issue #14](https://github.com/Genymobile/scrcpy/issues/14).

## Shortcuts

In the following list, `MOD` is the shortcut modifier. By default, it's (left)
`Alt` or (left) `Super`.

It can be changed using `--shortcut-mod`. Possible keys are `lctrl`, `rctrl`,
`lalt`, `ralt`, `lsuper` and `rsuper`. For example:

    
    
    # use RCtrl for shortcuts
    scrcpy --shortcut-mod=rctrl
    
    # use either LCtrl+LAlt or LSuper for shortcuts
    scrcpy --shortcut-mod=lctrl+lalt,lsuper

_`[Super](https://en.wikipedia.org/wiki/Super_key_\(keyboard_button\))` is
typically the `Windows` or `Cmd` key._

Action | Shortcut  
---|---  
Switch fullscreen mode | `MOD`+`f`  
Rotate display left | `MOD`+`←` _(left)_  
Rotate display right | `MOD`+`→` _(right)_  
Resize window to 1:1 (pixel-perfect) | `MOD`+`g`  
Resize window to remove black borders | `MOD`+`w` | _Double-click¹_  
Click on `HOME` | `MOD`+`h` | _Middle-click_  
Click on `BACK` | `MOD`+`b` | _Right-click²_  
Click on `APP_SWITCH` | `MOD`+`s`  
Click on `MENU` (unlock screen) | `MOD`+`m`  
Click on `VOLUME_UP` | `MOD`+`↑` _(up)_  
Click on `VOLUME_DOWN` | `MOD`+`↓` _(down)_  
Click on `POWER` | `MOD`+`p`  
Power on | _Right-click²_  
Turn device screen off (keep mirroring) | `MOD`+`o`  
Turn device screen on | `MOD`+`Shift`+`o`  
Rotate device screen | `MOD`+`r`  
Expand notification panel | `MOD`+`n`  
Collapse notification panel | `MOD`+`Shift`+`n`  
Copy to clipboard³ | `MOD`+`c`  
Cut to clipboard³ | `MOD`+`x`  
Synchronize clipboards and paste³ | `MOD`+`v`  
Inject computer clipboard text | `MOD`+`Shift`+`v`  
Enable/disable FPS counter (on stdout) | `MOD`+`i`  
Pinch-to-zoom | `Ctrl`+ _click-and-move_  
  
_¹Double-click on black borders to remove them._  
_²Right-click turns the screen on if it was off, presses BACK otherwise._  
_³Only on Android >= 7._

All `Ctrl`+ _key_ shortcuts are forwarded to the device, so they are handled
by the active application.

## Custom paths

To use a specific _adb_ binary, configure its path in the environment variable
`ADB`:

    
    
    ADB=/path/to/adb scrcpy
    

To override the path of the `scrcpy-server` file, configure its path in
`SCRCPY_SERVER_PATH`.
