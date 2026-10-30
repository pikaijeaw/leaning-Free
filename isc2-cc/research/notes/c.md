# Notes: batch c
Pages read: 10. With notes: 9. Skipped: 1 (learn.microsoft.com cloud service types "Summary" page is only a list of learning objectives and Copilot prompts, nothing teachable).

Flags for the September 2026 outline, up front:
- Pocket Prep (dated 1 October 2026) is current: five new domains and weights match topics.md. No outdated claims seen. It is a prep vendor page.
- cyber.gc.ca (January 2026) teaches the 4 step NIST SP 800-61 lifecycle. SP 800-61 Rev. 3 (April 2025) replaced that cycle with a mapping to CSF 2.0 functions. The 4 phases are still the classic CC answer, but say "classic NIST cycle", not "current NIST".
- cyber.gc.ca contradicts itself on whether BCP or DRP is the bigger plan (see Disagreements).
- dev.to lists switches as an OSI Layer 1 example. Wrong: switches work at Layer 2 (MAC addresses).
- isdecisions.com calls biometrics "difficult to replicate"; fine at this level, but biometrics cannot be changed once leaked, worth one line.

## T01 Exam format, the 2026 outline change, how people prepare, cost and value
- c:N1. Exam format under the 2026 outline: 100 to 125 items, computerized adaptive testing, 2 hours, pass at 700 of 1,000 scaled points, Pearson VUE, preliminary pass or fail at the test center. Format, time and passing score did not change with the new outline (their claim).
  - Source: https://www.pocketprep.com/posts/isc2-cc-exam-blueprint-subjects-official-resources-and-faqs/  Quote: "the format, time limit, and passing score stayed the same"
  - Kind: number
  - Level: foundation
  - Bias: Pocket Prep sells a CC question bank (800 questions).
- c:N2. Fee is US $199 standard registration; after passing you apply, agree to the Code of Ethics and pay a US $50 annual maintenance fee within nine months or you must retake the exam. Minimum age 16, no experience required. Retakes cost full price unless you bought Peace of Mind Protection (their claim). No "free exam" offer is mentioned, consistent with paid exams in 2026.
  - Source: https://www.pocketprep.com/posts/isc2-cc-exam-blueprint-subjects-official-resources-and-faqs/  Quote: "within nine months of passing, or you'll need to retake the exam"
  - Kind: number
  - Level: foundation
  - Also: T05
  - Bias: prep vendor.
- c:N3. What changed on 1 September 2026: a new Security Governance domain, a dedicated IAM domain, cloud folded into networking, incident response moved into security operations, and BC/DR moved under governance as "redundancy". AI concepts appear across all five domains. Weights: 24, 17.3, 20, 21.3, 17.3 percent.
  - Source: https://www.pocketprep.com/posts/isc2-cc-exam-blueprint-subjects-official-resources-and-faqs/  Quote: "Business continuity and disaster recovery didn't disappear. They now sit under governance as "redundancy.""
  - Kind: definition
  - Level: foundation
  - Also: T07
  - Bias: prep vendor, but quotes the official outline.
- c:N4. Study method: take a mixed baseline quiz first, weight time by domain (Principles plus Networking and Cloud are about 45 percent), tag every missed question with its outline number, add time for new content (GRC, metrics, identity life cycle, cloud, threat intelligence, security testing) if using pre-2026 books, then return to mixed practice because the adaptive exam needs steady performance across domains.
  - Source: https://www.pocketprep.com/posts/isc2-cc-exam-blueprint-subjects-official-resources-and-faqs/  Quote: "Map every miss to an objective."
  - Kind: technique
  - Level: foundation
  - Bias: prep vendor; the method naturally favors buying practice questions.
- c:N5. Any study guide or video course published before 2026 was written for the old outline; use the new blueprint to fill gaps. Two time facts for pacing: at 125 items in 120 minutes you get just under a minute per item, and scenario wording, not time, is the usual problem (their claim).
  - Source: https://www.pocketprep.com/posts/isc2-cc-exam-blueprint-subjects-official-resources-and-faqs/  Quote: "Accuracy on scenario wording is."
  - Kind: rule of thumb
  - Level: foundation
  - Bias: prep vendor.
