# Lesson 5. Groups and Aging

**Listen:** groups-and-aging.mp3 (2 min)

**The idea, in three lines**
- `usermod -aG group user` appends a supplementary group. Without the `a`, `-G` replaces all of the user's supplementary groups. usermod takes one user per command.
- Group changes reach a new login, not a session that is already open. Log out and back in before testing, or the test says "permission denied".
- Password aging is `chage`: `-M` max days, `-m` min days, `-W` warning days, `-E` account expiry date, `-d 0` forces a new password at next login. Check with `chage -l`.

**Impact:** group tasks pass on the first test, and aging tasks match the exact words of the task.

**Who says it:** 3 of the 9 pages on users and groups teach each half (groups, aging); none disagree. One aging guide warns that account expiry (`-E`) and maximum password age (`-M`) are easy to mix up.

**Try it** · Quick Win · 10 min
On a practice VM (Rocky Linux, AlmaLinux or RHEL):
> **1.** `sudo groupadd team` and `sudo useradd alice`
> **2.** `sudo usermod -aG team alice` then `id alice`. The list now includes `team`.
> **3.** `sudo chage -M 90 -W 7 alice`
> **4.** `sudo chage -l alice` and read back the maximum and warning lines.

No VM yet? On paper, write five task sentences ("password expires after 90 days", "account expires on 31 December", "warn 7 days before", "change password at first login", "at least 2 days between changes") and the chage flag for each.

**Rule to keep**
`-aG`, never bare `-G`.

**Skip** · no cost, no catch-up. Lesson 6 is just lesson 6.

**Go deeper (optional)**
- chage, flag by flag: https://open-exam-prep.com/study-guides/rhcsa/users-groups/password-aging
- Group troubleshooting, including the re-login cause (some commands there are dated; its troubleshooting section holds): https://kraker.codeberg.page/rhcsa/rhcsa_synthesis/03_user_group_management/
- Users and groups as quick marks, in an 8-week plan: https://www.certcrush.app/blog/how-to-pass-rhcsa-ex200-2026-8-week-study-plan
