# Lesson 5. Three Plans, One Umbrella

**Listen:** three-plans-one-umbrella.mp3 (2 min)

**The idea, in three lines**
- **Incident response** stops the attack ("how do we stop this?"). **Disaster recovery** restores IT systems and data ("how do we get back?"). **Business continuity** keeps the business running: people, processes, places.
- Business continuity is the umbrella; incident response and disaster recovery sit under it. Which one leads depends on the event: ransomware starts with IR, a fire starts with DR and BC together.
- Start with a business impact analysis (BIA), then set **RTO** (how fast it must be back) and **RPO** (how much data loss is tolerable, counted back to the last good backup). RTO must be shorter than the maximum tolerable downtime (MTD).

**Impact:** scenario questions get easier once you ask "which plan does this event fire first?"

**Who says it:** 4 of the 12 pages on business continuity and disaster recovery teach the three-plan split; none disagree. One page (cyber.gc.ca) contradicts itself on which plan is the umbrella; the ISC2 framing puts business continuity on top, so keep that.

**Try it** · Quick Win · 10 min
A mini impact analysis on paper. Pick three things your work relies on (for example email, a shared drive, your laptop). For each one:
> **1.** How long could you go without it before real damage? (your RTO)
> **2.** How much work could you lose without real harm? Hours, a day, a week? (your RPO)
> **3.** When was it last backed up? If the answer is "never" or "no idea", that's your first gap.

**Rule to keep**
Business continuity is the umbrella; incident response and disaster recovery sit under it.

**Skip** · no cost, no catch-up. Lesson 6 is just lesson 6.

**Go deeper (optional)**
- Four scenarios, which plan fires first (Prey): https://preyproject.com/blog/business-continuity-disaster-recovery-and-incident-response
- The three plans side by side (TechTarget): https://www.techtarget.com/cybersecurity/tip/Business-continuity-vs-disaster-recovery-vs-incident-response
- BIA, RTO, RPO and MTD in exam terms: https://open-exam-prep.com/blog/isc2-cc-certified-in-cybersecurity-guide-2026
