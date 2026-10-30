# Lesson 6. Right Disk

**Listen:** right-disk.mp3 (2 min)
**The idea, in three lines**
- EBS is one instance's hard drive (boot disks, databases), living in one Availability Zone. Default to gp3; step up to io2 when you need a guaranteed IOPS floor.
- EFS is a shared file system that many Linux instances mount at once, across zones. S3 is object storage you reach over an API, not a drive you mount.
- Instance store is very fast disk on the host, gone when the instance goes. Scratch only.

**Impact:** storage questions stop being a guess between four similar names; you match the disk to how many instances use it and how they reach it.

**Who says it:** 3 of the 3 pages on storage teach this split and gp3 as the EBS default; none disagree.

**Try it** · Quick Win · 5 min
On paper, sort these five workloads into EBS, EFS, S3 or instance store:
> **1.** The boot disk of a web server.
> **2.** Uploads that ten web servers in two zones all read and write.
> **3.** An archive of old videos, fetched now and then.
> **4.** A temporary cache you can rebuild in seconds.
> **5.** A single database server's data volume.

Answers: 1 EBS, 2 EFS, 3 S3, 4 instance store, 5 EBS (gp3, or io2 if it needs guaranteed IOPS).

**Rule to keep**
One instance, EBS; many instances, EFS; anything over HTTP, S3.

**Skip** · no cost, no catch-up. Lesson 7 is just lesson 7.

**Go deeper (optional)**
- EBS vs EFS, with use cases and prices: https://www.cloudzero.com/blog/ebs-vs-efs
- AWS's own comparison, including the gp3 default: https://aws.amazon.com/compare/ebs-and-efs/
