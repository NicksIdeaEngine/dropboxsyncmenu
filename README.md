# Dropbox Sync Menu
###### Created by Nick Garcia

If you have any suggestions for improving these scripts, this repository, or this README, please let me know!

These scripts provide an easy way to manage sync settings for Dropbox on Linux.

### Dependencies

Make sure you have the following installed before using `dropboxsyncmenu`:

* sed
* tree
* [Rofi](https://github.com/davatorium/rofi)
* [Polybar](https://github.com/polybar/polybar)

Optional:

* [Fira Code](https://github.com/tonsky/FiraCode) (great font!)

### Here's How It Looks

The first menu lets you choose between 'Synced Directories' and 'Excluded Directories'.  I haven't yet figured out how to mix the two lists in a way that indicates whether the directory is synced or unsynced, but the end goal is one list!

![List Selection Screenshot](https://raw.githubusercontent.com/NicksIdeaEngine/dropboxsyncmenu/master/List%20Selection.png)

Here's the 'Synced Directories' menu:

![Synced Directories Screenshot](https://raw.githubusercontent.com/NicksIdeaEngine/dropboxsyncmenu/master/Add%20to%20Exclude%20List.png)

And the 'Excluded Directories' menu:

![Excluded Directories Screenshot](https://raw.githubusercontent.com/NicksIdeaEngine/dropboxsyncmenu/master/Remove%20from%20Exclude%20List.png)

### How to Install

#### Step 1. Add Scripts

* Move `dropboxstatus` and `dropboxsyncmenu` to your scripts folder. For me this is a folder in my Dropbox, but you can use `~/.config/polybar/scripts` as well.
* Make both of those files are executible by running `chmod +x <filename>`
* Set the `DROPBOX` variable in `dropboxsyncmenu` to wherever your Dropbox folder is located.
* If needed, set the `FILE` variable to a folder this script can use for its `.tmp` file.
* If you don't use ZSH, change the first line of both scripts to match your shell (example for Bash users: `#!/bin/bash` )

#### Step 2. Set up Polybar

* Add the `dropboxstatus` module:
  * Copy [line 11 - 16](https://github.com/NicksIdeaEngine/dropboxsyncmenu/blob/07f343c3f5aa4c96fc3b46601e4d38164c12fcb4/user_modules.ini#L11-L16) into your `polybar/user_modules.ini` file.
  * Add `dropboxstats` to your `polybar/config.ini` file [like I have here on line 32](https://github.com/NicksIdeaEngine/dropboxsyncmenu/blob/07f343c3f5aa4c96fc3b46601e4d38164c12fcb4/config.ini#L32)
  * If needed, change `exec`, `click-left`, and `click-right` so it has the correct path for where you placed the scripts during Step 1.
* Make sure `include-file = ~/.config/polybar/user_modules.ini` is added to your `~/.config/polybar/config.ini` file [like so on line 5](https://github.com/NicksIdeaEngine/dropboxsyncmenu/blob/07f343c3f5aa4c96fc3b46601e4d38164c12fcb4/config.ini#L5)

#### Step 3. Set up Rofi

* Add `centermenu.rasi` to your `.config/rofi` directory
  * If you don't have [Fira Code](https://github.com/tonsky/FiraCode) installed, either install it or change the font on line 9 of the `centermenu.rasi` file.
  