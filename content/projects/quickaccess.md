---
title: "QuickAccess"
summary: "Background application to open folders and run scripts through a menu"
cover:
    image: "https://i.imgur.com/uTR6EeD.png"
    alt: "Screenshot of all windows"
weight: 150
---

⚠️ *The application is in maintenance mode, it will only receive bugfixes, and there is no Wayland support.*

**QuickAccess** is a background application offering a menu that allows you to open folders and their subfolders as well as creating and running scripts.

The menu can be opened through two dbus methods: showMenu and showDelayedMenu.

Both methods can open the menu in a predefined fixed position or on mouse position. 

**showMenu** shows the menu instantly, but in certain circumstances there are problems with the menu not showing or not closing. In these cases use the **showDelayedMenu**, there is a default delay of 150 miliseconds, but can be changed (see example below).

[Source code](https://github.com/g-fb/quickaccess)

[Report bugs](https://github.com/g-fb/quickaccess/issues)

----

1. [Installation](#_installation)
1. [Usage](#_usage)
    * [Start](#_start)
    * [Open Menu](#_open-menu)
    * [Open Settings](#_open-settings)
    * [Add Folder](#_add-folder)
    * [Add Menu](#_add-menu)
    * [Add Action](#_add-action)
1. [Dependencies](#_dependencies)
1. [Build](#_build)

----

# Installation
Easiest way to install is through [flatpak/flathub](https://flathub.org/apps/details/com.georgefb.quickaccess), flatpaks should work on all distros.

[Flatpak setup guide](https://flatpak.org/setup/)
```
flatpak install flathub com.georgefb.quickaccess
flatpak run com.georgefb.quickaccess
```

If you don't like flatpak you can build from source or ask the your distro to provide a package.

# Usage

#### Start
```bash
# with tray icon
quickaccess
# or
quickaccess --tray-icon=show
```

```bash
# without tray icon
quickaccess --tray-icon=hide
```

#### Open Menu
```bash
# with qdbus
qdbus com.georgefb.quickaccess /QuickAccess showMenu x
qdbus com.georgefb.quickaccess /QuickAccess showDelayedMenu 200 x
```

```bash
# with dbus-send
dbus-send --type=method_call --dest=com.georgefb.quickaccess /QuickAccess com.georgefb.QuickAccess.showMenu int32:x
dbus-send --type=method_call --dest=com.georgefb.quickaccess /QuickAccess com.georgefb.QuickAccess.showDelayedMenu int32:200 int32:x
```

replace x with an int from 0 to 9 to set the preffered position to open the menu.

- 0: mouse position (default)
- 1: top left
- 2: top hcenter
- 3: top right
- 4: vcenter left
- 5: center
- 6: vcenter right
- 7: bottom left
- 8: bottom hcenter
- 9: bottom right

#### Open Settings
- Open menu > click "Settings"
- Right click tray icon > click "Settings"

#### Add Folder
- Open Settings
- Click "Select and Add Folder"
- Use file picker to select a folder
- Click "Apply" or "OK" to save the settings

#### Add Menu
- Open Settings
- Click "Add Menu"
- Enter a name
- Click "OK" to add the menu
- Click "Apply" or "OK" to save the settings

#### Add Action
- Open Settings
- Click "Add Action"
- Fill the fields
- **Name**: text to be displayed in the menu
- **Icon**: name of the icon to be displayed in menu
- **Process**: name of the process/executable or path to script to be executed
- **Arguments**: arguments to be passed to the process, use **{clipboard}** to get the clipboard's text
- Click "OK" to add the action
- Click "Apply" or "OK" to save the settings

Actions can be dragged and dropped on menus

# Dependencies
Dependencies will be printed by cmake when trying to build. Or can be found in the main [CMakeLists.txt](https://invent.kde.org/multimedia/haruna/-/blob/master/CMakeLists.txt) file, look for `find_package`.

# Build
```
git clone https://github.com/g-fb/quickaccess
cd quickaccess
cmake -B build -G Ninja
cmake --build build
```
