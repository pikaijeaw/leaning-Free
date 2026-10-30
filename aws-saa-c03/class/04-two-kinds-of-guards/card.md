# Lesson 4. Two Kinds of Guards

**Listen:** two-kinds-of-guards.mp3 (2 min)
**The idea, in three lines**
- Security groups sit on the instance (its network interface), allow only, and are stateful: allowed traffic's replies come back automatically.
- Network ACLs sit on the subnet, can allow and deny, and are stateless: the way back needs its own rule.
- Only a network ACL can block one specific IP address.

**Impact:** a favorite exam distractor stops working on you, and the real bug "it can call out but never hears back" gets a one-line diagnosis.

**Who says it:** 3 of the 7 pages on VPCs teach the stateful vs stateless split; 3 of 7 teach chaining security groups tier to tier. None disagree.

**Try it** · Quick Win · 10 min
On your lesson 3 drawing (paper only, free):
> **1. Tiers.** In each zone, label a web tier (behind a load balancer), an app tier, and a database tier.
> **2. Groups.** Name four security groups: sg-alb, sg-web, sg-app, sg-db.
> **3. Rules.** Write one inbound rule each:
> sg-alb: port 443 from 0.0.0.0/0
> sg-web: port 80 from sg-alb
> sg-app: the app port (for example 8080) from sg-web
> sg-db: the database port (for example 3306) from sg-app
> **4. Block.** Pretend one IP keeps hammering the site. Write which guard blocks it (the network ACL, with a deny rule).

**Rule to keep**
Security groups for who may talk; network ACLs only to block.

**Skip** · no cost, no catch-up. Lesson 5 is just lesson 5.

**Go deeper (optional)**
- Security groups vs NACLs, and the ephemeral port scenario: https://www.sailor.sh/blog/aws-vpc-concepts-for-saa-c03
- The three-tier layout per zone: https://coursedesk.laravel.cloud/courses/aws-certified-solutions-architect-associate/lessons/vpc-anatomy-cidr-subnets-and-route-tables
