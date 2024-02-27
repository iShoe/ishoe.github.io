---
title: "CloudFS - Hybrid File System"
excerpt: "A hybrid FUSE-based file system that spans between SSD and S3 to provide best of both worlds: fast access of SSD
and unlimited storage of cloud. Implemented features like de-duplication, caching and ability to take snapshots."
collection: projects
---

* Designed and implemented CloudFS, a FUSE-based hybrid file system combing SSD and cloud storage for optimal performance and unlimited storage capacity.
    * **Hybrid File System**: Developed a fully functional file system with automatic file relocation between *SSD* and *cloud* based on file size. Smaller files on SSD and bigger ones on the cloud.
    * **Deduplication**: Implemented block-level deduplication to reduce data redundancy and minimize cloud storage costs.
    * **Cache**: Introduced caching layer between FUSE and the cloud, leveraging LRU eviction policy to optimize access speed and reduce cloud requests/expenses. 
    * **Snapshots**: Enchaced file system with snapshot capabilities, allowing users to create, restore and manage snapshots for data recovery and versioning. 

<br/><img src='/images/CloudFS.png' width='500' height='600'>