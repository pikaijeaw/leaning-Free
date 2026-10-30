# Lesson 11. Contain First

**Listen:** contain-first.mp3 (2 min)

**The idea, in three lines**
- The classic NIST SP 800-61 Rev. 2 model has four phases: Preparation; Detection and Analysis; Containment, Eradication and Recovery; Post-Incident Activity (lessons learned). Rev. 3 (April 2025) maps incident response onto the six CSF 2.0 functions; the four phases stay the common teaching model.
- Contain first, investigate second: isolate machines, disable compromised accounts, block malicious traffic, and preserve evidence. Life and safety come before all of it.
- Close the hole before you restore. Restoring from backup while the attacker still has access just reinfects you.

**Impact:** you pick "contain" over "investigate" or "restore" when an exam question asks for the first move.

**Who says it:** 5 of the 6 pages on incident response teach the four phases, and 4 of the 6 say contain before you investigate; none disagree on the order. Three of them (TCM Security, ArmorPoint, Prey) present the four phases as current NIST guidance; Consilien notes Rev. 3 retired them as the official structure in April 2025.

**Try it** · Admin · 10 min
On paper or in a phone note, write a home plan for "my email account got taken over":
> **1.** Contain: which device would you take off the network first?
> **2.** Eradicate: which passwords would you reset, and from which other device?
> **3.** Out of band: one phone number per person you'd warn, written down, in case your email or chat is what's compromised.

**Rule to keep**
Stop the bleeding, then ask how.

**Skip** · no cost, no catch-up. Lesson 12 is just lesson 12.

**Go deeper (optional)**
- The four phases, contain first, and what Rev. 3 changed: https://consilien.com/news/nist-incident-response-lifecycle-4-phases-explained
- Why restoring too early reinfects you: https://preyproject.com/blog/business-continuity-disaster-recovery-and-incident-response
- Preparation, out-of-band channels and the jump kit (it treats Rev. 2 as current): https://tcm-sec.com/nist-guidelines-for-incident-response-best-practices/
