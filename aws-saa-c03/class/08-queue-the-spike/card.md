# Lesson 8. Queue the Spike

**Listen:** queue-the-spike.mp3 (2 min)
**The idea, in three lines**
- Put an SQS queue between tiers: a spike waits in line, and a message stays until a worker deletes it, so a crashed worker loses nothing.
- Scale the workers on backlog per instance (messages waiting divided by workers).
- SNS fans one event out to many queues, one per consumer; it isn't a buffer on its own. Kinesis is for real-time streams with several readers and replay.

**Impact:** "orders lost at peak" and "decouple the tiers" questions get a clear answer, and you stop fixing healthy databases that the question only mentions to distract you.

**Who says it:** 2 of the 4 pages on decoupling teach the queue and the SNS fan-out; none disagree. 3 of the 4 point to Kinesis for real-time, replayable streams; none disagree.

**Try it** · Quick Win · 10 min
On paper:
> **1. Before.** Draw a box "web server" with an arrow straight to a box "payment workers".
> **2. After.** Redraw it with a box "SQS queue" in the middle: web server sends to the queue, workers poll it.
> **3. Scaling.** Under the workers, write: Auto Scaling group, target tracking on backlog per instance.
> **4. Fan out (bonus).** Add an SNS topic that sends each order to two queues: one for payments, one for confirmation emails.

**Rule to keep**
When load arrives in bursts, put a queue in front of the work.

**Skip** · no cost, no catch-up. Lesson 9 is just lesson 9.

**Go deeper (optional)**
- The "orders lost during a sale" scenario, worked through: https://www.examcert.app/blog/aws-saa-c03-scenario-questions/
- SQS vs SNS vs Kinesis, with the fan-out pattern: https://dashbird.io/blog/kinesis-sqs-sns-comparison
