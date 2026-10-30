# Lesson 11. Pay How You Use

**Listen:** pay-how-you-use.mp3 (2 min)
**The idea, in three lines**
- Steady, all-day work: a Savings Plan or Reserved Instances (a 1 or 3 year commitment). Work that can be interrupted: Spot. Short or unpredictable: On-Demand, paid by the second.
- A long business contract is not steady usage. Commitments bill every hour of the term, used or not.
- Hunt the quiet charges too: NAT gateways bill by the hour and per GB, and an unused Elastic IP still costs money.

**Impact:** you stop paying for idle hours, and the exam's "three-year contract" bait stops working on you.

**Who says it:** 2 of the 4 pages on EC2 purchasing options teach this match (one is AWS's own docs); none disagree. 8 of the 17 pages on cost warn about hidden charges.

**Try it** · Admin · 10 min
In the AWS Pricing Calculator (free, no resources launched):
> **1. Add EC2.** Add an Amazon EC2 estimate in a Region near you.
> **2. One small instance.** Pick one small general-purpose instance, Linux, running all month.
> **3. On-Demand.** Note the monthly cost with On-Demand pricing.
> **4. Savings Plan.** Switch the pricing model to a 1-year Savings Plan, no upfront. Note that monthly cost.
> **5. Think.** Write one line: if this ran only 3 hours a day, which would you pick, and why?

**Rule to keep**
Commit only to what runs all day; interruptible work goes to Spot.

**Skip** · no cost, no catch-up. Lesson 12 is just lesson 12.

**Go deeper (optional)**
- The nightly batch job scenario, worked through: https://www.examcert.app/blog/aws-saa-c03-scenario-questions/
- EC2 purchasing options, from AWS: https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/instance-purchasing-options.html
