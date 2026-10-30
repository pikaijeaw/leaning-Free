# Agreement map: AWS Certified Solutions Architect Associate (SAA-C03), beginner

Built from 37 pages across notes a to e (230 notes). M is the number of distinct pages with at least one note on the theme's main sub-topic (including `Also:` lines); N is how many of those pages support the theme. Pages per sub-topic: T01 16, T02 5, T03 5, T04 4, T05 3, T06 6, T07 7, T08 2, T09 10, T10 4, T11 4, T12 5, T13 7, T14 6, T15 4, T16 14, T17 17, T18 1.

45 themes: 23 foundation, 21 core, 1 advanced. Lines marked `Flag:` carry outdated or wrong source claims that lesson writers must not repeat.

Source-claim flags at a glance:
- Kinesis Data Streams retention "24 hours to 7 days" (https://dashbird.io/blog/kinesis-sqs-sns-comparison) is outdated; AWS now allows up to 365 days. See TH29.
- Origin Access Identity (OAI) (https://digitalcloud.training/aws-certified-solutions-architect-saa-c02/) is superseded by Origin Access Control (OAC). See TH25, TH26.
- Macie "removes" PII (https://www.janmeppe.com/blog/i-recently-passed-the-aws-solution-architect-associate-exam-aws-saa-c03-heres-how-i-did-it/) is wrong; Macie discovers and classifies sensitive data. See TH06, TH38.
- "720 is about 72%" (https://notes.kodekloud.com/docs/AWS-Solutions-Architect-Associate-Certification/Introduction/Solutions-Architecture-Exam-guide-What-to-focus-on/page) is wrong; the score is scaled, not a raw percentage. See TH01.

## TH01 Know the exam's shape before you study: 65 questions in 130 minutes (about 2 minutes each), scaled pass mark 720 of 1000, no guessing penalty, so answer every question
- Sub-topic: T01
- Agree: 7 of 16. Notes: a:N1, a:N10, b:N1, b:N2, b:N12, c:N7, c:N8, d:N1, e:N1, e:N2. Urls: https://digitalcloud.training/aws-certified-solutions-architect-saa-c02/ https://tutorialsdojo.com/my-saa-c03-aws-certified-solution-architect-associate-exam-experience-2023/ https://www.examcert.app/blog/aws-saa-c03-scenario-questions/ https://www.sailor.sh/blog/aws-vpc-concepts-for-saa-c03 https://8thlight.com/insights/making-most-aws-kubernetes-certifications https://dev.to/rabindratamang/how-i-passed-the-aws-solution-architect-associate-exam-my-study-plan-and-tips-5ahh https://notes.kodekloud.com/docs/AWS-Solutions-Architect-Associate-Certification/Introduction/Solutions-Architecture-Exam-guide-What-to-focus-on/page
- Disagree: https://notes.kodekloud.com/docs/AWS-Solutions-Architect-Associate-Certification/Introduction/Solutions-Architecture-Exam-guide-What-to-focus-on/page: glosses the scaled 720 as "about 72%"; a scaled score is not a raw percentage, so do not teach it that way; https://digitalcloud.training/aws-certified-solutions-architect-saa-c02/: most questions are a 1 to 2 line scenario that gets "straight to the point" (vs Tutorials Dojo's "long-winded scenarios with equally-long options", https://tutorialsdojo.com/my-saa-c03-aws-certified-solution-architect-associate-exam-experience-2023/)
- Flag: Wrong source gloss: KodeKloud equates the scaled 720 with 'about 72%'. Scaled scores do not map linearly to raw percentages; say 'a scaled 720 out of 1000'.
- Level: foundation
- Best story: The online proctored exam where you cannot leave your desk even for the toilet, after a webcam sweep of your room, https://8thlight.com/insights/making-most-aws-kubernetes-certifications

## TH02 Weight your study time by the four exam domains: Secure 30%, Resilient 26%, High-Performing 24%, Cost-Optimized 20%
- Sub-topic: T01 (also T17)
- Agree: 4 of 16. Notes: a:N2, b:N8, d:N2, e:N3, e:N4. Urls: https://digitalcloud.training/aws-certified-solutions-architect-saa-c02/ https://forum.freecodecamp.org/t/how-i-structured-a-6-week-study-plan-for-aws-saa-c03-what-actually-moved-the-needle/799377 https://dev.to/rabindratamang/how-i-passed-the-aws-solution-architect-associate-exam-my-study-plan-and-tips-5ahh https://notes.kodekloud.com/docs/AWS-Solutions-Architect-Associate-Certification/Introduction/Solutions-Architecture-Exam-guide-What-to-focus-on/page
- Disagree: none found
- Level: foundation
- Best story: The freeCodeCamp poster whose scores stayed flat while studying all four domains equally, https://forum.freecodecamp.org/t/how-i-structured-a-6-week-study-plan-for-aws-saa-c03-what-actually-moved-the-needle/799377

## TH03 Read the last line first: find the qualifier (MOST cost-effective, LEAST operational overhead, MOST secure), cut options on the hard constraints, then rank the survivors
- Sub-topic: T01 (also T17, T16)
- Agree: 5 of 16. Notes: a:N3, b:N3, b:N4, b:N5, b:N6, b:N7, b:N19, c:N1, c:N2, c:N3, c:N4, c:N5, c:N27, c:N28, d:N4. Urls: https://digitalcloud.training/aws-certified-solutions-architect-saa-c02/ https://www.examcert.app/blog/aws-saa-c03-scenario-questions/ https://builder.aws.com/content/3Kclu4dDUaoAETVUirp8jgTvSjB/a-practical-guide-to-secure-access-management https://coursedesk.laravel.cloud/courses/aws-certified-solutions-architect-associate/lessons/how-to-read-an-saa-c03-question https://dev.to/rabindratamang/how-i-passed-the-aws-solution-architect-associate-exam-my-study-plan-and-tips-5ahh
- Disagree: https://8thlight.com/insights/making-most-aws-kubernetes-certifications: what was missing was hands-on labs and reading beyond the videos, not question-reading technique (vs https://coursedesk.laravel.cloud/courses/aws-certified-solutions-architect-associate/lessons/how-to-read-an-saa-c03-question, which says most failers already know the services)
- Level: foundation
- Best story: The "12 hours" flip: 40 TB of logs, and changing "up to 12 hours" to "within 5 minutes" changes the whole answer, https://coursedesk.laravel.cloud/courses/aws-certified-solutions-architect-associate/lessons/how-to-read-an-saa-c03-question

## TH04 Start practice exams early, take each one at least twice, and log every wrong answer with the reason you missed it
- Sub-topic: T01
- Agree: 5 of 16. Notes: a:N4, a:N5, a:N6, a:N7, b:N9, d:N6, e:N2. Urls: https://tutorialsdojo.com/my-saa-c03-aws-certified-solution-architect-associate-exam-experience-2023/ https://www.janmeppe.com/blog/i-recently-passed-the-aws-solution-architect-associate-exam-aws-saa-c03-heres-how-i-did-it/ https://forum.freecodecamp.org/t/how-i-structured-a-6-week-study-plan-for-aws-saa-c03-what-actually-moved-the-needle/799377 https://dev.to/franciscojeg78/aws-saa-c03-30-day-learning-plan-using-stephane-maareks-ultimate-aws-certified-solutions-architect-17j3 https://notes.kodekloud.com/docs/AWS-Solutions-Architect-Associate-Certification/Introduction/Solutions-Architecture-Exam-guide-What-to-focus-on/page
- Disagree: https://digitalcloud.training/aws-certified-solutions-architect-saa-c02/: puts practice questions near the end, "after going through these questions a couple of times" (vs starting at 30% of the material, https://www.janmeppe.com/blog/i-recently-passed-the-aws-solution-architect-associate-exam-aws-saa-c03-heres-how-i-did-it/)
- Level: foundation
- Best story: Fresh graduate aces Cloud Practitioner, fails SAA-C03 after skipping practice tests, passes on the retake, https://tutorialsdojo.com/my-saa-c03-aws-certified-solution-architect-associate-exam-experience-2023/

## TH05 Build small hands-on projects (free tier, billing alert on) so the service-selection facts stick
- Sub-topic: T01 (also T13, T12)
- Agree: 8 of 16. Notes: a:N11, b:N10, b:N15, b:N30, c:N9, d:N5, d:N8, d:N9, e:N6. Urls: https://digitalcloud.training/aws-certified-solutions-architect-saa-c02/ https://forum.freecodecamp.org/t/how-i-structured-a-6-week-study-plan-for-aws-saa-c03-what-actually-moved-the-needle/799377 https://digitalcloud.training/why-an-aws-certification-will-not-get-you-an-aws-job/ https://builder.aws.com/content/3KXRAwuplncnbnTDQfWDtn5P1ML/building-your-first-serverless-rest-api-with-aws-lambda-api-gateway-and-dynamodb https://8thlight.com/insights/making-most-aws-kubernetes-certifications https://dev.to/franciscojeg78/aws-saa-c03-30-day-learning-plan-using-stephane-maareks-ultimate-aws-certified-solutions-architect-17j3 https://dev.to/rabindratamang/how-i-passed-the-aws-solution-architect-associate-exam-my-study-plan-and-tips-5ahh https://notes.kodekloud.com/docs/AWS-Solutions-Architect-Associate-Certification/Introduction/Solutions-Architecture-Exam-guide-What-to-focus-on/page
- Disagree: https://www.sailor.sh/blog/aws-vpc-concepts-for-saa-c03: the exam is entirely multiple choice with no labs, so console steps are not needed; https://coursedesk.laravel.cloud/courses/aws-certified-solutions-architect-associate/lessons/how-to-read-an-saa-c03-question: failures come from reading, not missing knowledge
- Level: foundation
- Best story: "Three small projects taught me more than 20 hours of video": S3 + CloudFront, a VPC with a NAT gateway, and an ASG with a deliberately broken health check, https://forum.freecodecamp.org/t/how-i-structured-a-6-week-study-plan-for-aws-saa-c03-what-actually-moved-the-needle/799377

## TH06 Know the core services deeply and everything else at "what is it, when would I use it" level, using the exam guide's task statements as the checklist
- Sub-topic: T01 (also T09, T11)
- Agree: 4 of 16. Notes: a:N8, b:N11, d:N4, e:N4, e:N5. Urls: https://www.janmeppe.com/blog/i-recently-passed-the-aws-solution-architect-associate-exam-aws-saa-c03-heres-how-i-did-it/ https://forum.freecodecamp.org/t/how-i-structured-a-6-week-study-plan-for-aws-saa-c03-what-actually-moved-the-needle/799377 https://dev.to/rabindratamang/how-i-passed-the-aws-solution-architect-associate-exam-my-study-plan-and-tips-5ahh https://notes.kodekloud.com/docs/AWS-Solutions-Architect-Associate-Certification/Introduction/Solutions-Architecture-Exam-guide-What-to-focus-on/page
- Disagree: none found
- Flag: Wrong source claim: Jan Meppe's example says Macie "removes" PII. Macie discovers and classifies sensitive data in S3; it does not remove it. Do not repeat "removes".
- Level: foundation
- Best story: VPC was a miserable slog until he let it simmer a week, then it clicked; start VPC early, https://www.janmeppe.com/blog/i-recently-passed-the-aws-solution-architect-associate-exam-aws-saa-c03-heres-how-i-did-it/

## TH07 Pick one focused course and a time budget you can keep (passers report about 40 hours over 2 months up to about four months part-time)
- Sub-topic: T01
- Agree: 5 of 16. Notes: a:N7, b:N11, c:N6, d:N3, d:N5. Urls: https://www.janmeppe.com/blog/i-recently-passed-the-aws-solution-architect-associate-exam-aws-saa-c03-heres-how-i-did-it/ https://forum.freecodecamp.org/t/how-i-structured-a-6-week-study-plan-for-aws-saa-c03-what-actually-moved-the-needle/799377 https://8thlight.com/insights/making-most-aws-kubernetes-certifications https://dev.to/rabindratamang/how-i-passed-the-aws-solution-architect-associate-exam-my-study-plan-and-tips-5ahh https://dev.to/franciscojeg78/aws-saa-c03-30-day-learning-plan-using-stephane-maareks-ultimate-aws-certified-solutions-architect-17j3
- Disagree: https://forum.freecodecamp.org/t/how-i-structured-a-6-week-study-plan-for-aws-saa-c03-what-actually-moved-the-needle/799377: skip any course over 15 hours and read the exam guide instead (vs Digital Cloud recommending a training course and selling long bootcamps, https://digitalcloud.training/why-an-aws-certification-will-not-get-you-an-aws-job/); https://dev.to/rabindratamang/how-i-passed-the-aws-solution-architect-associate-exam-my-study-plan-and-tips-5ahh: Cantrill for depth, Maarek only for revision (vs Maarek as the single primary resource, https://dev.to/franciscojeg78/aws-saa-c03-30-day-learning-plan-using-stephane-maareks-ultimate-aws-certified-solutions-architect-17j3); https://digitalcloud.training/aws-certified-solutions-architect-saa-c02/: AWS recommends one year of hands-on experience (vs Jan Meppe passing on about 40 hours of study, https://www.janmeppe.com/blog/i-recently-passed-the-aws-solution-architect-associate-exam-aws-saa-c03-heres-how-i-did-it/)
- Level: foundation
- Best story: The 8th Light developer who spent about 290 GBP and four months "in dribs and drabs", https://8thlight.com/insights/making-most-aws-kubernetes-certifications

## TH08 Treat SAA as the ticket to an interview, not the job: pair it with portfolio projects instead of stacking more badges
- Sub-topic: T01
- Agree: 3 of 16. Notes: b:N13, b:N14, b:N15, e:N6. Urls: https://digitalcloud.training/the-truth-about-aws-certifications-after-25-years-in-tech/ https://digitalcloud.training/why-an-aws-certification-will-not-get-you-an-aws-job/ https://notes.kodekloud.com/docs/AWS-Solutions-Architect-Associate-Certification/Introduction/Solutions-Architecture-Exam-guide-What-to-focus-on/page
- Disagree: https://digitalcloud.training/why-an-aws-certification-will-not-get-you-an-aws-job/: (2025) do all the associate certs plus a professional or specialty (vs the same company in 2026 saying one or two are enough and stacking is a trap, https://digitalcloud.training/the-truth-about-aws-certifications-after-25-years-in-tech/)
- Level: foundation
- Best story: none

## TH09 Choose a primary Region by latency to users, data-residency law, service availability and price, and choose carefully because moving later is expensive
- Sub-topic: T02 (also T17)
- Agree: 2 of 5. Notes: c:N11, c:N13, c:N14, c:N15, d:N11. Urls: https://cloudposse.com/blog/devops/cloud/how-to-pick-your-primary-aws-region https://dev.to/luminousmen/understanding-aws-regions-and-availability-zones-a-guide-for-beginners-1bcd
- Disagree: https://cloudposse.com/blog/devops/cloud/how-to-pick-your-primary-aws-region: avoid us-east-1 as the default (busiest, most outages); its own criteria can point straight back to us-east-1 for US East users
- Level: foundation
- Best story: Why not us-east-1: the busiest Region has historically had the most outages, https://cloudposse.com/blog/devops/cloud/how-to-pick-your-primary-aws-region

## TH10 Run in one Region across at least two Availability Zones, and use edge locations and the AWS backbone to reach users worldwide
- Sub-topic: T02 (also T10, T16)
- Agree: 4 of 5. Notes: a:N34, b:N34, d:N10, d:N12, d:N13, d:N14, d:N15, e:N7. Urls: https://tutorialsdojo.com/aws-global-accelerator-vs-amazon-cloudfront/ https://www.sailor.sh/blog/aws-vpc-concepts-for-saa-c03 https://dev.to/luminousmen/understanding-aws-regions-and-availability-zones-a-guide-for-beginners-1bcd https://docs.aws.eu/vpc/latest/userguide/VPC_Subnets.html
- Disagree: https://dev.to/luminousmen/understanding-aws-regions-and-availability-zones-a-guide-for-beginners-1bcd: edge locations "can be more expensive" and "more vulnerable to security threats" (unsupported; the DR whitepaper treats the edge network as a reliability win, https://docs.aws.amazon.com/whitepapers/latest/disaster-recovery-workloads-on-aws/disaster-recovery-options-in-the-cloud.html)
- Level: foundation
- Best story: Netflix keeps streaming when an AZ falls over; Peloton uses edge locations so there is "no buffering mid-burpee", https://dev.to/luminousmen/understanding-aws-regions-and-availability-zones-a-guide-for-beginners-1bcd

## TH11 Grant least privilege through IAM roles with temporary credentials, never stored access keys; MFA on privileged users and no root for daily work
- Sub-topic: T03 (also T12, T15)
- Agree: 3 of 5. Notes: b:N16, b:N17, b:N18, b:N19, b:N21, b:N31, c:N19. Urls: https://builder.aws.com/content/3Kclu4dDUaoAETVUirp8jgTvSjB/a-practical-guide-to-secure-access-management https://builder.aws.com/content/3KXRAwuplncnbnTDQfWDtn5P1ML/building-your-first-serverless-rest-api-with-aws-lambda-api-gateway-and-dynamodb https://builder.aws.com/content/3L0TDjBSq7BYCw9eRO0NlSZpRaQ/aws-shared-responsibility-model-explained-for-beginners
- Disagree: https://builder.aws.com/content/3KXRAwuplncnbnTDQfWDtn5P1ML/building-your-first-serverless-rest-api-with-aws-lambda-api-gateway-and-dynamodb: the tutorial attaches AmazonDynamoDBFullAccess to the Lambda role
- Level: foundation
- Best story: The EC2 app with an access key in its config file; the instance role that can read but not delete wins "MOST secure", https://builder.aws.com/content/3Kclu4dDUaoAETVUirp8jgTvSjB/a-practical-guide-to-secure-access-management

## TH12 Know the shared responsibility line: AWS secures the cloud, you secure what you put in it, and the split shifts with how managed the service is
- Sub-topic: T03 (also T14, T09)
- Agree: 2 of 5. Notes: c:N16, c:N17, c:N18, c:N20, c:N39. Urls: https://builder.aws.com/content/3L0TDjBSq7BYCw9eRO0NlSZpRaQ/aws-shared-responsibility-model-explained-for-beginners https://aws.amazon.com/architecture/well-architected
- Disagree: none found
- Level: foundation
- Best story: The accidentally public S3 bucket: AWS secured the data center, but your one checkbox exposed the files, https://builder.aws.com/content/3L0TDjBSq7BYCw9eRO0NlSZpRaQ/aws-shared-responsibility-model-explained-for-beginners

## TH13 Use a service control policy for rules every account must obey; know identity-based vs resource-based policies
- Sub-topic: T03 (also T09)
- Agree: 2 of 5. Notes: b:N20, b:N22. Urls: https://builder.aws.com/content/3Kclu4dDUaoAETVUirp8jgTvSjB/a-practical-guide-to-secure-access-management https://www.examcert.app/blog/aws-saa-c03-scenario-questions/
- Disagree: none found
- Level: core
- Best story: none

## TH14 Match the EC2 purchasing option to the usage pattern: Savings Plans or RIs for steady 24/7, Spot for interruptible, On-Demand for short or unpredictable, Dedicated for licensing
- Sub-topic: T04 (also T17)
- Agree: 2 of 4. Notes: b:N23, b:N24, d:N16, d:N17. Urls: https://www.examcert.app/blog/aws-saa-c03-scenario-questions/ https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/instance-purchasing-options.html
- Disagree: none found
- Level: core
- Best story: The nightly 3-hour batch job and the three-year contract that baits you into Reserved Instances; Spot wins because RIs bill all 24 hours, https://www.examcert.app/blog/aws-saa-c03-scenario-questions/

## TH15 Use EBS for one instance needing low latency, EFS (Linux, NFS) for many instances sharing files, FSx for Windows or HPC, and S3 for objects over an API
- Sub-topic: T05 (also T09, T17, T16)
- Agree: 3 of 3. Notes: a:N14, a:N15, a:N16, a:N17, a:N18, a:N19, a:N21, a:N22, c:N21, c:N22, c:N24. Urls: https://www.cloudzero.com/blog/ebs-vs-efs https://digitalcloud.training/aws-certified-solutions-architect-saa-c02/ https://aws.amazon.com/compare/ebs-and-efs/
- Disagree: none found
- Level: foundation
- Best story: none

## TH16 Default EBS to gp3, step up to io2 for a guaranteed IOPS floor; choose instance store or a cluster placement group only when you need raw speed and can lose the node
- Sub-topic: T05 (also T04, T17)
- Agree: 3 of 3. Notes: a:N12, a:N13, a:N20, c:N23. Urls: https://digitalcloud.training/aws-certified-solutions-architect-saa-c02/ https://www.cloudzero.com/blog/ebs-vs-efs https://aws.amazon.com/compare/ebs-and-efs/
- Disagree: none found
- Level: core
- Best story: none

## TH17 Put an internet-facing ALB in public subnets in front of an Auto Scaling group spread over several AZs in private subnets
- Sub-topic: T06 (also T13, T16)
- Agree: 4 of 6. Notes: a:N24, b:N37, d:N15, e:N11. Urls: https://www.golinuxcloud.com/aws-autoscaling-tutorial/ https://www.sailor.sh/blog/aws-vpc-concepts-for-saa-c03 https://dev.to/luminousmen/understanding-aws-regions-and-availability-zones-a-guide-for-beginners-1bcd https://notes.kodekloud.com/docs/AWS-For-Beginners-with-Hands-On-Labs/AWS-Essentials-Part-2/AWS-AutoscalingELB/page
- Disagree: none found
- Level: foundation
- Best story: none

## TH18 Configure the Auto Scaling group: min, desired and max, a versioned launch template, and a health-check grace period long enough for the app to boot; it then replaces failed instances itself
- Sub-topic: T06 (also T16)
- Agree: 2 of 6. Notes: a:N23, a:N25, a:N28, a:N29, e:N9, e:N10, e:N12, e:N14, e:N15. Urls: https://www.golinuxcloud.com/aws-autoscaling-tutorial/ https://notes.kodekloud.com/docs/AWS-For-Beginners-with-Hands-On-Labs/AWS-Essentials-Part-2/AWS-AutoscalingELB/page
- Disagree: none found
- Level: foundation
- Best story: Kill an instance on purpose and watch the ASG log "Instance terminated", then "Launching a new instance", https://notes.kodekloud.com/docs/AWS-For-Beginners-with-Hands-On-Labs/AWS-Essentials-Part-2/AWS-AutoscalingELB/page

## TH19 Default to target tracking on the metric that shows real load: CPU for web tiers, SQS backlog per instance for queue workers; use scheduled scaling for predictable peaks
- Sub-topic: T06 (also T11)
- Agree: 4 of 6. Notes: a:N26, a:N27, a:N30, a:N31, b:N25, b:N28, e:N13, e:N16. Urls: https://www.golinuxcloud.com/aws-autoscaling-tutorial/ https://digitalcloud.training/aws-certified-solutions-architect-saa-c02/ https://www.examcert.app/blog/aws-saa-c03-scenario-questions/ https://notes.kodekloud.com/docs/AWS-For-Beginners-with-Hands-On-Labs/AWS-Essentials-Part-2/AWS-AutoscalingELB/page
- Disagree: none found
- Level: core
- Best story: `stress -c 1` pushes CPU past the 40% target, desired capacity climbs from 1 to 3 and stops at the maximum, https://notes.kodekloud.com/docs/AWS-For-Beginners-with-Hands-On-Labs/AWS-Essentials-Part-2/AWS-AutoscalingELB/page

## TH20 Use RDS Multi-AZ for failover (synchronous, standby not readable) and read replicas for read scaling (asynchronous, readable); they solve different problems
- Sub-topic: T07 (also T16)
- Agree: 2 of 7. Notes: a:N33, e:N18, e:N19, e:N20, e:N21, e:N22. Urls: https://digitalcloud.training/aws-certified-solutions-architect-saa-c02/ https://notes.kodekloud.com/docs/AWS-Certified-DevOps-Engineer-Professional/Domain-3-Resilient-Cloud-Solutions/Demo-RDS-Multi-AZ-Read-Replicas/page
- Disagree: none found
- Level: foundation
- Best story: none

## TH21 Pick the database by access pattern: RDS or Aurora for SQL and joins, DynamoDB for known key lookups at single-digit ms, Redshift for analytics, ElastiCache as a cache, MemoryDB as a durable in-memory primary
- Sub-topic: T07 (also T12)
- Agree: 4 of 7. Notes: b:N32, c:N25, c:N26, e:N23. Urls: https://www.examcert.app/blog/aws-saa-c03-scenario-questions/ https://aws.amazon.com/compare/ebs-and-efs/ https://aws.amazon.com/compare/cloudfront-and-global-accelerator/ https://notes.kodekloud.com/docs/AWS-Certified-DevOps-Engineer-Professional/Domain-3-Resilient-Cloud-Solutions/Demo-RDS-Multi-AZ-Read-Replicas/page
- Disagree: none found
- Level: core
- Best story: none

## TH22 Pick the Route 53 routing policy by the question asked (latency, geolocation vs geoproximity, weighted, failover), and fail over on health checks rather than by hand-editing weights
- Sub-topic: T08 (also T16)
- Agree: 2 of 2 (thin evidence). Notes: d:N18, d:N19, d:N20. Urls: https://docs.aws.amazon.com/Route53/latest/DeveloperGuide/routing-policy.html https://docs.aws.amazon.com/whitepapers/latest/disaster-recovery-workloads-on-aws/disaster-recovery-options-in-the-cloud.html
- Disagree: https://docs.aws.amazon.com/Route53/latest/DeveloperGuide/routing-policy.html: lists weighted routing as a plain option (vs the DR whitepaper warning that changing weights for failover is a less resilient control plane action, https://docs.aws.amazon.com/whitepapers/latest/disaster-recovery-workloads-on-aws/disaster-recovery-options-in-the-cloud.html); https://docs.aws.amazon.com/whitepapers/latest/disaster-recovery-workloads-on-aws/disaster-recovery-options-in-the-cloud.html: also warns that automatic failover on health checks should be used with caution, since a false alarm costs data, and many teams start a fully automated failover by hand (d:N48)
- Level: core
- Best story: none

## TH23 Choose the S3 storage class by access frequency and required retrieval time; MOST cost-effective never licenses breaking a retrieval requirement
- Sub-topic: T09 (also T17, T01)
- Agree: 4 of 10. Notes: b:N11, b:N26, c:N27, c:N28, d:N21, d:N24, d:N25, d:N26, d:N27. Urls: https://forum.freecodecamp.org/t/how-i-structured-a-6-week-study-plan-for-aws-saa-c03-what-actually-moved-the-needle/799377 https://www.examcert.app/blog/aws-saa-c03-scenario-questions/ https://coursedesk.laravel.cloud/courses/aws-certified-solutions-architect-associate/lessons/how-to-read-an-saa-c03-question https://docs.aws.eu/AmazonS3/latest/dev/storage-class-intro.html
- Disagree: none found
- Level: core
- Best story: 40 TB of logs: Standard, then Standard-IA, then Deep Archive, until "within 5 minutes" replaces "up to 12 hours", https://coursedesk.laravel.cloud/courses/aws-certified-solutions-architect-associate/lessons/how-to-read-an-saa-c03-question

## TH24 Automate tiering with lifecycle rules, and respect the minimums: 30 days and 128 KB for the IA classes, One Zone-IA only for data you can re-create
- Sub-topic: T09 (also T17)
- Agree: 2 of 10. Notes: c:N27, c:N28, d:N22, d:N23, d:N28. Urls: https://coursedesk.laravel.cloud/courses/aws-certified-solutions-architect-associate/lessons/how-to-read-an-saa-c03-question https://docs.aws.eu/AmazonS3/latest/dev/storage-class-intro.html
- Disagree: none found
- Level: core
- Best story: The early-delete surprise: small or short-lived files in Standard-IA still bill 128 KB and 30 days each, https://docs.aws.eu/AmazonS3/latest/dev/storage-class-intro.html

## TH25 Lock down S3: bucket policies, SSE-KMS where you must control keys, and let users reach the bucket only through CloudFront using Origin Access Control (OAC) or signed URLs
- Sub-topic: T09 (also T10, T14, T03)
- Agree: 5 of 10. Notes: a:N38, b:N10, b:N20, b:N43, c:N18. Urls: https://digitalcloud.training/aws-certified-solutions-architect-saa-c02/ https://forum.freecodecamp.org/t/how-i-structured-a-6-week-study-plan-for-aws-saa-c03-what-actually-moved-the-needle/799377 https://builder.aws.com/content/3Kclu4dDUaoAETVUirp8jgTvSjB/a-practical-guide-to-secure-access-management https://www.examcert.app/blog/aws-saa-c03-scenario-questions/ https://builder.aws.com/content/3L0TDjBSq7BYCw9eRO0NlSZpRaQ/aws-shared-responsibility-model-explained-for-beginners
- Disagree: none found
- Flag: Outdated source wording: Digital Cloud (a:N38) names Origin Access Identity (OAI). OAI is legacy and superseded by Origin Access Control (OAC); teach OAC.
- Level: core
- Best story: none

## TH26 Use CloudFront to cache HTTP content at the edge; use Global Accelerator for static anycast IPs, TCP/UDP traffic and fast Regional failover
- Sub-topic: T10 (also T02, T16, T17)
- Agree: 3 of 4. Notes: a:N34, a:N35, a:N36, a:N37, c:N29, c:N30, c:N31, c:N32, d:N14. Urls: https://tutorialsdojo.com/aws-global-accelerator-vs-amazon-cloudfront/ https://aws.amazon.com/compare/cloudfront-and-global-accelerator/ https://dev.to/luminousmen/understanding-aws-regions-and-availability-zones-a-guide-for-beginners-1bcd
- Disagree: https://aws.amazon.com/compare/cloudfront-and-global-accelerator/: lists "API acceleration" under CloudFront while its own expert quote says Global Accelerator is for "non-cacheable traffic like APIs"; resolve by cacheability and protocol
- Flag: Outdated source wording: restricting an S3 origin is taught in some sources as Origin Access Identity (OAI); say Origin Access Control (OAC). See the S3 lock-down theme.
- Level: core
- Best story: Buffering video site fixed by moving assets to S3 behind CloudFront, versus a multi-Region bank app that needs Global Accelerator's static IPs, https://tutorialsdojo.com/aws-global-accelerator-vs-amazon-cloudfront/

## TH27 Put an SQS queue between tiers to absorb spikes: consumers poll, the visibility timeout hands a stuck message to another worker, and FIFO is the choice when order or exactly-once matters
- Sub-topic: T11 (also T06)
- Agree: 2 of 4. Notes: a:N39, a:N40, a:N41, b:N28, b:N29. Urls: https://dashbird.io/blog/kinesis-sqs-sns-comparison https://www.examcert.app/blog/aws-saa-c03-scenario-questions/
- Disagree: https://www.examcert.app/blog/aws-saa-c03-scenario-questions/: SNS push "is not a buffer", so it is the wrong answer for absorbing load
- Level: foundation
- Best story: The retailer losing orders in a sale; an SQS queue plus Auto Scaling on backlog fixes it, and the database at 20% CPU is a red herring, https://www.examcert.app/blog/aws-saa-c03-scenario-questions/

## TH28 Fan out one event to many consumers with an SNS topic and one SQS queue per consumer; start here before reaching for Kinesis
- Sub-topic: T11
- Agree: 2 of 4. Notes: a:N42, a:N45, b:N29. Urls: https://dashbird.io/blog/kinesis-sqs-sns-comparison https://www.examcert.app/blog/aws-saa-c03-scenario-questions/
- Disagree: none found
- Level: core
- Best story: none

## TH29 Use Kinesis Data Streams for real-time, replayable streams with several consumers, and Firehose to land streaming data in S3 or Redshift in near real time with no code
- Sub-topic: T11 (also T01)
- Agree: 3 of 4. Notes: a:N43, a:N44, a:N46, b:N29, e:N5. Urls: https://dashbird.io/blog/kinesis-sqs-sns-comparison https://www.examcert.app/blog/aws-saa-c03-scenario-questions/ https://notes.kodekloud.com/docs/AWS-Solutions-Architect-Associate-Certification/Introduction/Solutions-Architecture-Exam-guide-What-to-focus-on/page
- Disagree: none found
- Flag: Outdated source claim: Dashbird (2021) gives Kinesis Data Streams retention as 24 hours to 7 days. AWS now allows up to 365 days. Teach 24 hours default, extendable up to 365 days; do not repeat "7 days max". Firehose buffer figures are also from 2021.
- Level: core
- Best story: Live crypto prices every 10 seconds into a Kinesis stream, with Firehose dropping a new file into S3 every minute, https://dashbird.io/blog/kinesis-sqs-sns-comparison

## TH30 Reach for serverless when the stem says "without managing servers": API Gateway in front of a stateless Lambda that reads and writes DynamoDB, with EventBridge Scheduler for timed jobs
- Sub-topic: T12 (also T01, T07)
- Agree: 3 of 5. Notes: b:N30, b:N31, b:N32, c:N26. Urls: https://builder.aws.com/content/3KXRAwuplncnbnTDQfWDtn5P1ML/building-your-first-serverless-rest-api-with-aws-lambda-api-gateway-and-dynamodb https://www.examcert.app/blog/aws-saa-c03-scenario-questions/ https://aws.amazon.com/compare/cloudfront-and-global-accelerator/
- Disagree: https://builder.aws.com/content/3KXRAwuplncnbnTDQfWDtn5P1ML/building-your-first-serverless-rest-api-with-aws-lambda-api-gateway-and-dynamodb: attaches AmazonDynamoDBFullAccess to the Lambda role, against least privilege (https://builder.aws.com/content/3Kclu4dDUaoAETVUirp8jgTvSjB/a-practical-guide-to-secure-access-management)
- Level: foundation
- Best story: none

## TH31 Make a subnet public only through its route table (0.0.0.0/0 to an internet gateway), one subnet per AZ, and plan non-overlapping CIDRs (5 addresses reserved per subnet) from day one
- Sub-topic: T13 (also T02)
- Agree: 4 of 7. Notes: a:N9, b:N33, b:N34, b:N42, d:N30, d:N31, d:N32, d:N34, d:N39, e:N24, e:N25, e:N26, e:N27. Urls: https://www.janmeppe.com/blog/i-recently-passed-the-aws-solution-architect-associate-exam-aws-saa-c03-heres-how-i-did-it/ https://www.sailor.sh/blog/aws-vpc-concepts-for-saa-c03 https://coursedesk.laravel.cloud/courses/aws-certified-solutions-architect-associate/lessons/vpc-anatomy-cidr-subnets-and-route-tables https://docs.aws.eu/vpc/latest/userguide/VPC_Subnets.html
- Disagree: none found
- Level: foundation
- Best story: VPC was a miserable slog until he let it simmer a week, then it clicked, https://www.janmeppe.com/blog/i-recently-passed-the-aws-solution-architect-associate-exam-aws-saa-c03-heres-how-i-did-it/

## TH32 Tell security groups (stateful, allow-only, on the ENI) from network ACLs (stateless, allow and deny, on the subnet); only a NACL can block a specific IP
- Sub-topic: T13 (also T01)
- Agree: 3 of 7. Notes: b:N35, b:N36, c:N5, d:N34. Urls: https://www.sailor.sh/blog/aws-vpc-concepts-for-saa-c03 https://coursedesk.laravel.cloud/courses/aws-certified-solutions-architect-associate/lessons/how-to-read-an-saa-c03-question https://coursedesk.laravel.cloud/courses/aws-certified-solutions-architect-associate/lessons/vpc-anatomy-cidr-subnets-and-route-tables
- Disagree: none found
- Level: foundation
- Best story: The app that can call out but never hears back: a stateless NACL missing the ephemeral port return rule, https://www.sailor.sh/blog/aws-vpc-concepts-for-saa-c03

## TH33 Lay out three tiers per AZ (public, private app, private data) and chain security groups so each tier only accepts the one in front of it
- Sub-topic: T13 (also T06)
- Agree: 3 of 7. Notes: b:N37, d:N33, e:N11. Urls: https://www.sailor.sh/blog/aws-vpc-concepts-for-saa-c03 https://coursedesk.laravel.cloud/courses/aws-certified-solutions-architect-associate/lessons/vpc-anatomy-cidr-subnets-and-route-tables https://notes.kodekloud.com/docs/AWS-For-Beginners-with-Hands-On-Labs/AWS-Essentials-Part-2/AWS-AutoscalingELB/page
- Disagree: none found
- Level: core
- Best story: none

## TH34 Give private subnets outbound internet through a NAT gateway placed in a public subnet, one per AZ; a NAT instance only for special cases (source/destination check off)
- Sub-topic: T13 (also T16)
- Agree: 3 of 7. Notes: b:N38, d:N35, d:N36, d:N37, e:N28. Urls: https://www.sailor.sh/blog/aws-vpc-concepts-for-saa-c03 https://coursedesk.laravel.cloud/courses/aws-certified-solutions-architect-associate/lessons/vpc-anatomy-cidr-subnets-and-route-tables https://docs.aws.eu/vpc/latest/userguide/VPC_Subnets.html
- Disagree: https://www.sailor.sh/blog/aws-vpc-concepts-for-saa-c03: NAT Gateway scales "up to 100 Gbps" (vs "up to 45 Gbps" in https://coursedesk.laravel.cloud/courses/aws-certified-solutions-architect-associate/lessons/vpc-anatomy-cidr-subnets-and-route-tables); check the current AWS figure before quoting a number
- Level: core
- Best story: The NAT gateway in the wrong subnet: no route to the IGW, so nothing gets out, and a single NAT gateway takes every AZ's outbound traffic down with its own AZ, https://coursedesk.laravel.cloud/courses/aws-certified-solutions-architect-associate/lessons/vpc-anatomy-cidr-subnets-and-route-tables

## TH35 Keep traffic to AWS services private with VPC endpoints: free gateway endpoints for S3 and DynamoDB, interface endpoints (PrivateLink) for the rest
- Sub-topic: T13 (also T17)
- Agree: 2 of 7. Notes: b:N39, c:N5. Urls: https://www.sailor.sh/blog/aws-vpc-concepts-for-saa-c03 https://coursedesk.laravel.cloud/courses/aws-certified-solutions-architect-associate/lessons/how-to-read-an-saa-c03-question
- Disagree: none found
- Level: core
- Best story: none

## TH36 Connect networks with the right link: peering is one-to-one and not transitive, Transit Gateway is the hub for many VPCs, Site-to-Site VPN is fast to set up, Direct Connect is dedicated but slow to provision
- Sub-topic: T13
- Agree: 3 of 7. Notes: b:N40, b:N41, d:N30, e:N29, e:N30. Urls: https://www.sailor.sh/blog/aws-vpc-concepts-for-saa-c03 https://coursedesk.laravel.cloud/courses/aws-certified-solutions-architect-associate/lessons/vpc-anatomy-cidr-subnets-and-route-tables https://docs.aws.eu/vpc/latest/userguide/VPC_Subnets.html
- Disagree: none found
- Level: core
- Best story: none

## TH37 Encrypt with KMS envelope encryption, and pick a customer managed key when you must control, disable and audit the key
- Sub-topic: T14 (also T09, T15)
- Agree: 2 of 6. Notes: b:N43, e:N31, e:N32, e:N33, e:N34, e:N35, e:N36, e:N37, e:N38. Urls: https://www.examcert.app/blog/aws-saa-c03-scenario-questions/ https://workos.com/blog/envelope-encryption-explained
- Disagree: none found
- Level: core
- Best story: A key that never gets rotated: one AES key sits in an environment variable for years until an audit finds it in an old log, https://workos.com/blog/envelope-encryption-explained

## TH38 Map each security ask to its service: Secrets Manager to rotate credentials, WAF for SQL injection and XSS, encryption enabled at creation (RDS needs a snapshot copy to encrypt later)
- Sub-topic: T14 (also T07)
- Agree: 2 of 6. Notes: a:N32, b:N44. Urls: https://digitalcloud.training/aws-certified-solutions-architect-saa-c02/ https://www.examcert.app/blog/aws-saa-c03-scenario-questions/
- Disagree: none found
- Flag: Macie is not covered by any source here beyond one wrong example ("removes" PII, a:N8). If a lesson names it: Macie discovers and classifies sensitive data in S3; it does not remove it.
- Level: core
- Best story: none

## TH39 Tell the monitoring services apart: CloudTrail says who called which API, Config says what a resource looked like and whether it complies, CloudWatch holds metrics, logs and alarms, VPC Flow Logs hold traffic metadata
- Sub-topic: T15 (also T03, T13, T14)
- Agree: 4 of 4. Notes: b:N21, b:N45, c:N33, c:N34, c:N35, c:N36, c:N37, e:N37. Urls: https://builder.aws.com/content/3Kclu4dDUaoAETVUirp8jgTvSjB/a-practical-guide-to-secure-access-management https://www.sailor.sh/blog/aws-vpc-concepts-for-saa-c03 https://cloud.in28minutes.com/aws-certification-aws-cloudtrail-vs-config-vs-cloudwatch https://workos.com/blog/envelope-encryption-explained
- Disagree: none found
- Level: foundation
- Best story: none

## TH40 Separate high availability (survive an AZ failure with Multi-AZ) from disaster recovery (survive a Region loss or corruption), and state RTO and RPO before picking a design
- Sub-topic: T16
- Agree: 2 of 14. Notes: b:N46, b:N47, d:N47. Urls: https://hidekazu-konishi.com/entry/aws_disaster_recovery_strategies_guide.html https://docs.aws.amazon.com/whitepapers/latest/disaster-recovery-workloads-on-aws/disaster-recovery-options-in-the-cloud.html
- Disagree: none found
- Level: foundation
- Best story: none

## TH41 Pick the simplest DR strategy that meets RTO and RPO: backup and restore, pilot light (data on, servers off), warm standby (small copy serving), multi-site active/active
- Sub-topic: T16 (also T01)
- Agree: 3 of 14. Notes: a:N10, b:N48, b:N49, d:N40, d:N42, d:N43, d:N44. Urls: https://tutorialsdojo.com/my-saa-c03-aws-certified-solution-architect-associate-exam-experience-2023/ https://hidekazu-konishi.com/entry/aws_disaster_recovery_strategies_guide.html https://docs.aws.amazon.com/whitepapers/latest/disaster-recovery-workloads-on-aws/disaster-recovery-options-in-the-cloud.html
- Disagree: none found
- Level: core
- Best story: none from sources (a gas-stove picture of pilot light vs warm standby is the hosts' own image, not the whitepaper's)

## TH42 Set backup cadence to match your RPO and keep versioning and point-in-time backups, because replication is not backup; use Aurora Global Database or DynamoDB global tables when the RPO is seconds
- Sub-topic: T16 (also T07, T09, T12)
- Agree: 3 of 14. Notes: b:N27, b:N50, d:N29, d:N41, d:N45, d:N46, d:N49. Urls: https://hidekazu-konishi.com/entry/aws_disaster_recovery_strategies_guide.html https://www.examcert.app/blog/aws-saa-c03-scenario-questions/ https://docs.aws.amazon.com/whitepapers/latest/disaster-recovery-workloads-on-aws/disaster-recovery-options-in-the-cloud.html
- Disagree: none found
- Level: core
- Best story: Someone deletes or corrupts data and replication faithfully copies the damage to the DR Region; only versioning and point-in-time backups save you, https://docs.aws.amazon.com/whitepapers/latest/disaster-recovery-workloads-on-aws/disaster-recovery-options-in-the-cloud.html

## TH43 Test the DR plan: restore the backups, raise service quotas in the DR Region, and consider a manual, push-button trigger for a fully automated failover
- Sub-topic: T16
- Agree: 1 of 14. Notes: d:N48, d:N50. Urls: https://docs.aws.amazon.com/whitepapers/latest/disaster-recovery-workloads-on-aws/disaster-recovery-options-in-the-cloud.html
- Disagree: https://docs.aws.amazon.com/whitepapers/latest/disaster-recovery-workloads-on-aws/disaster-recovery-options-in-the-cloud.html: the same whitepaper calls health-check driven DNS failover the highly reliable data plane option (d:N20), so automatic vs push-button is a judgment call
- Level: advanced
- Best story: none

## TH44 Use the six Well-Architected pillars as a set of review questions; an honest "I don't know" marks the gap
- Sub-topic: T17 (also T01, T14, T16)
- Agree: 2 of 17. Notes: a:N47, a:N48, a:N49, a:N50, c:N38, c:N39, c:N40, c:N41, c:N42. Urls: https://tutorialsdojo.com/aws-well-architected-framework-six-pillars/ https://aws.amazon.com/architecture/well-architected
- Disagree: none found
- Level: foundation
- Best story: Financial app passes every test, then the team walks the Security pillar questions before go-live, and "I don't know" exposes the gap, https://tutorialsdojo.com/aws-well-architected-framework-six-pillars/

## TH45 Hunt the hidden charges: set billing alerts, delete lab resources, release idle Elastic IPs, route S3 traffic through gateway endpoints instead of NAT, and remember Config rules and Global Accelerator bill by the hour or rule
- Sub-topic: T17 (also T01, T06)
- Agree: 8 of 17. Notes: a:N17, a:N21, b:N39, c:N14, c:N32, c:N37, d:N7, d:N38, e:N17. Urls: https://www.cloudzero.com/blog/ebs-vs-efs https://www.sailor.sh/blog/aws-vpc-concepts-for-saa-c03 https://cloudposse.com/blog/devops/cloud/how-to-pick-your-primary-aws-region https://aws.amazon.com/compare/cloudfront-and-global-accelerator/ https://cloud.in28minutes.com/aws-certification-aws-cloudtrail-vs-config-vs-cloudwatch https://dev.to/franciscojeg78/aws-saa-c03-30-day-learning-plan-using-stephane-maareks-ultimate-aws-certified-solutions-architect-17j3 https://coursedesk.laravel.cloud/courses/aws-certified-solutions-architect-associate/lessons/vpc-anatomy-cidr-subnets-and-route-tables https://notes.kodekloud.com/docs/AWS-For-Beginners-with-Hands-On-Labs/AWS-Essentials-Part-2/AWS-AutoscalingELB/page
- Disagree: none found
- Level: core
- Best story: none

## The big splits
- **Hands-on projects vs reading skill.** For labs and projects: https://forum.freecodecamp.org/t/how-i-structured-a-6-week-study-plan-for-aws-saa-c03-what-actually-moved-the-needle/799377, https://8thlight.com/insights/making-most-aws-kubernetes-certifications, https://dev.to/rabindratamang/how-i-passed-the-aws-solution-architect-associate-exam-my-study-plan-and-tips-5ahh, https://digitalcloud.training/aws-certified-solutions-architect-saa-c02/. Against spending exam prep time on console work: https://www.sailor.sh/blog/aws-vpc-concepts-for-saa-c03 (the exam has no labs) and https://coursedesk.laravel.cloud/courses/aws-certified-solutions-architect-associate/lessons/how-to-read-an-saa-c03-question (failers know the services and misread the question). It turns on learning method versus exam format: projects make "which service" obvious, but the score is won or lost on reading the qualifier. (TH03, TH05)
- **How much study, and from what.** About 40 hours over 2 months on one course (https://www.janmeppe.com/blog/i-recently-passed-the-aws-solution-architect-associate-exam-aws-saa-c03-heres-how-i-did-it/) and "skip any course over 15 hours" (https://forum.freecodecamp.org/t/how-i-structured-a-6-week-study-plan-for-aws-saa-c03-what-actually-moved-the-needle/799377) vs AWS's one year of hands-on experience and long courses or bootcamps (https://digitalcloud.training/aws-certified-solutions-architect-saa-c02/, https://digitalcloud.training/why-an-aws-certification-will-not-get-you-an-aws-job/). Cantrill for depth (https://dev.to/rabindratamang/how-i-passed-the-aws-solution-architect-associate-exam-my-study-plan-and-tips-5ahh) vs Maarek as the only course (https://dev.to/franciscojeg78/aws-saa-c03-30-day-learning-plan-using-stephane-maareks-ultimate-aws-certified-solutions-architect-17j3). It turns on prior experience and on who sells the course. (TH07)
- **When to start practice exams.** Early, at about 30% of the material (https://www.janmeppe.com/blog/i-recently-passed-the-aws-solution-architect-associate-exam-aws-saa-c03-heres-how-i-did-it/) vs near the end (https://digitalcloud.training/aws-certified-solutions-architect-saa-c02/). Everyone agrees they matter; the person who skipped them failed (https://tutorialsdojo.com/my-saa-c03-aws-certified-solution-architect-associate-exam-experience-2023/). It turns on using tests to learn versus using them to check readiness. (TH04)
- **How many certifications.** Do all the associates plus a professional (https://digitalcloud.training/why-an-aws-certification-will-not-get-you-an-aws-job/, 2025) vs one or two, then build projects (https://digitalcloud.training/the-truth-about-aws-certifications-after-25-years-in-tech/, 2026). The same company reversed itself. It turns on whether badges or a portfolio get you hired. (TH08)
- **Short or long questions.** "Straight to the point" 1 to 2 line scenarios (https://digitalcloud.training/aws-certified-solutions-architect-saa-c02/, a page written for SAA-C02) vs "long-winded scenarios with equally-long options" (https://tutorialsdojo.com/my-saa-c03-aws-certified-solution-architect-associate-exam-experience-2023/, SAA-C03 in 2023). Most likely an exam-version difference. (TH01)
- **Automatic vs push-button failover.** Health-check driven DNS failover is the reliable data plane option and hand-edited weights are a weaker control plane action (https://docs.aws.amazon.com/whitepapers/latest/disaster-recovery-workloads-on-aws/disaster-recovery-options-in-the-cloud.html), while Route 53 docs list weighted routing as a plain option (https://docs.aws.amazon.com/Route53/latest/DeveloperGuide/routing-policy.html). The same whitepaper also warns that auto-failover on a false alarm costs data, so many teams start a fully automated failover by hand. It turns on false-alarm risk versus recovery speed. (TH22, TH43)
- **Least privilege vs tutorial shortcuts.** Scoped actions like s3:GetObject (https://builder.aws.com/content/3Kclu4dDUaoAETVUirp8jgTvSjB/a-practical-guide-to-secure-access-management) vs AmazonDynamoDBFullAccess on a Lambda role (https://builder.aws.com/content/3KXRAwuplncnbnTDQfWDtn5P1ML/building-your-first-serverless-rest-api-with-aws-lambda-api-gateway-and-dynamodb). It turns on convenience in a lab versus the exam's "MOST secure" answer. (TH11, TH30)
- **Smaller splits.** us-east-1 as a default Region (https://cloudposse.com/blog/devops/cloud/how-to-pick-your-primary-aws-region, TH09). CloudFront or Global Accelerator for APIs (https://aws.amazon.com/compare/cloudfront-and-global-accelerator/, TH26). NAT gateway throughput, 100 Gbps (https://www.sailor.sh/blog/aws-vpc-concepts-for-saa-c03) vs 45 Gbps (https://coursedesk.laravel.cloud/courses/aws-certified-solutions-architect-associate/lessons/vpc-anatomy-cidr-subnets-and-route-tables), TH34. Whether edge locations are riskier (https://dev.to/luminousmen/understanding-aws-regions-and-availability-zones-a-guide-for-beginners-1bcd, unsupported, TH10).

## Coverage gaps
- **Thin evidence (M under 3):** T08 Route 53 (2 pages, both AWS docs; TH22). T18 Containers (1 page, one passing note on AZ counts for Kubernetes); there is no container theme at all.
- **Barely covered (M 3 to 4, or one supporting page):** T05 storage (3 pages; FSx in one note, no Multi-Attach or snapshot lifecycle detail), T04 EC2 (4 pages; placement groups in one note), T10 edge (4), T11 decoupling (4), T15 monitoring (4; VPC Flow Logs in one page), TH38 security services (2 pages; Shield, GuardDuty and Macie absent).
- **What a beginner would expect that no source covered:**
  - Containers: ECS vs EKS, Fargate vs EC2 launch type, ECR. One test taker saw Kubernetes autoscaling on the exam (a:N10).
  - Route 53 basics: record types (A, AAAA, CNAME, alias), hosted zones, TTL.
  - EC2 basics: AMIs, instance families, user data, security groups on the instance, Spot interruption notice, hibernation.
  - Load balancers: NLB and Gateway Load Balancer, cross-zone load balancing, sticky sessions, TLS termination with ACM. Only the ALB is covered.
  - Decoupling: EventBridge rules and buses (only EventBridge Scheduler is named), SQS dead-letter queues, long polling, Step Functions.
  - Serverless: Lambda limits, concurrency and cold starts; DynamoDB capacity modes, streams and DAX (one mention).
  - Databases: ElastiCache caching strategies (lazy loading, write-through), Aurora Serverless, RDS Proxy, automated backups and point-in-time restore.
  - Security: Shield Standard vs Advanced, GuardDuty, Inspector, Macie (one source, and it gets Macie wrong), ACM, KMS key policies, Cognito, IAM Identity Center.
  - Migration and hybrid storage: Storage Gateway, DataSync, the Snow family, DMS, AWS Backup.
  - Data and analytics (a named SAA-C03 task statement, e:N5): Glue, Athena, Lake Formation, EMR, QuickSight.
  - Multi-account: AWS Organizations beyond SCPs, Control Tower.
- **Notes not used in any theme:** c:N10 (curriculum changes fast), c:N12 (avoid us-east-1, kept as a disagreement on TH09), e:N8 (backbone packet-loss target).
