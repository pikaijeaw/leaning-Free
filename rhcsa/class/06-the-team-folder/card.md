# Lesson 6. The Team Folder

**Listen:** the-team-folder.mp3 (2 min)

**The idea, in three lines**
- A new file takes its creator's primary group, so in a plain shared folder everyone's files land in their own private groups and nobody can edit anyone else's work.
- SGID on the directory (the 2 in front, an `s` in the group slot) makes every new file inside take the directory's group instead.
- The sticky bit (the 1 in front, a `t` or `T` at the end) stops group members from deleting each other's files. Together: 3770.

**Impact:** a "shared directory for group X" task becomes three commands you trust, and you can read the result at a glance with `ls -ld`.

**Who says it:** 3 of the 5 pages on special permissions teach this; none disagree. The James and Oliver example is from computernetworkingnotes; Red Hat's RHEL 10 objectives list "diagnose and correct file permission problems", and certcrush puts a setgid shared group directory in its study plan.

**Try it** · Quick Win · 10 min
On a practice VM (Rocky Linux, AlmaLinux or RHEL), run `sudo -i` first so every command below runs as root:
> **1.** `groupadd team`, then `useradd ann` and `useradd bob`
> **2.** `usermod -aG team ann`, then `usermod -aG team bob` (one user per command)
> **3.** `mkdir /team`, `chgrp team /team`, `chmod 2770 /team`, then `ls -ld /team`. Look for the `s` in the group slot.
> **4.** `su - ann` (a fresh login, so the new group counts), `touch /team/a.txt`, `ls -l /team`. The group says `team`. Type `exit`.
> **5.** `chmod 3770 /team`, then `su - bob` and `rm -f /team/a.txt`. Refused: "Operation not permitted". Type `exit`.
> **6.** Clean up when done: `rm -rf /team`, `userdel -r ann`, `userdel -r bob`, `groupdel team`.

No VM yet? On paper, draw /team with two users and write which group each new file gets with 770, then with 2770, and who can delete what with 3770.

**Rule to keep**
Shared folder: group owner, 2770, and think about the sticky bit.

**Skip** · no cost, no catch-up. Lesson 7 is just lesson 7.

**Go deeper (optional)**
- The James and Oliver walkthrough, SGID and sticky (it uses bare `usermod -G`; use `-aG`, as in lesson 5): https://www.computernetworkingnotes.com/linux-tutorials/suid-sgid-and-sticky-bit-explained.html
- Sticky bit on a shared directory, step by step: https://adamtheautomator.com/special-permissions-in-linux/
