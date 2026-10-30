# Lesson plan: ISC2 Certified in Cybersecurity (CC), beginner

12 lessons in 3 arcs of 4, about 2 minutes each. Built from 37 free pages (research/agreement-map.md), following the CC outline in force since 1 September 2026: Security Principles 24%, Security Governance 17.3%, IAM Concepts 20%, Networking and Cloud Security 21.3%, Security Operations and Incident Response 17.3%, with AI in every domain. The official ISC2 outline page and PDF could not be saved; weights come from pages that quote it. Agreement reads "N of the M pages on this sub-topic teach it".

Try-its are free and need no lab: paper, your own accounts, a phone.

## Arc 1. How security thinks
Why this arc: the CC tests judgment more than tools. Finish: you can say which leg of CIA a control protects, how a risk was treated, and which answer a manager would pick.

### L1. Three Legs
- Agree: 5 of the 5 pages on principles (TH07). Flag: confidentiality is not the same as privacy (privacy is its own principle).
- Idea: confidentiality (only the right people see it), integrity (it hasn't been changed), availability (it's there when needed). Every control protects at least one leg, and context decides which matters most.
- Story: one email, three legs (Coursera); OT and industrial systems put availability first, because a breach can cause injury or loss of life (Canadian Centre for Cyber Security).
- Try it: Quick Win, 10 min. Pick three things you use daily; for each, write which leg would hurt most if it failed.
- Rule: For every control, name the leg it protects.

### L2. Name the Treatment
- Agree: risk = likelihood x impact 4 of 6 (TH09); four treatments 3 of 6 (TH10).
- Idea: avoid, mitigate, transfer, accept. Accept only in writing; transfer moves cost, never accountability.
- Story: deleting a forgotten feature and its unused personal data removes the risk entirely (Stacker).
- Rule: Transfer moves the bill, not the blame.

### L3. Layers That Assume Failure
- Agree: control types and functions 5 of 6 (TH11); defense in depth 3 of 6 (TH12). Flags: IDS doesn't block; cryptography is a technical control.
- Idea: physical, technical, administrative; each layer assumes the one before it failed.
- Story: one phishing email traced through every layer (CyberDefenders).
- Rule: No control stands alone.

### L4. Think Like a Manager
- Agree: manager mindset 5 of 9 (TH05); canons in order 3 of 4 (TH14).
- Idea: the best first answer is usually policy, risk or process; when ethics canons conflict, the earlier one wins.
- Story: the contractor still holding admin rights three months later (certcrush); using exam dumps breaks the very Code you are tested on (a prep site, examcert; not cited on the card because its exam facts are outdated).
- Rule: Ask what a manager would do first, not what an engineer would type.

## Arc 2. Plans and people
Why this arc: governance and identity are over a third of the exam. Finish: you can tell the three plans apart and run an account from hire to exit.

### L5. Three Plans, One Umbrella
- Agree: 4 of 12 (TH17, TH18), none disagree on the split. Flag: cyber.gc.ca contradicts itself; BCP is the umbrella.
- Idea: incident response handles the attack, disaster recovery restores IT, business continuity keeps the business running. BIA first, then RTO and RPO.
- Story: ransomware vs office fire vs phishing click vs hurricane, which plan fires first (Prey).
- Rule: Business continuity is the umbrella; IR and DR sit under it.

### L6. Two Different Factors
- Agree: MFA categories 4 of 7 (TH21); long passwords, slow hashes, no forced resets 3 of 7 (TH22). Flag: forced 90-day resets are outdated advice.
- Idea: know, have, are; two from the same category is not MFA; authentication is not authorization.
- Rule: Two factors means two different kinds.

### L7. Joiners, Movers, Leavers
- Agree: identity lifecycle 6 of 8 (TH25); least privilege and separation of duties 4 of 8 (TH24).
- Idea: give the least access, split create from approve, review access, remove it promptly.
- Story: accounts payable clerks create, supervisors approve (Twingate); the leftover contractor (certcrush).
- Rule: Access ends the day the need ends.

### L8. Who Owns the Cloud Mess
- Agree: 4 of 5 (TH32).
- Idea: IaaS, PaaS, SaaS shift work to the provider, but the customer always owns its data, identities and configuration.
- Story: the PaaS customer with a weak password whose breach was their own (TechTarget).
- Rule: In any cloud, my data and my logins are mine to protect.

## Arc 3. Networks, crypto, incidents, AI
Why this arc: the operations side and the new AI material. Finish: you can explain detect vs block, lock vs fingerprint, contain-first, and why an AI bot is an identity.

### L9. Detect or Block
- Agree: IDS vs IPS and firewalls 3 of 6 (TH30); segmentation 4 of 6 (TH31). Flag: sources that say an IDS blocks are wrong.
- Idea: an IDS watches and alerts, an IPS sits inline and blocks; segment the network so one bad host stays contained.
- Rule: Detecting isn't stopping.

### L10. Lock or Fingerprint
- Agree: encryption 3 of 3 (TH33); hashing 3 of 3 (TH34). Flags: hashing is not a cipher; DES is obsolete; passwords need slow hashes.
- Idea: encryption is a lock you can open with a key; a hash is a one-way fingerprint for integrity.
- Story: hello123 vs hello124 give completely different digests (20i).
- Rule: Encrypt to hide, hash to prove nothing changed.

### L11. Contain First
- Agree: 5 of 6 (TH36, TH37); contain before investigate 4 of 6 (TH38). Flag: the four-phase NIST model is the classic Rev. 2 model; Rev. 3 (April 2025) maps IR onto CSF 2.0.
- Idea: preparation, detection and analysis, containment eradication recovery, lessons learned; contain before you investigate, close the hole before restoring.
- Story: the ransomware note while the firewall expert is on a plane (Consilien).
- Rule: Stop the bleeding, then ask how.

### L12. AI Is Another Identity
- Agree: AI across the domains 4 of 5 (TH43); AI governance 4 of 5 (TH45). Flag: use the 2025 OWASP LLM list, not 2023.
- Idea: poisoned training data is an integrity failure; AI service accounts get least privilege; keep sensitive data out of public AI tools.
- Story: over 2,000 "AI" browser extensions (Cloud Security Alliance); the poisoned image classifier (open-exam-prep).
- Rule: Every AI tool gets the same rules as any other user.

## Splits (decisions, not lessons)
- Old vs new outline: pages written before 1 September 2026 teach the old domains and "100 questions". The class follows the new outline.
- Free exam: closed to new enrolments 20 May 2026; now $199 plus $50 a year (several pages agree).
- Delivery: test centre only vs online proctoring also. Unresolved; check ISC2 when booking.
- Value: CC first vs go straight to Security+. Turns on background and target job postings.
- MFA factor count: classic three vs five types.

## Coverage gaps
Not in these 12: ports and the OSI model, malware types, policy hierarchy, laws vs standards, data lifecycle and destruction, exam format and cost. Thin in sources: non-repudiation and privacy, social engineering variants, cloud deployment models, logging and SIEM, security testing, threat intelligence. A fourth arc can cover these.

## Delivery
Lesson 1 first as a sample, then the rest once approved. Audio waits for ElevenLabs credits; scripts and cards come first.
