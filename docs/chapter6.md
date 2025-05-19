#Diving Deeper into Data Protection

As our ETIL process described earlier shows us the process for data extraction and storage, we will start a deeper dive of the data protection ecosystem by looking at storage media.  Typically, the data in backup systems is referred to as "secondary" data (compared to "primary" data) as it isn't directly accessed by production applications, other than backup software.  Secondary data can be stored on tape, disk, NAND flash or on the public cloud, which is an ofuscated version of the first set of technologies.

##Media Requirements

The characteristics of secondary data are generally different from that of primary data in computing systems.  Primary data resides on systems that deliver high random access I/O performance and good throughput.  Random access refers to the capability to retrieve any individual piece of data directly, compared to sequential access that requires traversing media until the required data is reached.  Tape, for example, is a sequential medium, as the tape must be spooled or read from the start to the required access point.  In contrast, HDD and SSD are random media that can be accessed by logical byte or block address.

Secondary data access used to be solely focused on throughput speed.  Backup time is measured by the throughput capability of secondary media.  The faster data can be written to tape or disk, the quicker the backup will complete.  Equally, the recovery time for data is also based on throughput.  The faster data can be retrieved from secondary storage, the shorter the recovery process.  As we will discuss later, data optimisation techniques have changed that paradigm somewhat, as data deduplication causes changes sequential I/O into almost totally random I/O.   
