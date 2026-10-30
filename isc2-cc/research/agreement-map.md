# Agreement map: ISC2 Certified in Cybersecurity (CC), beginner

Built 2026-10-30 from research/notes/a.md, b.md, c.md, d.md (37 pages with notes) against research/topics.md.
Current exam: outline effective 1 September 2026, five domains (Security Principles 24%, Security Governance 17.3%, IAM Concepts 20%, Networking and Cloud Security Concepts 21.3%, Security Operations and Incident Response 17.3%), AI threaded through all five. The free One Million CC program closed to new enrolments on 20 May 2026 (unexpired codes must be used by 31 December 2026); the exam is US$199 plus US$50 a year.

M per sub-topic (distinct pages with any note on it, including `Also:` lines): T01 9, T02 5, T03 6, T04 6, T05 4, T06 7, T07 12, T08 7, T09 8, T10 3, T11 4, T12 6, T13 5, T14 3, T15 4, T16 6, T17 4, T18 5. No sub-topic falls under M=3, so no theme is marked thin evidence; T10 and T14 sit exactly at 3.

## Flags: never repeat these in a lesson

Each item below also appears as a `Flag:` line on the affected theme.

1. **Old domains and weights.** examcert.app, trainingcamp.com and the stephenbernardombacisa substack use the pre-September 2026 outline (Security Principles 26%, BC/DR/IR 10%, Access Controls 22%, Network Security 24%, Security Operations 18%, or "Domain 4 - Network Security"). Teach only 24 / 17.3 / 20 / 21.3 / 17.3 with the new domain names. (TH01)
2. **"100 multiple-choice questions" as a fixed paper.** examcert.app says this. The exam is adaptive (CAT), 100 to 125 items. (TH02)
3. **The AI fold-in dated "late 2025".** examcert.app says this. Tie AI to the 1 September 2026 outline. (TH01, TH43)
4. **"Don't overinvest in the 10% BC/DR/IR domain."** examcert.app's study plan says this. There is no small domain left. (TH01)
5. **Free exam claims.** The substack (March 2025) says registering gets you free training and a free exam. One Million CC closed to new enrolments on 20 May 2026. Only people who already hold an unexpired code can still test free, and only until 31 December 2026. (TH03)
6. **NIST SP 800-61 Rev. 2's four phases presented as current NIST guidance.** tcm-sec.com, armorpoint.com, preyproject.com and cyber.gc.ca do this. Rev. 3 (April 2025) replaced it with a mapping to the CSF 2.0 functions. Call the four phases "the classic Rev. 2 model". (TH36, TH37, TH38, TH39)
7. **Forced 90-day password resets as good practice.** informationshield.com uses this as its model technical control. It conflicts with NIST SP 800-63B, which drops forced periodic rotation unless there is a sign of compromise. Use it only as an example of what a technical control is, never as password advice. (TH15, TH22)
8. **IDS described as blocking.** csoonline.com says "a firewall or IDS to try to block attacks". heimdalsecurity.com describes IDS/IPS as DNS query filtering. An IDS detects and alerts; an IPS sits inline and blocks. (TH12, TH13, TH30)
9. **Hashing called a cipher.** heimdalsecurity.com does this. Hashing is one-way, has no key and is not encryption. (TH34)
10. **RSA for stored data.** heimdalsecurity.com suggests RSA for encryption at rest. Bulk data at rest uses symmetric encryption (AES); RSA protects keys and signs. (TH33)
11. **DES as a "common" cipher.** rippling.com lists DES beside AES without saying it is obsolete and insecure. (TH33)
12. **Switches at OSI Layer 1.** dev.to says this. Switches work at Layer 2 (MAC addresses); routers work at Layer 3. (TH26)
13. **Cryptography and IAM called physical controls.** The substack says this. They are technical (logical) controls. (TH11)
14. **PAM as one of the four access control models.** twingate.com says this, calls PAM a type of RBAC, and leaves out ABAC. The models are DAC, MAC, RBAC and ABAC, plus rule-based. PAM is a practice for privileged accounts. (TH23, TH24)
15. **Confidentiality equated with privacy.** coursera.org says "think of confidentiality as privacy". The outline treats privacy as a separate principle: an individual's right to control their personal data. (TH07, TH08)
16. **cyber.gc.ca contradicts itself on BCP vs DRP.** In one place it says the DRP is the umbrella and the BCP is a subset of it; its summary says the BCP is the umbrella. Teach BCP as the umbrella (the ISC2 framing), with DR as the IT-restoration part. (TH17)
17. **The 2023 OWASP Top 10 for LLM applications.** cloudsecurityalliance.org (Tenable) presents the 2023 list. The 2025 list renames and replaces several entries (data and model poisoning, system prompt leakage, vector and embedding weaknesses, misinformation, unbounded consumption). (TH44)
18. **Salted SHA-256 for passwords.** 20i.com shows this example right after saying SHA-256 is too fast for passwords. Store passwords with a unique salt and a slow password hash (bcrypt, Argon2). (TH22, TH34)
19. **Online vs test-centre delivery is unresolved.** certcrush.app says Pearson VUE test centre or online proctoring. cyberexperts.com and pocketprep.com mention only test centres. No ISC2 page on delivery is on disk. Say "check ISC2's current scheduling page"; don't state either option as fact. (TH02)
20. Smaller slips to avoid. heimdalsecurity.com says a VPN "protects against external cyberattacks" (a VPN encrypts the tunnel; it doesn't stop malware or phishing). armorpoint.com's 277-day breach figure comes from an older IBM report (consilien.com quotes 241 days for 2025). isdecisions.com calls biometrics hard to replicate without noting that a leaked biometric can't be changed. osu.edu's research-data lifecycle is not the security data lifecycle. (TH13, TH21, TH35, TH41)

---

## TH01 Study the current 1 September 2026 outline (five domains, AI in all of them), use it to spot outdated material, and skip no domain
- Sub-topic: T01 (also T07, T18)
- Agree: 5 of 9. Notes: a:N1, a:N2, a:N3, a:N4, a:N56, b:N1, b:N2, b:N3, b:N13, b:N14, b:N33, c:N3, c:N4, c:N5. Urls: https://www.certcrush.app/blog/isc2-cc-exam-changes-2026-sit-before-september-1, https://open-exam-prep.com/blog/isc2-cc-certified-in-cybersecurity-guide-2026, https://www.certcrush.app/blog/isc2-cc-domains-2026-new-exam-outline-weightings, https://www.certcrush.app/blog/how-to-pass-isc2-cc-2026-4-week-study-plan, https://www.pocketprep.com/posts/isc2-cc-exam-blueprint-subjects-official-resources-and-faqs/
- Disagree: https://www.examcert.app/blog/isc2-cc-worth-it/: old domains and weights (26/10/22/24/18), AI added "late 2025", "BC/DR/IR 10%, do not overinvest". https://trainingcamp.com/articles/isc2-cc-certification-guide-2026-exam-domains-cost-and-what-its-worth/: old domain table (the page itself tells post-September testers to pull the new outline). https://stephenbernardombacisa.substack.com/p/reflections-and-tips-for-passing: old "Domain 4 - Network Security" naming.
- Level: foundation
- Flag: Teach only 24 / 17.3 / 20 / 21.3 / 17.3 under the new names. BC/DR now sits in Security Governance under "redundancy", IR in Domain 5, cloud in Domain 4. The old weights, the "late 2025" AI date and "skim the 10% domain" are all outdated. Any table that doesn't total about 100% is wrong.
- Best story: "There is no longer a 10% domain you can afford to skim": the gap between the biggest and smallest domain fell from 16 points to under 7. https://www.certcrush.app/blog/isc2-cc-exam-changes-2026-sit-before-september-1

## TH02 Expect an adaptive exam: 100 to 125 items in 2 hours, pass at 700 of 1000 scaled, no going back
- Sub-topic: T01
- Agree: 6 of 9. Notes: a:N5, b:N4, b:N5, b:N11, c:N1, c:N5, d:N4. Urls: https://open-exam-prep.com/blog/isc2-cc-certified-in-cybersecurity-guide-2026, https://www.certcrush.app/blog/how-to-pass-isc2-cc-2026-4-week-study-plan, https://www.certcrush.app/blog/isc2-cc-domains-2026-new-exam-outline-weightings, https://cyberexperts.com/isc2-cc-exam/, https://www.pocketprep.com/posts/isc2-cc-exam-blueprint-subjects-official-resources-and-faqs/, https://trainingcamp.com/articles/isc2-cc-certification-guide-2026-exam-domains-cost-and-what-its-worth/
- Disagree: https://www.examcert.app/blog/isc2-cc-worth-it/: "100 multiple-choice questions" (a fixed paper). Delivery: https://www.certcrush.app/blog/how-to-pass-isc2-cc-2026-4-week-study-plan says test centre or online proctoring; https://cyberexperts.com/isc2-cc-exam/ lists Pearson VUE test centres only.
- Level: foundation
- Flag: Never say "100 fixed questions". A scaled 700 is not 70% of the questions, and ending at 100 items says nothing about pass or fail. Online vs test-centre delivery is unresolved (no ISC2 page on disk), so don't state it either way.
- Best story: none

## TH03 Budget US$199 for the exam plus US$50 a year to keep it; the free One Million CC route is closed, and passing starts a nine-month clock
- Sub-topic: T01 (also T05)
- Agree: 6 of 9. Notes: a:N6, a:N7, b:N6, b:N7, c:N2, d:N1, d:N5, d:N11, d:N14; batch a flag header (certcrush.app). Urls: https://www.examcert.app/blog/isc2-cc-worth-it/, https://open-exam-prep.com/blog/isc2-cc-certified-in-cybersecurity-guide-2026, https://cyberexperts.com/isc2-cc-exam/, https://www.pocketprep.com/posts/isc2-cc-exam-blueprint-subjects-official-resources-and-faqs/, https://trainingcamp.com/articles/isc2-cc-certification-guide-2026-exam-domains-cost-and-what-its-worth/, https://www.certcrush.app/blog/isc2-cc-exam-changes-2026-sit-before-september-1
- Disagree: https://stephenbernardombacisa.substack.com/p/reflections-and-tips-for-passing: registering gets you a free course and a free exam (written March 2025).
- Level: foundation
- Flag: There is no free exam for new candidates. 1MCC closed to new enrolments on 20 May 2026, and existing unexpired codes must be used by 31 December 2026. After passing, apply and agree to the Code of Ethics within nine months or retake the exam. Keeping the cert means paying the $50 AMF and earning 45 CPE per three-year cycle. Retakes cost full price (up to four attempts in 12 months, with 30/60/90-day waits).
- Best story: "The CC is a subscription, not a purchase": about $249 in year one. https://www.examcert.app/blog/isc2-cc-worth-it/

## TH04 Learn the content first, use practice tests to diagnose, and book once you score 80%+ consistently on timed tests
- Sub-topic: T01 (also T15)
- Agree: 6 of 9. Notes: a:N12, b:N8, b:N9, c:N4, d:N6, d:N7, d:N9, d:N12, d:N13. Urls: https://open-exam-prep.com/blog/isc2-cc-certified-in-cybersecurity-guide-2026, https://www.certcrush.app/blog/how-to-pass-isc2-cc-2026-4-week-study-plan, https://cyberexperts.com/isc2-cc-exam/, https://www.pocketprep.com/posts/isc2-cc-exam-blueprint-subjects-official-resources-and-faqs/, https://trainingcamp.com/articles/isc2-cc-certification-guide-2026-exam-domains-cost-and-what-its-worth/, https://stephenbernardombacisa.substack.com/p/reflections-and-tips-for-passing
- Disagree: Order: https://www.pocketprep.com/posts/isc2-cc-exam-blueprint-subjects-official-resources-and-faqs/ starts with a mixed baseline quiz, while https://trainingcamp.com/articles/isc2-cc-certification-guide-2026-exam-domains-cost-and-what-its-worth/ says practice questions come only after a content pass. Hours: https://www.certcrush.app/blog/how-to-pass-isc2-cc-2026-4-week-study-plan says 8 to 10 hours a week for 4 weeks; https://cyberexperts.com/isc2-cc-exam/ says 5 to 7 hours a week (double if new); trainingcamp says 40 to 80 hours total; open-exam-prep says 44 to 58 hours over 7 weeks.
- Level: foundation
- Flag: The substack learner studied under the old outline and the free 1MCC course. Use his loop, not his domain names or his route to a free exam.
- Best story: A learner scores 59% on network security in his first practice test, lists every unknown acronym and climbs back. https://stephenbernardombacisa.substack.com/p/reflections-and-tips-for-passing

## TH05 Answer like a manager: the best or first action is usually policy, risk or process, the ISC2 textbook answer
- Sub-topic: T01 (also T05, T09)
- Agree: 5 of 9. Notes: a:N11, b:N10, b:N11, c:N5, c:N16, d:N8. Urls: https://open-exam-prep.com/blog/isc2-cc-certified-in-cybersecurity-guide-2026, https://cyberexperts.com/isc2-cc-exam/, https://www.certcrush.app/blog/how-to-pass-isc2-cc-2026-4-week-study-plan, https://trainingcamp.com/articles/isc2-cc-certification-guide-2026-exam-domains-cost-and-what-its-worth/, https://www.pocketprep.com/posts/isc2-cc-exam-blueprint-subjects-official-resources-and-faqs/
- Disagree: none found
- Level: foundation
- Best story: The model scenario question is a contractor who still holds admin rights three months after the project ended. https://www.certcrush.app/blog/how-to-pass-isc2-cc-2026-4-week-study-plan

## TH06 Treat CC as a door-knock, not a door-opener: it proves vocabulary and intent, so check local job postings against Security+
- Sub-topic: T01
- Agree: 3 of 9. Notes: a:N9, b:N12, d:N2, d:N10. Urls: https://www.examcert.app/blog/isc2-cc-worth-it/, https://cyberexperts.com/isc2-cc-exam/, https://trainingcamp.com/articles/isc2-cc-certification-guide-2026-exam-domains-cost-and-what-its-worth/
- Disagree: https://cyberexperts.com/isc2-cc-exam/: Security+ is the baseline employers want, and CC is "lesser known and not as respected". https://trainingcamp.com/articles/isc2-cc-certification-guide-2026-exam-domains-cost-and-what-its-worth/: if you can do both, take CC first. https://www.examcert.app/blog/isc2-cc-worth-it/: anyone with 3+ years in IT should skip to SSCP or CISSP. https://open-exam-prep.com/blog/isc2-cc-certified-in-cybersecurity-guide-2026: skip only with several years of hands-on security experience.
- Level: foundation
- Flag: Label the Security+ price ($404 vs $439) and the "65% work in cybersecurity" figure as the sources' claims. The second comes from ISC2's survey of its own holders.
- Best story: "the CC is a door-knock, not a door-opener" https://www.examcert.app/blog/isc2-cc-worth-it/

## TH07 Define confidentiality, integrity and availability through one example, map each control to the leg it protects, and let context decide which leg matters most
- Sub-topic: T02 (also T03, T04, T07, T14)
- Agree: 5 of 5. Notes: a:N14, b:N15, b:N16, b:N17, b:N18, c:N28, d:N15, d:N16, d:N17, d:N41. Urls: https://open-exam-prep.com/blog/isc2-cc-certified-in-cybersecurity-guide-2026, https://www.coursera.org/articles/cia-triad, https://www.portnox.com/cybersecurity-101/general-security/cia-triad/, https://rippling.com/blog/hashing-vs-encryption, https://cyber.gc.ca/en/guidance/improving-cyber-security-resilience-through-emergency-preparedness-planning-itsm10014
- Disagree: none found on the mapping (encryption → C; hashing and signatures → I; redundancy and backups → A).
- Level: foundation
- Flag: coursera.org's "think of confidentiality as privacy" must not be repeated (see TH08).
- Best story: One email walked through all three legs (an interceptor changes the key points = integrity lost) https://www.coursera.org/articles/cia-triad. Alternate: OT flips the order; an industrial control system breach can cost lives https://cyber.gc.ca/en/guidance/improving-cyber-security-resilience-through-emergency-preparedness-planning-itsm10014

## TH08 Teach privacy, authenticity, non-repudiation and AAA (authentication, authorization, accounting) as principles separate from CIA
- Sub-topic: T02 (also T08)
- Agree: 1 of 5. Notes: b:N19. Urls: https://www.coursera.org/articles/cia-triad
- Disagree: https://www.coursera.org/articles/cia-triad: "think of confidentiality as privacy" (the same page that lists AAA).
- Level: foundation
- Flag: Confidentiality is not privacy. Confidentiality keeps data to authorized people; privacy is an individual's right to control their personal data. No source defines non-repudiation or authenticity properly (see gaps).
- Best story: none

## TH09 Assess risk as a threat exploiting a vulnerability to harm an asset, rate it by likelihood and impact, and compare it with appetite and tolerance
- Sub-topic: T03 (also T07)
- Agree: 4 of 6. Notes: a:N15, a:N20, b:N21, c:N22. Urls: https://open-exam-prep.com/blog/isc2-cc-certified-in-cybersecurity-guide-2026, https://stacker.com/stories/small-business/4-risk-treatment-strategies-separate-proactive-businesses-reactive-ones, https://www.certcrush.app/blog/how-to-pass-isc2-cc-2026-4-week-study-plan, https://cyber.gc.ca/en/guidance/improving-cyber-security-resilience-through-emergency-preparedness-planning-itsm10014
- Disagree: none found
- Level: foundation
- Best story: none

## TH10 Name the treatment from a one-line scenario (avoid, mitigate, transfer, accept): accept only in writing, inside tolerance, and remember transfer moves cost but never accountability
- Sub-topic: T03 (also T07, T13, T15)
- Agree: 3 of 6. Notes: a:N15, a:N16, a:N17, a:N18, a:N19, b:N20, b:N21, b:N22. Urls: https://stacker.com/stories/small-business/4-risk-treatment-strategies-separate-proactive-businesses-reactive-ones, https://aptien.com/en/kb/articles/what-are-risk-treatment-strategies, https://www.certcrush.app/blog/how-to-pass-isc2-cc-2026-4-week-study-plan
- Disagree: https://aptien.com/en/kb/articles/what-are-risk-treatment-strategies: acceptance is simply "the most common choice for small, low-level risks", with no written reason required. https://stacker.com/stories/small-business/4-risk-treatment-strategies-separate-proactive-businesses-reactive-ones: acceptance is overused, and without a written "why" in the risk register it is unmanaged risk.
- Level: core
- Best story: A company avoids a breach risk entirely by deleting a legacy feature and the unused PII it collected. https://stacker.com/stories/small-business/4-risk-treatment-strategies-separate-proactive-businesses-reactive-ones

## TH11 Sort every control by type (physical, technical, administrative) and by function (preventive, detective, corrective, deterrent, compensating, recovery)
- Sub-topic: T04 (also T02)
- Agree: 5 of 6. Notes: a:N14, a:N21, a:N23, b:N24, c:N9; portnox.com (batch d "Disagreements seen", no note id). Urls: https://heimdalsecurity.com/blog/defense-in-depth-layers/, https://www.csoonline.com/article/3667476/defense-in-depth-explained-layering-tools-and-processes-for-better-security.html, https://cyberdefenders.org/cybersecurity-glossary/defense-in-depth/, https://open-exam-prep.com/blog/isc2-cc-certified-in-cybersecurity-guide-2026, https://www.portnox.com/cybersecurity-101/general-security/cia-triad/
- Disagree: https://stephenbernardombacisa.substack.com/p/reflections-and-tips-for-passing: "physical controls such as cryptography and identity access management" (d:N18).
- Level: foundation
- Flag: Cryptography and IAM are technical controls, not physical ones. Use the substack line only as a "spot the mistake" moment.
- Best story: "A network control means nothing if an attacker can walk out with the disk." https://cyberdefenders.org/cybersecurity-glossary/defense-in-depth/

## TH12 Layer your defenses so each one assumes the layer before it has failed (defense in depth)
- Sub-topic: T04 (also T11, T12)
- Agree: 3 of 6. Notes: a:N22, b:N23, b:N25, b:N27, c:N7, c:N10, c:N11. Urls: https://heimdalsecurity.com/blog/defense-in-depth-layers/, https://www.csoonline.com/article/3667476/defense-in-depth-explained-layering-tools-and-processes-for-better-security.html, https://cyberdefenders.org/cybersecurity-glossary/defense-in-depth/
- Disagree: none found on the idea itself.
- Level: foundation
- Flag: csoonline.com's network layer "starts with a firewall or IDS to try to block attacks" (an IDS detects; an IPS blocks). heimdalsecurity.com describes IDS/IPS as DNS query filtering and says a VPN protects against external attacks. Don't carry either into a lesson.
- Best story: One phishing email traced through every layer (training, email gateway, MFA, segmentation, EDR, patching, encrypted data); no single control stopped it, but the delay gave the SOC time. https://cyberdefenders.org/cybersecurity-glossary/defense-in-depth/

## TH13 Build depth from diverse controls, test each for a single point of failure, and run zero trust inside defense in depth, not instead of it
- Sub-topic: T04 (also T12)
- Agree: 2 of 6. Notes: b:N26, c:N8, c:N12, c:N13. Urls: https://cyberdefenders.org/cybersecurity-glossary/defense-in-depth/, https://www.csoonline.com/article/3667476/defense-in-depth-explained-layering-tools-and-processes-for-better-security.html
- Disagree: none found
- Level: advanced
- Flag: The same csoonline.com page wrongly has an IDS blocking attacks. An IDS detects and alerts; an IPS blocks.
- Best story: A control that nothing else backs up is "a single point of failure wearing a costume". https://cyberdefenders.org/cybersecurity-glossary/defense-in-depth/

## TH14 Recite the four ISC2 canons in order: when they conflict the earlier one wins, and observed violations must be reported
- Sub-topic: T05 (also T01)
- Agree: 3 of 4. Notes: a:N12, a:N25, c:N14, c:N15, c:N16. Urls: https://open-exam-prep.com/blog/isc2-cc-certified-in-cybersecurity-guide-2026, https://www.isc2.org/ethics, https://www.pocketprep.com/posts/isc2-cc-exam-blueprint-subjects-official-resources-and-faqs/
- Disagree: none found
- Level: foundation
- Best story: Using exam dumps breaks the very Code of Ethics you are tested on. https://open-exam-prep.com/blog/isc2-cc-certified-in-cybersecurity-guide-2026

## TH15 Rank governance documents (policy, then standard, then procedure, then guideline), write policies with "must" and no named technology, and keep standards private
- Sub-topic: T06 (also T09, T16)
- Agree: 4 of 7. Notes: a:N26, a:N27, a:N28, a:N29, c:N17, c:N18, c:N19. Urls: https://frsecure.com/blog/differentiating-between-policies-standards-procedures-and-guidelines/, https://informationshield.com/2023/10/27/security-policies-standard-and-procedures-whats-the-difference, https://informationsecurity.wustl.edu/policies-standards-and-guidelines, https://cyber.gc.ca/en/guidance/improving-cyber-security-resilience-through-emergency-preparedness-planning-itsm10014
- Disagree: none on the hierarchy. Placement: https://www.pocketprep.com/posts/isc2-cc-exam-blueprint-subjects-official-resources-and-faqs/ puts policies, standards and procedures in Domain 1 and GRC in Domain 2, so learners shouldn't expect "governance" in one place only.
- Level: foundation
- Flag: informationshield.com's model control "enforces password resets every 90 days" conflicts with NIST SP 800-63B. If you use it, use it only to show what a technical control is, never as password advice.
- Best story: WashU publishes its policies but keeps its standards behind a login, because standards tell attackers exactly what to target. https://informationsecurity.wustl.edu/policies-standards-and-guidelines

## TH16 Tell laws (GDPR, HIPAA, PIPEDA) from industry standards (PCI DSS) and from frameworks (NIST CSF, SP 800-53, ISO 27001)
- Sub-topic: T06 (also T16)
- Agree: 3 of 7. Notes: a:N31, b:N43, c:N20. Urls: https://open-exam-prep.com/blog/isc2-cc-certified-in-cybersecurity-guide-2026, https://consilien.com/news/nist-incident-response-lifecycle-4-phases-explained, https://cyber.gc.ca/en/guidance/improving-cyber-security-resilience-through-emergency-preparedness-planning-itsm10014
- Disagree: none found
- Level: core
- Best story: none

## TH17 Keep incident response, disaster recovery and business continuity as three plans with three jobs, with the BCP as the umbrella
- Sub-topic: T07 (also T16)
- Agree: 4 of 12. Notes: a:N32, b:N28, b:N31, c:N21, d:N19. Urls: https://preyproject.com/blog/business-continuity-disaster-recovery-and-incident-response, https://cyber.gc.ca/en/guidance/improving-cyber-security-resilience-through-emergency-preparedness-planning-itsm10014, https://www.techtarget.com/cybersecurity/tip/Business-continuity-vs-disaster-recovery-vs-incident-response, https://open-exam-prep.com/blog/isc2-cc-certified-in-cybersecurity-guide-2026
- Disagree: https://cyber.gc.ca/en/guidance/improving-cyber-security-resilience-through-emergency-preparedness-planning-itsm10014 contradicts itself. One section says the DRP "encompasses" the IRP and BCP and that the BCP is "a subset of the larger DRP"; its summary puts both under "the umbrella of a BCP". https://preyproject.com/blog/business-continuity-disaster-recovery-and-incident-response also contradicts itself: its sequence list says BC then DR, but its fire scenario starts DR and BC together.
- Level: foundation
- Flag: BCP is the umbrella; DR is the IT-restoration part inside it. Don't repeat cyber.gc.ca's "BCP is a subset of the DRP".
- Best story: Ransomware vs office fire vs phishing click vs hurricane: which plan fires first, and why. https://preyproject.com/blog/business-continuity-disaster-recovery-and-incident-response

## TH18 Run the business impact analysis first, set RTO, RPO and MTD from it (RTO shorter than MTD), and pick a hot, warm or cold site to match
- Sub-topic: T07 (also T01, T18)
- Agree: 4 of 12. Notes: a:N32, a:N33, b:N30, b:N33, c:N22, c:N23, c:N24, c:N26. Urls: https://open-exam-prep.com/blog/isc2-cc-certified-in-cybersecurity-guide-2026, https://cyber.gc.ca/en/guidance/improving-cyber-security-resilience-through-emergency-preparedness-planning-itsm10014, https://preyproject.com/blog/business-continuity-disaster-recovery-and-incident-response, https://www.certcrush.app/blog/how-to-pass-isc2-cc-2026-4-week-study-plan
- Disagree: none found. preyproject adds that each plan has its own metrics: RTO and RPO for DR, MTD for BC, time to detect and to contain for IR.
- Level: core
- Best story: Synchronous replication to a DR site means zero data loss but slower transactions and real expense; a low-turnover business can live with an RPO of days. https://cyber.gc.ca/en/guidance/improving-cyber-security-resilience-through-emergency-preparedness-planning-itsm10014

## TH19 Prove backups by restoring them, keep 3-2-1 copies, and never restore before the hole is closed
- Sub-topic: T07 (also T13, T16)
- Agree: 5 of 12. Notes: a:N33, a:N34, b:N38, d:N21, d:N39. Urls: https://tcm-sec.com/nist-guidelines-for-incident-response-best-practices/, https://consilien.com/news/nist-incident-response-lifecycle-4-phases-explained, https://www.techtarget.com/cybersecurity/tip/Business-continuity-vs-disaster-recovery-vs-incident-response, https://open-exam-prep.com/blog/isc2-cc-certified-in-cybersecurity-guide-2026, https://searchcloudcomputing.techtarget.com/feature/The-cloud-shared-responsibility-model-for-IaaS-PaaS-and-SaaS
- Disagree: none found
- Level: foundation
- Best story: "A backup you've never restored is a hope, not a recovery plan." https://consilien.com/news/nist-incident-response-lifecycle-4-phases-explained

## TH20 Name an owner and alternates for each plan, write the plans while calm, and test them at least yearly, from checklist up to full interruption
- Sub-topic: T07 (also T06, T16)
- Agree: 4 of 12. Notes: a:N33, b:N32, c:N25, c:N27, d:N20, d:N22. Urls: https://preyproject.com/blog/business-continuity-disaster-recovery-and-incident-response, https://cyber.gc.ca/en/guidance/improving-cyber-security-resilience-through-emergency-preparedness-planning-itsm10014, https://www.techtarget.com/cybersecurity/tip/Business-continuity-vs-disaster-recovery-vs-incident-response, https://open-exam-prep.com/blog/isc2-cc-certified-in-cybersecurity-guide-2026
- Disagree: none found
- Level: core
- Best story: The real failure is that "nobody knew they had the authority to act". https://preyproject.com/blog/business-continuity-disaster-recovery-and-incident-response

## TH21 Use MFA with factors from two different categories (know, have, are); two passwords, or a password plus a PIN, is not MFA, and authentication is not authorization
- Sub-topic: T08 (also T09)
- Agree: 4 of 7. Notes: a:N35, b:N19, c:N29, c:N30, c:N31. Urls: https://open-exam-prep.com/blog/isc2-cc-certified-in-cybersecurity-guide-2026, https://www.isdecisions.com/en/glossary/mfa-factors, https://duo.com/learn/access-control-models, https://www.coursera.org/articles/cia-triad
- Disagree: https://www.isdecisions.com/en/glossary/mfa-factors adds "somewhere you are" and "something you do" as factors; https://duo.com/learn/access-control-models lists only the three classic ones.
- Level: foundation
- Flag: Biometrics are hard to fake but can't be changed once leaked. Add that line when using isdecisions.
- Best story: none

## TH22 Favour long passwords, store them with a unique salt and a slow hash (bcrypt, Argon2), and drop forced periodic resets
- Sub-topic: T08 (also T14)
- Agree: 3 of 7. Notes: a:N35, a:N49, d:N43. Urls: https://open-exam-prep.com/blog/isc2-cc-certified-in-cybersecurity-guide-2026, https://www.20i.com/blog/how-encryption-works-from-hashing-to-modern-cryptography/, https://rippling.com/blog/hashing-vs-encryption
- Disagree: https://informationshield.com/2023/10/27/security-policies-standard-and-procedures-whats-the-difference: "enforces password resets every 90 days" as a model control. https://www.20i.com/blog/how-encryption-works-from-hashing-to-modern-cryptography/ shows a salted SHA-256 password example right after saying SHA-256 is too fast for passwords.
- Level: core
- Flag: Forced 90-day resets conflict with NIST SP 800-63B (change a password only on sign of compromise). Salted SHA-256 is not a password store; use bcrypt or Argon2.
- Best story: none

## TH23 Name the access control model from one sentence: DAC (the owner decides), MAC (labels and clearances), RBAC (roles), ABAC (attributes and context), and rule-based (one fixed rule for everyone, not role-based)
- Sub-topic: T09 (also T01)
- Agree: 4 of 8. Notes: a:N36, b:N48, c:N32, c:N33, c:N34, c:N35, c:N36, c:N37, c:N38, d:N23, d:N24, d:N26. Urls: https://open-exam-prep.com/blog/isc2-cc-certified-in-cybersecurity-guide-2026, https://www.certcrush.app/blog/how-to-pass-isc2-cc-2026-4-week-study-plan, https://duo.com/learn/access-control-models, https://www.twingate.com/blog/other/access-control-models
- Disagree: https://www.twingate.com/blog/other/access-control-models: the four common models are MAC, DAC, RBAC and PAM, PAM is a type of RBAC, and ABAC is omitted. https://trainingcamp.com/articles/isc2-cc-certification-guide-2026-exam-domains-cost-and-what-its-worth/ lists discretionary, mandatory, role-based and rule-based, with no ABAC.
- Level: foundation
- Flag: PAM is not an access control model. Teach DAC, MAC, RBAC and ABAC, plus rule-based. Watch for RBAC role explosion ("role engineering").
- Best story: ABAC at 11 p.m.: same user, same desk, same file, now denied. https://duo.com/learn/access-control-models. Alternate: a startup picks DAC, a hospital RBAC plus MAC, a bank ABAC. https://duo.com/learn/access-control-models

## TH24 Grant least privilege, split duties so the person who creates is never the person who approves, and give admins rights only temporarily
- Sub-topic: T09 (also T11)
- Agree: 4 of 8. Notes: a:N37, a:N40, c:N35, d:N25, d:N27. Urls: https://open-exam-prep.com/blog/isc2-cc-certified-in-cybersecurity-guide-2026, https://cybelangel.com/blog/20-common-types-of-malware/, https://duo.com/learn/access-control-models, https://www.twingate.com/blog/other/access-control-models
- Disagree: none found
- Level: core
- Flag: Privileged access management (PAM) is a practice for privileged accounts, not one of the access control models. twingate's 53%/85% stolen-credential figures are a vendor-cited study; label them as the source's claim.
- Best story: Accounts payable clerks can create payments but not approve them; supervisors can approve but not create. https://www.twingate.com/blog/other/access-control-models. Alternate: the 2002 UBS logic bomb planted by a disgruntled admin. https://cybelangel.com/blog/20-common-types-of-malware/

## TH25 Run the identity lifecycle (joiners, movers, leavers, periodic access reviews, prompt deprovisioning) so privilege creep never builds
- Sub-topic: T09 (also T01, T06, T18)
- Agree: 6 of 8. Notes: a:N29, a:N37, b:N10, b:N47, b:N48, c:N39 (its bias line credits duo.com with the same point). Urls: https://open-exam-prep.com/blog/isc2-cc-certified-in-cybersecurity-guide-2026, https://www.certcrush.app/blog/how-to-pass-isc2-cc-2026-4-week-study-plan, https://www.pocketprep.com/posts/isc2-cc-exam-blueprint-subjects-official-resources-and-faqs/, https://informationshield.com/2023/10/27/security-policies-standard-and-procedures-whats-the-difference, https://cyberexperts.com/isc2-cc-exam/, https://duo.com/learn/access-control-models
- Disagree: none found
- Level: foundation
- Best story: The contractor who still has admin rights three months after the project ended. https://www.certcrush.app/blog/how-to-pass-isc2-cc-2026-4-week-study-plan

## TH26 Use the OSI model as a map: switches at Layer 2, routers at Layer 3, ports at Layer 4; data is encapsulated on the way down, and every attack and defense lives on a layer
- Sub-topic: T10 (also T11, T12)
- Agree: 2 of 3. Notes: a:N38, c:N40, c:N41, c:N42. Urls: https://open-exam-prep.com/blog/isc2-cc-certified-in-cybersecurity-guide-2026, https://dev.to/alvinseyidov/networking-for-cybersecurity-part-1-osi-tcpip-ports-protocols-3eai
- Disagree: https://dev.to/alvinseyidov/networking-for-cybersecurity-part-1-osi-tcpip-ports-protocols-3eai lists switches as a Layer 1 example.
- Level: foundation
- Flag: Switches are Layer 2 (MAC addresses), not Layer 1.
- Best story: Encapsulation as a gift packed into nested boxes. https://dev.to/alvinseyidov/networking-for-cybersecurity-part-1-osi-tcpip-ports-protocols-3eai

## TH27 Memorise the core ports with the risk each one carries, and know TCP's three-way handshake vs connectionless UDP
- Sub-topic: T10 (also T11)
- Agree: 3 of 3. Notes: a:N38, b:N14, c:N43, c:N44, c:N45. Urls: https://open-exam-prep.com/blog/isc2-cc-certified-in-cybersecurity-guide-2026, https://www.certcrush.app/blog/how-to-pass-isc2-cc-2026-4-week-study-plan, https://dev.to/alvinseyidov/networking-for-cybersecurity-part-1-osi-tcpip-ports-protocols-3eai
- Disagree: none found (the lists differ slightly; the shared core is 22, 23, 25, 53, 80, 443, 3389).
- Level: foundation
- Best story: IP address = the house, port = the room, protocol = how you knock. https://dev.to/alvinseyidov/networking-for-cybersecurity-part-1-osi-tcpip-ports-protocols-3eai

## TH28 Tell malware apart by how it spreads and hides: a virus needs a host and a human, a worm spreads itself, a trojan disguises itself, a rootkit hides below the OS, and one sample can fit two categories
- Sub-topic: T11
- Agree: 2 of 4. Notes: a:N39, a:N40, a:N42, a:N43, d:N29, d:N30, d:N31, d:N32, d:N34. Urls: https://cybelangel.com/blog/20-common-types-of-malware/, https://www.trendmicro.com/en_us/what-is/endpoint-security/types-of-malware.html
- Disagree: none found
- Level: foundation
- Best story: Sony BMG shipped a rootkit on music CDs in 2005 as copy protection, and attackers then hid behind it. https://cybelangel.com/blog/20-common-types-of-malware/ (also https://www.trendmicro.com/en_us/what-is/endpoint-security/types-of-malware.html). Alternate: Melissa (1999) to WannaCry (2017). https://www.trendmicro.com/en_us/what-is/endpoint-security/types-of-malware.html

## TH29 Starve botnets and DDoS at the source: change default passwords, patch, watch outbound traffic to command-and-control, and know that UDP is easy to spoof for amplification
- Sub-topic: T11 (also T12)
- Agree: 3 of 4. Notes: a:N41, c:N45, d:N33. Urls: https://cybelangel.com/blog/20-common-types-of-malware/, https://dev.to/alvinseyidov/networking-for-cybersecurity-part-1-osi-tcpip-ports-protocols-3eai, https://www.trendmicro.com/en_us/what-is/endpoint-security/types-of-malware.html
- Disagree: none found
- Level: foundation
- Best story: The Mirai botnet hijacked IoT cameras and routers through default passwords and knocked Twitter, Netflix and Reddit offline in 2016. https://cybelangel.com/blog/20-common-types-of-malware/

## TH30 Remember that an IDS detects and alerts while an IPS sits inline and blocks, and know the three firewall generations (packet filter, stateful, next-gen)
- Sub-topic: T12 (also T10, T13)
- Agree: 3 of 6. Notes: a:N45, c:N10, c:N42, c:N46, c:N47. Urls: https://open-exam-prep.com/blog/isc2-cc-certified-in-cybersecurity-guide-2026, https://dev.to/alvinseyidov/networking-for-cybersecurity-part-1-osi-tcpip-ports-protocols-3eai, https://cyberdefenders.org/cybersecurity-glossary/defense-in-depth/
- Disagree: https://www.csoonline.com/article/3667476/defense-in-depth-explained-layering-tools-and-processes-for-better-security.html: "a firewall or IDS to try to block attacks". https://heimdalsecurity.com/blog/defense-in-depth-layers/: IDS/IPS described as DNS-level query filtering (its own product).
- Level: foundation
- Flag: An IDS never blocks. Don't use heimdal's IDS/IPS description.
- Best story: A next-gen firewall catches port 443 traffic that isn't real HTTPS. https://dev.to/alvinseyidov/networking-for-cybersecurity-part-1-osi-tcpip-ports-protocols-3eai

## TH31 Segment the network (zones, VLANs, a DMZ for public servers) so one compromised host stays a contained incident, and verify every request (zero trust)
- Sub-topic: T12 (also T04, T09, T13)
- Agree: 4 of 6. Notes: a:N45, b:N26, c:N13, c:N47, d:N28. Urls: https://open-exam-prep.com/blog/isc2-cc-certified-in-cybersecurity-guide-2026, https://cyberdefenders.org/cybersecurity-glossary/defense-in-depth/, https://www.csoonline.com/article/3667476/defense-in-depth-explained-layering-tools-and-processes-for-better-security.html, https://www.twingate.com/blog/other/access-control-models
- Disagree: none found
- Level: core
- Best story: none

## TH32 Map shared responsibility for each cloud model (IaaS, PaaS, SaaS): the customer always owns its data, identities and configuration, and should read the SLA for what it really pays out
- Sub-topic: T13 (also T03, T07, T08)
- Agree: 4 of 5. Notes: a:N17, a:N56, c:N6, d:N36, d:N37, d:N38, d:N39, d:N40. Urls: https://searchcloudcomputing.techtarget.com/feature/The-cloud-shared-responsibility-model-for-IaaS-PaaS-and-SaaS, https://www.pocketprep.com/posts/isc2-cc-exam-blueprint-subjects-official-resources-and-faqs/, https://stacker.com/stories/small-business/4-risk-treatment-strategies-separate-proactive-businesses-reactive-ones, https://open-exam-prep.com/blog/isc2-cc-certified-in-cybersecurity-guide-2026
- Disagree: none found
- Level: foundation
- Best story: A PaaS customer picks a weak password, an attacker logs in, injects code and deploys it, and the breach is the customer's, not the provider's. https://searchcloudcomputing.techtarget.com/feature/The-cloud-shared-responsibility-model-for-IaaS-PaaS-and-SaaS

## TH33 Use symmetric encryption (AES) for bulk data and asymmetric (RSA, ECC) for key exchange and signatures: TLS uses both, you sign with your private key, and you encrypt to someone's public key
- Sub-topic: T14
- Agree: 3 of 3. Notes: a:N47, a:N50, d:N44. Urls: https://www.20i.com/blog/how-encryption-works-from-hashing-to-modern-cryptography/, https://rippling.com/blog/hashing-vs-encryption, https://open-exam-prep.com/blog/isc2-cc-certified-in-cybersecurity-guide-2026
- Disagree: https://heimdalsecurity.com/blog/defense-in-depth-layers/: suggests RSA for encryption at rest. https://rippling.com/blog/hashing-vs-encryption: lists DES as a "common" symmetric algorithm.
- Level: foundation
- Flag: Data at rest uses AES, not RSA (RSA protects keys). DES is obsolete and insecure, so never present it as common. Quantum-resistant cryptography is named in the new outline but no source explains it.
- Best story: none

## TH34 Treat a hash as a one-way, fixed-length fingerprint for integrity, not encryption: one changed character changes the whole digest, and MD5 and SHA-1 are broken
- Sub-topic: T14 (also T02, T08)
- Agree: 3 of 3. Notes: a:N14, a:N48, a:N49, d:N41, d:N42, d:N43. Urls: https://www.20i.com/blog/how-encryption-works-from-hashing-to-modern-cryptography/, https://rippling.com/blog/hashing-vs-encryption, https://open-exam-prep.com/blog/isc2-cc-certified-in-cybersecurity-guide-2026
- Disagree: https://heimdalsecurity.com/blog/defense-in-depth-layers/: calls hashing "a cipher".
- Level: foundation
- Flag: Hashing is not a cipher and has no key. For passwords, see TH22: salted SHA-256 is not enough.
- Best story: hello123 and hello124 give completely different SHA-256 digests (the avalanche effect). https://www.20i.com/blog/how-encryption-works-from-hashing-to-modern-cryptography/

## TH35 Destroy data on a retention schedule and record when and why, sanitise media (zeroization, degaussing), and delete data you no longer need
- Sub-topic: T15 (also T01, T03)
- Agree: 3 of 4. Notes: a:N18, c:N48, d:N13. Urls: https://it.osu.edu/data/governance/data-literacy/data-lifecycle, https://stephenbernardombacisa.substack.com/p/reflections-and-tips-for-passing, https://stacker.com/stories/small-business/4-risk-treatment-strategies-separate-proactive-businesses-reactive-ones
- Disagree: https://it.osu.edu/data/governance/data-literacy/data-lifecycle uses a research-data lifecycle (plan, create, manage, use, share, reuse, destroy, close out), not the security lifecycle CC teaches (create, store, use, share, archive, destroy).
- Level: foundation
- Flag: Don't teach OSU's stages as the CC data lifecycle; use it only for the "document destruction" point.
- Best story: The forgotten PII feature: delete it and the risk is gone. https://stacker.com/stories/small-business/4-risk-treatment-strategies-separate-proactive-businesses-reactive-ones

## TH36 Teach the classic Rev. 2 incident response model (Preparation; Detection and Analysis; Containment, Eradication and Recovery; Post-Incident Activity) and SANS's six steps, and say that Rev. 3 (April 2025) now maps IR onto the CSF 2.0 functions
- Sub-topic: T16
- Agree: 5 of 6. Notes: a:N51, b:N34, b:N35, b:N36, b:N41, c:N49. Urls: https://tcm-sec.com/nist-guidelines-for-incident-response-best-practices/, https://consilien.com/news/nist-incident-response-lifecycle-4-phases-explained, https://preyproject.com/blog/business-continuity-disaster-recovery-and-incident-response, https://www.armorpoint.com/blog/a-step-by-step-guide-to-incident-response-practical-guidance-from-nist-sp-800-61, https://cyber.gc.ca/en/guidance/improving-cyber-security-resilience-through-emergency-preparedness-planning-itsm10014
- Disagree: https://tcm-sec.com/nist-guidelines-for-incident-response-best-practices/, https://www.armorpoint.com/blog/a-step-by-step-guide-to-incident-response-practical-guidance-from-nist-sp-800-61 and https://preyproject.com/blog/business-continuity-disaster-recovery-and-incident-response present the four phases as the current NIST model. https://consilien.com/news/nist-incident-response-lifecycle-4-phases-explained says Rev. 3 "retired the four-phase lifecycle as the official structure".
- Level: foundation
- Flag: Never call the four phases "current NIST guidance"; say "the classic Rev. 2 model". Rev. 3 (3 April 2025) maps IR onto Govern, Identify, Protect, Detect, Respond and Recover. Which model the CC exam wording uses is unverified, because no ISC2 outline page is on disk. "Five steps" is usually a vendor condensation.
- Best story: Run it as a loop, not a checklist: Recovery can uncover another compromised host and send you back to Containment. https://consilien.com/news/nist-incident-response-lifecycle-4-phases-explained

## TH37 Prepare before the incident: an IR policy approved by senior management, named roles and contacts, a jump kit, an out-of-band channel and tabletop exercises
- Sub-topic: T16 (also T06, T07)
- Agree: 5 of 6. Notes: a:N52, b:N39, b:N41, c:N19, d:N22. Urls: https://tcm-sec.com/nist-guidelines-for-incident-response-best-practices/, https://consilien.com/news/nist-incident-response-lifecycle-4-phases-explained, https://www.armorpoint.com/blog/a-step-by-step-guide-to-incident-response-practical-guidance-from-nist-sp-800-61, https://cyber.gc.ca/en/guidance/improving-cyber-security-resilience-through-emergency-preparedness-planning-itsm10014, https://www.techtarget.com/cybersecurity/tip/Business-continuity-vs-disaster-recovery-vs-incident-response
- Disagree: none found
- Level: core
- Flag: Several of these pages frame Preparation inside the Rev. 2 cycle as current; call it the classic Rev. 2 model.
- Best story: The ransomware note arrives while the one person who understands the firewall is on a plane. https://consilien.com/news/nist-incident-response-lifecycle-4-phases-explained. Alternate: the attacker is inside your Slack, so you need a pre-agreed out-of-band channel. https://tcm-sec.com/nist-guidelines-for-incident-response-best-practices/

## TH38 Contain first and investigate second: put life and safety first, preserve evidence, and remove the root cause before restoring, or you reinfect
- Sub-topic: T16 (also T07)
- Agree: 4 of 6. Notes: a:N53, b:N29, b:N37, b:N38, c:N50. Urls: https://tcm-sec.com/nist-guidelines-for-incident-response-best-practices/, https://consilien.com/news/nist-incident-response-lifecycle-4-phases-explained, https://cyber.gc.ca/en/guidance/improving-cyber-security-resilience-through-emergency-preparedness-planning-itsm10014, https://preyproject.com/blog/business-continuity-disaster-recovery-and-incident-response
- Disagree: none found
- Level: core
- Flag: Same Rev. 2 framing caveat as TH36.
- Best story: Stop the bleeding before asking how the patient fell. https://consilien.com/news/nist-incident-response-lifecycle-4-phases-explained

## TH39 Hold a blameless lessons-learned review within a week or two, and turn it into concrete changes (a control, a detection rule, a plan fix)
- Sub-topic: T16
- Agree: 3 of 6. Notes: a:N54, b:N41, b:N42. Urls: https://tcm-sec.com/nist-guidelines-for-incident-response-best-practices/, https://consilien.com/news/nist-incident-response-lifecycle-4-phases-explained, https://www.armorpoint.com/blog/a-step-by-step-guide-to-incident-response-practical-guidance-from-nist-sp-800-61
- Disagree: none found
- Level: foundation
- Flag: Same Rev. 2 framing caveat as TH36.
- Best story: A phishing review finds staff couldn't spot phishing, which leads to training and better email filtering. https://www.armorpoint.com/blog/a-step-by-step-guide-to-incident-response-practical-guidance-from-nist-sp-800-61. Tagline: "Never let a good crisis go to waste." https://tcm-sec.com/nist-guidelines-for-incident-response-best-practices/

## TH40 Know that breach-reporting clocks exist (e.g. DFARS 72 hours, SEC 4 business days, PIPEDA's "real risk of significant harm") and that slow detection makes them impossible to meet
- Sub-topic: T16 (also T06)
- Agree: 2 of 6. Notes: b:N43, c:N20. Urls: https://consilien.com/news/nist-incident-response-lifecycle-4-phases-explained, https://cyber.gc.ca/en/guidance/improving-cyber-security-resilience-through-emergency-preparedness-planning-itsm10014
- Disagree: none found
- Level: advanced
- Flag: These are jurisdiction-specific (US and Canada) and are the sources' claims. Use them as examples, not exam facts.
- Best story: none

## TH41 Tune and own your alerts instead of adding more tools: an alert that fires into an empty inbox is no alert, and detection is the slow part
- Sub-topic: T17 (also T16, T18)
- Agree: 2 of 4. Notes: a:N55, b:N40. Urls: https://tcm-sec.com/nist-guidelines-for-incident-response-best-practices/, https://consilien.com/news/nist-incident-response-lifecycle-4-phases-explained
- Disagree: https://www.armorpoint.com/blog/a-step-by-step-guide-to-incident-response-practical-guidance-from-nist-sp-800-61 cites IBM's 277 days (207 to identify); consilien cites 241 days for 2025. Different report years.
- Level: core
- Flag: Use the newer 241-day IBM figure and label it as IBM's 2025 number.
- Best story: none

## TH42 Cover the hygiene basics first: patch everything, run firewalls and EDR, train staff on phishing, and keep an approved-software inventory
- Sub-topic: T17 (also T11, T18)
- Agree: 2 of 4. Notes: b:N46, d:N35. Urls: https://www.trendmicro.com/en_us/what-is/endpoint-security/types-of-malware.html, https://cloudsecurityalliance.org/articles/to-secure-the-ai-attack-surface-start-with-fundamental-cyber-hygiene
- Disagree: none found
- Level: foundation
- Best story: none

## TH43 Attach one AI example to every CC concept: poisoned training data is an integrity failure, model drift a continuity risk, AI bots are identities, and SIEM AI helps against alert fatigue
- Sub-topic: T18 (also T01, T02, T07, T09)
- Agree: 4 of 5. Notes: a:N55, a:N56, a:N57, b:N13, b:N33, b:N47. Urls: https://open-exam-prep.com/blog/isc2-cc-certified-in-cybersecurity-guide-2026, https://www.certcrush.app/blog/how-to-pass-isc2-cc-2026-4-week-study-plan, https://cyberexperts.com/isc2-cc-exam/, https://tcm-sec.com/nist-guidelines-for-incident-response-best-practices/
- Disagree: https://www.examcert.app/blog/isc2-cc-worth-it/: AI added in "late 2025".
- Level: foundation
- Flag: AI is not a sixth domain, and it arrived with the 1 September 2026 outline, not "late 2025". The per-domain AI placements come from secondary pages quoting the outline.
- Best story: An attacker feeds mislabeled images into a publicly updating classifier; the answer is "integrity". https://open-exam-prep.com/blog/isc2-cc-certified-in-cybersecurity-guide-2026

## TH44 Recognise prompt injection and data poisoning, and use the current (2025) OWASP Top 10 for LLM applications
- Sub-topic: T18 (also T02)
- Agree: 2 of 5. Notes: a:N57, b:N44, b:N45. Urls: https://cloudsecurityalliance.org/articles/to-secure-the-ai-attack-surface-start-with-fundamental-cyber-hygiene, https://open-exam-prep.com/blog/isc2-cc-certified-in-cybersecurity-guide-2026
- Disagree: https://cloudsecurityalliance.org/articles/to-secure-the-ai-attack-surface-start-with-fundamental-cyber-hygiene presents the 2023 OWASP list (insecure output handling, insecure plugin design, model theft, and so on) as current.
- Level: core
- Flag: Don't teach the 2023 OWASP LLM list. The 2025 list includes data and model poisoning, system prompt leakage, vector and embedding weaknesses, misinformation and unbounded consumption. No OWASP page is on disk, so name it lightly.
- Best story: none

## TH45 Inventory AI tools, allow only approved models and extensions, keep sensitive data out of public AI services, and give AI service accounts least privilege
- Sub-topic: T18 (also T09, T15, T17)
- Agree: 4 of 5. Notes: a:N37, a:N56, b:N13, b:N46, b:N47. Urls: https://cloudsecurityalliance.org/articles/to-secure-the-ai-attack-surface-start-with-fundamental-cyber-hygiene, https://cyberexperts.com/isc2-cc-exam/, https://open-exam-prep.com/blog/isc2-cc-certified-in-cybersecurity-guide-2026, https://www.certcrush.app/blog/how-to-pass-isc2-cc-2026-4-week-study-plan
- Disagree: none found
- Level: core
- Best story: Searching "AI" in the Firefox extension catalog returns over 2,000 results, and employees often don't know their input may reach a third party. https://cloudsecurityalliance.org/articles/to-secure-the-ai-attack-surface-start-with-fundamental-cyber-hygiene

---

## The big splits

1. **Which exam are we describing?** On the old side: https://www.examcert.app/blog/isc2-cc-worth-it/, https://trainingcamp.com/articles/isc2-cc-certification-guide-2026-exam-domains-cost-and-what-its-worth/ and https://stephenbernardombacisa.substack.com/p/reflections-and-tips-for-passing (old domains and weights, "100 questions", AI in "late 2025"). On the current side: https://www.certcrush.app/blog/isc2-cc-exam-changes-2026-sit-before-september-1, https://www.certcrush.app/blog/isc2-cc-domains-2026-new-exam-outline-weightings, https://www.certcrush.app/blog/how-to-pass-isc2-cc-2026-4-week-study-plan, https://open-exam-prep.com/blog/isc2-cc-certified-in-cybersecurity-guide-2026 and https://www.pocketprep.com/posts/isc2-cc-exam-blueprint-subjects-official-resources-and-faqs/ (CAT, 100 to 125 items, 24/17.3/20/21.3/17.3). It turns on whether the page predates 1 September 2026. The current side wins.
2. **Is the exam free?** https://stephenbernardombacisa.substack.com/p/reflections-and-tips-for-passing (free via 1MCC) vs https://trainingcamp.com/articles/isc2-cc-certification-guide-2026-exam-domains-cost-and-what-its-worth/, https://cyberexperts.com/isc2-cc-exam/ and https://www.examcert.app/blog/isc2-cc-worth-it/ (closed to new enrolments on 20 May 2026; $199 plus $50 a year). It turns on the date. Paid wins.
3. **Is NIST's four-phase IR cycle current?** https://tcm-sec.com/nist-guidelines-for-incident-response-best-practices/, https://www.armorpoint.com/blog/a-step-by-step-guide-to-incident-response-practical-guidance-from-nist-sp-800-61 and https://preyproject.com/blog/business-continuity-disaster-recovery-and-incident-response say yes. https://consilien.com/news/nist-incident-response-lifecycle-4-phases-explained and https://open-exam-prep.com/blog/isc2-cc-certified-in-cybersecurity-guide-2026 say Rev. 3 (April 2025) replaced it with the CSF 2.0 mapping. It turns on the gap between the classic teaching model and current NIST guidance. Teach it as "the classic Rev. 2 model".
4. **Password hygiene.** https://informationshield.com/2023/10/27/security-policies-standard-and-procedures-whats-the-difference (90-day forced resets) vs https://open-exam-prep.com/blog/isc2-cc-certified-in-cybersecurity-guide-2026 (NIST SP 800-63B: no rotation without compromise). Separately, https://www.20i.com/blog/how-encryption-works-from-hashing-to-modern-cryptography/ shows a salted SHA-256 example against its own bcrypt/Argon2 advice, which https://rippling.com/blog/hashing-vs-encryption shares. It turns on legacy habit vs current NIST guidance.
5. **Which plan is the umbrella, BCP or DRP?** https://cyber.gc.ca/en/guidance/improving-cyber-security-resilience-through-emergency-preparedness-planning-itsm10014 says both in different sections. https://preyproject.com/blog/business-continuity-disaster-recovery-and-incident-response, https://www.techtarget.com/cybersecurity/tip/Business-continuity-vs-disaster-recovery-vs-incident-response and the ISC2 framing make BC the broad keep-the-business-running plan and DR the IT part. Teach BCP as the umbrella.
6. **Which access control models count?** https://www.twingate.com/blog/other/access-control-models (MAC, DAC, RBAC, PAM; no ABAC) vs https://duo.com/learn/access-control-models and https://open-exam-prep.com/blog/isc2-cc-certified-in-cybersecurity-guide-2026 (DAC, MAC, RBAC, ABAC, plus rule-based). It turns on mixing up a privileged-account practice with an access model.
7. **IDS: detect or block?** https://www.csoonline.com/article/3667476/defense-in-depth-explained-layering-tools-and-processes-for-better-security.html and https://heimdalsecurity.com/blog/defense-in-depth-layers/ blur the line. https://open-exam-prep.com/blog/isc2-cc-certified-in-cybersecurity-guide-2026 says an IDS detects and an IPS blocks inline. It turns on loose vendor wording vs the textbook definition.
8. **Where you can sit the exam.** https://www.certcrush.app/blog/how-to-pass-isc2-cc-2026-4-week-study-plan says test centre or online proctoring; https://cyberexperts.com/isc2-cc-exam/ says test centres only. Unresolved: no ISC2 page is on disk.
9. **Is CC worth it, and who should skip it?** https://cyberexperts.com/isc2-cc-exam/ (Security+ is more respected), https://trainingcamp.com/articles/isc2-cc-certification-guide-2026-exam-domains-cost-and-what-its-worth/ (take CC first if you can do both), https://www.examcert.app/blog/isc2-cc-worth-it/ (3+ years in IT, skip it) and https://open-exam-prep.com/blog/isc2-cc-certified-in-cybersecurity-guide-2026 (skip only with years of security experience). It turns on the reader's background and local job market.
10. **How to study and for how long.** https://www.pocketprep.com/posts/isc2-cc-exam-blueprint-subjects-official-resources-and-faqs/ (baseline quiz first) vs https://trainingcamp.com/articles/isc2-cc-certification-guide-2026-exam-domains-cost-and-what-its-worth/ (practice only after a content pass). Hours range from 30 to 100 across certcrush, cyberexperts, trainingcamp and open-exam-prep. It turns on prior IT experience.
11. **How many MFA factor types?** https://www.isdecisions.com/en/glossary/mfa-factors (five, adding location and behaviour) vs https://duo.com/learn/access-control-models (the classic three). The classic three are what the exam tests.

## Coverage gaps

- **No official ISC2 outline, pricing or scheduling page is on disk** (only https://www.isc2.org/ethics). The domain weights, CAT format, fees, retake rules and AI placements all come from prep vendors quoting ISC2. Online vs test-centre delivery is unresolved, and so is whether the exam uses the Rev. 2 phases or the Rev. 3 CSF 2.0 wording.
- **Borderline evidence:** T10 Networking (M=3) and T14 Cryptography (M=3) are at the minimum. T05 Ethics, T11 Threats, T15 Data security and T17 Security operations each have only 4 pages.
- **T02:** no source properly defines non-repudiation, authenticity or privacy as separate principles. The one page touching privacy (coursera) gets it wrong.
- **T11:** phishing variants (spear phishing, whaling, smishing, vishing), social engineering, man-in-the-middle, SQL injection and XSS beyond a one-line mention, DDoS types and ransomware mechanics. The topics.md title promises these, and no page covers them in depth.
- **T13:** deployment models (public, private, hybrid, community), the essential cloud characteristics and zero trust architecture appear only in passing. The outline names cloud and zero trust as the biggest new gap.
- **T15:** data classification levels and labelling, the security data lifecycle (create, store, use, share, archive, destroy), retention policy design, and sanitisation methods (clearing, purging, physical destruction) beyond one acronym list.
- **T17:** logging and SIEM basics, configuration and hardening baselines, change management, patch management process, and security awareness programme design and metrics. The new outline puts awareness and its measurement in Domain 2.
- **New-outline items no source teaches:** security testing (red, blue and purple teams; vulnerability scanning; static and dynamic analysis; threat modelling; physical penetration tests), threat intelligence, governance metrics (KRIs, dashboards, scorecards) and quantum-resistant cryptography are named as new but never explained.
- **Also uncovered:** PKI, certificates and VPN basics (only a flagged heimdal line), and physical security beyond one mantrap/bollard note.
- **T18:** AI content comes only from prep vendors and a Tenable-authored article. There is no OWASP 2025 or NIST AI RMF page, and nothing on AI-driven phishing, AI "impossible travel" detection, or isolated AI dev environments beyond a list.
