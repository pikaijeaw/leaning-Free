# Lesson 1. Two Zones Minimum

**Listen:** two-zones-minimum.mp3 (2:20)
**The idea, in three lines**
- A Region is a place on the map (Ohio, Frankfurt, Sydney). Each Region holds several Availability Zones: separate data centers with their own power and network.
- Running in two or more zones means one zone's outage doesn't take your app down.
- On the exam, "highly available" almost always means "more than one Availability Zone".

**Impact:** every design you sketch starts with two boxes, not one, and a whole family of exam distractors (single-AZ anything) stops fooling you.

**Who says it:** 4 of the 5 pages on global infrastructure teach "at least two zones"; none disagree. On picking a Region, Cloud Posse argues against us-east-1 as a default because it's the busiest and, by their account, has had the most outages.

**Try it** · Quick Win · 10 min
On paper, invent an app (for example, a booking site for gyms in Germany). Then:
> **1. Latency.** Where are most of your users? Which Region is closest?
> **2. Law.** Does any data have to stay in a country or region (for example, the EU)?
> **3. Services.** Note one service you'd want; AWS lists which Regions offer it.
> **4. Price.** Prices differ by Region; note that you'd compare.
> **5. Zones.** Write the Region you picked and two zones you'd spread across (for example, eu-central-1a and eu-central-1b).

**Rule to keep**
Nothing important runs in only one Availability Zone.

**Skip** · no cost, no catch-up. Lesson 2 is just lesson 2.

**Go deeper (optional)**
- Regions, zones and edge locations for beginners: https://dev.to/luminousmen/understanding-aws-regions-and-availability-zones-a-guide-for-beginners-1bcd
- How to pick a primary Region: https://cloudposse.com/blog/devops/cloud/how-to-pick-your-primary-aws-region
