# Lesson 3. Your Own Network

**Listen:** your-own-network.mp3 (2:16)
**The idea, in three lines**
- A VPC is your own isolated network in one Region; each subnet lives in exactly one Availability Zone.
- A subnet is public only because its route table sends 0.0.0.0/0 to an internet gateway. There is no "public" switch.
- Private subnets reach the internet through a NAT gateway, which sits in a public subnet, one per zone.

**Impact:** VPC questions turn mechanical: find the route table, follow the 0.0.0.0/0 line, and you know what can reach the internet.

**Who says it:** 4 of the 7 pages on VPCs teach "public is decided by the route table"; 3 of 7 teach NAT gateways in public subnets, one per zone. None disagree. (Sources give different NAT gateway bandwidth figures, so this lesson quotes none.)

**Try it** · Deep Focus · 15 min
On paper (nothing gets built, so it's free):
> **1. Box.** Draw a big box for the VPC, labelled with a range like 10.0.0.0/16.
> **2. Zones.** Split it into two columns, zone a and zone b.
> **3. Subnets.** In each column, draw a public subnet on top and a private subnet below.
> **4. Gateways.** An internet gateway on the edge of the box. One NAT gateway inside each public subnet.
> **5. Route tables.** Public: 0.0.0.0/0 to the internet gateway. Private in zone a: 0.0.0.0/0 to zone a's NAT gateway. Private in zone b: 0.0.0.0/0 to zone b's NAT gateway.
> **6. Check.** Circle anything that would stop working if zone a went dark. Ideally, only zone a's boxes.

**Rule to keep**
Public or private is decided by the route table, not the name.

**Skip** · no cost, no catch-up. Lesson 4 is just lesson 4.

**Go deeper (optional)**
- VPC anatomy, route tables and the NAT gateway mistakes: https://coursedesk.laravel.cloud/courses/aws-certified-solutions-architect-associate/lessons/vpc-anatomy-cidr-subnets-and-route-tables
- VPC concepts for SAA-C03: https://www.sailor.sh/blog/aws-vpc-concepts-for-saa-c03
- One learner's "VPC is hard, start early": https://www.janmeppe.com/blog/i-recently-passed-the-aws-solution-architect-associate-exam-aws-saa-c03-heres-how-i-did-it/