- c:N6. Sample question shapes for the new domains: which metric best shows phishing training is working (Governance); who patches the OS in IaaS (the customer); which architecture trusts no user or device by default (Zero Trust).
  - Source: https://www.pocketprep.com/posts/isc2-cc-exam-blueprint-subjects-official-resources-and-faqs/  Quote: "who is responsible for patching the operating system in an IaaS deployment (the customer)"
  - Kind: test
  - Level: core
  - Also: T13
  - Bias: prep vendor.

## T04 Security controls: physical, technical, administrative; defense in depth
- c:N7. Defense in depth assumes every control will fail. The goal is not to make a breach impossible but "slow, loud, and expensive" so detection and response have time to act.
  - Source: https://cyberdefenders.org/cybersecurity-glossary/defense-in-depth/  Quote: "make it slow, loud, and expensive"
  - Kind: rule of thumb
  - Level: foundation
  - Bias: CyberDefenders sells blue team training labs; glossary page is not a hard sell.
- c:N8. Two properties make layering work: redundancy (more than one control on the same asset) and diversity (layers fail to different attacks). A password and a hardware token both guard a login but fail to different attacks. Buying a second tool that does the same job adds cost and alerts, not depth.
  - Source: https://cyberdefenders.org/cybersecurity-glossary/defense-in-depth/  Quote: "Depth comes from controls that fail to different attacks, not from duplicates."
  - Kind: rule of thumb
  - Level: core
- c:N9. The three control categories with examples. Physical: locked server rooms, badges, cameras, guards, hardware destruction. Technical: firewalls, IDS/IPS, EDR, encryption, authentication. Administrative: policies, awareness training, IR plans, change management, hiring and offboarding. Categories are not ranked; a program with no training fails the moment a user is phished.
  - Source: https://cyberdefenders.org/cybersecurity-glossary/defense-in-depth/  Quote: "A network control means nothing if an attacker can walk out with the disk."
  - Kind: definition
  - Level: foundation
- c:N10. The standard layers, outside in: perimeter (firewalls, VPN), network (segmentation, IDS), endpoint (EDR, antivirus, hardening), application (patching, input validation, WAF), identity and access (MFA, least privilege), data (encryption, backups, DLP).
  - Source: https://cyberdefenders.org/cybersecurity-glossary/defense-in-depth/  Quote: "It is the first filter, not the last line."
  - Kind: definition
  - Level: foundation
  - Also: T12
- c:N11. Story: trace one phishing attack through the layers. Training cuts the click rate, an email gateway strips most lures, MFA blocks the stolen password, segmentation stops a direct path to the database, EDR flags lateral movement, a patched app resists the exploit, encrypted and logged data makes exfiltration slow and visible. No single control stopped it; the cumulative delay gave the SOC time.
  - Source: https://cyberdefenders.org/cybersecurity-glossary/defense-in-depth/  Quote: "No single control stopped the attack in this chain."
  - Kind: story
  - Level: foundation
  - Also: T11
- c:N12. Test for a weak layer: for each control, ask what happens when it is bypassed. If the answer is "nothing else catches it", that control is a single point of failure.
  - Source: https://cyberdefenders.org/cybersecurity-glossary/defense-in-depth/  Quote: "a single point of failure wearing a costume"
  - Kind: test
  - Level: core
- c:N13. Defense in depth vs layered security vs zero trust. Layered security usually means stacking technical tools; defense in depth spans physical, technical and administrative. Zero trust (never trust, always verify, every request) is a way to build the identity and network layers inside defense in depth, not a replacement: it does not cover physical controls, training or backups.
  - Source: https://cyberdefenders.org/cybersecurity-glossary/defense-in-depth/  Quote: "A mature program runs zero trust inside a defense-in-depth strategy, not instead of one."
  - Kind: definition
  - Level: core
  - Also: T12

