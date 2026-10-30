# Lesson 3. Layers That Assume Failure

**Listen:** layers-that-assume-failure.mp3 (2 min)

**The idea, in three lines**
- Three control types: **physical** (locks, badges, guards, cameras), **technical** (firewalls, encryption, MFA, endpoint detection), **administrative** (policies, training, hiring and offboarding).
- **Defense in depth:** stack layers so each one assumes the layer before it has already failed.
- Test any control by asking what catches the attack if it's bypassed. If nothing does, it's a single point of failure.

**Impact:** you stop looking for the one perfect control and start checking what sits behind each one.

**Who says it:** 5 of the 6 pages on controls teach the three types, and 3 of the 6 teach layering this way; none disagree on the idea. One learner's blog files cryptography under physical controls; cryptography is a technical control.

**Try it** · Quick Win · 10 min
On paper, pick one thing you protect (your email account works well). List every layer guarding it: password, MFA, new sign-in alerts, recovery codes, anything else. For each one:
> **1.** Physical, technical or administrative?
> **2.** If this layer fails, what catches the attacker next?
> **3.** If the answer is "nothing", circle it. That's your weak spot.

**Rule to keep**
No control stands alone.

**Skip** · no cost, no catch-up. Lesson 4 is just lesson 4.

**Go deeper (optional)**
- One phishing email traced through every layer, and the single point of failure test (CyberDefenders): https://cyberdefenders.org/cybersecurity-glossary/defense-in-depth/
- Defense in depth explained, with the three control types (CSO Online): https://www.csoonline.com/article/3667476/defense-in-depth-explained-layering-tools-and-processes-for-better-security.html
