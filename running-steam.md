# Yes, really
Steam can be run on the old box64 chroot environment.
You also will probably have to run an old version of steam as CEF, being chromium-based, eats up all the RAM, and it makes it even worse if you run it under box64.

Use this steam forum post to downgrade to a VGUI based version of steam: https://steamcommunity.com/discussions/forum/0/6516193260168294059/
then once you're done configuring your games, I would suggest adding BOX64_EXIT=1 to the chroot's /etc/box64.box64rc.
Note that this will break opening game properties, and uninstalling games, so comment it out if you want to uninstall anything or add any launch flags.

Also use DXVK-GPLASYNC to get DXVK 2.5. It runs way faster than anything Box64droid provides in that old chroot.

If you're making something similar to DEXtop, I would suggest putting the rootfs under something like "/opt/wineroot" or just "/box64rootfs" or something. I dunno, somewhere inside your DEXtop rootfs. I'm working on trying to get Wine 9.4 going in an effort to save a few gigabytes of space.
