---
title: "MyFTL - Flash Translation Layer"
excerpt: " Translates logical addresses into physical addresses on the flash, performs garbage collection of invalid blocks and incorporates block wear leveling to prolong the life of the SSD."
collection: projects
---

Flash Translation Layer (FTL) is a system within the SSD firm that takes the operations given to it by the file system or user programs and converts them to operations that need to be performed on the SSD. Its main function is to **translate logical addresses into physical addresses**. It has to do this while keeping the wear level of the SSD blocks in mind. 

In an SSD flash block, reads and writes can be performed with page-level granularity but an erase is performed at block granularity. There is a limit on the maximum number of erases a flash block can handle. Once this limit is reached by any of the SSD blocks, then the whole SSD is considered as not functional anymore. The lifetime of the SSD is the maximum erase count of any of the SSD blocks. A good FTL needs to prolong the life of an SSD by uniformly distributing the erases. This process is called **wear leveling**.

The FTL must also support **garbage collection**, which means cleaning up invalid data on the SSD to free up space to store more data. Cleaning up involves erasing any candidate blocks but saving the pages in the blocks which are still valid. This leads to write amplification which is doing more physical write operations than the actual logical operations requested by the file system. This is a side effect due to the nature of block-level granularity for erases. Having a high **write amplification** eventually adds up and decreases the life span of the SSD. Therefore, it is a good idea to design an FTL that has low write amplification.

MyFTL supports 3 operations: Read, Write and Trim (mark LBA as invalid).