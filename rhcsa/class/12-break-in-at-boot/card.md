# Lesson 12. Break In at Boot

**Listen:** break-in-at-boot.mp3 (2 min)

**The idea, in three lines**
- Easy way first: as root, `passwd`; as a wheel user, `sudo passwd root`. Only when neither works, interrupt the boot.
- At the GRUB menu press `e`, add `rd.break` to the end of the line starting with `linux`, and boot with Ctrl+x. You land in a small emergency shell, before the real system starts, with your disk read only under /sysroot.
- Then: `mount -o remount,rw /sysroot`, `chroot /sysroot`, `passwd`, `touch /.autorelabel`, `exit`, `exit`. Skipping the remount or the autorelabel is why a reset "doesn't work".

**Impact:** a locked-out machine becomes a short, known fix instead of a lost task.

**Who says it:** 3 of the 7 pages on boot recovery teach rd.break; dev.to also shows `init=/bin/bash`, which works too (then `mount -o remount,rw /`, `passwd`, `touch /.autorelabel`, `exec /sbin/init`). Pick one route and drill it. 2 of 7 single out the remount and autorelabel as the steps people skip.

**Try it** · Deep Focus · 15 min
Only on your own practice VM (Rocky Linux, AlmaLinux or RHEL), never on a machine you don't administer.
> **1.** Take a snapshot of the VM, then reboot it.
> **2.** At the GRUB menu press `e`, add `rd.break` at the end of the `linux` line, press Ctrl+x.
> **3.** `mount -o remount,rw /sysroot` then `chroot /sysroot`
> **4.** `passwd` (choose a new root password), then `touch /.autorelabel`
> **5.** `exit`, then `exit` again. The relabel takes a few minutes and the VM reboots.
> **6.** Log in as root with the new password.

No VM yet? On paper, write the six steps from memory, in order, then check them against the list above.

**Rule to keep**
Remount read-write and autorelabel, every time.

**Skip** · no cost, no catch-up. This is the last lesson in this set.

**Go deeper (optional)**
- Three ways to reset root, easiest first: https://tecmint.com/reset-forgotten-root-password-rhel-9
- Red Hat lists "interrupt the boot process in order to gain access to a system" as an objective: https://au.redhat.com/training/courses/ex200/
- Why one candidate did the boot and storage tasks first (older RHEL 7 era post): https://www.pluralsight.com/resources/blog/cloud/red-hat-exams-a-few-tips