## T05 ISC2 Code of Ethics
- c:N14. The four canons, in order: protect society, the common good, necessary public trust and confidence, and the infrastructure; act honorably, honestly, justly, responsibly, and legally; provide diligent and competent service to principals; advance and protect the profession.
  - Source: https://www.isc2.org/ethics  Quote: "There are only four mandatory canons in the Code."
  - Kind: definition
  - Level: foundation
  - Bias: none (official).
- c:N15. Members must report breaches they see: failing to follow the ethics complaint procedure when observing a violation can itself be a breach under Canon IV. Knowing violations go to a peer review panel and can cost the certification.
  - Source: https://www.isc2.org/ethics  Quote: "Failure to do so may be considered a breach of the Code pursuant to Canon IV."
  - Kind: rule of thumb
  - Level: foundation
- c:N16. Exam tip: know the canons in order; when an ethics question asks what to do, the answer that protects society and the common good usually wins (their claim).
  - Source: https://www.pocketprep.com/posts/isc2-cc-exam-blueprint-subjects-official-resources-and-faqs/  Quote: "the answer that protects society and the common good usually wins"
  - Kind: rule of thumb
  - Level: foundation
  - Also: T01
  - Bias: prep vendor.

## T06 Governance: policies, standards, procedures, guidelines; regulations
- c:N17. Policies are high level statements of management intent (what and why, not how). Standards name the specific technologies and configurations used to meet a policy. Guidelines are recommended, not mandatory, and fill gaps where standards do not apply.
  - Source: https://informationsecurity.wustl.edu/policies-standards-and-guidelines  Quote: "policies are high-level statements of management intent"
  - Kind: definition
  - Level: foundation
- c:N18. Real world detail: WashU publishes its policies but keeps standards and guidelines behind a login, because standards reveal exactly which technologies and configs are in use, which attackers would love to know. Good retellable hook for "standards are sensitive".
  - Source: https://informationsecurity.wustl.edu/policies-standards-and-guidelines  Quote: "Bad actors would love to have access to this information"
  - Kind: story
  - Level: foundation
- c:N19. An incident response policy sets authorities, roles and responsibilities and should be approved by senior management, then reviewed over time. Illustrates that policy authority comes from the top.
  - Source: https://cyber.gc.ca/en/guidance/improving-cyber-security-resilience-through-emergency-preparedness-planning-itsm10014  Quote: "This policy should be approved by your organization's senior management and executives."
  - Kind: rule of thumb
  - Level: foundation
  - Also: T16
- c:N20. Breach notification as a regulation example: under Canada's PIPEDA an organization must report breaches posing a "real risk of significant harm" to the regulator, notify affected individuals, and keep records of all breaches.
  - Source: https://cyber.gc.ca/en/guidance/improving-cyber-security-resilience-through-emergency-preparedness-planning-itsm10014  Quote: "keep records of all breaches"
  - Kind: definition
  - Level: core
  - Also: T16

## T07 Business continuity and disaster recovery
- c:N21. Three plans, three jobs. IRP: event focused, handles a specific security incident. BCP: keeps only the most critical operations running during a disruption, based on the BIA. DRP: returns the organization to full normal operations after a disaster, often by moving to another site. Under the 2026 outline these sit in the Governance domain as redundancy.
  - Source: https://cyber.gc.ca/en/guidance/improving-cyber-security-resilience-through-emergency-preparedness-planning-itsm10014  Quote: "A BCP is a specific plan to quickly resume only the most critical operations"
  - Kind: definition
  - Level: foundation
  - Also: T16
  - Bias: none (government guidance). Note internal contradiction on which plan is the umbrella; see Disagreements.
