---
title: "Hana"
summary: "Video thumbnails generator"
cover:
    image: "/images/hana/hana.png"
    alt: "Main window screenshot"
weight: 110
---

**Hana** is a video thumbnails generator. It creates thumbnail images from video files and join them in one image.

[Project website](https://apps.kde.org/hana)

[Source code](https://invent.kde.org/multimedia/hana)

[Report bugs or request features](https://bugs.kde.org/enter_bug.cgi?product=Hana)

----

1. [Features](#features)
1. [Installation](#installation)
1. [Dependencies](#dependencies)
1. [Build](#_build)

----
# Features
1. parallel processing
1. set number of rows and columns
1. toggle file info
1. set thumbnail width and spacing
1. set background and text colors

Output image
![output image](/images/hana/BigBuckBunny.mkv.thumbs.png)

# Installation
Easiest way to install is through [flatpak](https://flathub.org/apps/details/org.kde.hana), flatpaks should work on all distros.

[Flatpak setup guide](https://flatpak.org/setup/)
```
flatpak install flathub org.kde.hana
flatpak run org.kde.hana
```

If you don't like flatpak you can build from source or ask the your distro to provide a package.

# Dependencies
Dependencies will be printed by cmake when trying to build. Or can be found in the main [CMakeLists.txt](https://invent.kde.org/multimedia/hana/-/blob/master/CMakeLists.txt) file, look for `find_package`.

# Build
```
git clone https://invent.kde.org/multimedia/hana
cd hana
cmake -B build -G Ninja
cmake --build build
```
