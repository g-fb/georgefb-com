---
title: "MangaReader"
summary: "Application to read your local manga"
cover:
    image: "https://i.imgur.com/CknoY6T.png"
    alt: "Main window screenshot"
---

⚠️ *The application is in maintenance mode, it will only receive bugfixes.*

**MangaReader** is an application allowing you to read your local manga.

[Source code](https://github.com/g-fb/mangareader)

[Report bugs](https://github.com/g-fb/mangareader/issues)

----

1. [Installation](#installation)
1. [Features](#features)
1. [Dependencies](#dependencies)
1. [Build](#build)
1. [Screenshots](#screenshots)

----

# Features
 - Open manga folder (folder containing images)
 - Open archives, zip, cbz, rar, cbr, 7z, cb7, tar, cbt
 - Bookmarks
 - Fullscreen
 - Change background color
 - Maximum width
 - Fit width
 - Fit height
 - Upscale images
 - Zoom
 - Keyboard navigation
 - Folder-tree for folders containig manga
 - Switch between manga folders in the folder-tree

# Installation
Easiest way to install is through [flatpak/flathub](https://flathub.org/apps/details/com.georgefb.mangareader), flatpaks should work on all distros.

[Flatpak setup guide](https://flatpak.org/setup/)
```
flatpak install flathub com.georgefb.mangareader
flatpak run com.georgefb.mangareader
```

If you don't like flatpak you can build from source or ask the your distro to provide a package.

# Dependencies
Dependencies will be printed by cmake when trying to build. Or can be found in the main [CMakeLists.txt](https://invent.kde.org/multimedia/haruna/-/blob/master/CMakeLists.txt) file, look for `find_package`.

# Build
```
git clone https://github.com/g-fb/mangareader
cd mangareader
# append `-D CMAKE_INSTALL_PREFIX:PATH=/your/custom/path` to install to a custom location
cmake -B build -G Ninja
cmake --build build
```

# Screenshots

![Manga Reader main window, light theme](https://i.imgur.com/d9psv8S.png)
![Manga Reader main window, dark theme](https://i.imgur.com/vmhDMW5.png)
![Manga Reader settings dialog](https://i.imgur.com/vEfME6H.png)
![Manga Reader with images](https://i.imgur.com/XZZsMq6.png)