- c:N22. Business impact analysis asks three questions: which resources and activities are critical, how long can you stop before significant damage, and what do interruptions cost. The BIA drives what goes in the BCP.
  - Source: https://cyber.gc.ca/en/guidance/improving-cyber-security-resilience-through-emergency-preparedness-planning-itsm10014  Quote: "How long can you stop operations without causing significant damage to your business?"
  - Kind: template
  - Level: foundation
  - Also: T03
- c:N23. RTO vs RPO. RTO is the maximum downtime you can tolerate (time forward from the disaster). RPO is the maximum data loss you can tolerate, measured back to the last good backup. RPO tells you how often to back up. Together they show how much lost business is "designed into" the plan.
  - Source: https://cyber.gc.ca/en/guidance/improving-cyber-security-resilience-through-emergency-preparedness-planning-itsm10014  Quote: "the amount of time from the start of the outage to your last valid data backup"
  - Kind: definition
  - Level: foundation
- c:N24. Recovery sites: hot (full duplicate, always running, near zero downtime), warm (connectivity and some equipment, needs setup, some data loss), cold (space and backups, little equipment, slowest and riskiest). Cost runs the other way.
  - Source: https://cyber.gc.ca/en/guidance/improving-cyber-security-resilience-through-emergency-preparedness-planning-itsm10014  Quote: "The benefit of a hot site is that it can nearly eliminate downtime."
  - Kind: definition
  - Level: foundation
- c:N25. DR test types from least to most disruptive: checklist, walkthrough, tabletop, simulation, parallel (recovery system runs without interrupting operations), full interruption (main system taken down; thorough but risky and sometimes not allowed for safety or regulatory reasons).
  - Source: https://cyber.gc.ca/en/guidance/improving-cyber-security-resilience-through-emergency-preparedness-planning-itsm10014  Quote: "A full interruption test is the most disruptive test."
  - Kind: definition
  - Level: core
- c:N26. Trade off worth retelling: synchronous replication to a DR site means no data loss, but significantly slower transactions and considerable expense. Low turnover businesses can live with an RPO of days; high volume ones cannot tolerate minutes.
  - Source: https://cyber.gc.ca/en/guidance/improving-cyber-security-resilience-through-emergency-preparedness-planning-itsm10014  Quote: "This ensures no data is lost, but results in significantly slower transaction speeds"
  - Kind: rule of thumb
  - Level: core
- c:N27. Shared elements of all three plans: a named point of contact with alternates for absences, periodic reviews, and scheduled tests with simulated disruptions. Store the BCP somewhere secure but reachable when the main systems are down.
  - Source: https://cyber.gc.ca/en/guidance/improving-cyber-security-resilience-through-emergency-preparedness-planning-itsm10014  Quote: "identifying a designated point of contact and designated team members and their alternates"
  - Kind: rule of thumb
  - Level: foundation
- c:N28. Operational technology twist: OT and industrial control systems prioritize availability and reliability over data security, often run old unpatched gear, and a compromise can cause injury or loss of life, not just data loss. CIA priority order flips.
  - Source: https://cyber.gc.ca/en/guidance/improving-cyber-security-resilience-through-emergency-preparedness-planning-itsm10014  Quote: "OT design typically prioritizes availability and process repeatability and reliability over data security."
  - Kind: rule of thumb
  - Level: core
  - Also: T02

## T08 Authentication and MFA factors
- c:N29. Three classic factor types: something you know (password, PIN, security answers), something you have (phone, token, smart card), something you are (fingerprint, face, voice, retina). Extra categories some systems use: somewhere you are (IP or GPS location) and something you do (typing rhythm, navigation patterns).
  - Source: https://www.isdecisions.com/en/glossary/mfa-factors  Quote: "Location Factors (Somewhere you are)"
  - Kind: definition
  - Level: foundation
  - Bias: IS Decisions sells UserLock (MFA product), page ends with a free trial pitch.
- c:N30. MFA means combining two or more different categories, so a stolen password alone is not enough. Common exam trap: password plus PIN is two of the same factor, not MFA (inference from the definition).
  - Source: https://duo.com/learn/access-control-models  Quote: "MFA combines two or more of these categories"
  - Kind: test
  - Level: foundation
  - Bias: Duo (Cisco) sells MFA.
