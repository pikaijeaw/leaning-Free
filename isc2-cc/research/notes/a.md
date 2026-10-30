# Notes: batch a
Pages read: 10. With notes: 10. Skipped: 0 (every page had teachable content; several are vendor marketing, flagged under Bias).

## Outdated or wrong claims flagged (read before using any note)
- examcert.app (https://www.examcert.app/blog/isc2-cc-worth-it/) is OUTDATED on the exam: it lists the old domains and weights (Security Principles 26%, BC/DR/IR 10%, Access Control 22%, Network Security 24%, Security Operations 18%), says "100 multiple-choice questions", and dates the AI fold-in to "late 2025". Under the 1 September 2026 outline the exam is CAT, 100 to 125 items, five renamed domains (24 / 17.3 / 20 / 21.3 / 17.3). Its study plan ("Week 5 BC/DR/IR 10%, do not overinvest") is now bad advice. Its cost and value points still hold.
- tcm-sec.com (https://tcm-sec.com/nist-guidelines-for-incident-response-best-practices/) cites NIST SP 800-61 Rev. 2 as current. Rev. 3 (April 2025) supersedes it and is organized around CSF 2.0 (per open-exam-prep). The four Rev. 2 phases are still what most CC courses teach, so use them, but say "Rev. 2 model".
- informationshield.com uses "enforces password resets every 90 days" as a model technical control. Current NIST SP 800-63B guidance drops forced periodic rotation without sign of compromise (open-exam-prep). Fine as an example of "technical control", not as password advice.
- heimdalsecurity.com has technical slips: calls hashing "a cipher" (hashing is not encryption and has no key); suggests RSA for encryption at rest (bulk data at rest uses symmetric AES; RSA protects keys); describes IDS/IPS as "query filtering at the level of the DNS" (that is their DNS-filtering product, not what IDS/IPS means); says a VPN "protects against external cyberattacks" (it encrypts the tunnel; it does not stop malware or phishing).
- 20i.com is accurate but shows a salted SHA-256 example right after saying SHA-256 is too fast for passwords; the course should say salt plus a slow password hash (bcrypt, Argon2).
- No page in this batch offers a still-valid free exam. Three pages (open-exam-prep, certcrush, examcert) correctly say 1MCC closed to new participants on 20 May 2026; unexpired codes must be used by 31 December 2026.

## T01 Exam format, the 2026 outline change, how people prepare, cost and value
- a:N1. New outline effective 1 September 2026: Security Principles 24%, Security Governance 17.3%, IAM Concepts 20%, Networking and Cloud Security Concepts 21.3%, Security Operations and Incident Response 17.3%. Old outline was 26 / 10 / 22 / 24 / 18 under different names.
  - Source: https://www.certcrush.app/blog/isc2-cc-exam-changes-2026-sit-before-september-1  Quote: "three of the five domains were renamed, the standalone business continuity domain was folded into a new Security Governance domain"
  - Kind: number
  - Level: foundation
  - Bias: sells a CC practice course
- a:N2. Where old topics moved: BC/DR into Domain 2 Security Governance (under "redundancy"); incident response into Domain 5; physical controls in Domain 1; physical penetration testing in Domain 5; cloud named in Domain 4; security awareness and measuring effectiveness named in Domain 2.
  - Source: https://open-exam-prep.com/blog/isc2-cc-certified-in-cybersecurity-guide-2026  Quote: "It is not a light refresh: the domain names and weights changed."
  - Kind: definition
  - Level: foundation
  - Also: T07
  - Bias: sells practice questions and an AI tutor
- a:N3. The weightings flattened: old gap between biggest and smallest domain was 16 points, new gap under 7. Rule of thumb: there is no small domain left to skip.
  - Source: https://www.certcrush.app/blog/isc2-cc-exam-changes-2026-sit-before-september-1  Quote: "There is no longer a 10% domain you can afford to skim."
  - Kind: rule of thumb
  - Level: foundation
  - Bias: sells a CC practice course
- a:N4. If you studied the old outline, add four things: cloud security and zero trust (biggest gap), identity lifecycle (joiner, mover, leaver, including non-human accounts), GRC planning plus awareness plus metrics, and AI framing across all domains. Old question banks over-train network security and inflate your score.
  - Source: https://www.certcrush.app/blog/isc2-cc-exam-changes-2026-sit-before-september-1  Quote: "Your practice score will look better than your readiness is."
  - Kind: mistake
  - Level: foundation
  - Bias: sells a CC practice course
- a:N5. Format (their claim, citing ISC2): Computerized Adaptive Testing, 100 to 125 items, 2 hours, pass at 700 of 1000. No going back to earlier questions. About one minute per item. Older guides that say a fixed 100-question paper are wrong for the current exam.
  - Source: https://open-exam-prep.com/blog/isc2-cc-certified-in-cybersecurity-guide-2026  Quote: "ISC2 exams do not let you skip a question and return to it later."
  - Kind: number
  - Level: foundation
  - Bias: sells practice questions
- a:N6. Cost after 1MCC: 1MCC closed to new participants 20 May 2026; unexpired codes must be used by 31 December 2026. Now US$199 exam plus US$50 annual maintenance fee, so real year one is about $249, and about $449 over five years (their claim).
  - Source: https://www.examcert.app/blog/isc2-cc-worth-it/  Quote: "The CC is a subscription, not a purchase."
  - Kind: number
  - Level: foundation
  - Bias: sells practice tests; also see outdated-outline flag above
- a:N7. After passing: within nine months agree to the Code of Ethics and submit the application, pay the first $50 AMF; no endorsement needed. Maintain with 45 CPEs per 3-year cycle (15 a year recommended). Miss the 9-month window and you retake the exam.
  - Source: https://open-exam-prep.com/blog/isc2-cc-certified-in-cybersecurity-guide-2026  Quote: "If you do not submit the application within nine months, you must retake the exam."
  - Kind: rule of thumb
  - Level: foundation
  - Also: T05

- a:N9. Honest value framing: CC is a "door-knock, not a door-opener". It proves intent and gets past resume screens; it is not a skills badge, gives no CISSP experience credit, and a help-desk year plus a home lab beats it on a CV. Worth it if starting from zero or someone else pays.
  - Source: https://www.examcert.app/blog/isc2-cc-worth-it/  Quote: "the CC is a door-knock, not a door-opener"
  - Kind: rule of thumb
  - Level: foundation
  - Bias: sells practice tests

- a:N11. Biggest test-taking pitfall: overthinking scenario questions. Several options are technically correct; pick the one that hits the root cause or follows the documented process. Treat it as a concepts exam: knowing why a firewall sits at the edge, not how to configure one.
  - Source: https://open-exam-prep.com/blog/isc2-cc-certified-in-cybersecurity-guide-2026  Quote: "CC is a concepts exam."
  - Kind: technique
  - Level: foundation
- a:N12. Study routine and readiness test: 45 min reading, 30 min flashcards, 30 min practice questions daily; do not book until consistently scoring 80%+ on practice sets. 7-week beginner track is about 44 to 58 hours (their claim). Avoid dumps: they break the Code of Ethics you are tested on.
  - Source: https://open-exam-prep.com/blog/isc2-cc-certified-in-cybersecurity-guide-2026  Quote: "If you are not consistently scoring 80%+ on practice sets, you are probably not ready."
  - Kind: test
  - Level: foundation

## T02 CIA triad and core principles
- a:N14. Map controls to properties: encryption protects confidentiality, hashing protects integrity, redundancy protects availability. Drill: stolen laptop with unencrypted data = confidentiality lost; encryption (preventive technical control) would have stopped it.
  - Source: https://open-exam-prep.com/blog/isc2-cc-certified-in-cybersecurity-guide-2026  Quote: "encryption → confidentiality; hashing → integrity; redundancy → availability"
  - Kind: test
  - Level: foundation
  - Also: T14

## T03 Risk management
- a:N15. Four treatments: mitigate (most used), accept (overused when nobody owns the risk), transfer (underused), avoid (rare, often misapplied). Applied after risks are assessed on likelihood and impact.
  - Source: https://stacker.com/stories/small-business/4-risk-treatment-strategies-separate-proactive-businesses-reactive-ones  Quote: "Accept is frequently overused due to unclear ownership or limited guidance."
  - Kind: rule of thumb
  - Level: core
  - Bias: written by Vanta, a GRC software vendor; ends by pitching risk software
- a:N16. Acceptance test: acceptance is only valid if the cost of mitigation clearly exceeds the impact and the reason is written in the risk register. No written "why" means unmanaged risk, not acceptance.
  - Source: https://stacker.com/stories/small-business/4-risk-treatment-strategies-separate-proactive-businesses-reactive-ones  Quote: "it's not risk acceptance, but rather unmanaged risk"
  - Kind: test
  - Level: core
  - Bias: Vanta
- a:N17. Transfer moves financial impact, never accountability. Cyber insurance or a cloud provider does not absolve you; under GDPR the data controller stays responsible even when processing is outsourced. Transfer does not lower likelihood.
  - Source: https://stacker.com/stories/small-business/4-risk-treatment-strategies-separate-proactive-businesses-reactive-ones  Quote: "you can never outsource the ultimate accountability for your customers' data"
  - Kind: mistake
  - Level: core
  - Also: T13
  - Bias: Vanta
- a:N18. Avoidance example: decommission a legacy feature that still collects PII nobody uses; delete the data and the breach risk is gone. Avoidance costs growth, so save it for high-impact risks.
  - Source: https://stacker.com/stories/small-business/4-risk-treatment-strategies-separate-proactive-businesses-reactive-ones  Quote: "deleting a dataset associated with the risk"
  - Kind: story
  - Level: core
  - Also: T15
  - Bias: Vanta
- a:N19. Treatments layer: mitigate a high-probability vulnerability to lower severity, transfer the remaining financial exposure to an insurer, formally accept what is left inside tolerance (residual risk).
  - Source: https://stacker.com/stories/small-business/4-risk-treatment-strategies-separate-proactive-businesses-reactive-ones  Quote: "formally accept whatever remains within your tolerance threshold"
  - Kind: technique
  - Level: core
  - Bias: Vanta
- a:N20. Risk appetite = what leadership is willing to pursue; risk tolerance = acceptable variation or threshold within it. Inside both, you may accept; outside, you treat. Threat exploits vulnerability to harm an asset.
  - Source: https://open-exam-prep.com/blog/isc2-cc-certified-in-cybersecurity-guide-2026  Quote: "A threat exploits a vulnerability to harm an asset."
  - Kind: definition
  - Level: foundation

## T04 Security controls and defense in depth
- a:N21. Three control layers with examples: physical (CCTV, fences, guards, guard dogs, locked doors), technical (antivirus, firewall, disk encryption, authentication, biometrics), administrative (data handling procedures, hiring practices, confidentiality policies).
  - Source: https://heimdalsecurity.com/blog/defense-in-depth-layers/  Quote: "physical controls, technical controls, and administrative controls"
  - Kind: definition
  - Level: foundation
  - Bias: Heimdal sells PAM and DNS filtering; see technical-slips flag
- a:N22. Defense in depth comes from a military idea: slow an attack with several lines instead of one big formation, so one failed system is covered by the next. Their minimum: at least two layers, aim for many.
  - Source: https://heimdalsecurity.com/blog/defense-in-depth-layers/  Quote: "slowing down an attack with various lines of defense instead of focusing resources on one large formation"
  - Kind: story
  - Level: foundation
  - Bias: Heimdal vendor
- a:N23. Control functions besides type: preventive, detective, corrective, deterrent, compensating, recovery. Physical examples: lighting and fences deter, bollards and turnstiles block, mantraps (access control vestibules) stop tailgating, guards and visitor logs compensate.
  - Source: https://open-exam-prep.com/blog/isc2-cc-certified-in-cybersecurity-guide-2026  Quote: "access control vestibules (mantraps) against tailgating"
  - Kind: definition
  - Level: core

## T05 ISC2 Code of Ethics
- a:N25. Four canons in order: protect society, act honorably, provide diligent service to principals, advance the profession. When canons conflict, the earlier one wins.
  - Source: https://open-exam-prep.com/blog/isc2-cc-certified-in-cybersecurity-guide-2026  Quote: "When canons conflict, the earlier one wins."
  - Kind: rule of thumb
  - Level: foundation

## T06 Governance: policies, standards, procedures, guidelines; regulations
- a:N26. Hierarchy: policy (mandatory, broad, from senior management, lasts years) then standard (mandatory, specific) then procedure (step by step) then guideline (recommended, optional, open to interpretation).
  - Source: https://frsecure.com/blog/differentiating-between-policies-standards-procedures-and-guidelines/  Quote: "Guidelines, by nature, should open to interpretation and do not need to be followed to the letter."
  - Kind: definition
  - Level: foundation
  - Bias: security consultancy, light CTA
- a:N27. Worked chain: Policy "Company X must change all default passwords before systems go into production." Standard "Baseline Configuration Standard for Windows Servers" gives the detail per platform. Policies say what and who, never name a specific technology.
  - Source: https://informationshield.com/2023/10/27/security-policies-standard-and-procedures-whats-the-difference  Quote: "information security policies should not refer to any specific technical platform"
  - Kind: template
  - Level: core
  - Bias: sells policy templates
- a:N28. Mistake: vague policy language. "Users should consider security when accessing the internet" cannot be enforced or measured. Policies use "must".
  - Source: https://informationshield.com/2023/10/27/security-policies-standard-and-procedures-whats-the-difference  Quote: "Many organizations make the mistake of using vague language in policy statements."
  - Kind: mistake
  - Level: foundation
  - Bias: sells policy templates
- a:N29. Procedure example, employee termination: manager notifies HR and IT; HR schedules exit interview and has badge disabled; IT suspends user ID and access; manager and HR collect company property. Procedures exist where people, not just tech, must enforce a control.
  - Source: https://informationshield.com/2023/10/27/security-policies-standard-and-procedures-whats-the-difference  Quote: "IT suspends User ID and system access"
  - Kind: template
  - Level: foundation
  - Also: T09
  - Bias: sells policy templates

- a:N31. Frameworks sit above policies (NIST SP 800-53, NIST CSF, PCI DSS, ISO 27001/27002, CMMC). PCI DSS is an industry standard, not a law; GDPR (EU privacy) and HIPAA (US health) are laws.
  - Source: https://open-exam-prep.com/blog/isc2-cc-certified-in-cybersecurity-guide-2026  Quote: "PCI DSS for payment cards, an industry standard rather than a law"
  - Kind: definition
  - Level: core

## T07 Business continuity and disaster recovery
- a:N32. BC keeps the business running (people, processes, sites); DR restores IT. RTO = how fast back; RPO = how much data loss is tolerable; MTD = ceiling before unacceptable harm, and RTO must be shorter than MTD. BIA comes before the BC/DR plan.
  - Source: https://open-exam-prep.com/blog/isc2-cc-certified-in-cybersecurity-guide-2026  Quote: "RTO must be shorter than MTD"
  - Kind: definition
  - Level: core
- a:N33. Backups: full, incremental (since last backup of any type; fast to make, slow to restore), differential (since last full). 3-2-1 rule: 3 copies, 2 media, 1 off-site. Sites: hot (ready, costly), warm (partial), cold (space and power only). Exercises least to most realistic: checklist, walk-through, tabletop, simulation, parallel, full interruption.
  - Source: https://open-exam-prep.com/blog/isc2-cc-certified-in-cybersecurity-guide-2026  Quote: "3 copies, 2 different media, 1 off-site"
  - Kind: rule of thumb
  - Level: core
- a:N34. Cheapest ransomware recovery is a recent, working, tested backup; test backups before you restore from them.
  - Source: https://tcm-sec.com/nist-guidelines-for-incident-response-best-practices/  Quote: "the best (and cheapest) way to recover from a ransomware incident is to have recent, working backups"
  - Kind: rule of thumb
  - Level: foundation
  - Also: T16

## T08 Authentication and MFA
- a:N35. MFA means factors from at least two different categories (know, have, are). Two passwords is not MFA. Passwords: length beats forced complexity.
  - Source: https://open-exam-prep.com/blog/isc2-cc-certified-in-cybersecurity-guide-2026  Quote: "two passwords are not MFA"
  - Kind: test
  - Level: foundation

## T09 Access control models, least privilege, separation of duties
- a:N36. Model-matching drill: "Finance department can read payroll" = RBAC; "Top Secret clearance only" = MAC; "department = Sales AND 9 to 5 AND managed device" = ABAC; owner sets file shares = DAC; firewall ACL = rule-based.
  - Source: https://open-exam-prep.com/blog/isc2-cc-certified-in-cybersecurity-guide-2026  Quote: "Only users with a Top Secret clearance can read this file → MAC"
  - Kind: test
  - Level: core
- a:N37. Separation of duties example: one person creates a vendor, another approves payment. Identity lifecycle: provision, review access periodically, deprovision; a mover loses the old role's access.
  - Source: https://open-exam-prep.com/blog/isc2-cc-certified-in-cybersecurity-guide-2026  Quote: "one person creates a vendor, another approves payment"
  - Kind: rule of thumb
  - Level: foundation
  - Also: T18 (AI bots and service accounts go through the same lifecycle)

## T10 Networking basics
- a:N38. OSI mnemonic bottom up: Please Do Not Throw Sausage Pizza Away. Switches/MAC at L2, routers/IP at L3, TCP/UDP ports at L4. Ports: 22 SSH, 23 Telnet (insecure), 25 SMTP, 53 DNS, 80 HTTP, 443 HTTPS, 3389 RDP. TCP handshake SYN, SYN/ACK, ACK; UDP connectionless. Private ranges 10/8, 172.16/12, 192.168/16.
  - Source: https://open-exam-prep.com/blog/isc2-cc-certified-in-cybersecurity-guide-2026  Quote: "Please Do Not Throw Sausage Pizza Away"
  - Kind: rule of thumb
  - Level: foundation

## T11 Threats and attacks
- a:N39. Trojan vs worm: a trojan must trick a user into running it; a worm spreads by itself through unpatched holes. WannaCry (2017) used EternalBlue and infected over 300,000 machines in days (their claim).
  - Source: https://cybelangel.com/blog/20-common-types-of-malware/  Quote: "Unlike trojans, they don't need to trick users."
  - Kind: story
  - Level: foundation
  - Bias: CybelAngel sells external threat intelligence; ends with a demo CTA
- a:N40. Logic bomb story: in 2002 a disgruntled UBS systems administrator planted code that crashed servers on trading days, costing over $3 million (their claim). Insider threat plus separation of duties and code review.
  - Source: https://cybelangel.com/blog/20-common-types-of-malware/  Quote: "a disgruntled UBS Systems administrator planted a logic bomb"
  - Kind: story
  - Level: foundation
  - Also: T09
  - Bias: CybelAngel vendor
- a:N41. Botnet story: Mirai took over hundreds of thousands of IoT devices (weak default credentials) and its 2016 DDoS knocked Twitter, Netflix and Reddit offline (their claim). Defense: change default passwords, patch, watch outbound traffic to command-and-control.
  - Source: https://cybelangel.com/blog/20-common-types-of-malware/  Quote: "knocked major sites like Twitter, Netflix, and Reddit offline in 2016"
  - Kind: story
  - Level: foundation
  - Also: T12
  - Bias: CybelAngel vendor
- a:N42. Rootkits and bootkits hide below the OS; rebuilding from known-good backups may be the only safe cleanup; UEFI Secure Boot blocks bootkits. Story: Sony BMG shipped a rootkit on music CDs in 2005 for copy protection, which attackers then used to hide malware.
  - Source: https://cybelangel.com/blog/20-common-types-of-malware/  Quote: "Sony BMG included a rootkit in its music CDs"
  - Kind: story
  - Level: core
  - Bias: CybelAngel vendor
- a:N43. Supply chain backdoor: SolarWinds SUNBURST rode inside a signed Orion software update and gave access to US agencies for months. Macro virus: Melissa (1999) mailed itself to the first 50 Outlook contacts. Polymorphic: Storm Worm changed its code about every 30 minutes, so signature tools fall behind; use behavior-based detection.
  - Source: https://cybelangel.com/blog/20-common-types-of-malware/  Quote: "inserted a backdoor known as SUNBURST into the Orion software update"
  - Kind: story
  - Level: core
  - Bias: CybelAngel vendor

## T12 Network defenses
- a:N45. IDS detects and alerts; IPS sits inline and blocks; both can be signature or anomaly based. Firewalls: stateless, stateful, next-gen. Segmentation tools: zones, VLANs, micro-segmentation, DMZ (screened subnet) for public servers; Zero Trust is "never trust, always verify".
  - Source: https://open-exam-prep.com/blog/isc2-cc-certified-in-cybersecurity-guide-2026  Quote: "IDS detects and alerts, IPS blocks inline"
  - Kind: definition
  - Level: foundation
  - Also: T13

## T14 Cryptography basics
- a:N47. Symmetric = one shared key, fast, bulk data (AES); problem is getting the key to the other side. Asymmetric = public/private pair, slower, solves key distribution. TLS uses both: asymmetric in the handshake to authenticate and agree session keys, then fast symmetric encryption for the data.
  - Source: https://www.20i.com/blog/how-encryption-works-from-hashing-to-modern-cryptography/  Quote: "The connection then uses fast symmetric authenticated encryption to protect application data."
  - Kind: definition
  - Level: foundation
  - Bias: web host, light product mentions
- a:N48. Avalanche effect demo: hello123 and hello124 give completely different SHA-256 digests (6ca13d52... vs 0adab7ae...). Hash = any input, fixed-length output, one way; protects integrity, not confidentiality.
  - Source: https://www.20i.com/blog/how-encryption-works-from-hashing-to-modern-cryptography/  Quote: "Even a tiny change in the input drastically changes the hash output."
  - Kind: test
  - Level: foundation
- a:N49. MD5 (128-bit) and SHA-1 (160-bit) are broken by collision attacks (SHAttered). SHA-256 is fine for integrity and signatures but too fast for passwords; store passwords with a unique salt and a slow hash like bcrypt or Argon2. Salt defeats rainbow tables and makes two users with the same password have different hashes.
  - Source: https://www.20i.com/blog/how-encryption-works-from-hashing-to-modern-cryptography/  Quote: "it's not suitable for storing passwords, as it is too fast"
  - Kind: rule of thumb
  - Level: core
  - Also: T08
- a:N50. Signing rule: sign with your private key, others verify with your public key; encrypt to someone with their public key, they decrypt with their private key. Storing a password = salted hashing, not encryption. Quantum-resistant cryptography is named in the new outline.
  - Source: https://open-exam-prep.com/blog/isc2-cc-certified-in-cybersecurity-guide-2026  Quote: "the private key signs and the public key verifies"
  - Kind: test
  - Level: core

## T16 Incident response lifecycle (NIST)
- a:N51. NIST SP 800-61 Rev. 2 four phases: Preparation; Detection and Analysis; Containment, Eradication and Recovery; Post-Incident Activity. SANS splits the same into six (Preparation, Identification, Containment, Eradication, Recovery, Lessons Learned). Rev. 3 (April 2025) supersedes Rev. 2.
  - Source: https://tcm-sec.com/nist-guidelines-for-incident-response-best-practices/  Quote: "SANS breaks down some of NIST's phases into more granular steps"
  - Kind: definition
  - Level: foundation
  - Bias: TCM sells SOC training; also see outdated flag
- a:N52. Preparation includes out-of-band communication: if Teams or Slack is compromised by the attacker, fall back to a pre-agreed separate channel. Responders keep a "jump kit": spare laptop, memory capture and disk imaging tools, write blockers, chain of custody forms, evidence bags.
  - Source: https://tcm-sec.com/nist-guidelines-for-incident-response-best-practices/  Quote: "out-of-band channels in case the primary means of communication is lost or compromised"
  - Kind: technique
  - Level: core
- a:N53. Containment balances three things: stop the threat, preserve evidence, keep business running (e.g. isolate infected hosts by segmentation, reset a compromised account's credentials). Eradication without fixing the root vulnerability means reinfection even after restoring from backup. First priority in any incident is life and safety.
  - Source: https://tcm-sec.com/nist-guidelines-for-incident-response-best-practices/  Quote: "balances stopping the threat, preserving evidence, and maintaining business operations"
  - Kind: rule of thumb
  - Level: core
- a:N54. Post-incident: hold a lessons-learned meeting soon after, write a post-mortem with timeline and damage estimate; findings justify budget. "Never let a good crisis go to waste."
  - Source: https://tcm-sec.com/nist-guidelines-for-incident-response-best-practices/  Quote: "Never let a good crisis go to waste."
  - Kind: technique
  - Level: foundation

## T17 Security operations
- a:N55. Alert fatigue: the instinct to add more monitoring tools is usually wrong; tune signal to noise, integrate existing tools, set baselines, and give staff a clear channel to report odd things.
  - Source: https://tcm-sec.com/nist-guidelines-for-incident-response-best-practices/  Quote: "a common but misguided reaction is to add more data"
  - Kind: mistake
  - Level: core
  - Also: T16, T18 (SIEM using AI to cut alert fatigue is in the new outline)

## T18 AI security risks
- a:N56. Where ISC2 places AI in the new outline (as reported): model poisoning and training data (D1 integrity), AI governance and non-bias (D1), AI-driven phishing (D2 awareness), model drift and backing up AI configs and datasets (D2 BC/DR), AI KRIs (D2), AI bots and service accounts in identity lifecycle (D3), AI "impossible travel" detection (D3), AI firewalls/IDS and isolated AI dev environments (D4), shared responsibility for AI in the cloud (D4), SIEM AI vs alert fatigue (D5), data leakage to public AI services (D5).
  - Source: https://open-exam-prep.com/blog/isc2-cc-certified-in-cybersecurity-guide-2026  Quote: "integrated foundational AI concepts across all five domains"
  - Kind: definition
  - Level: foundation
  - Also: T01
- a:N57. Poisoning drill: attacker feeds mislabeled images into a publicly updating classifier; integrity is violated; controls are data validation, access control on the training pipeline, provenance logging. AI content is recognition, not engineering.
  - Source: https://open-exam-prep.com/blog/isc2-cc-certified-in-cybersecurity-guide-2026  Quote: "Answer: Integrity"
  - Kind: test
  - Level: core
  - Also: T02

## Disagreements seen
- Exam format and weights: examcert.app says 100 linear questions and the old 26/10/22/24/18 domains; certcrush.app and open-exam-prep.com say CAT, 100 to 125 items, 24/17.3/20/21.3/17.3. The latter match the 1 September 2026 outline. (https://www.examcert.app/blog/isc2-cc-worth-it/ vs https://www.certcrush.app/blog/isc2-cc-exam-changes-2026-sit-before-september-1)
- When AI arrived: examcert says the outline was refreshed "in late 2025" to add AI; certcrush and open-exam-prep tie the AI thread to the 1 September 2026 outline.
- Password rotation: informationshield.com holds up 90-day forced resets as a model control; open-exam-prep.com says NIST SP 800-63B no longer calls for periodic rotation without signs of compromise.
- IR standard: tcm-sec.com presents NIST SP 800-61 Rev. 2 as current; open-exam-prep.com notes Rev. 3 (April 2025) supersedes it.
- Who should skip CC: examcert says anyone with 3+ years IT should go straight to SSCP or even CISSP (as Associate); open-exam-prep says skip only with several years of hands-on security experience.

## Best stories
- Mirai botnet: hijacked IoT cameras and routers on default passwords and knocked Twitter, Netflix and Reddit offline in 2016. https://cybelangel.com/blog/20-common-types-of-malware/
- UBS logic bomb, 2002: a disgruntled admin's hidden code crashed trading servers, over $3 million in damage. https://cybelangel.com/blog/20-common-types-of-malware/
- Sony BMG rootkit, 2005: copy protection on music CDs secretly installed a rootkit that malware authors then hid behind. https://cybelangel.com/blog/20-common-types-of-malware/
- The compromised Slack: during an incident the attacker is inside your chat tool, so responders need a pre-agreed out-of-band channel. https://tcm-sec.com/nist-guidelines-for-incident-response-best-practices/
- The forgotten PII feature: a company avoids breach risk entirely by deleting a legacy feature and the unused personal data it collected. https://stacker.com/stories/small-business/4-risk-treatment-strategies-separate-proactive-businesses-reactive-ones
