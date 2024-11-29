# Putting a chroot environment on external storage

As we all know, Debian and distros based upon it can get quite big when you install development tools, compilers, etc.
Sometimes, you don't have the space for that, in which case it's time to start looking at putting the chroot on the SD card.

## The hurdles I encountered

Of course, it's not as easy as simply moving the chroot to the SD card's main partition, no. 
If you do that, it wont matter how many times you run chmod and chown, it'll always get set to root:everybody and 777.
That would royally screw up the chroot. What you have to do is make two partitions. 

Partition number one is what Android will automatically mount and use, so it's best you resize the pre-existing partiion using Termux's parted tool.
Partition number two should be ext4, and will contain the rootfs that you chroot into.
I haven't tried moving a pre-existing rootfs to it, but creating a new rootfs of Debian Bookworm there worked flawlessly. In fact, I'm typing from it right now!
