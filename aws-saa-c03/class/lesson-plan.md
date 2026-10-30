# Lesson plan: AWS Solutions Architect Associate (SAA-C03), beginner

12 lessons in 3 arcs of 4, about 2 minutes each. Built from 37 free pages (research/agreement-map.md), following the SAA-C03 exam guide's topics and the usual course order, not the Udemy videos themselves. Agreement reads "N of the M pages on this sub-topic teach it"; a low N with no dissent means the other pages covered nearby ground, not that they disagree.

Try-its are free (paper, the pricing calculator, account settings) unless a lesson says otherwise. Lesson 2 sets a budget alert before anything is built.

## Arc 1. The ground floor
Why this arc: every later answer sits on where things run, who can touch them, and how the network is laid out. Finish: you can sketch a two-AZ VPC with public and private subnets from memory.

### L1. Two Zones Minimum
- Agree: 4 of 5 pages on global infrastructure (TH10); Region choice 2 of 5 (TH09), Cloud Posse pushes back on us-east-1 as a default.
- Idea: a Region is a place on the map; Availability Zones are separate data centers inside it. Run in one Region across at least two AZs.
- Why it matters: "highly available" on the exam almost always means "more than one AZ".
- Story: Netflix keeps streaming when an AZ fails; Peloton uses edge locations, "no buffering mid-burpee" (dev.to luminousmen). Cloud Posse: the busiest Region has historically had the most outages.
- Try it: Quick Win, 10 min. On paper, pick a Region for a made-up app using four checks (users' latency, data law, services offered, price), then name two AZs you'd spread across.
- Rule: Nothing important runs in only one Availability Zone.

### L2. Guard the Account
- Agree: 3 of 5 IAM pages (TH11); shared responsibility 2 of 5, none disagree (TH12); billing alerts 8 of 17 (TH45, TH05).
- Idea: AWS secures the building; you secure what you put in it. Lock the root user, use roles with temporary credentials instead of stored access keys.
- Why it matters: Secure is the biggest exam domain (30%), and a leaked key or surprise bill ends a learner's lab days fast.
- Story: the accidentally public S3 bucket, AWS's data center was fine, one setting exposed the files (builder.aws.com shared responsibility). The EC2 app with an access key in its config file vs an instance role (builder.aws.com IAM guide).
- Try it: Admin, 10 min. In your AWS account: MFA on the root user, then a Budgets alert at a small amount (for example 5 dollars). If no account yet, write these two steps on the first page of your notes.
- Rule: Root gets MFA and gets left alone; apps get roles, never keys.

### L3. Your Own Network
- Agree: 4 of 7 VPC pages (TH31); NAT placement 3 of 7 (TH34). NAT throughput figures disagree between sources, so no number is quoted.
- Idea: a subnet is public only because its route table sends 0.0.0.0/0 to an internet gateway. Private subnets reach out through a NAT gateway that lives in a public subnet.
- Why it matters: VPC is where beginners stall (Jan Meppe), and it shows up across every domain.
- Story: the NAT gateway put in a private subnet, nothing gets out; and one NAT gateway taking every AZ's outbound traffic down with its own AZ (coursedesk VPC anatomy).
- Try it: Deep Focus, 15 min. Draw a VPC: two AZs, a public and a private subnet in each, IGW, one NAT gateway per AZ, and the two route tables with their 0.0.0.0/0 lines.
- Rule: Public or private is decided by the route table, not the name.

### L4. Two Kinds of Guards
- Agree: 3 of 7 VPC pages (TH32); tier chaining 3 of 7 (TH33). None disagree.
- Idea: security groups are stateful allow-lists on the instance; network ACLs are stateless allow-and-deny lists on the subnet. Only a NACL can block one IP.
- Why it matters: a favorite exam distractor, and the root of real "it can call out but never hears back" bugs.
- Story: the app whose NACL had no return rule for ephemeral ports 1024 to 65535 (sailor.sh).
- Try it: Quick Win, 10 min. On your L3 drawing, write the security group rules for web, app and database tiers, each one accepting only the security group in front of it.
- Rule: Security groups for who may talk; NACLs only to block.

## Arc 2. Parts that heal themselves
Why this arc: the Resilient and High-Performing domains are about compute, storage and databases that survive failure and absorb load. Finish: you can explain a self-healing, queue-buffered web app end to end.

### L5. Self-Healing Fleet
- Agree: 4 of 6 ELB/ASG pages (TH17, TH19); ASG setup 2 of 6, none disagree (TH18).
- Idea: an Application Load Balancer in public subnets in front of an Auto Scaling group spread over AZs in private subnets; the group replaces sick instances and scales on a target metric.
- Story: kill an instance on purpose and watch the activity log say "Instance terminated", then "Launching a new instance"; `stress` pushes CPU past a 40% target and capacity climbs from 1 to 3 (KodeKloud lab).
- Try it: Deep Focus, 15 min. Fill in min, desired, max and a target metric for a shop that needs 2 servers normally and 6 at peak. (Optional lab costs money; tear down after.)
- Rule: Let the group replace a sick server; never nurse one by hand.

### L6. Right Disk
- Agree: 3 of 3 storage pages (TH15, TH16).
- Idea: EBS for one instance's disk, EFS for many Linux instances sharing files, S3 for objects over an API, instance store only for scratch you can lose. gp3 as the default EBS type.
- Story: CloudZero on EBS per node adding up vs one shared EFS.
- Try it: Quick Win, 5 min. Sort five workloads (boot disk, shared web uploads, video archive, temp cache, database volume) into EBS, EFS, S3 or instance store.
- Rule: One instance, EBS; many instances, EFS; anything over HTTP, S3.

### L7. Twin or Copy
- Agree: Multi-AZ vs read replicas 2 of 7, none disagree (TH20); database by access pattern 4 of 7 (TH21).
- Idea: Multi-AZ is a hidden twin for failover (synchronous, not readable). Read replicas are readable copies for scaling reads (asynchronous). Different problems.
- Story: KodeKloud RDS demo; examcert's database-by-access-pattern mapping.
- Try it: Quick Win, 5 min. For three one-line scenarios, mark Multi-AZ, read replica, or both.
- Rule: Failover is Multi-AZ; more reads is replicas.

### L8. Queue the Spike
- Agree: 2 of 4 decoupling pages (TH27, TH28), none disagree; Kinesis for streams 3 of 4 (TH29). No retention figure quoted (source outdated).
- Idea: put an SQS queue between tiers so a spike waits in line instead of breaking things; SNS to fan one event out to many queues; Kinesis for ordered, replayable streams.
- Story: the retailer losing orders in a sale; a queue plus scaling on backlog fixes it, the database at 20% CPU is a red herring (examcert).
- Try it: Quick Win, 10 min. Redraw a "web server calls worker directly" diagram with a queue in between, and write which metric the workers scale on.
- Rule: When load arrives in bursts, put a queue in front of the work.

## Arc 3. Safe, cheap, recoverable
Why this arc: the Secure and Cost-Optimized domains, plus the exam habit of reading the qualifier. Finish: you can answer "most secure", "most cost-effective" and "least overhead" questions on purpose.

### L9. Lock the Bucket
- Agree: 5 of 10 S3 pages (TH25); customer managed keys 2 of 6, none disagree (TH37).
- Idea: S3 is private by default; keep it that way with bucket policies, serve files through CloudFront rather than a public bucket, and use a customer managed KMS key when you must disable and audit the key.
- Story: the two-person security team that must disable a key at once and log every use; SSE-KMS with a customer managed key wins (examcert). The public-bucket checkbox from L2.
- Try it: Admin, 10 min. In S3 settings (or on paper), confirm Block Public Access is on at the account level.
- Rule: No bucket is public; files reach people through CloudFront.

### L10. Read the Clock
- Agree: storage class by access and retrieval 4 of 10 (TH23); reading the qualifier 5 of 16 (TH03); one source (8th Light) says hands-on gaps, not reading, were the real problem.
- Idea: pick the S3 class by how often data is read and how fast it must come back; on the exam, find the qualifier and the hard constraint before ranking options.
- Story: 40 TB of logs heads for Deep Archive, until "up to 12 hours" becomes "within 5 minutes" and the answer flips (coursedesk).
- Try it: Quick Win, 10 min. Take any one practice question, underline the qualifier and every hard number before reading the options.
- Rule: The last line of the question decides the answer.

### L11. Pay How You Use
- Agree: purchasing options 2 of 4, none disagree (TH14); hidden charges 8 of 17 (TH45).
- Idea: Savings Plans or Reserved for steady 24/7, Spot for work that can be interrupted, On-Demand for short or unpredictable; and hunt the quiet charges.
- Story: the nightly 3-hour batch job and the 3-year contract that baits you into Reserved Instances; Spot wins because Reserved bills all 24 hours (examcert).
- Try it: Admin, 10 min. In the AWS Pricing Calculator, price one small instance On-Demand vs a 1-year Savings Plan.
- Rule: Commit only to what runs all day; interruptible work goes to Spot.

### L12. Plan for Disaster
- Agree: HA vs DR and RTO/RPO 2 of 14 recovery pages, none disagree (TH40); four strategies 3 of 14 (TH41); replication is not backup 3 of 14 (TH42).
- Idea: High availability survives an AZ; disaster recovery survives losing a Region or your data. Name RTO and RPO first, then pick the cheapest of backup and restore, pilot light, warm standby, active/active that meets them.
- Story: deleted data that replication faithfully copies to the DR Region (AWS DR whitepaper). Hosts may offer their own stove image for pilot light vs warm standby; only the distinction is cited.
- Try it: Deep Focus, 15 min. For a small app, write an RTO and RPO, then pick one of the four strategies and say why the cheaper one fails.
- Rule: Say the RTO and RPO before saying the design.

## Splits (decisions, not lessons)
- **Hands-on labs vs question reading.** freeCodeCamp, 8th Light, rabindratamang favor small projects; sailor.sh and coursedesk say the score is won reading the qualifier. Deciding: if service names blur together, build; if practice scores stall with familiar services, read.
- **How much study.** About 40 hours on one focused course (Meppe, freeCodeCamp) vs AWS's suggested year of hands-on and long courses (Digital Cloud). Deciding: prior IT experience.
- **When to start practice exams.** At about 30% of the material (Meppe) vs near the end (Digital Cloud). All agree they matter; the Tutorials Dojo author skipped them and failed once.
- **How many certifications.** Digital Cloud said "stack them" in 2025 and "one or two, then build" in 2026.
- **Automatic vs push-button failover.** Same AWS whitepaper argues both ways.

## Coverage gaps
Not in these 12: CloudFront vs Global Accelerator, serverless (Lambda, API Gateway, DynamoDB), monitoring (CloudWatch, CloudTrail, Config), Route 53 routing, VPC endpoints and peering, containers. Thin or absent in sources: containers, Route 53 records, Shield/GuardDuty, migration services, analytics. A fourth arc can cover the first group if wanted.

## Delivery
Lesson 1 first as a sample (audio plus card), then the rest once the format is approved. Audio zips plus one combined cards file, and class/playbook.md for rules kept.
