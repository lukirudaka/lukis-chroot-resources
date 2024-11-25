# Kernel 4.14 compatible distros and versions


GLIBc 2.38 and newer are completely borked on Kernel 4.14, which many (still updated) android devices still run, primarily Samsung devices.
Samsung got lazy and decided to never update the kernel on many devices, including mine. Since it's a PITA to mainline these things, I've published this in the meantime.
The things that break are pretty crucial for me, such as the ability to compile via meson/ninja. As we all know, that means I can't compile any mesa drivers on those versions of GLIBc.

## COMPATIBLE DISTROS
- Debian
  Debian Bookworm (12.8) is still using GLIBC 2.36, which plays nice with Kernel 4.14 with no issues
- Ubuntu (Lunar Lobster and older)
  Ubuntu Lunar Lobster is the last version of Ubuntu to use GLIBc older than 2.38. Anything newer than this will break. (sigh)

## ANYTHING ROLLING RELEASE WILL BREAK. Sorry arch fans.
we can still be friends, right? TwT
