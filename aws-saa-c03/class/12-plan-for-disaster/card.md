# Lesson 12. Plan for Disaster

**Listen:** plan-for-disaster.mp3 (2 min)
**The idea, in three lines**
- High availability survives losing an Availability Zone. Disaster recovery survives losing a Region, or losing your data.
- Name the RTO (how long until you're serving again) and RPO (how much data, measured in time, you can lose) first. Then pick the cheapest strategy that meets them: backup and restore, pilot light, warm standby, multi-site active/active.
- Replication is not backup: it copies a delete or corruption too. Keep versioning and point-in-time backups.

**Impact:** your designs start from two numbers instead of a guess, and you stop paying for a second Region you don't need.

**Who says it:** 2 of the 14 pages on recovery teach HA vs DR and RTO/RPO first; 3 of the 14 teach the four strategies; 3 of the 14 teach that replication is not backup; none disagree. The AWS whitepaper draws the pilot light vs warm standby line: pilot light can't serve requests until servers are switched on; warm standby serves at reduced capacity right away. (The gas stove picture in the audio is the hosts' own, not a source's.)

**Try it** · Deep Focus · 15 min
On paper, pick a small app (for example, an online bakery's order system). Then:
> **1. RTO.** How long can it be down? Write a number (for example, 4 hours).
> **2. RPO.** How many minutes of orders could you lose? Write a number (for example, 15 minutes).
> **3. Strategy.** Pick one: backup and restore, pilot light, warm standby, or multi-site active/active.
> **4. Why not cheaper.** Write one line on why the next cheaper strategy misses your numbers.
> **5. Data disaster.** Write how you'd recover from an accidental delete (versioning, point-in-time backup).

**Rule to keep**
Say the RTO and RPO before saying the design.

**Skip** · no cost, no catch-up. This is the last lesson.

**Go deeper (optional)**
- AWS's four DR strategies: https://docs.aws.amazon.com/whitepapers/latest/disaster-recovery-workloads-on-aws/disaster-recovery-options-in-the-cloud.html
- HA vs DR and RTO/RPO, explained: https://hidekazu-konishi.com/entry/aws_disaster_recovery_strategies_guide.html
