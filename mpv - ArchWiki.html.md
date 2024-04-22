[](https://www.archlinux.org/)

  * [Home](https://www.archlinux.org/)
  * [Packages](https://www.archlinux.org/packages/)
  * [Forums](https://bbs.archlinux.org/)
  * [Wiki](https://wiki.archlinux.org/)
  * [Bugs](https://bugs.archlinux.org/)
  * [Security](https://security.archlinux.org/)
  * [AUR](https://aur.archlinux.org/)
  * [Download](https://www.archlinux.org/download/)

# mpv

From ArchWiki

Jump to navigation Jump to search

Related articles

  * [MPlayer](https://wiki.archlinux.org/index.php/MPlayer "MPlayer")
  * [youtube-dl](https://wiki.archlinux.org/index.php/Youtube-dl "Youtube-dl")

[mpv](https://mpv.io/) is a media player based on
[MPlayer](https://wiki.archlinux.org/index.php/MPlayer "MPlayer") and the now
unmaintained _mplayer2_. It supports a wide variety of video file formats,
audio and video codecs, and subtitle types. A comprehensive (although
admittedly incomplete) list of differences between _mpv_ and the
aforementioned players can be found [here](https://github.com/mpv-
player/mpv/blob/master/DOCS/mplayer-changes.rst).

## Contents

  * 1 Installation
    * 1.1 Front ends
  * 2 Configuration
    * 2.1 General settings
      * 2.1.1 High quality configurations
      * 2.1.2 Custom profiles
    * 2.2 Key bindings
    * 2.3 Additional configuration files
  * 3 Scripts
    * 3.1 JavaScript
    * 3.2 Lua
      * 3.2.1 mpv-stats
      * 3.2.2 mpv-webm
    * 3.3 C
      * 3.3.1 mpv-mpris
  * 4 Vapoursynth
    * 4.1 SVP 4 Linux (SmoothVideoProject)
  * 5 Tips and Tricks
    * 5.1 Hardware video acceleration
    * 5.2 Save position on quit
    * 5.3 Volume is too low
    * 5.4 Play a DVD
    * 5.5 Quickly cycle between aspect ratios
    * 5.6 Ignoring aspect ratio
    * 5.7 Draw to the root window
    * 5.8 Always show application window
    * 5.9 Disable video output
    * 5.10 Restoring old OSC
    * 5.11 Use as a browser plugin
    * 5.12 Improving mpv as a music player with Lua scripts
    * 5.13 Twitch.tv streaming over mpv
    * 5.14 youtube-dl and choosing formats
    * 5.15 youtube-dl audio with search
    * 5.16 Creating a single screenshot
  * 6 Troubleshooting
    * 6.1 General debugging
    * 6.2 Fix jerky playback and tearing
    * 6.3 Problems with window compositors
    * 6.4 No volume bar, cannot change volume
    * 6.5 GNOME Blank screen (Wayland)
    * 6.6 Use mpv with a compositor
    * 6.7 Cursor theme not respected under GNOME Wayland

## Installation

[Install](https://wiki.archlinux.org/index.php/Install "Install") the
[mpv](https://www.archlinux.org/packages/?name=mpv) package or [mpv-
git](https://aur.archlinux.org/packages/mpv-git/)AUR for the development
version.

### Front ends

See [List of applications/Multimedia#mpv-
based](https://wiki.archlinux.org/index.php/List_of_applications/Multimedia#mpv-
based "List of applications/Multimedia").

## Configuration

_mpv_ comes with good all-around defaults that should work well on computers
with weaker/older video cards. However, if you have a computer with a more
modern video card then _mpv_ allows you to do a great deal of configuration to
achieve better video quality (limited only by the power of your video card).
To do this one only needs to create a few configuration files (they do not
exist by default).

**Note:** Configuration files are read system-wide from `/etc/mpv` and per-
user from `~/.config/mpv` (unless the [environment
variable](https://wiki.archlinux.org/index.php/Environment_variable
"Environment variable") `XDG_CONFIG_HOME` is set), where per-user settings
override system-wide settings, all of which are overridden by the command
line. User specific configuration is suggested since it may require some trial
and error.

To help you get started _mpv_ provides sample configuration files with default
settings. Copy them to use as a starting point:

    
    
    $ cp -r /usr/share/doc/mpv/ ~/.config/
    

`mpv.conf` contains the majority of _mpv'_ s settings, `input.conf` contains
key bindings. Read through both of them to get an idea of how they work and
what options are available.

### General settings

Add the following settings to `~/.config/mpv/mpv.conf`.

#### High quality configurations

This loads high quality OpenGL options when using `vo=gpu` as video output
(default). Most users can run these without any problems, but they are not
enabled by default to avoid causing problems for the few users who cannot run
them:

    
    
    profile=gpu-hq
    

The `gpu-hq` profile defaults to the `spline36` scaling filter for mid quality
and speed. For the best quality video output, the manual states that if your
hardware can run it, `ewa_lanczossharp` is probably what you should use.

    
    
    profile=gpu-hq
    scale=ewa_lanczossharp
    cscale=ewa_lanczossharp
    

These last three options are a little more complicated. The first option makes
it so that if audio and video go out of sync then instead of dropping video
frames it will resample the audio (a slight change in audio pitch is often
less noticeable than dropped frames). The mpv wiki has an in depth article on
it titled [Display Synchronization](https://github.com/mpv-
player/mpv/wiki/Display-synchronization). The remaining two essentially make
motion appear smoother on your display by changing the way that frames are
shown so that the source framerate jives better with your display's refresh
rate (not to be confused with SVP's technique which actually converts video to
60fps). The mpv wiki has an in depth article on it titled
[Interpolation](https://github.com/mpv-player/mpv/wiki/Interpolation) though
it is also commonly known as _smoothmotion_.

    
    
    profile=gpu-hq
    scale=ewa_lanczossharp
    cscale=ewa_lanczossharp
    video-sync=display-resample
    interpolation
    tscale=oversample
    

**Note:** If [NVIDIA
Optimus](https://wiki.archlinux.org/index.php/NVIDIA_Optimus "NVIDIA Optimus")
is being used, the line `video-sync=display-resample` may cause video to be
sped up.

Beyond this there is still a lot you can do but things become more
complicated, require more powerful video cards, and are in constant
development. As a brief overview, it is possible to load special shaders that
perform exotic scaling and sharpening techniques including some that actually
use deep neural networks trained on images (for both real world and animated
content). To learn more about this take a look around the [mpv
wiki](https://github.com/mpv-player/mpv/wiki), particularly the [user shader's
section](https://github.com/mpv-player/mpv/wiki/User-Scripts#user-shaders).

There are also plenty of other options you may find desirable as well. It is
worthwhile taking a look at
[mpv(1)](https://jlk.fjfi.cvut.cz/arch/manpages/man/mpv.1). It is also helpful
to run _mpv_ from the command line to check for error messages about the
config.

#### Custom profiles

In `mpv.conf` it is possible to create _profiles_ which are essentially just
"groups of options" with which you can:

  * Quickly switch between different configurations without having to rewrite the file.
  * Create special profiles for special content.
  * _nest_ profiles so that you can make more complicated _profiles_ out of simpler ones.

Creating a profile is easy. The area at the top of `mpv.conf` is called the
top level, any options you write there will kick into effect once _mpv_ is
started. However, once you define a profile by writing its name in brackets
then every option you write below it (until you define a new profile) is
considered part of that profile. Here is an example `mpv.conf`:

    
    
    profile=myprofile2        #Top level area, load myprofile2
    ontop=yes                 #Always on top
    
    [myprofile1]              #A simple profile, top level area ends here
    profile-desc="a profile"  #Optional description for profile
    fs=yes                    #Start in full screen
    
    [myprofile2]              #Another simple profile
    profile=gpu-hq            #A built in profile that comes with mpv
    log-file=~~/log           #Sets a location for writing a log file, ~~/ translates to ~/.config/mpv
    

There are only two lines within the top level area and there are two separate
profiles defined below it. When _mpv_ starts it sees the first line, loads the
options in `myprofile2` (which means it loads the options in `gpu-hq` and
`log-file=~~/log`) finally it loads `ontop=yes` and finishes starting up.
Note, `myprofile1` is never loaded because it is never called in the top level
area.

Alternatively one could call _mpv_ from the command line with:

    
    
    $ mpv --profile=myprofile1 video.mkv
    

and it would ignore all options except the ones for `myprofile1`.

### Key bindings

Key bindings are fairly straightforward given the examples in
`/usr/share/doc/mpv/input.conf` and the relevant section in the
[manual](https://mpv.io/manual/master/#command-interface).

Add the following examples to `~/.config/mpv/input.conf`:

    
    
    shift+s         screenshot each-frame
    Shift+UP        seek  600
    Shift+DOWN      seek -600
    =               cycle video-unscaled
    -               cycle-values window-scale 2 3 1 .5
    WHEEL_UP        add volume 5
    WHEEL_DOWN      add volume -5
    WHEEL_LEFT      ignore
    WHEEL_RIGHT     ignore
    Alt+RIGHT       add video-rotate 90
    Alt+LEFT        add video-rotate -90
    Alt+-           add video-zoom -0.25
    Alt+=           add video-zoom 0.25
    Alt+j           add video-pan-x -0.05
    Alt+l           add video-pan-x 0.05
    Alt+i           add video-pan-y 0.05
    Alt+k           add video-pan-y -0.05
    Alt+BS          set video-zoom 0; set video-pan-x 0; set video-pan-y 0
    

For an attempt to reproduce MPC-HC key bindings in mpv, see
[[1]](https://github.com/dragons4life/MPC-HC-config-for-
MPV/blob/master/input.conf).

### Additional configuration files

In addition there are a few more configuration files and directories that can
be created, among which:

  * `~/.config/mpv/script-opts/osc.conf` manages the [On Screen Controller](https://mpv.io/manual/master/#on-screen-controller).
  * `~/.config/mpv/scripts/ _script-name_.lua` for Lua scripts. See [[2]](https://github.com/mpv-player/mpv/issues/3500#issuecomment-305646994) for an example.

See <https://mpv.io/manual/master/#files> for more.

## Scripts

_mpv_ has a [large variety of scripts](https://github.com/mpv-
player/mpv/wiki/User-Scripts) that extend the functionality of the player. To
this end, it has internal bindings for both Lua and JavaScript (added
recently).

Scripts are typically installed by putting them in the
`~/.config/mpv/scripts/` directory (you may have to create it first). After
that they will be automatically loaded when mpv starts (this behavior can be
altered with other _mpv_ options). Some scripts come with their own
installation and configuration instructions, so make sure to have a look. In
addition some scripts are old, broken, and unmaintained.

### JavaScript

Since JavaScript support is still fairly new, there is currently very little
in the way of scripts, but [documentation
exists](https://mpv.io/manual/master/#javascript) for anyone interested in
making their own.

JavaScript support is not available in the
[mpv](https://www.archlinux.org/packages/?name=mpv) build, but it is supported
by some AUR packages e.g. [mpv-full](https://aur.archlinux.org/packages/mpv-
full/)AUR and [mpv-full-git](https://aur.archlinux.org/packages/mpv-full-
git/)AUR.

### Lua

There are a lot of interesting Lua scripts for mpv. If you would like to make
your own, the relevant documentation may be found
[here](https://github.com/mpv-player/mpv/blob/master/DOCS/man/lua.rst).

#### mpv-stats

[mpv-stats](https://github.com/Argon-/mpv-stats/) (or simply _stats_ ) is a
Lua script that outputs a lot of live statistics showing how well _mpv_ is
currently doing. It is very useful for making sure that your hardware can keep
up with your configuration and for comparing different configurations. Since
version [v0.28.0](https://github.com/mpv-player/mpv/releases/tag/v0.28.0), the
script is built into [mpv](https://www.archlinux.org/packages/?name=mpv) and
can be toggled on or off with the `i` or `I` keys (by default).

#### mpv-webm

[mpv-webm](https://github.com/ElegantMonkey/mpv-webm) (or simply _webm_ ) is a
very easy to use Lua script that allows one to create WebM files while
watching videos. It includes several features and does not have any extra
dependencies (relies entirely on mpv).

### C

#### mpv-mpris

The C plugin [mpv-mpris](https://github.com/hoyon/mpv-mpris) allows other
applications to integrate with _mpv_ via the MPRIS protocol. For example, with
mpv-mpris installed,
[kdeconnect](https://www.archlinux.org/packages/?name=kdeconnect) can
automatically pause video playback in _mpv_ when a phone call arrives.

Install [mpv-mpris](https://aur.archlinux.org/packages/mpv-mpris/)AUR and
follow the post-installation instructions displayed by Pacman.

## Vapoursynth

Vapoursynth is an alternative to AviSynth that can be used on Linux and allows
for Video manipulation via python scripts. Vapoursynths python scripts can be
used as video filters for _mpv_.

To use vapoursynth filters you have to install the
[vapoursynth](https://www.archlinux.org/packages/?name=vapoursynth) package
(or [vapoursynth-git](https://aur.archlinux.org/packages/vapoursynth-git/)AUR)
and compile _mpv_ with the `--enable-vapoursynth` build flag.

This is easier to do by first installing Vapoursynth and then installing (or
re-installing if it is already installed) [mpv-
git](https://aur.archlinux.org/packages/mpv-git/)AUR. The configure script for
[mpv-git](https://aur.archlinux.org/packages/mpv-git/)AUR will auto-detect
Vapoursynth (as long as it has already been installed) and it will
automatically compile _mpv_ with support for Vapoursynth without having to
manually change any configure options or anything (this makes it very easy to
update _mpv_ as well).

### SVP 4 Linux (SmoothVideoProject)

[SmoothVideoProject SVP](https://www.svp-team.com/wiki/Main_Page) is a program
that is primarily known for converting video to 60fps. It is free [as in beer]
and full featured for 64bit Linux (costs money for Windows and OS X and is
incompatible with 32bit Linux).

It has three main features and each one can be disabled/enabled as one chooses
(you are not forced to use motion interpolation).

  1. [Motion interpolation](https://www.svp-team.com/wiki/Manual:FRC) ([youtube video](https://www.youtube.com/watch?v=Wjb6CSe4708)) - An algorithm that converts video to 60fps. This creates the somewhat controversial "soap opera effect" that some people love and others hate. Unfortunately the algorithm is not perfect and it also introduces more than its share of weird artifacts. The algorithm can be tuned (via a slider) for either performance or quality. It also has some artifact reduction settings that interpolate actual frames with the generated frames reducing the noticeability of the artifacts. The framerate detection can be set to automatic or manual (manual seems to resolve performance issues for some users).
  2. [Black bar lighting](https://www.svp-team.com/wiki/Manual:Outer_lighting) ([youtube video](https://www.youtube.com/watch?v=yTzTpW3kTBE)) - If the image has an aspect ratio that produces black bars on your display then SVP will illuminate the black bars with "lights" generated by the content on the screen. It has some amount of customization but the defaults are pretty close to optimal.
  3. [LED ambient lighting control](https://www.svp-team.com/wiki/Manual:SVPlight) ([youtube video](https://www.youtube.com/watch?v=UUM2n-8kIJ8)) - Has the ability to control LED ambient lighting attached to your television.

Once you have _mpv_ compiled with Vapoursynth support it is fairly easy to get
SVP working with _mpv_. Simply install
[svp](https://aur.archlinux.org/packages/svp/)AUR, open the SVP program to let
it assess your system performance (you may want to close other programs first
so that it gets an accurate reading), and finally add the following _mpv_
profile to your mpv.conf[[3]](https://www.svp-team.com/wiki/SVP:mpv):

    
    
    mpv.conf
    
    
    [svp]
    input-ipc-server=/tmp/mpvsocket     # Receives input from SVP
    hr-seek-framedrop=no                # Fixes audio desync
    resume-playback=no                  # Not compatible with SVP
    
    # Can fix stuttering in some cases, in other cases probably causes it. Try it if you experience stuttering.
    #opengl-early-flush=yes

Then, in order to use SVP you must have the SVP program running in the
background before opening the file using _mpv_ with that profile. Either do:

    
    
    $ mpv --profile=svp video.mkv
    

or set `profile=svp` in the top-level portion of the _mpv_ configuration.

If you want to use hardware decoding then you must use a copy-back decoder
since normal decoders are not compatible with Vapoursynth (choose a `hwdec`
option that ends in `-copy`). For instance:

    
    
    hwdec=auto-copy
    hwdec-codecs=all
    

Either way, hardware decoding is discouraged by _mpv_ developers and is not
likely to make a significant difference in performance.

## Tips and Tricks

### Hardware video acceleration

See [Hardware video
acceleration](https://wiki.archlinux.org/index.php/Hardware_video_acceleration
"Hardware video acceleration").

Hardware accelerated video decoding is available via `--hwdec= _API_` option.
For list of all supported APIs and other required options see [relevant manual
section](https://mpv.io/manual/stable/#options-hwdec).

For [Wayland](https://wiki.archlinux.org/index.php/Wayland "Wayland") use
`--gpu-context=wayland` option. For list of other available GPU APIs see
[manual](https://mpv.io/manual/stable/#options-gpu-context).

### Save position on quit

By default you can save the position and quit by pressing `Shift+q`. The
shortcut can be changed by setting `quit_watch_later` in the key bindings
configuration file.

To automatically save the current playback position on quit, start _mpv_ with
`--save-position-on-quit`, or add `save-position-on-quit` to the configuration
file.

### Volume is too low

Set `volume-max= _value_` in your configuration file to a reasonable amount,
such as `volume-max=150`, which then allows you to increase your volume up to
150%, which is more than twice as loud. Increasing your volume too high will
result in clipping artefacts. Additionally (or alternatively), you can utilize
[dynamic range
compression](https://en.wikipedia.org/wiki/Dynamic_range_compression
"wikipedia:Dynamic range compression") with `af=acompressor`.

### Play a DVD

mpv does not support DVD menus. To start the main stream with the longest
title of a video DVD, use the command:

    
    
    $ mpv dvd://
    

An optional title specifier is a number (starting at 0) which selects between
separate video streams on the DVD:

    
    
    $ mpv dvd://[title] 
    

DVDs which have been copied on to a local file system (by e.g. the
[dvdbackup](https://wiki.archlinux.org/index.php/Dvdbackup "Dvdbackup") tool)
are accommodated by specifying the path to the local copy: `--dvd-device=
_PATH_`.

See the following [desktop
file](https://wiki.archlinux.org/index.php/Desktop_file "Desktop file")
example for playing DVDs from a local file system:

    
    
    [Desktop Entry]
    Type=Application
    Name=mpv Media Player DVD 
    GenericName=Multimedia player
    Comment=Play movies and songs
    Icon=mpv
    Exec=mpv dvd:// --player-operation-mode=pseudo-gui --force-window --idle --dvd-device=%f
    Terminal=false
    Categories=AudioVideo;Audio;Video;Player;TV;
    # (MimeType and X-KDE-Protocols omitted, see orginianl mpv.desktop file)
    

By replacing the Exec line with

    
    
    Exec=mpv dvd://0 dvd://1 dvd://2 dvd://3 dvd://4 dvd://5 dvd://6 dvd://7 dvd://8 dvd://9  --player-operation-mode=pseudo-gui --force-window --idle --dvd-device=%f
    

the mpv player will queue DVD title 0 to 9 in the playlist, which allows the
user to play the titles consecutively or jump forward and backward in the DVD
titles with the mpv GUI.

Install [libdvdcss](https://www.archlinux.org/packages/?name=libdvdcss), to
fix the error:

    
    
    [dvdnav] Error getting next block from DVD 1 (Error reading from DVD.)
    

### Quickly cycle between aspect ratios

You can cycle between aspect ratios using `Shift+a`.

### Ignoring aspect ratio

You can ignore aspect ratio using `--keepaspect= _no_`. To make option
permanent, add line `keepaspect= _no_` to configuration file.

### Draw to the root window

Run _mpv_ with `--wid=0`. _mpv_ will draw to the window with a window ID of 0.

### Always show application window

To show application window even for audio files when launching mpv from
command line use `--force-window` option. To make option permament, add line
`force-window=yes` to the configuration file.

### Disable video output

To disable video output when launching from command line use `--vid=no`
option, or its alias, `--no-video`.

### Restoring old OSC

Since version 0.21.0, _mpv_ has replaced the on-screen controls by a
bottombar. In case you want on-screen controls back, you can edit the _mpv_
configuration [as described here](https://github.com/mpv-
player/mpv/wiki/FAQ#i-want-the-old-osc-back).

### Use as a browser plugin

With the help of
[mozplugger](https://aur.archlinux.org/packages/mozplugger/)AUR, _mpv_ can be
used in a supported browser to play video. See [Browser
plugins#MozPlugger](https://wiki.archlinux.org/index.php/Browser_plugins#MozPlugger
"Browser plugins") for configuration details. This coupled with a user script
such as [ViewTube](http://isebaro.com/viewtube/?ln=en), allows you to use
_mpv_ in place of a site's integrated video player.

It may be needed to specify a valid user agent for HTTP streaming, e.g. `user-
agent="Mozilla/5.0 (X11; Linux x86_64; rv:49.0) Gecko/20100101 Firefox/49.0"`.

[Browser plugins#Multimedia
playback](https://wiki.archlinux.org/index.php/Browser_plugins#Multimedia_playback
"Browser plugins") page shows other easy ways to watch videos.

### Improving mpv as a music player with Lua scripts

The development of _mpv'_ s Lua scripts are documented in
[DOCS/man/lua.rst](https://github.com/mpv-
player/mpv/blob/master/DOCS/man/lua.rst) and examples are shown in
[TOOLS/lua](https://github.com/mpv-player/mpv/tree/master/TOOLS/lua) of the
[mpv repository](https://github.com/mpv-player/mpv). [This blog
post](https://web.archive.org/web/20160320001546/http://bamos.github.io/2014/07/05/mpv-
lua-scripting/) introduces the
[music.lua](https://github.com/bamos/dotfiles/blob/master/.mpv/scripts.old/music.lua)
script, which shows how Lua scripts can be used to improve _mpv_ as a music
player.

### Twitch.tv streaming over mpv

If [youtube-dl](https://wiki.archlinux.org/index.php/Youtube-dl "Youtube-dl")
is installed, _mpv_ can directly open a Twitch livestream.

Alternatively, see
[Streamlink#Twitch](https://wiki.archlinux.org/index.php/Streamlink#Twitch
"Streamlink").

Another alternative based on Livestreamer is this Lua script:
<https://gist.github.com/ChrisK2/8701184fe3ea7701c9cc>

### youtube-dl and choosing formats

The default `--ytdl-format` is `bestvideo+bestaudio/best`. For youtube videos
that have 4K resolutions available, this may mean that your device will
struggle to decode 4K VP9 encoded video in software even if the attached
monitor is much lower resolution.

Setting the right youtube-dl format selectors can fix this easily though. In
the following configuration example, only videos with a vertical resolution of
1080 pixels or less will be considered.

    
    
    ytdl-format="bestvideo[height<=?1080]+bestaudio/best"
    

If you wish to avoid a certain codec altogether because you cannot hardware-
decode it, you can add this to the format selector. For example, we can
additionally choose to ignore VP9 as follows:

    
    
    ytdl-format="bestvideo[height<=?1080][vcodec!=vp9]+bestaudio/best"
    

If you prefer best quality open codecs (VP9 and Opus), use:

    
    
    ytdl-format="((bestvideo[vcodec^=vp9]/bestvideo)+(bestaudio[acodec=opus]/bestaudio[acodec=vorbis]/bestaudio[acodec=aac]/bestaudio))/best"
    

### youtube-dl audio with search

To find and stream audio from your terminal emulator with `yta _search terms_`
put the following function in your `.bashrc`:

    
    
    function yta() {
        mpv --ytdl-format=bestaudio ytdl://ytsearch:"$*"
    }
    

### Creating a single screenshot

An example of creating a single screenshot, by using a start time
(`HH:MM:SS`):

    
    
    $ mpv --no-audio --start=00:01:30 --frames=1 /path/to/video/file --o=/path/to/screenshot.png
    

Screenshots will be saved in /path/to/screenshot.png.

## Troubleshooting

### General debugging

If you are having trouble with _mpv'_ s playback (or if it is flat out failing
to run) then the first three things you should do are:

  1. Run _mpv_ from the command line (the -v flag increases verbosity). If you are lucky there will be an error message there telling you what is wrong.  
`$ mpv -v video.mkv`

  2. Have _mpv_ output a log file. The log file might be difficult to sift through but if something is broken you might see it there.  
`$ mpv -v --log-file=./log video.mkv`

  3. Run _mpv_ without a configuration. If this runs well then the problem is somewhere in your configuration (perhaps your hardware cannot keep up with your settings).  
`$ mpv --no-config video.mkv`

If _mpv_ runs but it just does not run well then a fourth thing that might be
worth taking a look at is installing the mpv-stats script and using it to see
exactly how it is performing.

### Fix jerky playback and tearing

_mpv_ defaults to using the OpenGL video output device setting on hardware
that supports it. In cases such as trying to play video back on a 4K display
using a Intel HD4XXX series card or similar, you will find video playback
unreliable, jerky to the point of stopping entirely at times and with major
tearing when using any OpenGL output setting. If you experience any of these
issues, using the XV ([Xorg](https://wiki.archlinux.org/index.php/Xorg "Xorg")
only) video output device may help:

    
    
    ~/.config/mpv/mpv.conf
    
    
    vo=xv

**Note:** This is the most compatible VO on X, but may be low-quality, and has
issues with OSD and subtitle display.

It is possible to increase playback performance even more (especially on lower
hardware), but this decreases the video quality dramatically in most cases.

The following options may be considered to increase the video playback
performance:

    
    
    ~/.config/mpv/mpv.conf
    
    
    vd-lavc-fast
    vd-lavc-skiploopfilter=<skipvalue>
    vd-lavc-skipframe=<skipvalue>
    vd-lavc-framedrop=<skipvalue>
    vd-lavc-threads=<threads>

### Problems with window compositors

Window compositors such as KWin or Mutter can cause trouble for playback
smoothness. In such cases, it may help to set `x11-bypass-compositor=yes` to
make _mpv_ also disable window compositing when playing in windowed mode (if
supported by the compositor).

With KWin compositing and hardware decoding, you may also want to set
`x11-bypass-compositor=no` to keep compositing enabled in fullscreen, since
reanabling compositing after leaving fullscreen may introduce stutter for a
period of time.

### No volume bar, cannot change volume

Spin the mouse wheel over the volume icon.

### GNOME Blank screen (Wayland)

_mpv_ may not suspend GNOME's Power Saving Settings if using Wayland resulting
in screen saver turning off the monitor during video playback. A workaround is
to add `gnome-session-inhibit` to the beginning of the `Exec=` line in
`mpv.desktop`.

### Use mpv with a compositor

If you are using a compositor (e.g. in KDE Plasma 5) and find that composition
is disabled (e.g. in Plasma this would make you unable to present windows or
see window thumbnails in the default app switcher) when _mpv_ is playing a
video, try `x11-bypass-compositor=no`

### Cursor theme not respected under GNOME Wayland

On Wayland, clients can display different cursor themes because there is not a
unique configuration file for it. For the cursor theme, Qt apps usually accept
the value that is set for the [environment
variable](https://wiki.archlinux.org/index.php/Environment_variable
"Environment variable") `XCURSOR_THEME`. However, in the specific case of mpv,
the cursor theme that is displayed needs to be the one set in
`~/.icons/default/index.theme`. Since GNOME does not update this file when
changing the cursor theme with GNOME Tweaks, you will have to do it manually.
See [Cursor themes#XDG
specification](https://wiki.archlinux.org/index.php/Cursor_themes#XDG_specification
"Cursor themes") for more information.

Retrieved from
"[https://wiki.archlinux.org/index.php?title=Mpv&oldid=606258](https://wiki.archlinux.org/index.php?title=Mpv&oldid=606258)"

[Categories](https://wiki.archlinux.org/index.php/Special:Categories
"Special:Categories"):

  * [Video](https://wiki.archlinux.org/index.php/Category:Video "Category:Video")
  * [Audio](https://wiki.archlinux.org/index.php/Category:Audio "Category:Audio")
  * [Streaming](https://wiki.archlinux.org/index.php/Category:Streaming "Category:Streaming")

## Navigation menu

### Personal tools

  * [Create account](https://wiki.archlinux.org/index.php?title=Special:CreateAccount&returnto=Mpv "You are encouraged to create an account and log in; however, it is not mandatory")
  * [Log in](https://wiki.archlinux.org/index.php?title=Special:UserLogin&returnto=Mpv "You are encouraged to log in; however, it is not mandatory \[alt-shift-o\]")

### Namespaces

  * [Page](https://wiki.archlinux.org/index.php/Mpv "View the content page \[alt-shift-c\]")
  * [Discussion](https://wiki.archlinux.org/index.php/Talk:Mpv "Discussion about the content page \[alt-shift-t\]")

###  Variants

### Views

  * [Read](https://wiki.archlinux.org/index.php/Mpv)
  * [View source](https://wiki.archlinux.org/index.php?title=Mpv&action=edit "This page is protected.
You can view its source \[alt-shift-e\]")

  * [View history](https://wiki.archlinux.org/index.php?title=Mpv&action=history "Past revisions of this page \[alt-shift-h\]")

### More

###  Search

[](https://wiki.archlinux.org/index.php/Main_page "Visit the main page")

### Navigation

  * [Main page](https://wiki.archlinux.org/index.php/Main_page "Visit the main page \[alt-shift-z\]")
  * [Table of contents](https://wiki.archlinux.org/index.php/Table_of_contents)
  * [Getting involved](https://wiki.archlinux.org/index.php/Getting_involved "Various ways Archers can contribute to the community")
  * [Wiki news](https://wiki.archlinux.org/index.php/ArchWiki:News "The latest lowdown on the wiki")
  * [Random page](https://wiki.archlinux.org/index.php/Special:Random "Load a random page \[alt-shift-x\]")

### Interaction

  * [Help](https://wiki.archlinux.org/index.php/Category:Help "Wiki navigation, reading, and editing help")
  * [Contributing](https://wiki.archlinux.org/index.php/ArchWiki:Contributing)
  * [Recent changes](https://wiki.archlinux.org/index.php/Special:RecentChanges "A list of recent changes in the wiki \[alt-shift-r\]")
  * [Recent talks](https://wiki.archlinux.org/index.php/Special:RecentChanges?namespace=0&invert=1)
  * [New pages](https://wiki.archlinux.org/index.php/Special:NewPages)
  * [Statistics](https://wiki.archlinux.org/index.php/ArchWiki:Statistics)
  * [Requests](https://wiki.archlinux.org/index.php/ArchWiki:Requests)

### Tools

  * [What links here](https://wiki.archlinux.org/index.php/Special:WhatLinksHere/Mpv "A list of all wiki pages that link here \[alt-shift-j\]")
  * [Related changes](https://wiki.archlinux.org/index.php/Special:RecentChangesLinked/Mpv "Recent changes in pages linked from this page \[alt-shift-k\]")
  * [Special pages](https://wiki.archlinux.org/index.php/Special:SpecialPages "A list of all special pages \[alt-shift-q\]")
  * [Printable version](https://wiki.archlinux.org/index.php?title=Mpv&printable=yes "Printable version of this page \[alt-shift-p\]")
  * [Permanent link](https://wiki.archlinux.org/index.php?title=Mpv&oldid=606258 "Permanent link to this revision of the page")
  * [Page information](https://wiki.archlinux.org/index.php?title=Mpv&action=info "More information about this page")

### In other languages

  * [Español](https://wiki.archlinux.org/index.php/Mpv_\(Espa%C3%B1ol\) "Mpv – español")
  * [日本語](https://wiki.archlinux.jp/index.php/Mpv "Mpv – 日本語")
  * [Русский](https://wiki.archlinux.org/index.php/Mpv_\(%D0%A0%D1%83%D1%81%D1%81%D0%BA%D0%B8%D0%B9\) "Mpv – русский")
  * [中文（简体）‎](https://wiki.archlinux.org/index.php/Mpv_\(%E7%AE%80%E4%BD%93%E4%B8%AD%E6%96%87\) "Mpv – 中文（简体）‎")

  * This page was last edited on 15 April 2020, at 17:42.
  * Content is available under [GNU Free Documentation License 1.3 or later](http://www.gnu.org/copyleft/fdl.html) unless otherwise noted.

  * [Privacy policy](https://wiki.archlinux.org/index.php/ArchWiki:Privacy_policy "ArchWiki:Privacy policy")
  * [About ArchWiki](https://wiki.archlinux.org/index.php/ArchWiki:About "ArchWiki:About")
  * [Disclaimers](https://wiki.archlinux.org/index.php/ArchWiki:General_disclaimer "ArchWiki:General disclaimer")

  * 

