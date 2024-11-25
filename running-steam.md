# Yes, really

Steam can be run, but it has to be within Box64droid's old chroot environment AND using a different version of WINE that box64droid doesn't come with.
You also will probably have to run an old version of steam as CEF, being chromium-based, eats up all the RAM, and it makes it even worse if you run it under box64.

First off, you'll need that custom version of WINE. It's WINE GE. Go grab it from here and replace the wine install located at /opt/wine in the rootfs with it: https://github.com/GloriousEggroll/wine-ge-custom

Use this steam forum post to downgrade to a VGUI based version of steam: https://steamcommunity.com/discussions/forum/0/6516193260168294059/
then once you're done configuring your games, I would suggest adding BOX64_EXIT=1 to the chroot's /etc/box64.box64rc.
Note that this will break opening game properties, and uninstalling games, so comment it out if you want to uninstall anything or add any launch flags.

Also use DXVK-GPLASYNC to get DXVK 2.5. It runs way faster than anything Box64droid provides in that old chroot.