- c:N31. Authentication proves who you are; it does not decide what you may do. Access control runs in sequence: authentication, then authorization, then auditing (record what happened).
  - Source: https://duo.com/learn/access-control-models  Quote: "Authentication verifies the subject's identity, but it does not decide what they are allowed to do."
  - Kind: definition
  - Level: foundation
  - Also: T09
  - Bias: Duo sells identity products.

## T09 Access control models (DAC, MAC, RBAC, ABAC), least privilege, separation of duties
- c:N32. Subjects request, objects are requested. A subject can be a person, device, app or automated process; an object is a file, database, server or SaaS app. Every access decision is "should this subject reach this object".
  - Source: https://duo.com/learn/access-control-models  Quote: "Every access control decision evaluates whether a specific subject should be allowed to access a specific object."
  - Kind: definition
  - Level: foundation
  - Bias: Duo.
- c:N33. MAC: the system compares a label on the object (Unclassified, Confidential, Secret, Top Secret) with a clearance on the subject. Users cannot share, reclassify or override; only admins change labels. Used for classified government data and especially sensitive health records.
  - Source: https://duo.com/learn/access-control-models  Quote: "the defining characteristic of MAC is that users have no say in the matter"
  - Kind: definition
  - Level: foundation
  - Bias: Duo.
- c:N34. DAC: the owner decides. Sharing a document from your own computer is DAC. Weakness: one wrong share to a distribution list leaks data, and malware inherits the rights of the user who ran it.
  - Source: https://duo.com/learn/access-control-models  Quote: "a malicious program might inherit the access rights of the user who launched it"
  - Kind: definition
  - Level: foundation
  - Bias: Duo.
- c:N35. RBAC: permissions attach to roles, people get roles. Instead of configuring 5,000 employees an admin manages perhaps 50 roles (their claim). Supports least privilege and is the most widely used enterprise model.
  - Source: https://duo.com/learn/access-control-models  Quote: "an administrator manages perhaps 50 roles"
  - Kind: number
  - Level: foundation
  - Bias: Duo.
- c:N36. ABAC: decisions combine user, resource, action and environment attributes. Story: Finance user, internal file, read only, corporate network, business hours: allowed. Same user, same desk, same file at 11 p.m.: denied. Most granular, most effort to maintain.
  - Source: https://duo.com/learn/access-control-models  Quote: "same desk, same file, at 11 p.m.? Denied."
  - Kind: story
  - Level: core
  - Bias: Duo.
- c:N37. Rule based access control is not RBAC: it applies the same fixed rule to everyone (no logins after hours, lock after five failed attempts, firewall blocks a port). Classic name confusion on exams.
  - Source: https://duo.com/learn/access-control-models  Quote: "Rule-based access control differs from RBAC despite the similar name."
  - Kind: mistake
  - Level: core
  - Bias: Duo.
- c:N38. Story ladder for choosing a model: a ten person startup uses DAC for sharing and plans RBAC past 100 staff; a hospital uses RBAC for doctors and nurses plus MAC for psychiatric records; a bank layers ABAC so traders reach trading systems only from approved devices in market hours.
  - Source: https://duo.com/learn/access-control-models  Quote: "As the company scales past 100 employees, the team plans to transition to RBAC"
  - Kind: story
  - Level: core
  - Bias: Duo.
