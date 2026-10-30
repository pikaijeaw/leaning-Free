# Lesson 2. The Manual Is Allowed

**Listen:** the-manual-is-allowed.mp3 (2 min)

**The idea, in three lines**
- The exam has no internet, but Red Hat says the documentation that ships with the product is available. The man pages are your search engine for three hours.
- The four doors: `man -k <word>` to find a page by topic, section numbers like `man 5 fstab` for file formats, the help flag on most commands, and /usr/share/doc for examples.
- Finding an answer fast in the man pages is a skill. Practise it before the exam, not for the first time under pressure.

**Impact:** a forgotten option or field order stops being a lost task and becomes a thirty second lookup.

**Who says it:** 7 of the 16 pages on exam prep teach this; two guides get the rules wrong ("no documentation", "limited internet"), and Red Hat's own page settles it: no internet, shipped documentation available.

**Try it** · Quick Win · 10 min
On a practice VM (Rocky Linux, AlmaLinux or RHEL), with no browser:
> **1.** `man 5 fstab` and find the order of the six fields in an fstab line. Write them down.
> **2.** `man -k nmcli` and spot the page called `nmcli-examples`. Open it with `man nmcli-examples` and find one example that adds a connection.
> **3.** If `man -k` answers "nothing appropriate", run `sudo mandb` once and try again.

No VM yet? On paper, list the three places you would look (man, the help flag, /usr/share/doc), guess the six fstab fields, and check your guess the day you have a VM.

**Rule to keep**
Before searching the web, search the man pages.

**Skip** · no cost, no catch-up. Lesson 3 is just lesson 3.

**Go deeper (optional)**
- Red Hat's EX200 objectives, including the documentation rule: https://au.redhat.com/training/courses/ex200/
- Documentation vs. open web, from an exam-facts guide: https://open-exam-prep.com/study-guides/rhcsa/introduction/exam-facts
- The man -k and /usr/share/doc tip, in an 8-week plan: https://www.certcrush.app/blog/how-to-pass-rhcsa-ex200-2026-8-week-study-plan
