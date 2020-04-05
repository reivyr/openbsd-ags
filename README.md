# openbsd-ags
A draft to build the latest release (3.5.0.24) of Adventure Game Studio on OpenBSD.

First you need the [Allegro update](https://marc.info/?l=openbsd-ports&m=157171476128442&w=2) by Nam Nguyen. After that, clone this repository and copy **games/ags** (there is **ags-git** if you want to try too but it should be renamed to ags) in your **`mystuff`** directory (or the directory you use in your **`PORTSDIR_PATH`**). If you already have installed `audio/dumb` (a build dep. for ags) please uninstall it because it depends of `games/allegro` too. Finally, you can install ags like any other port.

More information on my [Reddit comment](https://www.reddit.com/r/openbsd_gaming/comments/fvbb8u/testing_ags_games_on_openbsd/fmhha2c/)
