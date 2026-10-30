# Lesson 2. Guard the Account

**Listen:** guard-the-account.mp3 (2:17)
**The idea, in three lines**
- AWS secures the cloud (buildings, hardware, network); you secure what you put in it (logins, permissions, settings, data).
- The root user gets multi factor authentication (MFA) and stays out of daily work.
- Apps and servers get IAM roles with temporary credentials, never access keys stored in code or config files.

**Impact:** a leaked config file or a forgotten lab stops being a disaster, and "MOST secure" exam answers start to look obvious: the role, the narrow permission, the private bucket.

**Who says it:** 3 of the 5 pages on access teach roles over stored keys and MFA on privileged users; 2 of 5 teach the shared responsibility line; 8 of 17 pages on cost warn about surprise charges, with billing alerts as the first defense. None disagree, though one AWS tutorial takes a shortcut and gives its Lambda role full DynamoDB access.

**Try it** · Admin · 10 min
In your AWS account (both steps are free settings, nothing gets built):
> **1. Root MFA.** Sign in as root, open your account's security credentials page, and assign an MFA device (an authenticator app works).
> **2. Budget alert.** Open AWS Budgets, create a cost budget at a small amount (for example 5 dollars a month), and add your email as the alert recipient.
> **3. Sign out of root.** Daily work happens as a separate, less powerful user.

No account yet? Write steps 1 and 2 on the first page of your notes and do them the day you sign up.

**Rule to keep**
Root gets MFA and gets left alone; apps get roles, never keys.

**Skip** · no cost, no catch-up. Lesson 3 is just lesson 3.

**Go deeper (optional)**
- Shared responsibility for beginners: https://builder.aws.com/content/3L0TDjBSq7BYCw9eRO0NlSZpRaQ/aws-shared-responsibility-model-explained-for-beginners
- IAM roles, least privilege and the access key example: https://builder.aws.com/content/3Kclu4dDUaoAETVUirp8jgTvSjB/a-practical-guide-to-secure-access-management
