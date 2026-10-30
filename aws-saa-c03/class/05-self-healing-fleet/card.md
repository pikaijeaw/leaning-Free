# Lesson 5. Self-Healing Fleet

**Listen:** self-healing-fleet.mp3 (2 min)
**The idea, in three lines**
- An Application Load Balancer in public subnets sends traffic only to healthy servers.
- Behind it, an Auto Scaling group keeps a fleet between a minimum and a maximum, spread over zones in private subnets, and replaces any server that fails.
- A target tracking policy (for example, average CPU at 40 or 50 percent) adds servers when load rises and removes them when it drops.

**Impact:** "highly available and scales with demand" questions get one picture as the answer, and you stop thinking of servers as pets to be nursed back to health.

**Who says it:** 4 of the 6 pages on load balancing and scaling teach the load balancer in front of a multi-zone Auto Scaling group, and target tracking on a real load metric; 2 of 6 walk through the min, desired and max setup. None disagree.

**Try it** · Deep Focus · 15 min
On paper (free):
> **1. The shop.** A small online shop needs 2 servers on a normal day and 6 at its busiest.
> **2. Numbers.** Write min, desired and max. (One answer: 2, 2, 6.)
> **3. Metric.** Pick a target tracking metric and value (for example, average CPU at 50 percent).
> **4. Zones.** Write which two zones the servers spread over, and that they sit in private subnets.
> **5. Failure.** One server dies at 3 a.m. Write the two log lines the group would show.

**Optional lab (costs money).** A load balancer and EC2 instances bill while they run, even small ones. If you build it, follow the KodeKloud walkthrough below, then tear down in this order: delete the Auto Scaling group (it terminates its instances), then the load balancer, then the target group, then check the EC2 console that no instances are left running.

**Rule to keep**
Let the group replace a sick server; never nurse one by hand.

**Skip** · no cost, no catch-up. Lesson 6 is just lesson 6.

**Go deeper (optional)**
- The KodeKloud lab: terminate an instance, stress the CPU, watch it scale: https://notes.kodekloud.com/docs/AWS-For-Beginners-with-Hands-On-Labs/AWS-Essentials-Part-2/AWS-AutoscalingELB/page
- A step by step Auto Scaling tutorial: https://www.golinuxcloud.com/aws-autoscaling-tutorial/
