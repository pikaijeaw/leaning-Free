# Agreement map: RHCSA (EX200), beginner, RHEL 10 era

Built from research/notes/a.md, b.md, c.md, d.md (178 notes, 33 distinct pages) against the sub-topics in research/topics.md. Authority for scope is Red Hat's own page (https://au.redhat.com/training/courses/ex200/): hands-on, no internet, no notes or books, shipped documentation available, everything must persist after reboot without intervention, no containers section, Flatpak, systemd timer units and tuning profiles are in scope.

How to read the counts: "N of M" means M pages had at least one note on the theme's sub-topic (including `Also:` lines), and N of them support the theme. Pages, not notes. M under 3 is marked "thin evidence". The official page is counted as agreeing only where it actually states the idea. Notes listed under "Flagged notes" sit on the theme so they are accounted for, but they are not counted as support.

## Flags: do not repeat these in any lesson

Readers marked these source claims as outdated or wrong for the RHEL 10 exam. Each affected theme carries a `Flag:` line.

1. **RHEL 7 era advice** (pluralsight, lisenet): "yum" and "Red Hat Network" (now dnf and Red Hat Content Delivery Network); network teaming / teamd (gone in RHEL 9/10); iSCSI, postfix, make-dummy-cert, mysql, EX300 (RHCE-era, not RHCSA); the tip to install the "Server with GUI" group at exam start (d:N9). Themes: TH03, TH05, TH18, TH44.
2. **`update-grub` / `GRUB_DEFAULT` to change the boot target** (kodekloud blog, a:N11): Debian/Ubuntu helper, and GRUB_DEFAULT picks a menu entry, not a systemd target. Use `systemctl set-default`; bootloader changes use `grubby` or `grub2-mkconfig`. Theme: TH21.
3. **Podman / containers on the exam** (certland, b:N7 context): the RHEL 10 objectives have no containers section. Themes: TH09, TH07.
4. **"No documentation access"** (certland) and **"limited internet access"** plus made-up category percentages, IPs (kraker exam overview, c:N5): the official page says no internet, and the shipped documentation is available. Themes: TH03, TH07.
5. **`usermod -aG group user1,user2`** (kraker 03, c:N23): usermod takes one user; use `gpasswd -a` per user or loop. Theme: TH14.
6. **`passwd -e` as a "fix" for an expired password** (kraker 03, c:N23): it expires the password. (Using `passwd -e` or `chage -d 0` to force a change at next login, b:N13, is correct.) Theme: TH15.
7. **`finger`** (kraker 03, c:N23): not shipped on RHEL 9/10. Theme: TH16.
8. **"Don't forget `useradd -m`"** (kraker 03, c:N23) and the hand-made `mkdir /home/userA` (adamtheautomator, Ubuntu demo, a:N37): on RHEL, CREATE_HOME is on and useradd makes the home directory. Theme: TH14.
9. **SUID on shell scripts runs them as the owner** (dev.to austinozor, computernetworkingnotes exercise; c:N13, c:N15): Linux ignores SUID on interpreted scripts; it only works on compiled binaries. Theme: TH11.
10. **Special-bit typos and gaps**: computernetworkingnotes "7 (6+4+1)" is 4+2+1 (c:N9); dev.to austinozor skips that GNU `chmod 755` on a directory keeps SGID, so use `g-s` or `chmod -2000` (c:N15); adamtheautomator once calls the 2 bit "SUID" and mislabels a primary group (a:N35). Themes: TH10, TH12.
11. **`semanage boolean -I` / `semanage fcontext -I -C`** (github SELinux notes, c:N43): typo for lowercase `-l`. Themes: TH41, TH42, TH44.
12. **`createrepo`** (dev.to shamain_anjum, c:N26): on RHEL 9/10 the package is `createrepo_c`; hosting a repo is not itself an objective, only client access is. Theme: TH18.
13. **`PASS_MIN_LEN` in /etc/login.defs** (kodekloud notes, d:N14 if retold): not enforced on modern RHEL; pam_pwquality `minlen` governs length. Theme: TH15.
14. **Debian autofs commands** (opensource.com, d:N26, d:N27): `apt-get install nfs-common autofs` and `service`. On RHEL: `dnf install nfs-utils autofs`, `systemctl enable --now autofs`, and a drop-in under /etc/auto.master.d/*.autofs is the common way. Themes: TH34, TH35.
15. **"rd.break for RHEL 9, init=/bin/bash for RHEL 10"** (dev.to dhavalthakar97, c:N29): the author's own mapping, not a Red Hat rule; both work. Same page writes `remount rw` with a space; the standard form is `remount,rw`. Themes: TH23, TH24, TH25.
16. **Terminology and variants on the linuxtechi rescue page** (a:N14, a:N19): calls the rd.break shell "rescue mode" and equates it with single user and emergency mode (they are distinct on RHEL); prompt `sh-4.4#` is RHEL 8 era; the `rw init=/sysroot/bin/sh` variant is unusual, check before teaching. Themes: TH22, TH23, TH24, TH26, TH33.
17. **`nmstatectl eddit`** (linuxtechi static IP, a:N25): typo for `edit`, and nmstate is not installed by default. Theme: TH36.
18. **SELinux domain man pages** (Red Hat blog, d:N42; github SELinux c:N44): on RHEL 9/10 `man httpd_selinux` and friends may need the `selinux-policy-doc` package; verify before promising them. Theme: TH44.
19. **Outdated platform and price on certland** (b:N9, b:N38 context): RHEL 9 VM, $400. Theme: TH07.

## Themes

### Exam format and preparation (T01, T02)

## TH01 Treat "it survives a reboot" as the scoring rule: start and enable, mount and fstab, --permanent, and the connection profile rather than `ip`
- Sub-topic: T01 (also T11, T13, T15, T16)
- Agree: 9 of 15. Notes: b:N1, a:N2, b:N2, c:N2, d:N4, a:N22, a:N26, d:N31, a:N41. Urls: https://au.redhat.com/training/courses/ex200/, https://open-exam-prep.com/study-guides/rhcsa/introduction/exam-facts, https://www.certcrush.app/blog/how-to-pass-rhcsa-ex200-2026-8-week-study-plan, https://kraker.codeberg.page/rhcsa/rhcsa_synthesis/00_exam_overview/, https://www.pluralsight.com/resources/blog/cloud/red-hat-exams-a-few-tips, https://linuxtechi.com/set-static-ip-address-on-rhel-9, https://www.golinuxcloud.com/firewalld-cheat-sheet/, https://notes.kodekloud.com/docs/Prep-Course-Red-Hat-Certified-System-Administrator-RHCSA/Managing-Network-Configuration-and-Security/Demo-Configuring-Firewalld/page, https://open-exam-prep.com/study-guides/rhcsa/filesystems-network/autofs
- Disagree: none found
- Level: foundation
- Best story: You walk out feeling good, the grading script reboots the box, and the service you started but never enabled, the mount not in fstab and the firewall rule without --permanent all quietly fail. https://www.certcrush.app/blog/how-to-pass-rhcsa-ex200-2026-8-week-study-plan

## TH02 Reboot and re-verify each cluster of tasks, and keep the last stretch of the exam for a final reboot check
- Sub-topic: T01
- Agree: 4 of 15. Notes: a:N3, b:N3, c:N3, d:N1. Urls: https://open-exam-prep.com/study-guides/rhcsa/introduction/exam-facts, https://www.certcrush.app/blog/how-to-pass-rhcsa-ex200-2026-8-week-study-plan, https://kraker.codeberg.page/rhcsa/rhcsa_synthesis/00_exam_overview/, https://www.lisenet.com/?p=5574
- Disagree: none found
- Level: foundation
- Best story: The 80-minute perfect score: finished every task, then spent the spare time rebooting the VM again and again to prove it all stuck. https://www.lisenet.com/?p=5574

## TH03 Drill the shipped documentation (man -k, man 5 fstab, info, --help, /usr/share/doc, example files) because there is no internet
- Sub-topic: T01 (also T02, T14, T17)
- Agree: 7 of 16. Notes: b:N1, b:N12, a:N4, b:N10, d:N10, c:N7, d:N42. Urls: https://au.redhat.com/training/courses/ex200/, https://open-exam-prep.com/study-guides/rhcsa/introduction/exam-facts, https://www.certcrush.app/blog/how-to-pass-rhcsa-ex200-2026-8-week-study-plan, https://www.webasha.com/blog/rhcsa-certification-course-details-syllabus-exam-career-scope%29, https://www.lisenet.com/?p=5574, https://github.com/1980is/rhcsa-9/blob/main/NFS%20and%20Autofs.md, https://www.redhat.com/en/blog/semanage-keep-selinux-enforcing
- Disagree: https://certland.net/blog/red-hat-certified-system-administrator-rhcsa-study-guide-2026/: has a heading "No documentation access" and says Red Hat publishes no tidy objective list. https://kraker.codeberg.page/rhcsa/rhcsa_synthesis/00_exam_overview/: says "Limited internet access".
- Flag: no-documentation and limited-internet claims are wrong (Flags 4); lisenet's own man-page list includes RHEL 7 RHCE items (teamd, iscsiadm, postfix, make-dummy-cert, mysql) that are not RHCSA (Flags 1).
- Level: foundation
- Best story: none

## TH04 Start the exam with a routine: read every task, note which depend on each other, ask the proctor about unclear ones, and work from several SSH sessions
- Sub-topic: T01 (also T02, T12)
- Agree: 4 of 15. Notes: c:N1, b:N3, d:N3, d:N2, d:N11. Urls: https://kraker.codeberg.page/rhcsa/rhcsa_synthesis/00_exam_overview/, https://www.certcrush.app/blog/how-to-pass-rhcsa-ex200-2026-8-week-study-plan, https://www.pluralsight.com/resources/blog/cloud/red-hat-exams-a-few-tips, https://www.lisenet.com/?p=5574
- Disagree: none found (the order to work in after reading is split; see TH05 and TH06)
- Level: foundation
- Best story: none

## TH05 Do the quick independent tasks first, budget minutes per task, and skip anything stuck for ten minutes
- Sub-topic: T01
- Agree: 2 of 15. Notes: b:N3, c:N1, c:N4. Urls: https://www.certcrush.app/blog/how-to-pass-rhcsa-ex200-2026-8-week-study-plan, https://kraker.codeberg.page/rhcsa/rhcsa_synthesis/00_exam_overview/
- Flagged notes (not counted): d:N9
- Disagree: https://www.pluralsight.com/resources/blog/cloud/red-hat-exams-a-few-tips: do the risky storage, fstab and bootloader tasks first, because a reset or unbootable VM costs less early on.
- Flag: the "install Server with GUI at exam start" tip is a RHEL 7 habit; do not teach it (Flags 1).
- Level: core
- Best story: none

## TH06 Do the risky boot and storage tasks first and test them, because an unbootable VM can zero the whole exam
- Sub-topic: T01 (also T08, T12, T13)
- Agree: 1 of 15. Notes: d:N4, d:N5. Urls: https://www.pluralsight.com/resources/blog/cloud/red-hat-exams-a-few-tips
- Disagree: https://www.certcrush.app/blog/how-to-pass-rhcsa-ex200-2026-8-week-study-plan: do quick independent tasks (users, sudo, firewall port) first and the storage chain later in one block. https://kraker.codeberg.page/rhcsa/rhcsa_synthesis/00_exam_overview/: do easy ones first.
- Level: core
- Best story: The zero score: one unbootable VM wipes out a perfect set of tasks, so do the risky storage and GRUB work first while you still have little to lose. https://www.pluralsight.com/resources/blog/cloud/red-hat-exams-a-few-tips

## TH07 Know the format: live VMs, a task list, about 3 hours, and all-or-nothing grading per task; treat every study point as scored
- Sub-topic: T01 (also T03)
- Agree: 5 of 15. Notes: a:N1, a:N5, a:N6, b:N8, b:N11, c:N5, d:N6. Urls: https://open-exam-prep.com/study-guides/rhcsa/introduction/exam-facts, https://www.certcrush.app/blog/how-to-pass-rhcsa-ex200-2026-8-week-study-plan, https://kraker.codeberg.page/rhcsa/rhcsa_synthesis/00_exam_overview/, https://www.webasha.com/blog/rhcsa-certification-course-details-syllabus-exam-career-scope%29, https://www.pluralsight.com/resources/blog/cloud/red-hat-exams-a-few-tips
- Disagree: https://www.webasha.com/blog/rhcsa-certification-course-details-syllabus-exam-career-scope%29: Red Hat publishes neither the pass score nor the duration, so aim to finish every task (certland states 70% and certcrush 210/300 as fact-like). https://certland.net/blog/red-hat-certified-system-administrator-rhcsa-study-guide-2026/: about $400 versus https://www.certcrush.app/blog/how-to-pass-rhcsa-ex200-2026-8-week-study-plan: $500 in the US.
- Flag: kraker's category percentages, sample IPs and "limited internet" are not from Red Hat (Flags 4); certland's RHEL 9 platform, $400 price and Podman domain are outdated (Flags 3, 19).
- Level: foundation
- Best story: none

## TH08 Study by doing: a two-VM lab, drills from a broken or blank state, timed runs, and full mock exams
- Sub-topic: T01 (also T08, T09, T12)
- Agree: 5 of 15. Notes: a:N7, b:N4, b:N5, b:N6, b:N24, c:N6, d:N12. Urls: https://open-exam-prep.com/study-guides/rhcsa/introduction/exam-facts, https://www.certcrush.app/blog/how-to-pass-rhcsa-ex200-2026-8-week-study-plan, https://certland.net/blog/red-hat-certified-system-administrator-rhcsa-study-guide-2026/, https://kraker.codeberg.page/rhcsa/rhcsa_synthesis/00_exam_overview/, https://www.lisenet.com/?p=5574
- Disagree: https://www.lisenet.com/?p=5574: calls RHCSA "like a colouring book" for experienced admins; https://www.pluralsight.com/resources/blog/cloud/red-hat-exams-a-few-tips: "certainly not easy" and can "break the spirits" of veterans (difficulty, not method).
- Level: foundation
- Best story: Boot recovery tasks "take three minutes once you have done them ten times. Most candidates have done them twice." https://www.certcrush.app/blog/how-to-pass-rhcsa-ex200-2026-8-week-study-plan

## TH09 Study from RHEL 10 material: Flatpak and systemd timers are in, containers and Podman are out; recheck the official page the week you book
- Sub-topic: T01 (also T06, T11)
- Agree: 2 of 15. Notes: b:N7, b:N22. Urls: https://www.certcrush.app/blog/how-to-pass-rhcsa-ex200-2026-8-week-study-plan, https://au.redhat.com/training/courses/ex200/
- Disagree: https://certland.net/blog/red-hat-certified-system-administrator-rhcsa-study-guide-2026/: lists Podman (run, rootless, podman generate systemd) as a domain and says the exam is RHEL 9.
- Flag: Podman on the exam (Flags 3).
- Level: foundation
- Best story: "If your study material never mentions Flatpak, it predates the current exam." https://www.certcrush.app/blog/how-to-pass-rhcsa-ex200-2026-8-week-study-plan

### Permissions (T03, T04)

## TH10 Give all four octal digits and read special bits in the execute slots: 4/s owner, 2/s group, 1/t others, capital S/T means no execute underneath
- Sub-topic: T04
- Agree: 3 of 5. Notes: a:N33, c:N8, c:N9, c:N15. Urls: https://adamtheautomator.com/special-permissions-in-linux/, https://www.computernetworkingnotes.com/linux-tutorials/suid-sgid-and-sticky-bit-explained.html, https://dev.to/austinozor/understanding-acl-and-special-permissions-in-linux-3g3h
- Disagree: none found
- Flag: "7 (6+4+1)" typo; `chmod 755` keeps SGID on directories, use `g-s` or `chmod -2000` (Flags 10).
- Level: core
- Best story: none

## TH11 Use SUID only on trusted compiled programs; it runs them with the owner's rights, and does nothing on scripts
- Sub-topic: T04
- Agree: 2 of 5. Notes: a:N33, a:N34, c:N10, c:N13. Urls: https://adamtheautomator.com/special-permissions-in-linux/, https://www.computernetworkingnotes.com/linux-tutorials/suid-sgid-and-sticky-bit-explained.html
- Flagged notes (not counted): c:N15
- Disagree: https://dev.to/austinozor/understanding-acl-and-special-permissions-in-linux-3g3h: after `chmod u+s` on a script, "any user can run this script with root privileges". https://www.computernetworkingnotes.com/linux-tutorials/suid-sgid-and-sticky-bit-explained.html: uses a script in its SUID exercise, implying the same.
- Flag: SUID on scripts (Flags 9).
- Level: core
- Best story: The passwd puzzle: a normal user changes their own password even though /etc/shadow is root-only, because /usr/bin/passwd carries SUID root. https://www.computernetworkingnotes.com/linux-tutorials/suid-sgid-and-sticky-bit-explained.html (Alternative: SUID on `cat` lets a plain user read /etc/shadow, and the author hurries to undo it. https://adamtheautomator.com/special-permissions-in-linux/)

## TH12 For a shared team folder, set SGID on the directory so new files inherit its group, and add the sticky bit so users cannot delete each other's files
- Sub-topic: T04 (also T05)
- Agree: 3 of 5. Notes: a:N35, a:N36, c:N11, c:N12, b:N20. Urls: https://adamtheautomator.com/special-permissions-in-linux/, https://www.computernetworkingnotes.com/linux-tutorials/suid-sgid-and-sticky-bit-explained.html, https://www.certcrush.app/blog/how-to-pass-rhcsa-ex200-2026-8-week-study-plan
- Disagree: none found
- Flag: adamtheautomator calls the 2 bit "SUID" once and mislabels the primary group in step 10; teach from the concept (Flags 10).
- Level: core
- Best story: James and Oliver in /sales: their files land in their own private groups until one `chmod g+s` makes everything belong to marketing. https://www.computernetworkingnotes.com/linux-tutorials/suid-sgid-and-sticky-bit-explained.html (Sticky version: userA tries to delete userB's file and is refused, file "safe and sound". https://adamtheautomator.com/special-permissions-in-linux/)

## TH13 Grant one extra user or group access with ACLs: setfacl -m, -x, -b, and check with getfacl
- Sub-topic: T04
- Agree: 1 of 5. Notes: c:N14. Urls: https://dev.to/austinozor/understanding-acl-and-special-permissions-in-linux-3g3h
- Disagree: none found
- Level: core
- Best story: none

### Users, groups and passwords (T05)

## TH14 Append supplementary groups with `usermod -aG` one user at a time, know primary vs supplementary, and re-login before testing
- Sub-topic: T05 (also T03)
- Agree: 3 of 9. Notes: c:N16, c:N17, c:N21, d:N18, b:N20. Urls: https://kraker.codeberg.page/rhcsa/rhcsa_synthesis/03_user_group_management/, https://www.pluralsight.com/resources/blog/cloud/red-hat-exams-a-few-tips, https://www.certcrush.app/blog/how-to-pass-rhcsa-ex200-2026-8-week-study-plan
- Flagged notes (not counted): c:N23, a:N37
- Disagree: none found
- Flag: `usermod -aG group user1,user2` is invalid (Flags 5); useradd already makes the home dir on RHEL, no `-m` reminder or manual mkdir needed (Flags 8).
- Level: foundation
- Best story: The "I added them but it still says permission denied" ticket: group changes do not reach a session that is already open. https://kraker.codeberg.page/rhcsa/rhcsa_synthesis/03_user_group_management/

## TH15 Map the task words to the right chage flag (-M, -m, -W, -I, -E, -d 0) and use chage for existing users, login.defs only for new ones
- Sub-topic: T05
- Agree: 3 of 9. Notes: b:N13, b:N16, b:N17, c:N18, c:N19, c:N22, d:N14, d:N15. Urls: https://open-exam-prep.com/study-guides/rhcsa/users-groups/password-aging, https://kraker.codeberg.page/rhcsa/rhcsa_synthesis/03_user_group_management/, https://notes.kodekloud.com/docs/Prep-Course-Red-Hat-Certified-System-Administrator-RHCSA/User-Management/Password-Management/page
- Flagged notes (not counted): c:N23
- Disagree: none found
- Flag: `passwd -e` is not a fix for an expired password (Flags 6); PASS_MIN_LEN is not enforced (Flags 13).
- Level: core
- Best story: none

## TH16 Set passwords with `passwd --stdin` and verify with `chage -l`, not by decoding /etc/shadow; pick a strong password rather than fighting PAM
- Sub-topic: T05 (also T07)
- Agree: 3 of 9. Notes: b:N14, b:N15, b:N19, c:N24, c:N21, d:N13, d:N16, d:N17. Urls: https://open-exam-prep.com/study-guides/rhcsa/users-groups/password-aging, https://kraker.codeberg.page/rhcsa/rhcsa_synthesis/03_user_group_management/, https://notes.kodekloud.com/docs/Prep-Course-Red-Hat-Certified-System-Administrator-RHCSA/User-Management/Password-Management/page
- Flagged notes (not counted): c:N23
- Disagree: none found
- Flag: `finger` is not on RHEL 9/10 (Flags 7).
- Level: core
- Best story: none

## TH17 Locking is not blocking: `usermod -L` or `passwd -l` leaves SSH keys working, so add nologin or expire the account, and avoid `passwd -d`
- Sub-topic: T05 (also T18)
- Agree: 2 of 9. Notes: b:N18, c:N20. Urls: https://open-exam-prep.com/study-guides/rhcsa/users-groups/password-aging, https://kraker.codeberg.page/rhcsa/rhcsa_synthesis/03_user_group_management/
- Disagree: none found
- Level: core
- Best story: none

### Software and scripts (T06, T07)

## TH18 Configure client repo access with a .repo file in /etc/yum.repos.d and confirm with `dnf repolist`, until it is automatic, because every package task depends on it
- Sub-topic: T06
- Agree: 3 of 4. Notes: b:N21, c:N25, d:N8, c:N26. Urls: https://au.redhat.com/training/courses/ex200/, https://dev.to/shamain_anjum/host-a-local-rpm-package-repository-on-red-hat-linux-21lb, https://www.pluralsight.com/resources/blog/cloud/red-hat-exams-a-few-tips
- Disagree: none found
- Flag: pluralsight says "yum" and "Red Hat Network" (Flags 1); `createrepo` is `createrepo_c` on RHEL 9/10 and hosting a repo is only a practice lab (Flags 12).
- Level: foundation
- Best story: none

## TH19 Practise Flatpak: add a remote, search it, install and remove an app, list what is installed
- Sub-topic: T06 (also T01)
- Agree: 2 of 4. Notes: b:N21, b:N22, b:N7. Urls: https://au.redhat.com/training/courses/ex200/, https://www.certcrush.app/blog/how-to-pass-rhcsa-ex200-2026-8-week-study-plan
- Disagree: none found (but no source gives the actual commands; see gaps)
- Level: core
- Best story: none

## TH20 Keep scripts simple (if/test, for loops, $1 $2, command substitution) and use absolute paths when cron or systemd runs them
- Sub-topic: T07 (also T11)
- Agree: 3 of 3. Notes: b:N23, b:N37, c:N24. Urls: https://www.certcrush.app/blog/how-to-pass-rhcsa-ex200-2026-8-week-study-plan, https://www.centron.de/tutorials/systemd-timers-instead-of-cron, https://kraker.codeberg.page/rhcsa/rhcsa_synthesis/03_user_group_management/
- Disagree: none found
- Level: foundation
- Best story: The script that works in your shell but fails in the unit, because units get a fixed PATH and no profile. https://www.centron.de/tutorials/systemd-timers-instead-of-cron

### Boot, targets and root reset (T08, T09)

## TH21 Set the default target with `systemctl set-default`; `systemctl isolate` only changes the running system
- Sub-topic: T08
- Agree: 1 of 6. Notes: a:N8, a:N9, a:N12. Urls: https://kodekloud.com/blog/linux-boot-or-change-system-into-different-operating-modes/
- Flagged notes (not counted): a:N11
- Disagree: https://kodekloud.com/blog/linux-boot-or-change-system-into-different-operating-modes/: the same page also says to change the default via `GRUB_DEFAULT` in /etc/default/grub plus `update-grub`.
- Flag: `update-grub` / `GRUB_DEFAULT` for targets is wrong on RHEL (Flags 2).
- Level: foundation
- Best story: Need a 3D app for one hour on a text-only server: `systemctl isolate graphical.target`, and on reboot you are back in text mode. https://kodekloud.com/blog/linux-boot-or-change-system-into-different-operating-modes/

## TH22 Know the boot entry points: edit a GRUB entry with `e` (one-time, Ctrl+x to boot), rescue.target, emergency.target, and the rd.break shell are four different things
- Sub-topic: T08 (also T09, T13)
- Agree: 4 of 6. Notes: a:N10, a:N12, a:N13, a:N20, c:N27. Urls: https://kodekloud.com/blog/linux-boot-or-change-system-into-different-operating-modes/, https://linuxtechi.com/boot-rhel-9-into-rescue-mode, https://dev.to/dhavalthakar97/linux-in-action-resetting-the-root-password-on-rhel-10-28j2, https://tecmint.com/reset-forgotten-root-password-rhel-9
- Flagged notes (not counted): a:N14
- Disagree: https://linuxtechi.com/boot-rhel-9-into-rescue-mode: calls the rd.break shell "rescue mode" and says rescue mode is also called single user or emergency mode.
- Flag: linuxtechi rescue naming and RHEL 8 era prompt (Flags 16).
- Level: core
- Best story: none

## TH23 Reset a lost root password with rd.break: remount /sysroot read-write, chroot, passwd, touch /.autorelabel, exit twice
- Sub-topic: T09 (also T08)
- Agree: 3 of 7. Notes: a:N15, a:N16, c:N28, b:N24. Urls: https://tecmint.com/reset-forgotten-root-password-rhel-9, https://dev.to/dhavalthakar97/linux-in-action-resetting-the-root-password-on-rhel-10-28j2, https://www.certcrush.app/blog/how-to-pass-rhcsa-ex200-2026-8-week-study-plan
- Disagree: https://linuxtechi.com/boot-rhel-9-into-rescue-mode: ends with `reboot -f` from inside the chroot rather than `exit` twice, and offers `rw init=/sysroot/bin/sh` instead. https://dev.to/dhavalthakar97/linux-in-action-resetting-the-root-password-on-rhel-10-28j2: pins rd.break to RHEL 9 only.
- Flag: the rd.break-vs-init version split is the author's choice (Flags 15); linuxtechi's variant and naming are unverified (Flags 16).
- Level: core
- Best story: Locked out with no wheel access: interrupt GRUB, rd.break, chroot, passwd, and the easy-to-forget /.autorelabel. https://tecmint.com/reset-forgotten-root-password-rhel-9

## TH24 Know the init=/bin/bash alternative: remount,rw /, passwd, touch /.autorelabel, exec /sbin/init
- Sub-topic: T09
- Agree: 1 of 7. Notes: c:N29. Urls: https://dev.to/dhavalthakar97/linux-in-action-resetting-the-root-password-on-rhel-10-28j2
- Flagged notes (not counted): a:N19
- Disagree: https://linuxtechi.com/boot-rhel-9-into-rescue-mode: uses `rw init=/sysroot/bin/sh` then `chroot /sysroot` and `reboot -f`.
- Flag: version split is the author's mapping and `remount rw` should be `remount,rw` (Flags 15); init=/sysroot/bin/sh variant unverified (Flags 16).
- Level: advanced
- Best story: none

## TH25 Never skip the read-write remount or /.autorelabel; those two misses are why a reset "doesn't work"
- Sub-topic: T09 (also T17)
- Agree: 2 of 7. Notes: a:N16, a:N17, c:N30, c:N45. Urls: https://tecmint.com/reset-forgotten-root-password-rhel-9, https://dev.to/dhavalthakar97/linux-in-action-resetting-the-root-password-on-rhel-10-28j2
- Disagree: https://github.com/1980is/rhcsa-9/blob/main/SELinux.md: for ordinary label problems prefers `restorecon -Rv` over `touch /.autorelabel`, which relabels the whole disk (different situation, not a contradiction for the reset).
- Flag: `remount rw` spacing (Flags 15).
- Level: core
- Best story: Lost root via a rotated vault secret that never propagated; the fix is a GRUB edit, a remount, passwd, and the /.autorelabel you must not forget. https://dev.to/dhavalthakar97/linux-in-action-resetting-the-root-password-on-rhel-10-28j2

## TH26 Try the easy reset first (`passwd` as root, `sudo passwd root` as a wheel user), and expect the exam VM may need recovery before you can start
- Sub-topic: T09 (also T05)
- Agree: 2 of 7. Notes: a:N18, d:N7, c:N31. Urls: https://tecmint.com/reset-forgotten-root-password-rhel-9, https://www.pluralsight.com/resources/blog/cloud/red-hat-exams-a-few-tips
- Disagree: none found
- Flag: if quoting linuxtechi on recovery, avoid its terminology and variant (Flags 16).
- Level: foundation
- Best story: none

### Logs, services and scheduling (T10, T11)

## TH27 Make the journal persistent: Storage=persistent drop-in, /var/log/journal, restart journald, verify with `journalctl --list-boots`
- Sub-topic: T10
- Agree: 1 of 2 (thin evidence). Notes: b:N25, b:N26, b:N27. Urls: https://oneuptime.com/blog/post/2026-03-04-configure-persistent-journald-storage-on-rhel/view
- Disagree: none found
- Level: core
- Best story: Vanishing logs: you reboot to chase a crash and the evidence is gone because the journal lived in tmpfs under /run. https://oneuptime.com/blog/post/2026-03-04-configure-persistent-journald-storage-on-rhel/view

## TH28 Start and enable every service with `systemctl enable --now`, and check `is-enabled`, including firewalld and autofs themselves
- Sub-topic: T11 (also T01, T14, T16)
- Agree: 5 of 8. Notes: a:N2, b:N2, c:N2, c:N3, a:N31, a:N41. Urls: https://open-exam-prep.com/study-guides/rhcsa/introduction/exam-facts, https://www.certcrush.app/blog/how-to-pass-rhcsa-ex200-2026-8-week-study-plan, https://kraker.codeberg.page/rhcsa/rhcsa_synthesis/00_exam_overview/, https://www.golinuxcloud.com/firewalld-cheat-sheet/, https://open-exam-prep.com/study-guides/rhcsa/filesystems-network/autofs
- Disagree: none found
- Level: foundation
- Best story: none

## TH29 Build a systemd timer as two units with the same name, enable the .timer not the .service, and add Persistent=true to catch missed runs
- Sub-topic: T11
- Agree: 3 of 7. Notes: b:N28, b:N29, b:N30, b:N34, b:N35, c:N32, c:N34. Urls: https://www.centron.de/tutorials/systemd-timers-instead-of-cron, https://adminschoice.com/systemd-timers-vs-cron/, https://cronuru.com/guides/systemd-timers
- Disagree: none found
- Level: core
- Best story: The timer that never fired: backup.service enabled instead of backup.timer, list-timers shows NEXT n/a, and the backup never runs. https://www.centron.de/tutorials/systemd-timers-instead-of-cron (Also: machine off at 2am, cron skips, Persistent=true runs it once at boot. https://adminschoice.com/systemd-timers-vs-cron/)

## TH30 Write OnCalendar in systemd syntax, not cron syntax, test it with `systemd-analyze calendar`, and verify with `list-timers` and `journalctl -u`
- Sub-topic: T11 (also T10)
- Agree: 2 of 7. Notes: b:N31, b:N32, b:N33, c:N33, c:N35, c:N36. Urls: https://www.centron.de/tutorials/systemd-timers-instead-of-cron, https://cronuru.com/guides/systemd-timers
- Disagree: none found
- Level: core
- Best story: The 30-second timer that silently runs once a minute because AccuracySec defaults to 1 minute, and list-timers still looks fine. https://cronuru.com/guides/systemd-timers

## TH31 Keep cron for simple one-line or per-user jobs, and practise one job three ways: at, cron and a timer
- Sub-topic: T11
- Agree: 3 of 7. Notes: b:N36, c:N37. Urls: https://adminschoice.com/systemd-timers-vs-cron/, https://cronuru.com/guides/systemd-timers, https://www.certcrush.app/blog/how-to-pass-rhcsa-ex200-2026-8-week-study-plan
- Disagree: none found (soft: https://www.centron.de/tutorials/systemd-timers-instead-of-cron frames timers as a replacement for cron and warns to remove the crontab line when migrating)
- Level: foundation
- Best story: none

### Storage and file systems (T12, T13)

## TH32 Build the LVM chain layer by layer (pvcreate, vgcreate, lvcreate, check with pvs/vgs/lvs), grow the file system with the LV (`lvextend -r`, or `xfs_growfs` / `resize2fs`; XFS never shrinks), and tear down in reverse
- Sub-topic: T12 (also T13)
- Agree: 2 of 4. Notes: d:N19, d:N20, d:N21, d:N22, d:N23, b:N38. Urls: https://notes.kodekloud.com/docs/Prep-Course-Red-Hat-Certified-System-Administrator-RHCSA/Storage-Management/Demo-Working-With-Logical-Volumes/page, https://certland.net/blog/red-hat-certified-system-administrator-rhcsa-study-guide-2026/
- Disagree: none found
- Level: core
- Best story: The LV that grew but the disk did not: lvextend to 800M, df still says 336M, until xfs_growfs makes it 736M. https://notes.kodekloud.com/docs/Prep-Course-Red-Hat-Certified-System-Administrator-RHCSA/Storage-Management/Demo-Working-With-Logical-Volumes/page

## TH33 Mount by UUID in /etc/fstab and prove it with `mount -a` before rebooting; a bad fstab line can stop the boot, so know how to comment it out from rescue
- Sub-topic: T13 (also T01, T08, T12)
- Agree: 4 of 6. Notes: d:N24, d:N25, b:N9, a:N13, d:N4. Urls: https://notes.kodekloud.com/docs/Prep-Course-Red-Hat-Certified-System-Administrator-RHCSA/Storage-Management/Demo-Working-With-Logical-Volumes/page, https://certland.net/blog/red-hat-certified-system-administrator-rhcsa-study-guide-2026/, https://linuxtechi.com/boot-rhel-9-into-rescue-mode, https://www.pluralsight.com/resources/blog/cloud/red-hat-exams-a-few-tips
- Disagree: none found
- Flag: linuxtechi calls the rd.break shell "rescue mode"; name the states correctly when retelling the fstab fix (Flags 16).
- Level: core
- Best story: none

### Network file systems (T14)

## TH34 Choose autofs or fstab by the task verb ("when accessed" vs "at boot") and wire autofs as a master line or auto.master.d drop-in plus a map file, with `*` and `&` for home directories
- Sub-topic: T14 (also T13)
- Agree: 3 of 3. Notes: a:N38, a:N39, a:N40, c:N38, c:N39, c:N40, d:N26, d:N27, d:N28. Urls: https://open-exam-prep.com/study-guides/rhcsa/filesystems-network/autofs, https://github.com/1980is/rhcsa-9/blob/main/NFS%20and%20Autofs.md, https://opensource.com/article/18/6/using-autofs-mount-nfs-shares
- Disagree: https://github.com/1980is/rhcsa-9/blob/main/NFS%20and%20Autofs.md: "NFS is not a part of the RHCSA exam" (meaning server setup; its practice-server recipe c:N40 is a lab, not an exam task) versus https://au.redhat.com/training/courses/ex200/, which lists mounting NFS and configuring autofs.
- Flag: opensource.com uses Debian commands (apt-get, nfs-common, service) (Flags 14).
- Level: core
- Best story: none

## TH35 Debug autofs from the bottom up: manual NFS mount and `showmount -e` first, reload after map edits, relative keys, matching UIDs, and do not panic at an empty directory
- Sub-topic: T14 (also T01, T05)
- Agree: 3 of 3. Notes: a:N41, a:N42, a:N43, c:N7, c:N38, d:N29, d:N30. Urls: https://open-exam-prep.com/study-guides/rhcsa/filesystems-network/autofs, https://github.com/1980is/rhcsa-9/blob/main/NFS%20and%20Autofs.md, https://opensource.com/article/18/6/using-autofs-mount-nfs-shares
- Disagree: none found
- Flag: Debian autofs commands (Flags 14).
- Level: core
- Best story: The empty directory that is not empty: `ls` in /mnt/tree shows nothing, yet `cd ourfiles` drops you straight into a freshly mounted NFS share. https://opensource.com/article/18/6/using-autofs-mount-nfs-shares (Same moment: https://github.com/1980is/rhcsa-9/blob/main/NFS%20and%20Autofs.md)

### Networking and firewall (T15, T16)

## TH36 Set a static address with `nmcli connection modify`: method manual plus addresses, gateway and DNS, then bring the connection up; IPv6 uses the same ipv6.* properties
- Sub-topic: T15 (also T01)
- Agree: 2 of 2 (thin evidence). Notes: a:N21, a:N22, a:N23, a:N24, a:N25, b:N39, b:N40, b:N41. Urls: https://linuxtechi.com/set-static-ip-address-on-rhel-9, https://oneuptime.com/blog/post/2026-03-04-configure-static-ip-addresses-rhel-9-nmcli/view
- Disagree: none found
- Flag: `nmstatectl eddit` typo and nmstate not installed by default (Flags 17).
- Level: core
- Best story: none

## TH37 Make every firewall change with --permanent and then --reload (or test live, then --runtime-to-permanent)
- Sub-topic: T16 (also T01, T06, T14)
- Agree: 5 of 7. Notes: a:N26, a:N27, b:N42, d:N31, c:N26, c:N40. Urls: https://www.golinuxcloud.com/firewalld-cheat-sheet/, https://www.certcrush.app/blog/how-to-pass-rhcsa-ex200-2026-8-week-study-plan, https://notes.kodekloud.com/docs/Prep-Course-Red-Hat-Certified-System-Administrator-RHCSA/Managing-Network-Configuration-and-Security/Demo-Configuring-Firewalld/page, https://dev.to/shamain_anjum/host-a-local-rpm-package-repository-on-red-hat-linux-21lb, https://github.com/1980is/rhcsa-9/blob/main/NFS%20and%20Autofs.md
- Disagree: none found
- Level: foundation
- Best story: The "five minutes later" trap: a firewall rule or IP that looks right until the grader reboots. https://open-exam-prep.com/study-guides/rhcsa/introduction/exam-facts

## TH38 Open known services with --add-service and others with --add-port=N/tcp, check the interface's zone, keep SSH open, and skip rich rules for this exam
- Sub-topic: T16 (also T11)
- Agree: 2 of 7. Notes: a:N28, a:N29, a:N30, a:N31, a:N32, d:N32, d:N33, d:N34, d:N35. Urls: https://www.golinuxcloud.com/firewalld-cheat-sheet/, https://notes.kodekloud.com/docs/Prep-Course-Red-Hat-Certified-System-Administrator-RHCSA/Managing-Network-Configuration-and-Security/Demo-Configuring-Firewalld/page
- Disagree: none found (https://www.lisenet.com/?p=5574 lists `man firewalld.richlanguage`, but in an RHCE context)
- Level: core
- Best story: none

### SELinux (T17)

## TH39 Keep SELinux enforcing; never leave it permissive or disabled to make a task work, and if you need to isolate one service use per-domain permissive
- Sub-topic: T17
- Agree: 3 of 8. Notes: b:N43, c:N41, d:N41. Urls: https://www.certcrush.app/blog/how-to-pass-rhcsa-ex200-2026-8-week-study-plan, https://github.com/1980is/rhcsa-9/blob/main/SELinux.md, https://www.redhat.com/en/blog/semanage-keep-selinux-enforcing
- Disagree: https://www.pluralsight.com/resources/blog/cloud/red-hat-exams-a-few-tips: briefly disable SELinux (setenforce 0) to see if it is the cause, re-enable, then fix.
- Level: foundation
- Best story: Panic switch: a candidate sets SELinux to permissive to fix one stubborn task and loses points on every other task, because the grader checks the mode. https://www.certcrush.app/blog/how-to-pass-rhcsa-ex200-2026-8-week-study-plan

## TH40 Test whether SELinux is the cause by switching to permissive for a moment, then turn it back on and fix properly
- Sub-topic: T17 (also T16)
- Agree: 1 of 8. Notes: d:N43. Urls: https://www.pluralsight.com/resources/blog/cloud/red-hat-exams-a-few-tips
- Disagree: https://www.certcrush.app/blog/how-to-pass-rhcsa-ex200-2026-8-week-study-plan: the grader checks the mode, so permissive is the most damaging move. https://www.redhat.com/en/blog/semanage-keep-selinux-enforcing: keep enforcing and use `semanage permissive -a <domain>` for one domain instead.
- Level: core
- Best story: none

## TH41 Fix file labels in two steps: `semanage fcontext -a -t TYPE '/dir(/.*)?'` writes the rule, `restorecon -Rv` applies it; not chcon, and watch moved files
- Sub-topic: T17 (also T09)
- Agree: 4 of 8. Notes: c:N42, c:N45, d:N36, d:N37, b:N44, d:N44. Urls: https://github.com/1980is/rhcsa-9/blob/main/SELinux.md, https://www.redhat.com/en/blog/semanage-keep-selinux-enforcing, https://www.pluralsight.com/resources/blog/cloud/red-hat-exams-a-few-tips, https://www.certcrush.app/blog/how-to-pass-rhcsa-ex200-2026-8-week-study-plan
- Disagree: none found
- Flag: the github SELinux page writes `semanage fcontext -I -C`; the option is `-l -C` (Flags 11).
- Level: core
- Best story: none

## TH42 Flip SELinux booleans persistently with `setsebool -P` (or `semanage boolean -m`), finding them with `getsebool -a` or `semanage boolean -l`
- Sub-topic: T17
- Agree: 3 of 8. Notes: c:N43, d:N39, b:N44. Urls: https://github.com/1980is/rhcsa-9/blob/main/SELinux.md, https://www.redhat.com/en/blog/semanage-keep-selinux-enforcing, https://www.certcrush.app/blog/how-to-pass-rhcsa-ex200-2026-8-week-study-plan
- Disagree: none found (https://www.redhat.com/en/blog/semanage-keep-selinux-enforcing calls `semanage boolean` the "alternate (and newer) way"; both are valid)
- Flag: `semanage boolean -I` typo for `-l` (Flags 11).
- Level: core
- Best story: none

## TH43 Label a non-default service port with `semanage port -a -t TYPE -p tcp N`, or the service fails with "cannot bind to port"
- Sub-topic: T17 (also T16)
- Agree: 3 of 8. Notes: d:N38, b:N45, c:N43, c:N7. Urls: https://www.redhat.com/en/blog/semanage-keep-selinux-enforcing, https://au.redhat.com/training/courses/ex200/, https://github.com/1980is/rhcsa-9/blob/main/SELinux.md
- Disagree: none found
- Level: core
- Best story: The "cannot bind to port" mystery: a web server on a new port that refuses to start until SELinux is told about the port. https://www.redhat.com/en/blog/semanage-keep-selinux-enforcing

## TH44 Diagnose denials with the audit log, `sealert` and `ausearch`, read the domain man pages, and list your own changes with `-l -C`
- Sub-topic: T17 (also T02)
- Agree: 4 of 8. Notes: b:N44, c:N44, d:N10, d:N40, d:N42, d:N44. Urls: https://www.certcrush.app/blog/how-to-pass-rhcsa-ex200-2026-8-week-study-plan, https://github.com/1980is/rhcsa-9/blob/main/SELinux.md, https://www.lisenet.com/?p=5574, https://www.redhat.com/en/blog/semanage-keep-selinux-enforcing
- Disagree: none found
- Flag: domain man pages may need selinux-policy-doc (Flags 18); the github SELinux page writes `-I` for `-l` (Flags 11); lisenet's man-page list mixes in RHEL 7 RHCE items (Flags 1).
- Level: core
- Best story: none

### SSH and time (T18)

## TH45 Set up key-based SSH and a chrony time client; both are named objectives
- Sub-topic: T18 (also T05)
- Agree: 1 of 2 (thin evidence). Notes: b:N46, c:N20. Urls: https://au.redhat.com/training/courses/ex200/, https://kraker.codeberg.page/rhcsa/rhcsa_synthesis/03_user_group_management/
- Disagree: none found
- Level: foundation
- Best story: none

## The big splits

1. **Containers on the exam.** https://certland.net/blog/red-hat-certified-system-administrator-rhcsa-study-guide-2026/ lists Podman (run, rootless, podman generate systemd) and says RHEL 9. https://www.certcrush.app/blog/how-to-pass-rhcsa-ex200-2026-8-week-study-plan and https://au.redhat.com/training/courses/ex200/ have no containers section and say RHEL 10. Turns on which exam version the page was written for; the official page settles it: no Podman.
2. **Documentation and internet in the exam room.** https://certland.net/blog/red-hat-certified-system-administrator-rhcsa-study-guide-2026/ says "No documentation access"; https://kraker.codeberg.page/rhcsa/rhcsa_synthesis/00_exam_overview/ says "Limited internet access". https://au.redhat.com/training/courses/ex200/ says no internet, but the documentation that ships with the product is available, backed by https://open-exam-prep.com/study-guides/rhcsa/introduction/exam-facts, https://www.certcrush.app/blog/how-to-pass-rhcsa-ex200-2026-8-week-study-plan, https://www.lisenet.com/?p=5574. Turns on careless or stale third-party summaries; the official wording settles it.
3. **Which tasks to do first.** https://www.certcrush.app/blog/how-to-pass-rhcsa-ex200-2026-8-week-study-plan and https://kraker.codeberg.page/rhcsa/rhcsa_synthesis/00_exam_overview/: quick independent tasks first, storage in one block later. https://www.pluralsight.com/resources/blog/cloud/red-hat-exams-a-few-tips: risky storage, fstab and bootloader work first, because a VM reset or unbootable box costs less early. Turns on what you fear more: running out of time, or a late breakage wiping finished work. Both agree on reading every task first (https://www.pluralsight.com/resources/blog/cloud/red-hat-exams-a-few-tips, https://www.certcrush.app/blog/how-to-pass-rhcsa-ex200-2026-8-week-study-plan, https://kraker.codeberg.page/rhcsa/rhcsa_synthesis/00_exam_overview/). Lesson writers should present it as a judgment call.
4. **Testing SELinux by switching it off.** https://www.pluralsight.com/resources/blog/cloud/red-hat-exams-a-few-tips: setenforce 0, see if the problem goes away, re-enable, fix. https://www.certcrush.app/blog/how-to-pass-rhcsa-ex200-2026-8-week-study-plan: the grader checks the mode, never go permissive. https://www.redhat.com/en/blog/semanage-keep-selinux-enforcing: stay enforcing and put one domain in permissive. Turns on whether you trust yourself to switch it back; the safe teaching is per-domain permissive or reading the AVC denial.
5. **Root reset method and ending.** https://tecmint.com/reset-forgotten-root-password-rhel-9 and https://dev.to/dhavalthakar97/linux-in-action-resetting-the-root-password-on-rhel-10-28j2: rd.break, then exit twice. https://dev.to/dhavalthakar97/linux-in-action-resetting-the-root-password-on-rhel-10-28j2: init=/bin/bash, then exec /sbin/init, pinned to RHEL 10 by the author's own choice. https://linuxtechi.com/boot-rhel-9-into-rescue-mode: rw init=/sysroot/bin/sh and reboot -f. Turns on habit, not on version; all rely on remount read-write and /.autorelabel.
6. **Pass mark and duration.** https://open-exam-prep.com/study-guides/rhcsa/introduction/exam-facts, https://www.certcrush.app/blog/how-to-pass-rhcsa-ex200-2026-8-week-study-plan, https://kraker.codeberg.page/rhcsa/rhcsa_synthesis/00_exam_overview/ and https://certland.net/blog/red-hat-certified-system-administrator-rhcsa-study-guide-2026/ give 210/300 (70%) and about 3 hours; https://www.webasha.com/blog/rhcsa-certification-course-details-syllabus-exam-career-scope%29 says Red Hat publishes neither. https://www.certcrush.app/blog/how-to-pass-rhcsa-ex200-2026-8-week-study-plan itself says the 210/300 is "widely reported" but not published. Teach as "reported", not official.
7. **SUID on scripts.** https://dev.to/austinozor/understanding-acl-and-special-permissions-in-linux-3g3h says a SUID-root script runs as root; https://www.computernetworkingnotes.com/linux-tutorials/suid-sgid-and-sticky-bit-explained.html uses a script in its SUID lab. Readers flag both: Linux ignores SUID on interpreted scripts.
8. **How to change the default target.** https://kodekloud.com/blog/linux-boot-or-change-system-into-different-operating-modes/ gives both `GRUB_DEFAULT` + `update-grub` and `systemctl set-default`; only the second is right on RHEL.
9. **What "rescue mode" means.** https://linuxtechi.com/boot-rhel-9-into-rescue-mode equates the rd.break shell with rescue, single user and emergency mode; https://kodekloud.com/blog/linux-boot-or-change-system-into-different-operating-modes/ treats rescue.target and emergency.target as distinct states. RHEL has three distinct things.
10. **Is NFS on the exam?** https://github.com/1980is/rhcsa-9/blob/main/NFS%20and%20Autofs.md says "NFS is not a part of the RHCSA exam" (meaning server setup); https://au.redhat.com/training/courses/ex200/ lists mounting NFS and configuring autofs. Client side is in scope, server side is not.
11. **Cron vs timers (soft).** https://www.centron.de/tutorials/systemd-timers-instead-of-cron frames timers as replacing cron; https://adminschoice.com/systemd-timers-vs-cron/ and https://cronuru.com/guides/systemd-timers keep cron for one-line and per-user jobs. The exam lists at, cron and timers, so all three are taught.

## Coverage gaps

Sub-topics with thin evidence (M under 3):
- **T03 Standard permissions** (2 pages, neither on permissions proper; no theme): no source teaches chmod symbolic vs octal, chown/chgrp, **umask** ("Manage default file permissions") or "diagnose and correct file permission problems", both official objectives.
- **T10 Processes, tuning and logs** (2 pages, only on the journal and timer output): nothing on **tuned profiles** (`tuned-adm`, an official objective), **nice/renice**, **top/ps/kill**, or "locate and interpret system log files" beyond journalctl -u.
- **T15 Networking** (2 pages): no **IPv6** worked example (only "same with ipv6.*"), nothing on **hostname** (`hostnamectl`) or **hostname resolution** (/etc/hosts, nsswitch).
- **T18 SSH keys and time sync** (2 pages, both one-line mentions): no recipe for `ssh-keygen` / `ssh-copy-id`, and nothing on **chrony** (/etc/chrony.conf, `chronyc sources`).

Expected by a learner but not covered by any source:
- **T02 Essential tools**: redirection, grep with regex, tar with gzip/bzip2, hard and soft links, `su`/switching users, **scp/sftp** ("securely transfer files"). Only the doc-lookup part is covered.
- **T05 Privileged access**: no sudoers / wheel recipe (`visudo`, /etc/sudoers.d drop-in), groupadd/groupdel, userdel.
- **T06 Software**: no actual **Flatpak commands** (`flatpak remote-add`, `install`, `list`, `uninstall`); nothing on installing a local .rpm or `dnf` basics beyond repolist.
- **T07 Shell scripts**: no worked script with if/test, a for loop over input and $1/$2.
- **T08 Boot**: nothing on **modifying the bootloader persistently** with `grubby` (official objective), or normal shutdown/reboot.
- **T11 Scheduling**: no **at** or crontab syntax walkthrough, only cron-to-OnCalendar mapping.
- **T12/T13 Storage**: no **GPT partitioning** (`parted`/`gdisk`), no **swap** (`mkswap`, `swapon`, fstab swap line), no **VFAT** or ext4 creation, no mounting by **LABEL**, no non-destructive add of partitions, and no persistent NFS line in /etc/fstab (`_netdev`) for the "mount at boot" case.
- **T01**: Red Hat's own objectives page is the only scope source; no page covers exam booking, remote vs test-centre delivery.
