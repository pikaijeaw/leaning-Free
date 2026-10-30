# Lesson plan: RHCSA (EX200), beginner

12 lessons in 3 arcs of 4, about 2 minutes each. Built from 34 free pages (research/agreement-map.md), led by Red Hat's own EX200 objectives page (RHEL 10 era). Agreement reads "N of the M pages on this sub-topic teach it"; a low N with no dissent means the other pages covered nearby ground, not that they disagree.

Try-its assume a free practice VM (Rocky Linux, AlmaLinux, or RHEL from the free Red Hat developer subscription) or, with no VM yet, paper. Nothing in this class costs money.

## Arc 1. How the exam thinks
Why this arc: the RHCSA is a live system graded after a reboot, with no internet. Habits beat facts. Finish: a working practice VM and the reboot-and-verify reflex.

### L1. Survive the Reboot
- Agree: 9 of the 15 exam-format pages (TH01); reboot-and-verify 4 of 15 (TH02). None disagree.
- Idea: a grading script reboots your machine, then checks. Started but not enabled, mounted but not in fstab, firewall rule without --permanent: all fail.
- Story: certcrush's "walk out feeling good, then the grading reboot"; lisenet finished in about 80 minutes and spent the spare time rebooting to prove it stuck (RHEL 7 era post, habit unchanged).
- Try it: Quick Win, 10 min. On a practice VM: `systemctl enable --now chronyd`, reboot, then `systemctl is-enabled chronyd` and `is-active`. No VM: write the persistent version of three changes.
- Rule: Nothing counts until it survives a reboot.

### L2. The Manual Is Allowed
- Agree: 7 of 16 (TH03). Red Hat: no internet, shipped documentation available. Some guides wrongly say "no documentation" or "limited internet".
- Idea: man -k, man 5 fstab, --help, /usr/share/doc are your internet in the exam; practise finding answers there.
- Try it: Quick Win, 10 min. Find the fstab field order and one nmcli example using only man pages.
- Rule: Before searching the web, search the man pages.

### L3. Build Your Lab
- Agree: 5 of 15 study by doing (TH08); current material 2 of 15 (TH09, Red Hat page settles it).
- Idea: a two-VM lab, drills from a broken state, timed mocks; study RHEL 10 material: Flatpak and systemd timers in, Podman out.
- Story: "takes three minutes once you have done them ten times. Most candidates have done them twice" (certcrush).
- Try it: Deep Focus, 15 min. Install one free RHEL-compatible VM, or write the plan for it.
- Rule: Practice on a live box, from a blank or broken state.

### L4. Enable, Then Start
- Agree: 5 of 8 (TH28).
- Idea: `systemctl enable --now`, check `is-enabled`, including firewalld and autofs themselves.
- Try it: Quick Win, 5 min. List enabled services; pick one, disable, re-enable with --now.
- Rule: Every service I touch gets enable --now.

## Arc 2. People, files, software, schedules
Why this arc: users, permissions, packages and timed jobs are most of the daily task list. Finish: you can set up a shared team folder and a nightly job from memory.

### L5. Groups and Aging
- Agree: 3 of 9 (TH14, TH15). Flags: usermod takes one user; passwd -e expires, doesn't fix.
- Idea: `usermod -aG` appends (one user at a time), re-login before testing; chage -M -m -W -E -d 0, check with chage -l.
- Story: "I added them but it still says permission denied" (kraker).
- Rule: -aG, never bare -G.

### L6. The Team Folder
- Agree: 3 of 5 (TH12, TH10).
- Idea: SGID on a directory makes new files inherit its group; sticky bit stops users deleting each other's files.
- Story: James and Oliver in /sales (computernetworkingnotes).
- Rule: Shared folder: group owner, 2770, and think about the sticky bit.

### L7. Repo Before Packages
- Agree: 3 of 4 (TH18); Flatpak 2 of 4 (TH19).
- Idea: a .repo file in /etc/yum.repos.d, then `dnf repolist`; Flatpak: add a remote, install, list.
- Rule: dnf repolist before dnf install.

### L8. Timers That Fire
- Agree: 3 of 7 (TH29, TH31). Soft split: centron says timers replace cron, adminschoice and cronuru keep cron for simple jobs; the exam lists at, cron and timers.
- Idea: two units with the same name, enable the .timer, Persistent=true catches missed runs.
- Story: the timer that never fired, service enabled instead of timer (centron).
- Rule: Enable the .timer, never the .service.

## Arc 3. Storage, network, security, recovery
Why this arc: the heaviest and riskiest tasks. Finish: you can grow a volume, open a port the right way, keep SELinux on, and get back into a locked machine.

### L9. Grow the Volume
- Agree: 2 of 4 LVM (TH32); fstab by UUID 4 of 6 (TH33).
- Idea: PV, VG, LV, file system; grow with lvextend -r; mount by UUID and prove it with mount -a.
- Story: LV grew to 800M, df still 336M until xfs_growfs (KodeKloud).
- Rule: mount -a before reboot, every time.

### L10. Permanent Firewall
- Agree: 5 of 7 (TH37); services and ports 2 of 7 (TH38).
- Idea: --permanent then --reload; --add-service, --add-port=N/tcp; keep SSH open.
- Story: the "five minutes later" trap (open-exam-prep).
- Rule: No firewall change without --permanent.

### L11. Label, Don't Disable
- Agree: keep enforcing 3 of 8 (TH39); fcontext + restorecon 4 of 8 (TH41); ports 3 of 8 (TH43). Split: pluralsight suggests a brief setenforce 0 test (TH40).
- Idea: keep SELinux enforcing; fix labels with semanage fcontext then restorecon; label ports with semanage port.
- Story: the panic switch to permissive (certcrush); "cannot bind to port" (Red Hat blog).
- Rule: SELinux stays enforcing; fix the label, not the mode.

### L12. Break In at Boot
- Agree: 3 of 7 (TH23); never skip remount and autorelabel 2 of 7 (TH25). init=/bin/bash alternative 1 of 7 (TH24). Version split between methods is one author's habit, not a Red Hat rule.
- Idea: rd.break, mount -o remount,rw /sysroot, chroot /sysroot, passwd, touch /.autorelabel, exit twice.
- Story: tecmint's locked-out admin; the risky-first tactic (pluralsight).
- Rule: Remount read-write and autorelabel, every time.

## Splits (decisions, not lessons)
- Task order: quick tasks first (certcrush, kraker) vs risky boot and storage first (pluralsight). All agree on reading every task first.
- SELinux testing: brief permissive test (pluralsight) vs never leave enforcing (certcrush) vs per-domain permissive (Red Hat blog).
- Root reset: rd.break vs init=/bin/bash; habit, not version.
- Pass mark and duration: 210/300 and about 3 hours are reported, not published by Red Hat.

## Coverage gaps
Not in these 12: autofs and NFS, nmcli networking and IPv6, ACLs, journal persistence, tuned profiles, processes, shell scripts, SSH keys, chrony, partitions and swap. Thin or absent in sources: essential tools (redirection, grep, tar), sudoers, tuned, IPv6, grubby, at/crontab syntax. A fourth arc can cover these.

## Delivery
Lesson 1 first as a sample, then the rest once approved. Audio waits for ElevenLabs credits; scripts and cards come first.
