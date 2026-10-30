# Lesson 11. Label, Don't Disable

**Listen:** label-dont-disable.mp3 (2 min)

**The idea, in three lines**
- Keep SELinux enforcing. The grading script checks the mode, so switching to permissive for one task can cost points on every task that depends on SELinux.
- Fix file labels in two steps: `semanage fcontext -a -t TYPE '/dir(/.*)?'` writes the rule, then `restorecon -Rv /dir` applies it. The rule survives a relabel; `chcon` alone does not.
- A service on a non-default port also needs the port labelled: `semanage port -a -t TYPE -p tcp N`. Without it the service fails with an error like "cannot bind to port".

**Impact:** you fix the actual cause, and the rest of your tasks keep the enforcing mode the grader checks for.

**Who says it:** 4 of the 8 pages on SELinux teach fcontext then restorecon; none disagree. Keeping it enforcing is 3 of 8. Pluralsight (an older post) suggests switching SELinux off briefly to test, then back on to fix; certcrush answers that "the grading script checks the mode", and Red Hat's blog offers `semanage permissive -a` for a single domain instead.

**Try it** · Quick Win · 10 min
On a practice VM (Rocky Linux, AlmaLinux or RHEL), as root:
> **1.** `mkdir /web` then `ls -Zd /web`: the type is `default_t`.
> **2.** `semanage fcontext -a -t httpd_sys_content_t '/web(/.*)?'`
> **3.** `restorecon -Rv /web` then `ls -Zd /web` again: now `httpd_sys_content_t`.
> **4.** `getenforce`: still `Enforcing`.


No VM yet? On paper, write steps 2 and 3 from memory, quotes and pattern included, and next to each, what it changes (the rule, or the files).

**Rule to keep**
SELinux stays enforcing; fix the label, not the mode.

**Skip** · no cost, no catch-up. Lesson 12 is just lesson 12.

**Go deeper (optional)**
- Four semanage commands, ports and per-domain permissive included: https://www.redhat.com/en/blog/semanage-keep-selinux-enforcing
- Why permissive is the most damaging exam move: https://www.certcrush.app/blog/how-to-pass-rhcsa-ex200-2026-8-week-study-plan
- Compact RHCSA SELinux notes (use `-l` where the page writes `-I`): https://github.com/1980is/rhcsa-9/blob/main/SELinux.md
