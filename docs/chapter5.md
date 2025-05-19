#A Short History of Data Protection

Data protection has been a key feature of computer systems since the first commercial computers entered production in 1951.  For at least two decades, backup and recovery of data was a bespoke solution implemented by systems programmers, rather than a product which could be bought and installed on the system.  

Part of the challenge for system operators at that time was the lack of suitable offline media.  UNISERVO, a tape system based on heavy steel tape, was introduced for the UNIVAC I in 1951.  IBM introduced its first tape solution, the IBM 726, with the IBM 701 in 1952.  Reel-to-Reel tape persisted as the standard medium, based on magnetic coated film, until the mid-1980s, with the introduction of the IBM 3480 tape cartridge.

On the IBM mainframe, Hierarchical Storage Manager was introduced by IBM on the MVS operating system and System/370 platform in 1977.  Version 2 was renamed DFHSM (Data Facility Hierarchical Storage Manager) and eventually DFSMShsm with the introduction of system-managed storage and the Storage Management Subsystem (DFSMS) in the late 1980s.  

Elsewhere, Unix systems generally relied on native commands, including tar, introduced in Unix Version 7 in 1979.  The tar utility was preceded by tp and tap commands.  Other utilities such as cp and cpio offered the capability to transfer data to and from tape.  

Many of the data protection solutions we know today had origins in bespoke or custom software tools.  BackupExec derived from tape streaming software developed by Maynard Electronics in 1982.  Netbackup was first used to protect data on SGI IRIX systems.  Dell Networker, part of the Dell Technologies Data Protection Suite, was originally developed by Legato Systems, Inc and released in 1990.  EMC Corporation acquired Legato in 2002, being subsequently acquired itself by Dell in 2016.  Arcserve was originally developed by Cheyenne in 1990.

##Single & Multi-Machine

We can divide the history of commercial data protection solutions into two parts.  There are software products which are designed as a single-machine solution and those designed for multi-machine environments.  

Single-machine solutions typically run on one server and protect the data for that machine, using local media (or increasingly, the public cloud).  These products co-exist with the application or applications running on the server.

Multi-machine solutions offer more enterprise-class capabilities and protect many individual physical or virtual machines.  They generally run on dedicated infrastructure, either one or more physical servers or virtual instances.  Multi-machine solutions are designed to support large-scale computing environments where a key requirement is to scale out the data protection process for both backup and restore.

##Backup Appliances

The appliance model has been a popular choice for smaller organisations looking to implement data protection without needing significant investment in skills and resources.  There have been two forms of backup appliances over the last two decades.  The initial set of solutions acted purely as secondary data stores, optimised for the long-term retention of backup data.  This category includes, for example, deduplicating appliances and virtual tape libraries (VTLs).  The second option incorporates data protection software into the appliance itself.

Rather than deploy software onto a hardware or virtual instance configuration, the appliance comes pre-installed with vendor backup software designed to work with the appliance capabilities.  Typically, the appliance configuration is managed by the vendor and updated automatically or through a scheduled approach.  

The customer benefits from a backup appliance as there are few skills (or time and effort) required to manage the infrastructure.  In geographically dispersed businesses, this has particular benefit by removing the requirement for on-site trained staff.  Most appliances can be managed remotely.

##SaaS

Over the last decade, data protection has evolved from the bespoke software and appliance models to software-as-a-service.  In this option, data protection is delivered either from managed service provider infrastructure or as an application running in the public cloud.  The customer does not need to install any on-site equipment, although network bandwidth in and out of the customer’s data centre becomes a factor.  

SaaS offerings can protect on-premises infrastructure, edge locations, the public cloud and other SaaS services.  The multi-faceted nature of SaaS is a boon for businesses that may have little or no on-premises infrastructure and don’t want to be required to deploy hardware to take independent backups.

As businesses increasingly rely on SaaS and managed services such as public cloud, we believe that SaaS data protection will be a major force in the industry and become the dominant deployment model.  We can envisage this happening due to several factors.

* Infinite scale.  SaaS offers customers effectively infinite scaling capability.  The more well-designed SaaS platforms scale backup and restore on demand, using the features of public clouds as a mechanism to optimise cost and scale up to meet unpredictable demand.  This removes the requirement for the customer to plan data protection capacity management, as would be required on-premises.  
* Continuous development.  In an on-premises model, data protection software is generally managed by the customer (with perhaps the exception of the appliance model).  In SaaS offerings, the vendor can update and enhance the service with new features and functionality, on an almost continuous basis.  There are limitations, of course.  No customer wants to see their familiar interface changing frequently.  However, we have all become comfortable with the concept of regular app updates on our mobile devices, so the leap for the enterprise is not difficult to see.
* Responsiveness.  One major aspect of modern data protection is the need to detect and mitigate hacking, malware attacks and ransomware.  The profile of attacks is constantly changing, which requires detection and mitigation software to also change at a rapid pace.  Delivering data protection as a service enables vendors to be responsive in evolving threat detection technology and making it available to the customer in a timely fashion.  Additionally, the vendor has immediate access to the shared knowledge of potentially thousands of customers at the same time.  This provides the capability to offer more dynamic protection if a widespread malware attack occurs.
* Air Gap Security.  One method of attack used by ransomware groups is to target both primary and backup storage systems.  With SaaS data protection, the secondary copy of data is usually (but not always) stored within the security domain of the vendor.  This enables additional security features, such as time locking of snapshots or backups, to be implemented in a way that cannot be overridden, even if the customer’s primary security domain is breached.  
* Forensic Analysis.  With secondary data stored in the public cloud, SaaS vendors can more easily implement data analysis and forensic services such as cleanrooms.  In modern data recovery, particularly from ransomware, a critical requirement is the ability to test and validate for known good backups.  This process is much easier when your data protection vendor is already in the public cloud and can automate the entire process.

