# Lesson 4. Enable, Then Start

**Listen:** enable-then-start.mp3 (2 min)

**The idea, in three lines**
- Start runs a service now. Enable brings it back after a reboot. The grader reboots, so every service needs both.
- One command does both (`systemctl enable` with the now flag), or run `systemctl enable` then `systemctl start`. Check with `systemctl is-enabled` and `systemctl is-active`.
- The tools behind a task count too: a firewall rule needs firewalld enabled, an automount needs autofs enabled.

**Impact:** services you set up are still running after the grading reboot, not just for the five minutes after you typed the command.

**Who says it:** 5 of the 8 pages on services teach this; none disagree. One guide: a start without enable "may look correct for five minutes and fail after restart."

**Try it** · Quick Win · 5 min
On a practice VM (Rocky Linux, AlmaLinux or RHEL):
> **1.** `systemctl list-unit-files | grep enabled` to see what comes back at boot. The first state column is what counts; the last column is only the vendor default.
> **2.** `sudo systemctl disable chronyd`
> **3.** `sudo systemctl enable chronyd` then `sudo systemctl start chronyd`
> **4.** `systemctl is-enabled chronyd` and `systemctl is-active chronyd`. Both should say yes (`enabled`, `active`).
> **5.** Bonus: `systemctl is-enabled firewalld`

No VM yet? On paper, write three services you might touch in the exam (a web server, firewalld, autofs) and the two commands each one gets.

**Rule to keep**
Every service I touch gets enabled, started, and checked.

**Skip** · no cost, no catch-up. Lesson 5 is just lesson 5.

**Go deeper (optional)**
- The "five minutes" warning and persistence rules: https://open-exam-prep.com/study-guides/rhcsa/introduction/exam-facts
- Started but not enabled, in the list of five common mistakes: https://www.certcrush.app/blog/how-to-pass-rhcsa-ex200-2026-8-week-study-plan
- Enabling autofs itself, step by step: https://open-exam-prep.com/study-guides/rhcsa/filesystems-network/autofs
