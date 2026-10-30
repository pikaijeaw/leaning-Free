# Lesson 7. Twin or Copy

**Listen:** twin-or-copy.mp3 (2 min)
**The idea, in three lines**
- Multi-AZ keeps a standby twin in another Availability Zone, updated synchronously. You can't read from it; it's there for automatic failover.
- A read replica is a readable copy, updated asynchronously (it can lag). It's there to take reads off the primary.
- Pick the database itself by access pattern: RDS or Aurora for SQL and joins, DynamoDB for key lookups, Redshift for analytics.

**Impact:** "highly available database" and "too many reads" stop looking like the same question, and the read-replica-as-failover distractor stops working on you.

**Who says it:** 2 of the 7 pages on databases teach the Multi-AZ vs read replica split; none disagree. 4 of the 7 teach picking the database by access pattern; none disagree.

**Try it** · Quick Win · 5 min
On paper, mark each scenario Multi-AZ, read replica, or both:
> **1.** A booking database has to keep running if its Availability Zone fails.
> **2.** Monthly reports run heavy queries that slow the app for everyone.
> **3.** A shop's database has to survive a zone outage, and its product pages are read thousands of times per order.

Answers: 1 Multi-AZ, 2 read replica, 3 both.

Optional console demo (KodeKloud, link below): it creates billable databases. If you follow it, delete the read replica first, then the primary, as soon as you're done.

**Rule to keep**
Failover is Multi-AZ; more reads is replicas.

**Skip** · no cost, no catch-up. Lesson 8 is just lesson 8.

**Go deeper (optional)**
- Console demo with a Multi-AZ vs read replica table: https://notes.kodekloud.com/docs/AWS-Certified-DevOps-Engineer-Professional/Domain-3-Resilient-Cloud-Solutions/Demo-RDS-Multi-AZ-Read-Replicas/page
- Exam keyword decoder, including the read-replica distractor: https://www.examcert.app/blog/aws-saa-c03-scenario-questions/
