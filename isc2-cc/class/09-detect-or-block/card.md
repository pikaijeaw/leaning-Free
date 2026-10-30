# Lesson 9. Detect or Block

**Listen:** detect-or-block.mp3 (2 min)

**The idea, in three lines**
- **IDS:** watches traffic, detects and alerts; a person acts. **IPS:** sits inline in the traffic path and blocks.
- Firewalls come in three generations: basic filters (address, port, protocol), stateful (remembers connections), next gen (looks inside the traffic, for example port 443 traffic that isn't real HTTPS).
- Segment the network (zones, VLANs, a DMZ or screened subnet for public servers) so one compromised host stays a contained incident.

**Impact:** you stop falling for answer choices where a detective control is credited with stopping an attack.

**Who says it:** 3 of the 6 pages on network defense teach IDS detects and IPS blocks, and 4 of the 6 teach segmentation; two pages (CSO Online, Heimdal) blur it and describe an IDS as blocking, which is wrong. An IDS detects and alerts; an IPS blocks.

**Try it** · Quick Win · 10 min
On paper, list five tools: smoke alarm, IDS, IPS, door lock, security camera. For each one:
> **1.** Write "detect" or "block".
> **2.** For every "detect", write who acts when it alerts (you, a guard, a security analyst).
> **3.** Circle the one that sits in the path, the way an IPS sits inline.

**Rule to keep**
Detecting isn't stopping.

**Skip** · no cost, no catch-up. Lesson 10 is just lesson 10.

**Go deeper (optional)**
- IDS vs IPS, firewalls and segmentation in the CC outline: https://open-exam-prep.com/blog/isc2-cc-certified-in-cybersecurity-guide-2026
- Why segmentation contains a compromised host: https://cyberdefenders.org/cybersecurity-glossary/defense-in-depth/
- The three firewall generations, with the port 443 example: https://dev.to/alvinseyidov/networking-for-cybersecurity-part-1-osi-tcpip-ports-protocols-3eai
