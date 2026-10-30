# Lesson 7. Repo Before Packages

**Listen:** repo-before-packages.mp3 (2 min)

**The idea, in three lines**
- Every install task depends on a working repository, so one broken repo can sink several tasks at once.
- Client access is a small text file in /etc/yum.repos.d ending in `.repo`: an `[id]`, `name=`, `baseurl=` (the address you're given), `enabled=1` and a `gpgcheck=` line. Then `dnf repolist` to prove it's seen.
- Flatpak is on the RHEL 10 exam too: add a remote at the location you're given (`flatpak remote-add`), search it (`flatpak search`), install an app (`flatpak install`), list what's installed (`flatpak list`).

**Impact:** every later install task starts from a repo you've already proven works, so one mistake no longer takes several tasks down with it.

**Who says it:** 3 of the 4 pages on software repos teach this; none disagree. Flatpak practice: 2 of the 4 (Red Hat's objectives and certcrush). Red Hat lists "configure access to RPM repositories" and "configure access to Flatpak repositories" as objectives. Pluralsight's older (RHEL 7 era) tips call a broken repo a potential instant fail.

**Try it** · Quick Win · 10 min
On a practice VM (Rocky Linux, AlmaLinux or RHEL), run `sudo -i` first so every command below runs as root:
> **1.** `dnf repolist`, then `ls /etc/yum.repos.d`
> **2.** Open the file holding a repo id you saw in step 1 and read that block: the `[id]` line and the lines under it.
> **3.** Create /etc/yum.repos.d/practice.repo. Copy every line of that first block into it, then change the id to `[practice]`, the name to `name=Practice repo`, and set `enabled=1`.
> **4.** `dnf repolist` again. Look for `practice` in the list.
> **5.** Delete /etc/yum.repos.d/practice.repo and run `dnf repolist` once more.

In the exam the shape is the same, with the address you're given. A local example:
```
[practice]
name=Practice repo
baseurl=file:///mnt/repo
enabled=1
gpgcheck=0
```

No VM yet? On paper, write the five lines of a .repo file from memory, then check them against a real one later.

**Rule to keep**
dnf repolist before dnf install.

**Skip** · no cost, no catch-up. Lesson 8 is just lesson 8.

**Go deeper (optional)**
- Red Hat's EX200 objectives, including RPM and Flatpak repositories: https://au.redhat.com/training/courses/ex200/
- Why Flatpak marks current study material: https://www.certcrush.app/blog/how-to-pass-rhcsa-ex200-2026-8-week-study-plan
- A .repo file written by hand, then dnf repolist (it builds the repo with `createrepo`; on RHEL 9 and 10 the package is `createrepo_c`): https://dev.to/shamain_anjum/host-a-local-rpm-package-repository-on-red-hat-linux-21lb
