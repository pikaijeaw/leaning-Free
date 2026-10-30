# Lesson 1. Survive the Reboot

**Listen:** survive-the-reboot.mp3 (2 min)

**The idea, in three lines**
- The RHCSA is a live machine and a task list, not multiple choice. After you finish, a grading script reboots the machine and then checks your work.
- Started but not enabled, mounted but not in /etc/fstab, firewall rule added without the permanent flag: each one looks fine until the reboot, then fails.
- Two habits: write the persistent version of every change straight away, and reboot to verify, in practice and in the exam.

**Impact:** your practice scores start matching what a grader would see, and the most common way to lose easy points disappears.

**Who says it:** 9 of the 15 pages on the exam format teach this; none disagree. Red Hat's own exam page: "configurations must persist after reboot without intervention."

**Try it** · Quick Win · 10 min
On a practice VM (Rocky Linux, AlmaLinux or RHEL):
> **1.** `sudo systemctl enable chronyd` then `sudo systemctl start chronyd`
> **2.** `sudo reboot`
> **3.** `systemctl is-enabled chronyd` and `systemctl is-active chronyd`. Both should say yes (`enabled`, `active`).

No VM yet? On paper, write three changes (start a service, mount a disk, open a firewall port) and, next to each, the version that survives a reboot.

**Rule to keep**
Nothing counts until it survives a reboot.

**Skip** · no cost, no catch-up. Lesson 2 is just lesson 2.

**Go deeper (optional)**
- Red Hat's EX200 objectives and exam format: https://au.redhat.com/training/courses/ex200/
- The grading reboot, and an 8-week plan built around it: https://www.certcrush.app/blog/how-to-pass-rhcsa-ex200-2026-8-week-study-plan
- A perfect-score write-up (RHEL 7 era, habit unchanged): https://www.lisenet.com/?p=5574