- c:N39. Privilege creep: when people change roles and keep old access. Fix with periodic access reviews and prompt deprovisioning; an access audit asks whether former employees or contractors still have active accounts and whether shared accounts exist.
  - Source: https://www.pocketprep.com/posts/isc2-cc-exam-blueprint-subjects-official-resources-and-faqs/  Quote: "Periodic access reviews and prompt deprovisioning are the usual fixes."
  - Kind: mistake
  - Level: foundation
  - Also: T01
  - Bias: prep vendor. Duo page makes the same point (https://duo.com/learn/access-control-models).

## T10 Networking basics: OSI, TCP/IP, ports and protocols
- c:N40. Map OSI to TCP/IP: Link = OSI 1 and 2, Internet = 3, Transport = 4, Application = 5, 6 and 7. OSI is the teaching map; TCP/IP is what real stacks and tools follow.
  - Source: https://dev.to/alvinseyidov/networking-for-cybersecurity-part-1-osi-tcpip-ports-protocols-3eai  Quote: "OSI is theory"
  - Kind: definition
  - Level: foundation
  - Bias: personal learner blog. Error: lists switches as a Layer 1 example; switches are Layer 2.
- c:N41. Encapsulation in one breath: app data, TCP adds ports (segment), IP adds addresses (packet), Ethernet adds MAC addresses (frame), physical sends bits. Receiver unwraps in reverse. Gift in nested boxes analogy.
  - Source: https://dev.to/alvinseyidov/networking-for-cybersecurity-part-1-osi-tcpip-ports-protocols-3eai  Quote: "like putting a gift into multiple boxes"
  - Kind: definition
  - Level: foundation
- c:N42. Attacks live on layers: ARP spoofing at 2, IP spoofing at 3, SYN flood at 4, SQL injection at 7. Defenses too: packet filter at 3, stateful firewall at 4, WAF at 7.
  - Source: https://dev.to/alvinseyidov/networking-for-cybersecurity-part-1-osi-tcpip-ports-protocols-3eai  Quote: "Every attack lives on a specific layer"
  - Kind: rule of thumb
  - Level: core
  - Also: T11, T12
- c:N43. Analogy: IP address is the house, port is the room, protocol is how you knock. Ranges: well known 0 to 1023, registered 1024 to 49151, dynamic 49152 to 65535. The client uses a random high port, the server a fixed one.
  - Source: https://dev.to/alvinseyidov/networking-for-cybersecurity-part-1-osi-tcpip-ports-protocols-3eai  Quote: "IP address = the house"
  - Kind: definition
  - Level: foundation
- c:N44. Ports to memorize, with a risk each: 21 FTP (cleartext), 22 SSH/SFTP (brute force target), 23 Telnet (cleartext), 25 SMTP, 53 DNS (poisoning, tunneling), 80 HTTP (cleartext), 110 POP3, 123 NTP (DDoS amplification), 143 IMAP, 443 HTTPS, 445 SMB (WannaCry), 3389 RDP (ransomware entry).
  - Source: https://dev.to/alvinseyidov/networking-for-cybersecurity-part-1-osi-tcpip-ports-protocols-3eai  Quote: "Major ransomware entry point."
  - Kind: template
  - Level: foundation
  - Also: T11
- c:N45. TCP vs UDP: TCP does the 3 way handshake (SYN, SYN-ACK, ACK), guarantees order and delivery, and is harder to spoof; UDP has no handshake, is fast, easy to spoof and is used for DNS and NTP amplification DDoS.
  - Source: https://dev.to/alvinseyidov/networking-for-cybersecurity-part-1-osi-tcpip-ports-protocols-3eai  Quote: "UDP does not care. It just throws the data and runs."
  - Kind: definition
  - Level: foundation
  - Also: T11

## T12 Network defenses: firewalls, segmentation, IDS/IPS
- c:N46. Three firewall generations: basic filters (IP, port, protocol), stateful (remembers connections, allows return traffic automatically), next generation (inspects application content, for example traffic on 443 that is not real HTTPS, or DNS tunneling).
  - Source: https://dev.to/alvinseyidov/networking-for-cybersecurity-part-1-osi-tcpip-ports-protocols-3eai  Quote: "Port 443 but not real HTTPS → suspicious"
  - Kind: definition
  - Level: core
- c:N47. Segmentation turns one compromised host into a contained incident instead of an estate wide breach; IDS/IPS watch east west traffic between segments.
  - Source: https://cyberdefenders.org/cybersecurity-glossary/defense-in-depth/  Quote: "turns a single compromised host into a contained incident"
  - Kind: rule of thumb
  - Level: foundation

## T15 Data security: classification, data lifecycle, retention, destruction
- c:N48. A university data lifecycle: plan, create, manage, use, share, collect or reuse, destroy, close out. At destruction, follow retention schedules and document when and why data was destroyed. Note: this is a research data lifecycle, not the security lifecycle usually taught for CC (create, store, use, share, archive, destroy); use only for the "document destruction against a retention schedule" point.
  - Source: https://it.osu.edu/data/governance/data-literacy/data-lifecycle  Quote: "document when and why you have destroyed the data"
  - Kind: rule of thumb
  - Level: foundation

## T16 Incident response lifecycle (NIST)
- c:N49. Classic NIST SP 800-61 cycle: preparation; detection and analysis; containment, eradication and recovery; post-incident activity. SANS splits the same work into six: preparation, identification, containment, eradication, recovery, lessons learned. NIST groups the middle three because they overlap. Caution: Rev. 3 (2025) reorganized NIST guidance around CSF 2.0; this page teaches the Rev. 2 cycle.
  - Source: https://cyber.gc.ca/en/guidance/improving-cyber-security-resilience-through-emergency-preparedness-planning-itsm10014  Quote: "NIST combines containment, eradication, and recovery into one step"
  - Kind: definition
  - Level: foundation
- c:N50. Containment choice questions: what damage does it pose, how important is preserving evidence, how much time and resources, how long can you afford downtime, is it full or partial containment. And in recovery: make sure all malware is gone before restoring backups, or you reinfect.
  - Source: https://cyber.gc.ca/en/guidance/improving-cyber-security-resilience-through-emergency-preparedness-planning-itsm10014  Quote: "How important is it to preserve the evidence?"
  - Kind: template
  - Level: core

## Disagreements seen
- Which plan is the umbrella: cyber.gc.ca says in section 1.2.3 that a DRP "encompasses the main principles of an IRP and a BCP" and in section 3 that a BCP is "often considered a subset of the larger DRP", but its own summary says IRP and DRP principles "fall under the umbrella of a BCP". ISC2 materials generally treat BCP as the broader plan. https://cyber.gc.ca/en/guidance/improving-cyber-security-resilience-through-emergency-preparedness-planning-itsm10014
- MFA factor count: isdecisions.com lists three types plus location and behavior; duo.com lists only the three classic ones. https://www.isdecisions.com/en/glossary/mfa-factors vs https://duo.com/learn/access-control-models
- Governance placement: Pocket Prep puts policies, standards and procedures in Domain 1 (Security Principles) and GRC, BC/DR and awareness in Domain 2 (Security Governance); topics.md files policies and BC/DR as separate topics. Worth a line so learners do not hunt for "governance" in one place only. https://www.pocketprep.com/posts/isc2-cc-exam-blueprint-subjects-official-resources-and-faqs/
- Data lifecycle stages: OSU's research lifecycle (plan, create, manage, use, share, reuse, destroy, close out) differs from the security lifecycle CC teaches. https://it.osu.edu/data/governance/data-literacy/data-lifecycle

## Best stories
- One phishing email traced through every layer, each slowing the attacker until the SOC catches them: https://cyberdefenders.org/cybersecurity-glossary/defense-in-depth/
- ABAC at 11 p.m.: same user, same desk, same file, now denied: https://duo.com/learn/access-control-models
- WashU hides its standards behind a login because they tell attackers exactly what to target: https://informationsecurity.wustl.edu/policies-standards-and-guidelines
- Startup to hospital to bank: which access model each picks and why: https://duo.com/learn/access-control-models
- OT flips the CIA order: an industrial control system breach can cost lives, not just data: https://cyber.gc.ca/en/guidance/improving-cyber-security-resilience-through-emergency-preparedness-planning-itsm10014
