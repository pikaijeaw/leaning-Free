# Notes: batch b
Pages read: 9. With notes: 9. Skipped: 0 (all on topic; webasha.com is a thin training sales page but carries a few usable claims).

Currency flags (RHEL 9/10): certland.net is written for RHEL 9 (Podman section, $400, "RHEL 9 VM") and contradicts the official RHEL 10 objectives on containers. oneuptime nmcli post was written against RHEL 9 but the commands still match the RHEL 10 "Configure IPv4 and IPv6 addresses" objective. adminschoice.com was tested on RHEL 9; timer syntax is unchanged on 10.

## T01 Exam format and how people prepare
- b:N1. Official rule: "configurations must persist after reboot without intervention." No internet, no notes or books; the documentation that ships with the product is available. Exam is based on RHEL 10.
  - Source: https://au.redhat.com/training/courses/ex200/  Quote: "configurations must persist after reboot without intervention"
  - Kind: rule of thumb
  - Level: foundation
  - Bias: none (vendor's own page)
- b:N2. The grader reboots your machine and then checks. Persistence failures, not missing knowledge, are the common fail: started but not enabled, mounted but not in fstab, firewall rule without --permanent, network change not written to the connection profile.
  - Source: https://www.certcrush.app/blog/how-to-pass-rhcsa-ex200-2026-8-week-study-plan  Quote: "a grading script reboots your machine and checks whether your configuration survived"
  - Kind: mistake
  - Level: foundation
  - Also: T11
  - Bias: sells practice exams and question banks
- b:N3. Exam day tactic: spend the first five minutes reading every task; do quick independent ones first (users, sudo rule, firewall port), take the storage chain in one uninterrupted block, check progress at 90 minutes, abandon anything stuck for 10 minutes, keep the final 20 minutes for reboot and re-verify (their claim).
  - Source: https://www.certcrush.app/blog/how-to-pass-rhcsa-ex200-2026-8-week-study-plan  Quote: "Reserve the final twenty minutes for one job and one job only"
  - Kind: technique
  - Level: core
  - Bias: sells practice exams
- b:N4. Benchmark: if you can build VG, LV, format XFS, mount and confirm it survives reboot in under six minutes without lookup you are in good shape; twenty minutes means that is where study time goes (their claim). After each mock, drill only tasks that took over eight minutes or failed the reboot check.
  - Source: https://www.certcrush.app/blog/how-to-pass-rhcsa-ex200-2026-8-week-study-plan  Quote: "in under six minutes without looking anything up"
  - Kind: test
  - Level: core
  - Also: T12
  - Bias: sells practice exams
- b:N5. Lab setup: two VMs, one to configure and one as NFS/SSH client (or one to break and recover). A free Red Hat Developer subscription covers RHEL. AlmaLinux or Rocky are close enough, but sit the final two weeks on real RHEL 10 (their claim). Certland says snapshot reset and redo is the most important practice technique.
  - Source: https://www.certcrush.app/blog/how-to-pass-rhcsa-ex200-2026-8-week-study-plan  Quote: "sit at least your final two weeks on genuine RHEL 10"
  - Kind: technique
  - Level: foundation
  - Bias: sells practice exams; second source https://certland.net/blog/red-hat-certified-system-administrator-rhcsa-study-guide-2026/ also sells question banks
- b:N6. Study budget: about 8 weeks at 8 to 10 hours a week with some Linux background; 12 to 16 weeks if new to Linux (their claim). Certland says 60 to 80 lab hours (their claim).
  - Source: https://www.certcrush.app/blog/how-to-pass-rhcsa-ex200-2026-8-week-study-plan  Quote: "budget twelve to sixteen weeks"
  - Kind: number
  - Level: foundation
  - Bias: sells practice exams
- b:N7. What changed for RHEL 10: Flatpak repositories and systemd timer units are on the official objectives; containers/Podman are not. Many 2026 third-party guides still list Podman, so check the official page the week you book.
  - Source: https://www.certcrush.app/blog/how-to-pass-rhcsa-ex200-2026-8-week-study-plan  Quote: "do not spend three weeks drilling Podman"
  - Kind: rule of thumb
  - Level: foundation
  - Also: T06, T11
  - Bias: sells practice exams (claim confirmed against https://au.redhat.com/training/courses/ex200/)
- b:N8. Format numbers: 3 hours, roughly 15 to 20 tasks, pass mark 210 of 300 "widely reported" but not published by Red Hat, $500 USD in the US, valid 3 years (their claims). Webasha says Red Hat publishes neither pass score nor duration, so aim to finish every task.
  - Source: https://www.certcrush.app/blog/how-to-pass-rhcsa-ex200-2026-8-week-study-plan  Quote: "Red Hat does not publish the 210 out of 300 pass mark"
  - Kind: number
  - Level: foundation
  - Bias: sells practice exams
- b:N9. Cascading tasks: a mistake in early storage work can break a later service task, and a typo in fstab can stop the box booting at grading time and fail many tasks at once (their claim).
  - Source: https://certland.net/blog/red-hat-certified-system-administrator-rhcsa-study-guide-2026/  Quote: "a wrong early configuration on RHCSA can invalidate several subsequent tasks"
  - Kind: mistake
  - Level: core
  - Also: T13
  - Bias: sells question banks; page is RHEL 9 era (OUTDATED: platform, $400 price, Podman domain)
- b:N10. Use the on-box docs: man -k to search, /usr/share/doc for examples, man 5 fstab for the fstab format. Practise the final week with only local docs.
  - Source: https://www.certcrush.app/blog/how-to-pass-rhcsa-ex200-2026-8-week-study-plan  Quote: "knowing that /usr/share/doc and man -k exist has saved a lot of candidates"
  - Kind: technique
  - Level: foundation
  - Also: T02
  - Bias: sells practice exams; man 5 fstab tip from https://www.webasha.com/blog/rhcsa-certification-course-details-syllabus-exam-career-scope%29 (training sales page)
- b:N11. Recertification: certifications last three years; renew by passing a current exam or moving up (RHCE requires a current RHCSA). Red Hat restructured the programme in May 2026 into five tracks, RHCSA now a Level 2 credential in Enterprise Linux (their claim).
  - Source: https://www.webasha.com/blog/rhcsa-certification-course-details-syllabus-exam-career-scope%29  Quote: "Red Hat certifications are valid for three years"
  - Kind: number
  - Level: foundation
  - Bias: training institute sales page; programme restructure claim from https://www.certcrush.app/blog/how-to-pass-rhcsa-ex200-2026-8-week-study-plan

## T02 Essential tools
- b:N12. Official essential tools list: redirection (>, >>, |, 2>), grep with regex, ssh, switching users, tar with gzip and bzip2, hard and soft links, ugo/rwx, and man, info and /usr/share/doc.
  - Source: https://au.redhat.com/training/courses/ex200/  Quote: "Locate, read, and use system documentation including man, info, and files in /usr/share/doc"
  - Kind: definition
  - Level: foundation
  - Bias: none

## T05 Users, groups and privileged access
- b:N13. Map the task wording to the flag: "password expires every N days" is chage -M; "account expires on DATE" is chage -E; "must change at next login" is chage -d 0 or passwd -e. -E (account) and -M (password) are different shadow fields.
  - Source: https://open-exam-prep.com/study-guides/rhcsa/users-groups/password-aging  Quote: "Read the task words"
  - Kind: rule of thumb
  - Level: core
  - Bias: exam prep site, free page
- b:N14. Non-interactive password set on RHEL: echo 'Pass' | passwd --stdin alice. Then verify with chage -l alice, the human readable view, instead of decoding /etc/shadow epoch day numbers.
  - Source: https://open-exam-prep.com/study-guides/rhcsa/users-groups/password-aging  Quote: "know chage -l as your primary verification tool"
  - Kind: technique
  - Level: foundation
  - Bias: exam prep site
- b:N15. /etc/shadow field order: name:hash:lastchange:min:max:warn:inactive:expire:reserved. Lastchange is days since 1970-01-01; a hash starting ! or !! means locked.
  - Source: https://open-exam-prep.com/study-guides/rhcsa/users-groups/password-aging  Quote: "name:hash:lastchange:min:max:warn:inactive:expire:reserved"
  - Kind: definition
  - Level: core
  - Bias: exam prep site
- b:N16. One line full policy: chage -d 0 -m 1 -M 30 -W 5 -I 3 -E 2026-11-30 contractor1. chage -E -1 removes account expiry. -I is grace days after the password expires before the account is disabled.
  - Source: https://open-exam-prep.com/study-guides/rhcsa/users-groups/password-aging  Quote: "-E -1 clears"
  - Kind: template
  - Level: core
  - Bias: exam prep site
- b:N17. Common traps: editing PASS_MAX_DAYS in /etc/login.defs when the task names one user (login.defs only affects new accounts); chage -d 0 without first setting a password; locking an account when only aging was asked; setting min higher than max.
  - Source: https://open-exam-prep.com/study-guides/rhcsa/users-groups/password-aging  Quote: "do not overshoot"
  - Kind: mistake
  - Level: core
  - Bias: exam prep site
- b:N18. Lock and unlock: passwd -l / -u or usermod -L / -U; passwd -S shows status. Avoid passwd -d (empty password), which can leave an account oddly accessible depending on PAM.
  - Source: https://open-exam-prep.com/study-guides/rhcsa/users-groups/password-aging  Quote: "prefer lock/expire patterns"
  - Kind: technique
  - Level: core
  - Bias: exam prep site
- b:N19. If passwd rejects a weak password (pam_pwquality, /etc/security/pwquality.conf), pick a longer mixed password and retry; never disable PAM on the exam.
  - Source: https://open-exam-prep.com/study-guides/rhcsa/users-groups/password-aging  Quote: "Do not disable PAM system-wide on the exam"
  - Kind: mistake
  - Level: core
  - Bias: exam prep site
- b:N20. Users and groups are "quick marks": users with specific UIDs, chage aging, supplementary groups, shared group directory with setgid, sudo rule for a user or group.
  - Source: https://www.certcrush.app/blog/how-to-pass-rhcsa-ex200-2026-8-week-study-plan  Quote: "Users and groups are quick marks"
  - Kind: rule of thumb
  - Level: foundation
  - Also: T04
  - Bias: sells practice exams

## T06 Software
- b:N21. Official objectives now include "Configure access to Flatpak repositories" and installing/removing Flatpak packages, alongside RPM repositories. Practise adding a remote, searching it, installing an app and listing installed apps.
  - Source: https://au.redhat.com/training/courses/ex200/  Quote: "Configure access to Flatpak repositories"
  - Kind: definition
  - Level: core
  - Bias: none; practice steps from https://www.certcrush.app/blog/how-to-pass-rhcsa-ex200-2026-8-week-study-plan
- b:N22. Test for stale material: "If your study material never mentions Flatpak, it predates the current exam."
  - Source: https://www.certcrush.app/blog/how-to-pass-rhcsa-ex200-2026-8-week-study-plan  Quote: "If your study material never mentions Flatpak, it predates the current exam"
  - Kind: test
  - Level: foundation
  - Also: T01
  - Bias: sells practice exams

## T07 Shell scripts
- b:N23. Scripting is kept deliberately simple: if/test, for loops, $1 $2, command substitution. Write three or four small scripts that take an argument and act on a list of inputs (their claim).
  - Source: https://www.certcrush.app/blog/how-to-pass-rhcsa-ex200-2026-8-week-study-plan  Quote: "the exam keeps deliberately simple"
  - Kind: technique
  - Level: foundation
  - Bias: sells practice exams

## T08 Boot process and targets
- b:N24. Boot recovery tasks (root password reset, rescue target, fixing a broken fstab entry) "take three minutes once you have done them ten times. Most candidates have done them twice." Certland target: root reset under 3 minutes.
  - Source: https://www.certcrush.app/blog/how-to-pass-rhcsa-ex200-2026-8-week-study-plan  Quote: "Most candidates have done them twice"
  - Kind: rule of thumb
  - Level: core
  - Also: T09
  - Bias: sells practice exams

## T10 Processes, tuning and logs
- b:N25. Default journal storage may be /run/log/journal (tmpfs), wiped every reboot. With the default Storage=auto, journald goes persistent only if /var/log/journal exists.
  - Source: https://oneuptime.com/blog/post/2026-03-04-configure-persistent-journald-storage-on-rhel/view  Quote: "Storage=auto -> persistent if /var/log/journal/ exists"
  - Kind: definition
  - Level: core
  - Bias: vendor blog (monitoring product), mild
- b:N26. Make the journal persistent: drop-in /etc/systemd/journald.conf.d/persistent.conf with [Journal] Storage=persistent, mkdir -p /var/log/journal, systemd-tmpfiles --create --prefix /var/log/journal, systemctl restart systemd-journald. Verify with journalctl --list-boots and journalctl -b -1.
  - Source: https://oneuptime.com/blog/post/2026-03-04-configure-persistent-journald-storage-on-rhel/view  Quote: "Or use a drop-in configuration (recommended)"
  - Kind: template
  - Level: core
  - Bias: vendor blog, mild
- b:N27. Size controls: SystemMaxUse=, SystemMaxFileSize=, SystemKeepFree=, MaxRetentionSec=; manual cleanup with journalctl --vacuum-size=500M or --vacuum-time=14d.
  - Source: https://oneuptime.com/blog/post/2026-03-04-configure-persistent-journald-storage-on-rhel/view  Quote: "journalctl --vacuum-time=14d"
  - Kind: technique
  - Level: advanced
  - Bias: vendor blog, mild

## T11 Services and scheduling
- b:N28. A timer is two files: .service says what, .timer says when; matching base names link them (or set Unit=). The service needs no [Install] section; the timer has WantedBy=timers.target.
  - Source: https://www.centron.de/tutorials/systemd-timers-instead-of-cron  Quote: "It only says when; the service says what"
  - Kind: definition
  - Level: core
  - Bias: cloud hosting vendor tutorial (sells VMs)
- b:N29. Template: backup.service with [Service] Type=oneshot, ExecStart=/usr/local/bin/backup.sh; backup.timer with [Timer] OnCalendar=*-*-* 02:00:00, Persistent=true, [Install] WantedBy=timers.target. Then systemctl daemon-reload and systemctl enable --now backup.timer.
  - Source: https://adminschoice.com/systemd-timers-vs-cron/  Quote: "Enable the timer (not the service)"
  - Kind: template
  - Level: core
  - Bias: ad-supported site
- b:N30. Most common mistake: enabling the .service instead of the .timer. The persistence comes from the symlink in timers.target.wants/ created by enable.
  - Source: https://www.centron.de/tutorials/systemd-timers-instead-of-cron  Quote: "Enabling the service instead of the timer is the single most common mistake"
  - Kind: mistake
  - Level: core
  - Bias: hosting vendor
- b:N31. Never guess OnCalendar: systemd-analyze calendar "Mon..Fri 07:00" prints the next elapse; a bad expression prints "Failed to parse calendar specification".
  - Source: https://www.centron.de/tutorials/systemd-timers-instead-of-cron  Quote: "Never guess an expression"
  - Kind: test
  - Level: core
  - Bias: hosting vendor
- b:N32. Cron to OnCalendar mapping: 30 2 * * * is *-*-* 02:30:00; */10 * * * * is *:0/10; 0 3 * * 0 is Sun *-*-* 03:00:00; @daily is daily; @reboot is OnBootSec=5min. Format is DayOfWeek Year-Month-Day Hour:Minute:Second.
  - Source: https://www.centron.de/tutorials/systemd-timers-instead-of-cron  Quote: "The five cron fields map directly onto OnCalendar"
  - Kind: template
  - Level: core
  - Bias: hosting vendor
- b:N33. Verify: systemctl list-timers shows NEXT, LEFT, LAST and ACTIVATES. NEXT showing n/a means loaded but not armed (not enabled, or all OnCalendar times in the past). Test the job now with systemctl start backup.service; read output with journalctl -u backup.service.
  - Source: https://www.centron.de/tutorials/systemd-timers-instead-of-cron  Quote: "A NEXT column showing n/a means the timer is loaded but not armed"
  - Kind: test
  - Level: core
  - Bias: hosting vendor
- b:N34. Persistent=true: if the machine was off at trigger time, the job runs once at next boot (once, not once per missed interval). Cron simply skips it.
  - Source: https://adminschoice.com/systemd-timers-vs-cron/  Quote: "A cron job in the same situation is simply skipped"
  - Kind: definition
  - Level: core
  - Bias: ad-supported site
- b:N35. Monotonic alternative: OnBootSec=10min plus OnUnitActiveSec=15min runs 10 minutes after boot then 15 minutes after each activation. When migrating, remove the crontab line or the job runs twice.
  - Source: https://www.centron.de/tutorials/systemd-timers-instead-of-cron  Quote: "Leaving both in place means the job runs twice per night"
  - Kind: mistake
  - Level: advanced
  - Bias: hosting vendor
- b:N36. When cron is still right: simple one-line job, portability to non-systemd Unix, team already knows crontab. The exam lists at, cron and systemd timers; build one job all three ways.
  - Source: https://adminschoice.com/systemd-timers-vs-cron/  Quote: "Timers aren't always better"
  - Kind: rule of thumb
  - Level: foundation
  - Bias: ad-supported site; three-ways drill from https://www.certcrush.app/blog/how-to-pass-rhcsa-ex200-2026-8-week-study-plan
- b:N37. Units run with a minimal environment (fixed PATH, no shell profile, no cd to home): a script that works in your shell can fail in the unit. Use absolute paths.
  - Source: https://www.centron.de/tutorials/systemd-timers-instead-of-cron  Quote: "The script works in your shell but fails in the unit"
  - Kind: mistake
  - Level: advanced
  - Also: T07
  - Bias: hosting vendor

## T12 Local storage
- b:N38. Storage chain (partition, PV, VG, LV, mkfs, mount, fstab) is the biggest time sink and appears on "almost every" exam; errors stay invisible until the grading reboot. Practise lvextend -r, which grows the filesystem with the LV. XFS cannot shrink; ext4 can (their claims).
  - Source: https://certland.net/blog/red-hat-certified-system-administrator-rhcsa-study-guide-2026/  Quote: "The LVM workflow appears on almost every RHCSA exam"
  - Kind: rule of thumb
  - Level: core
  - Also: T13
  - Bias: sells question banks; RHEL 9 era page

## T15 Networking
- b:N39. Static IPv4 in one command: nmcli connection modify ens192 ipv4.method manual ipv4.addresses 192.168.1.100/24 ipv4.gateway 192.168.1.1 ipv4.dns "8.8.8.8,8.8.4.4" connection.autoconnect yes, then nmcli connection up ens192. IPv6 is the same with ipv6.* properties.
  - Source: https://oneuptime.com/blog/post/2026-03-04-configure-static-ip-addresses-rhel-9-nmcli/view  Quote: "modify the connection properties, then bring the connection up"
  - Kind: template
  - Level: core
  - Bias: vendor blog, mild; written against RHEL 9, still valid for RHEL 10
- b:N40. Pitfalls: setting an address but leaving method auto gives you DHCP plus your static (two addresses); changes from modify do not apply until connection up or reboot.
  - Source: https://oneuptime.com/blog/post/2026-03-04-configure-static-ip-addresses-rhel-9-nmcli/view  Quote: "you might end up with two addresses on the interface"
  - Kind: mistake
  - Level: core
  - Bias: vendor blog, mild
- b:N41. Profiles are keyfiles in /etc/NetworkManager/system-connections/*.nmconnection; nmcli -f NAME,FILENAME connection show shows which file. Verify with ip addr, ip route show default, cat /etc/resolv.conf.
  - Source: https://oneuptime.com/blog/post/2026-03-04-configure-static-ip-addresses-rhel-9-nmcli/view  Quote: "stores persistent connection profiles as keyfiles"
  - Kind: test
  - Level: core
  - Bias: vendor blog, mild

## T16 Firewall
- b:N42. Every practice firewall change: --permanent then --reload, "until doing it any other way feels wrong." A rule without --permanent vanishes at the grading reboot.
  - Source: https://www.certcrush.app/blog/how-to-pass-rhcsa-ex200-2026-8-week-study-plan  Quote: "until doing it any other way feels wrong"
  - Kind: rule of thumb
  - Level: foundation
  - Bias: sells practice exams

## T17 SELinux
- b:N43. Most damaging move: setting SELinux to permissive or disabled to make a task work. The grader checks the mode, so it costs points across every SELinux-dependent task (their claim).
  - Source: https://www.certcrush.app/blog/how-to-pass-rhcsa-ex200-2026-8-week-study-plan  Quote: "The grading script checks the mode"
  - Kind: mistake
  - Level: foundation
  - Bias: sells practice exams
- b:N44. One loop: diagnose with ausearch or sealert, fix with semanage fcontext plus restorecon or setsebool -P, verify, move on. Drill: break a web server with a wrong context and fix it without disabling SELinux, five times.
  - Source: https://www.certcrush.app/blog/how-to-pass-rhcsa-ex200-2026-8-week-study-plan  Quote: "Diagnose, fix, verify, move on"
  - Kind: technique
  - Level: core
  - Bias: sells practice exams
- b:N45. Official SELinux objectives include managing SELinux port labels, besides modes, contexts, restorecon and booleans.
  - Source: https://au.redhat.com/training/courses/ex200/  Quote: "Manage SELinux port labels"
  - Kind: definition
  - Level: core
  - Bias: none

## T18 SSH keys and time sync
- b:N46. Official objectives include "Configure key-based authentication for SSH" and "Configure time service clients"; plan practises chrony and SSH keys between two lab VMs.
  - Source: https://au.redhat.com/training/courses/ex200/  Quote: "Configure key-based authentication for SSH"
  - Kind: definition
  - Level: foundation
  - Bias: none

## Disagreements seen
- Containers: certland lists Podman (run, rootless, podman generate systemd) as a domain; certcrush and the official RHEL 10 objectives have no containers section. Certland is RHEL 9 era. https://certland.net/blog/red-hat-certified-system-administrator-rhcsa-study-guide-2026/ vs https://www.certcrush.app/blog/how-to-pass-rhcsa-ex200-2026-8-week-study-plan and https://au.redhat.com/training/courses/ex200/
- Platform: certland says RHEL 9; official page, certcrush and webasha say RHEL 10. Same urls as above plus https://www.webasha.com/blog/rhcsa-certification-course-details-syllabus-exam-career-scope%29
- Cost: about $400 (certland) vs $500 US (certcrush). https://certland.net/blog/red-hat-certified-system-administrator-rhcsa-study-guide-2026/ vs https://www.certcrush.app/blog/how-to-pass-rhcsa-ex200-2026-8-week-study-plan
- Objectives and docs: certland says Red Hat publishes no tidy objective list and has a heading "No documentation access"; the official page lists detailed study points and says shipped documentation is available. https://certland.net/blog/red-hat-certified-system-administrator-rhcsa-study-guide-2026/ vs https://au.redhat.com/training/courses/ex200/
- Pass mark and duration: certland states 70% and certcrush 210/300 as fact-like; webasha says Red Hat publishes neither score nor duration. https://www.webasha.com/blog/rhcsa-certification-course-details-syllabus-exam-career-scope%29

## Best stories
- The grading reboot: you walk out feeling good, the script reboots the box, and the service you started but never enabled, the mount not in fstab, the firewall rule without --permanent all quietly fail. https://www.certcrush.app/blog/how-to-pass-rhcsa-ex200-2026-8-week-study-plan
- Panic switch: a candidate sets SELinux to permissive to fix one stubborn task and loses points on every other task, because the grader checks the mode. https://www.certcrush.app/blog/how-to-pass-rhcsa-ex200-2026-8-week-study-plan
- The timer that never fired: someone enables backup.service instead of backup.timer, list-timers shows NEXT n/a, and the backup never runs. https://www.centron.de/tutorials/systemd-timers-instead-of-cron
- Machine off at 2am: cron silently skips the backup; a timer with Persistent=true runs it once on next boot. https://adminschoice.com/systemd-timers-vs-cron/
- Vanishing logs: you reboot to chase a crash and the evidence is gone because the journal lived in tmpfs under /run. https://oneuptime.com/blog/post/2026-03-04-configure-persistent-journald-storage-on-rhel/view
