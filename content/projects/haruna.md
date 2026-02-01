---
title: "Haruna"
summary: "Media player built with Qt/QML and libmpv"
cover:
    image: "/images/haruna-light.webp"
    alt: "Main window screenshot"
weight: 100
---

**Haruna** is an open source media player built with Qt/QML and libmpv.

[Project website](https://haruna.kde.org)

[Source code](https://invent.kde.org/multimedia/haruna)

[Report bugs or request features](https://bugs.kde.org/enter_bug.cgi?product=Haruna)

----

1. [Features](#features)
1. [Installation](#installation)
1. [Dependencies](#dependencies)
1. [Build](#_build)

----
# Features

These are just some features that sets Haruna apart from others players:
- video preview on seek/progress bar
- play online videos, through yt-dlp
- toggle playlist with mouse-over, playlist overlays the video
- auto skip chapter containing certain words
- configurable shortcuts and mouse buttons
- quick jump to next chapter by middle click on progress bar
- custom mpv commands, can be run at start up or on keyboard shortcut

# Installation
Easiest way to install is through [flatpak](https://flathub.org/apps/details/org.kde.haruna), flatpaks should work on all distros.

[Flatpak setup guide](https://flatpak.org/setup/)
```
flatpak install flathub org.kde.haruna
flatpak run org.kde.haruna
```

If you don't like flatpak you can build from source or ask the your distro to provide a package.

# Dependencies
Dependencies will be printed by cmake when trying to build. Or can be found in the main [CMakeLists.txt](https://invent.kde.org/multimedia/haruna/-/blob/master/CMakeLists.txt) file, look for `find_package`.

# Build
```
git clone https://invent.kde.org/multimedia/haruna
cd haruna
cmake -B build -G Ninja
cmake --build build
```
