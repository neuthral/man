<h1 align="center">Gord</h1>

A maintained fork of [Cordless](https://github.com/Bios-Marcel/cordless) with extra features.

## Warning!
Gord is in development and is against Discord's TOS. We are not responsible for any damage.

## Overview

- [How to install it](#installation)
  - [Using a package manager](#using-a-package-manager)
  - [Using prebuilt binaries](#using-prebuilt-binaries)
  - [Building from source](#building-from-source)
- [Login](#login)
- [Quick overview - Navigation (switching between boxes / containers)](#quick-overview---navigation-switching-between-boxes--containers)
- [Extending Cordless via the scripting interface](#extending-cordless-via-the-scripting-interface)
- [Troubleshooting](#troubleshooting)
- [FAQ](#faq)
- [This project isn't for you, if](#this-project-isnt-for-you-if)
- [Similar projects](#similar-projects)
- [Credits](#credits)

Gord is a custom [Discord](https://discord.com/app) client that aims to
have a low memory footprint and be aimed at power-users.

The application only uses the official Discord API and doesn't send data to
third parties. However, this application is not an official product by
Discord Inc.

![Demo Screenshot](.github/images/chat-demo.png)

## Installation

### Using a package manager
Gord is available on multiple package managers (2 and counting).

#### AUR (Arch Linux)
On Arch Linux, you can install the latest release with `gord-bin`,
or get the latest commit with `gord-git`.

A good AUR helper is `yay`, which can be installed manually [from the AUR](https://aur.archlinux.org/packages/yay/).
```
yay -S gord-bin
```

#### Homebrew (MacOS) (and Linuxbrew)
On MacOS (or on Linux via Linuxbrew), you can use Homebrew to install Gord.
Install homebrew with the following (works on mac and linux):
```
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```
Then install Gord with the following (you MUST add `--without-pngpaste` on linux):
```
brew tap yellowsink/gord
# MacOS
brew install gord
# Linux
brew install gord --without-pngpaste
```

#### Portage (Gentoo Linux)
[Add](https://github.com/binex-dsk/ebuilds#adding-the-repository) the `swirl` repository.

To build and install the latest release:
```
# emerge --ask gord
```

Or, to build and install from the latest commit, unmask the `9999` version:
```
# echo "=net-im/gord-9999 ~amd64" >> /etc/portage/package.accept_keywords"
```

Then install:
```
# emerge --ask =net-im/gord-9999
```

### Using prebuilt binaries
If you don't want to build the application yourself or use some kind of
package management system, you can get the latest binaries for the three
major systems in the release overview:

https://github.com/cainy-a/gord/releases/latest

### Building from source

In order to execute the following commands, you need to install **go 1.13 or**
higher. You can find golang packages at https://golang.org/doc/install.
On top of that, you need to have **git** installed. It can be found at
https://git-scm.com/downloads.

**UPDATES HAVE TO BE INSTALLED MANUALLY**

Open a command line and execute the following commands:

```shell
git clone https://github.com/cainy-a/gord
cd gord
go build
```

This will create an executable file called `gord` or `gord.exe`
depending on whether you are on Windows or not. Move that file anywhere
 that your terminal can find it. I recommend adding a `bin` folder to your
user home and adding it to your systems `PATH` variable. Please search the
internet, using your favorite search engine, for
`how to set an environment variable in XXX` in order to update your `PATH`
variable correctly.

For updating, you simply have to delete the folder you downloaded last
time and repeat the instructions.

Note:

* X11 users need `xclip` in order to copy and paste.
* Wayland users need `wl-clipboard` in order to copy and paste.
* Mac OS users need `pngpaste` in order to copy and paste images.

### Login

**YOUR PASSWORD IS NEVER SAVED LOCALLY.**

Logging in works via the UI on first startup of the application.

If you are logging in with a bot token, you have to prepend `Bot` in front of
the token. You also need to enable an intent if you want to view server users, but this is optional.
![](https://cdn.discordapp.com/attachments/690477562857521174/829450090829053972/unknown.png)

If you need to find out how to retrieve your token, check [the gord wiki](https://github.com/cainy-a/gord/wiki/Retrieving-your-token).

**Currently captcha-code login isn't supported. Thanks for your SHIT-API, Google**

## Quick overview - Navigation (switching between boxes / containers)

| Shortcut | Action |
| - |:- |
| <kbd>Alt</kbd> + <kbd>S</kbd> | Sets the focus on the servers (guilds) container |
| <kbd>Alt</kbd> + <kbd>C</kbd> | Sets the focus on the channels container |
| <kbd>Alt</kbd> + <kbd>T</kbd> | Sets the focus on the messages container |
| <kbd>Alt</kbd> + <kbd>M</kbd> | Sets the focus on the messages input field |
| <kbd>Alt</kbd> + <kbd>U</kbd> | Sets the focus on the users container |
| <kbd>Alt</kbd> + <kbd>P</kbd> | Opens the direct messages container |
| <kbd>Alt</kbd> + <kbd>.</kbd> | Toggles the internal console view |

Further shortcuts / key-bindings can be found in the manual on the internal
console with the command `manual`.

If any of the default commands don't work for you, open the keyboard shortcut
changer via <kbd>Ctrl</kbd> + <kbd>K</kbd>.

## Extending Cordless via the scripting interface

[Check the Gord wiki](https://github.com/cainy-a/gord/wiki/Extending-Gord-via-the-scripting-interface)

## Troubleshooting

If you happen to encounter a crash or a bug, please submit a bug report via
the projects GitHub issue tracker. Bugs reported via Discord will probably
be forgotten or overseen.

For general problems faced by gord users, check out the [gord wiki](https://github.com/cainy-a/gord/wiki/Troubleshooting) at

If you need help or have questions that you don't want to create an issue
for, just join the Gord Discord server: https://discord.gg/e4HnvY28Wq

# FAQ

In order to find answers to common questions, check out the [FAQ](https://github.com/cainy-a/gord/wiki/FAQ)

## This project isn't for you, if

- You like a physical, fancy GUI with proper mouse support
- You need to have all of Discord's latest features
- You need to manage or moderate servers

## Similar projects

Here is a list of similar projects:

- [terminal-discord](https://github.com/xynxynxyn/terminal-discord) (DEPRECATED)
- [Discurses](https://github.com/topisani/Discurses) (ARCHIVED)
- [Discline](https://github.com/MitchWeaver/Discline) (ARCHIVED)
- [discord-term](https://github.com/cloudrex/discord-term) (STALE)
- [6cord](https://gitlab.com/diamondburned/6cord) (DEPRECATED)

Hit me up if you have a similar project, and I'll gladly add it to the list.

## Credits

This project is based off of [Cordless by Bios-Marcel](https://github.com/Bios-Marcel/cordless)