Although SaaS seems like the point of convergence for all data protection, there are some caveats to consider.  Secondary data stored in a SaaS platform is likely to be accessible only for the lifetime of the service subscription.  If the service is terminated (or the customer ceases paying), then access to that content may be curtailed.  Of course, there is an option here for SaaS data protection vendors to offer a reduced cost “read-only” service, if the customer moves to another provider.

As with on-premises data protection software, the format in which the secondary data is stored is generally proprietary.  This is also the case in SaaS platforms.  However, whereas on-premises an IT team could choose to retain physical media and do bespoke restores where necessary, this facility doesn’t exist for SaaS solutions.  

One final point to consider is the impact of data sovereignty and legal discovery.  When a business owns its own data, it manages security, encryption and the physical location of that data, with the option to put that data out of reach of law enforcement agencies, for example.  In SaaS platforms, that capability may not be so simple.  Businesses choosing SaaS data protection therefore need to think carefully where their data will be stored and processed, with respect to country-specific data protection rules.
The Evolution of Data Stores

In the ETIL model, primary data is extracted, transformed, indexed and then loaded into a secondary storage solution.  Historically, this process has evolved from the use of tape media to disk systems and now the public cloud as a target repository.  Irrespective of the storage medium (and there is no reason why several may not be used in parallel), the destination for secondary data is generally referred to as a “storage target”.  

Tape was the first widespread target medium for secondary data.  It was relatively cheap (compared to disk systems), with easy portability.  This made it possible to transport tape reels to geographically diverse locations for additional data safety.  It also makes it possible to optimise the use of tape drives, when data is inactive 90-99% of the time.  

Tape evolved quickly during the 1980s and 1990s, with IBM leading the way in the enterprise.  The tape cartridge format was first introduced in 1984, quickly replacing reel-to-reel tape as the standard form factor.  Cartridges are secure, portable and easy to transport and store.  However, as with any mass media, businesses quickly encountered “tape sprawl”, with a significant volume of manual media handling required.  Technology firms saw an opportunity to automate, with the introduction of automated tape libraries from the 1990s onwards.  These systems employed robotic arms to retrieve tapes from a storage slot and insert them into a drive mechanism in an entirely automated process.

Despite high degrees of automation, tape still has one Achilles Heel – it is a sequential read and write medium.  If data is stored towards the end of a tape, the entire contents must be spooled through to reach the desired read point.  Access time that could be milliseconds or microseconds on hard drives or SSDs can be minutes on tape.  In addition, it is extremely difficult to write-in-place to a tape cartridge, unless the data being overwritten is the same length or shorter than the available space.

As tapes are written and overwritten, content becomes out of sequence and fragmented.  In the 1980s and 1990s, the solution employed by platforms such as DFHSM and Netbackup was to restack or re-order data, reading data from partially filled tapes, consolidating it and creating fully utilised ones.  While this process works, it ties up at least two tape drives, plus the media being consolidated.  

As tape media increased in capacity, the time required for consolidation becomes excessive for tapes that are constantly in use.  The answer to the problem emerged in two disk-based technologies – virtual tape libraries and deduplicating appliances.

##Virtual Tape

Tape drives are relatively simple devices, conforming to the SCSI protocol, whether directly connected, or attached via SAS or Fibre Channel transports.  These commands can be emulated through software, creating the concept of a virtual tape device that appears to operate like a physical tape library.  As disk systems became much cheaper in the early 2000s, so virtual tape libraries offered an alternative for frequently accessed data stored on tape.  Statistically, backups are most frequently used within the first few hours and days from creation, after which their use declines over time.  VTLs provide a mechanism to store and retrieve backups during the initial period of activity, eventually archiving backups to tape for longer-term retention.  

VTLs provide much faster “time to first byte” than tape systems, which must spool a tape to the initial reading position before starting to read data.  They also reduce the impact of fragmentation and restacking, as short-lived backups can be retained purely on disk.

##De-duplication

While VTLs offer mitigation for the sequential nature of tape, they still store significant volumes of essentially duplicated data.  As an example, many backup policies traditionally took full copies of data on a weekly basis, keeping that data for up to six months.  Between full backups, incremental changes are identified and kept separately.  When hundreds of physical servers (or thousands of virtual servers) are based on a standardised image, the degree of duplication in secondary backup data can be substantial.  

De-duplicating appliances emerged in the early 2000s, as a way to reduce the volume of secondary data being stored on disk systems.  As data is ingested, the content is split into chunks and fingerprinted (a process called hashing).  Data with new hashes is stored and indexed against the source, while data that shows a known hash is also indexed but the physical data is discarded.  

Deduplication relies on hashing techniques that produce unique values from a specific piece of content, which historically took significant computing power to achieve.  Some primary storage systems today use weak hashing algorithms and manage hash “collisions” with an exception process as a way to reduce CPU usage.

While deduplication appliances are a powerful way to reduce secondary data storage volumes, they do have some challenges.  Firstly, on early disk-based systems, over time the hashing process essentially creates an entirely random data set on disk, which results in performance problems when reading data during a restore.  Vendors have mitigated these issues with content-aware placement and flash-based systems.  

Second, the ability to access and restore data relies entirely on the accuracy of the hash indexing held by the deduplication appliance.  If that data is lost or corrupted, then accessing the data becomes impossible.  This creates a significant single point of failure in design that vendors must explain how they mitigate.


