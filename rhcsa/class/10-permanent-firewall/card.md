# Lesson 10. Permanent Firewall

**Listen:** permanent-firewall.mp3 (2 min)

**The idea, in three lines**
- A plain `firewall-cmd` rule changes only the running firewall. It works now and disappears at the grader's reboot.
- The permanent flag writes the rule to the saved config but leaves the running firewall alone. A reload copies saved into running.
- So every change is two steps: add it with the permanent flag, then reload. Known services go in by name (http, nfs); anything else as a port, like 8080/tcp. Keep ssh in the list.

**Impact:** your firewall rules work right away and still work after the reboot, with no guessing about which copy you changed.

**Who says it:** 5 of the 7 pages on firewalls teach this; none disagree. A 2026 study plan: use the permanent flag followed by reload in practice "until doing it any other way feels wrong."

**Try it** · Quick Win · 10 min
On a practice VM (Rocky Linux, AlmaLinux or RHEL). Every `firewall-cmd` option starts with two hyphens; the option names are below in bold.
> **1.** `sudo firewall-cmd` with **add-service=http** (no permanent). Then `sudo firewall-cmd` with **list-services**: http is there.
> **2.** `sudo firewall-cmd` with **reload**, then **list-services** again: http is gone. It was runtime only.
> **3.** `sudo firewall-cmd` with **add-service=http** and **permanent**. Then **list-services**: not there yet.
> **4.** **reload**, then **list-services**: http is there. `sudo reboot` and list once more: still there.

Leave ssh in the list throughout. On a VM you reach over SSH, removing it locks you out.

No VM yet? On paper, write the two steps to open port 8080/tcp for good, and next to each, which copy of the firewall it changes (saved or running).

**Rule to keep**
No firewall change without the permanent flag, then a reload.

**Skip** · no cost, no catch-up. Lesson 11 is just lesson 11.

**Go deeper (optional)**
- firewalld commands on one page, permanent and reload included: https://www.golinuxcloud.com/firewalld-cheat-sheet/
- Why the permanent flag alone doesn't change the running firewall: https://notes.kodekloud.com/docs/Prep-Course-Red-Hat-Certified-System-Administrator-RHCSA/Managing-Network-Configuration-and-Security/Demo-Configuring-Firewalld/page
- The "five minutes" trap and other persistence rules: https://open-exam-prep.com/study-guides/rhcsa/introduction/exam-facts
