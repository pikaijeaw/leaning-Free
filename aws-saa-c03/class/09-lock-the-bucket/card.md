# Lesson 9. Lock the Bucket

**Listen:** lock-the-bucket.mp3 (2 min)
**The idea, in three lines**
- Keep every bucket closed to the public; decide who gets in with a bucket policy on the bucket itself.
- When people need the files, serve them through CloudFront and keep the bucket private, instead of opening the bucket to the internet.
- When the company has to control, disable and audit its keys, encrypt with SSE-KMS and a customer managed KMS key.

**Impact:** "most secure" S3 questions get a quick answer, and the accidentally public bucket from lesson 2 has two locks in its way.

**Who says it:** 5 of the 10 pages on S3 teach locking buckets down this way; none disagree. 2 of the 6 pages on encryption teach the customer managed key for control and audit; none disagree.

**Try it** · Admin · 10 min
Free; you only look, nothing gets created.
> **1.** Sign in to the AWS console and open S3.
> **2.** In the left menu, choose **Block Public Access settings for this account**.
> **3.** Check that "Block all public access" is on. If it's off and you have no bucket that's meant to be public, turn it on.
> **4.** No account yet? On the first page of your security notes, write: policy on the bucket, files through CloudFront, customer managed key when keys must be controlled.

**Rule to keep**
No bucket is public; files reach people through CloudFront.

**Skip** · no cost, no catch-up. Lesson 10 is just lesson 10.

**Go deeper (optional)**
- The "keys the company controls" scenario, worked through: https://www.examcert.app/blog/aws-saa-c03-scenario-questions/
- Why a public bucket is your side of the deal: https://builder.aws.com/content/3L0TDjBSq7BYCw9eRO0NlSZpRaQ/aws-shared-responsibility-model-explained-for-beginners
