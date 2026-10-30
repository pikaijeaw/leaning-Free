# Lesson 10. Read the Clock

**Listen:** read-the-clock.mp3 (2 min)
**The idea, in three lines**
- Pick the S3 storage class by two things: how often the data is read, and how fast it has to come back. Standard for hot data, the infrequent access classes next, the Glacier family at the cold end.
- On the exam, find the qualifier (MOST cost-effective, LEAST operational overhead) and every hard number before ranking options.
- Cheapest never wins if it breaks a hard requirement like a retrieval time.

**Impact:** long scenario questions shrink to a search for one phrase and a few numbers, and "cheap but too slow" distractors stop catching you.

**Who says it:** 4 of the 10 pages on S3 storage teach choosing by access and retrieval time; none disagree. 5 of the 16 exam-technique pages teach reading the qualifier first. One 8th Light engineer pushes back: for him, the gap was hands-on labs, not question reading.

**Try it** · Quick Win · 10 min
Take any one practice question (from any free set you already use). Before reading the options:
> **1. Last line first.** Read the final sentence. Underline the qualifier (for example, "MOST cost-effective").
> **2. Hard numbers.** Circle every time, size or count in the stem (for example, "within 5 minutes", "seven years").
> **3. Cut.** Now read the options. Cross out each one that breaks a circled number.
> **4. Rank.** Pick the survivor that best fits the qualifier.
> **5. Check.** Compare with the explanation. If you missed it, note which circled number you skipped.

**Rule to keep**
The last line of the question decides the answer.

**Skip** · no cost, no catch-up. Lesson 11 is just lesson 11.

**Go deeper (optional)**
- How to read an SAA-C03 question, with the 40 TB log example: https://coursedesk.laravel.cloud/courses/aws-certified-solutions-architect-associate/lessons/how-to-read-an-saa-c03-question
- The S3 storage classes, from AWS: https://docs.aws.eu/AmazonS3/latest/dev/storage-class-intro.html
- The hands-on view: https://8thlight.com/insights/making-most-aws-kubernetes-certifications
