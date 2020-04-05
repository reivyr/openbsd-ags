# openbsd-ags
A draft to build the latest release (3.5.0.24) of Adventure Game Studio on OpenBSD.

First you need the [Allegro's update](https://marc.info/?l=openbsd-ports&m=157171476128442&w=2) by Nam Nguyen. After that, clone this repository and copy **games/ags** (there's **ags-git** if you want to try too but it should be renamed to **ags**, however **I tested more the AGS release**) into your **`mystuff`** directory (or the directory you use in your **`PORTSDIR_PATH`**). If you already have installed `audio/dumb` (a build dep. for ags) please uninstall it because it also depends of `games/allegro`. Finally, you can install ags like any other port.

## Playing Games

This build doesn't work with all AGS games. **About which games I tried and what difficulties I encountered, please read [this](https://www.reddit.com/r/openbsd_gaming/comments/fvbb8u/testing_ags_games_on_openbsd/fmhha2c/).**

You need to execute `ags` (use `--help` to see more options) in your game directory (the directory containing `acsetup.cfg` and the `vox` files).

**Tip**: I don't play games on fullscreen (this is usually the default behaviour) since my mouse usually feels laggy in that mode, so I use the `--windowed` parameter but if you want to resize the window, at least in cwm, you need to add `--gfxfilter StdScale N` which **N** is the scale specified by an integer number.

More information about the options and settings (`acsetup.cfg`) [here](https://github.com/adventuregamestudio/ags/blob/master/OPTIONS.md).
