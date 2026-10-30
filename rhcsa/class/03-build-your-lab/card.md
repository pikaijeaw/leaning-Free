# Lesson 3. Build Your Lab

**Listen:** build-your-lab.mp3 (2 min)

**The idea, in three lines**
- You can't read your way through a practical exam. Learn on a live box: two VMs, one to configure and one to act as a client for NFS and SSH tasks.
- Drill each objective from a blank or broken state, time yourself, and later sit full mock exams that end with a reboot check.
- Study RHEL 10 material. Flatpak and systemd timers are in; the containers section is gone from Red Hat's objectives. If a guide never mentions Flatpak, it predates the current exam.

**Impact:** tasks move from "I've read about this" to "I've done this ten times", which is the speed the three hours ask for.

**Who says it:** 5 of the 15 pages on exam prep teach study by doing; none disagree on the method (two only argue about how hard the exam feels). On current material, 2 of the 15 teach it, Red Hat's own page among them; one guide still lists Podman, and Red Hat's page does not.

**Try it** · Deep Focus · 15 min
> **1.** Pick a free image: Rocky Linux, AlmaLinux, or RHEL through the free Red Hat developer subscription.
> **2.** Create a VM in whatever VM software you already have (2 GB of memory and a 20 GB disk is plenty to start) and begin the install.
> **3.** Name it `server`. A second VM called `client` can wait for another day.

No room for a VM today? On paper, write the plan: which machine, how much memory and disk, the two VM names, and the first three drills you'll run (for example: enable a service, add an fstab mount, open a firewall port, each followed by a reboot).

**Rule to keep**
Practice on a live box, from a blank or broken state.

**Skip** · no cost, no catch-up. Lesson 4 is just lesson 4.

**Go deeper (optional)**
- The two-VM lab, RHEL 10 changes and the "done them twice" line: https://www.certcrush.app/blog/how-to-pass-rhcsa-ex200-2026-8-week-study-plan
- Drills from a blank or broken state, and study time ranges: https://open-exam-prep.com/study-guides/rhcsa/introduction/exam-facts
- Red Hat's current objectives, worth rechecking the week you book: https://au.redhat.com/training/courses/ex200/
