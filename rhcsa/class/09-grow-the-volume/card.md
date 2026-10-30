# Lesson 9. Grow the Volume

**Listen:** grow-the-volume.mp3 (2 min)

**The idea, in three lines**
- LVM is four layers: physical volume (`pvcreate`), volume group (`vgcreate`), logical volume (`lvcreate`), then the file system on top. Check each with `pvs`, `vgs`, `lvs`.
- Growing the volume doesn't grow the file system. `lvextend -r` does both in one go (or follow with `xfs_growfs` for XFS, `resize2fs` for ext4). XFS grows but never shrinks.
- Mount by UUID in /etc/fstab, then prove the line with `mount -a` before any reboot. A bad fstab line can stop the boot.

**Impact:** "extend this volume" and "mount it at boot" become calm tasks, and a typo in fstab gets caught while you can still fix it.

**Who says it:** 2 of the 4 pages on LVM teach the build and grow steps, and 4 of the 6 pages on mounting teach UUID plus `mount -a`; none disagree. The 800M volume that still showed 336M in df until `xfs_growfs` is KodeKloud's demo; the one-step `lvextend -r` is from certland.

**Try it** · Deep Focus · 15 min
On a practice VM (Rocky Linux, AlmaLinux or RHEL), run `sudo -i` first so every command below runs as root. **Never use the system disk.** Use a spare virtual disk you added to the VM (`lsblk` shows it, for example /dev/vdb), or a loop file as below.
> **1.** Loop file: `truncate -s 1G /root/lvm.img`, then `losetup -f` (prints a free device, say /dev/loop0), then `losetup /dev/loop0 /root/lvm.img`. With a spare disk, skip this and use its name instead of /dev/loop0.
> **2.** `pvcreate /dev/loop0`, `vgcreate practicevg /dev/loop0`, `lvcreate -n practicelv -L 500M practicevg`, then `pvs`, `vgs`, `lvs`
> **3.** `mkfs.xfs /dev/practicevg/practicelv`, `mkdir /mnt/practice`, `mount /dev/practicevg/practicelv /mnt/practice`, `df -h /mnt/practice`
> **4.** `lvextend -r -L +300M /dev/practicevg/practicelv`, then `df -h /mnt/practice`. It grew.
> **5.** `blkid /dev/practicevg/practicelv` for the UUID, then add to /etc/fstab: `UUID=<your-uuid> /mnt/practice xfs defaults,nofail 0 0`
> **6.** `umount /mnt/practice`, `systemctl daemon-reload`, `mount -a`, `df -h /mnt/practice`. Silent `mount -a` and the mount is back: the line is good.
> **7.** Loop file: don't reboot (the loop device isn't attached at boot). Clean up in reverse: `umount /mnt/practice`, delete the fstab line, `systemctl daemon-reload`, `lvremove -y practicevg/practicelv`, `vgremove practicevg`, `pvremove /dev/loop0`, `losetup -d /dev/loop0`, `rm /root/lvm.img`. With a spare disk, reboot first and check it mounted, then clean up the same way.

No VM yet? On paper, draw the four layers and write the command that creates each, plus the fstab line for one of them.

**Rule to keep**
mount -a before reboot, every time.

**Skip** · no cost, no catch-up. Lesson 10 is just lesson 10.

**Go deeper (optional)**
- The full LVM demo, the 336M surprise, and the fstab check: https://notes.kodekloud.com/docs/Prep-Course-Red-Hat-Certified-System-Administrator-RHCSA/Storage-Management/Demo-Working-With-Logical-Volumes/page
- Study plan with lvextend -r and the XFS shrink limit: https://certland.net/blog/red-hat-certified-system-administrator-rhcsa-study-guide-2026/
