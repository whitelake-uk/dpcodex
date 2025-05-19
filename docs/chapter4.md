#ETIL

What are the mechanics of a data protection process?  Many readers may be familiar with the term “ETL”, a common standard in data pipelines which stands for Extract, Transform and Load.  Data processing techniques, such as those which build data warehouses, extract data from production systems, transform them in some way (such as changing the structure into XML or JSON, or removing personal information) and then store that data in another system for further use (the load step).  ETL can also be used for data cleaning, where the quality of source data is poor or needs additional metadata or other content to supplement it.  An example could be adding postcodes (zip codes) to addresses, or validating date of birth information is in the correct format and a valid date.

In this book we use ETIL to describe the process in which data is secured as a backup for future use in recovery.  The additional step represented by the letter “I” stands for “indexing”, essentially ensuring that the data being protected can be easily searched in the future.  In essence, data protection is like an ETL process, but with that one additional step, which provides for the future searching of backup information.

Why do we need these four processes in data protection?  Let’s look at each of them in a little more detail.

##Extract

As we’ve already explained, backup is the process of taking a point-in-time copy of data as an insurance policy for some future incident.  Essentially, we extract a copy of data from our primary applications and systems.  Exactly how this is done depends on the data and the platform.  For example, data on a shared storage array could be extracted via a snapshot copy; data in a database could be extracted using a SQL query; data in a virtual server platform could be extracted via an advertised API.  

Each of these processes will be tailored to the platform and the data.  Using the server virtualisation platform as an example, VMware vSphere offers a specific API to extract changed data at a block level for individual virtual machines.  VADP (VMware vSphere Storage APIs – Data Protection) provides a stream of changed blocks separately for each virtual machine, which is more efficient than, taking snapshots within the virtual machine or copying data at the datastore level.

Data extraction must be non-invasive (as much as possible), create a consistent version of data, while being obtained in a form that can be usefully used later for recovery.  

##Transform

Once a backup solution has extracted data from a primary application, that data will go through some form of transformation.  The transform step is used to optimise data before it is saved for future use.  This could mean deduplicating the content (if identical data already exists on the backup system), parsing the data to extract only the content to be stored (from a snapshot, for example), or discarding data that hasn’t been changed since the last backup cycle.  

The transformation process may also put data into a different format that is optimised for long-term storage.  This may mean aggregation into large chunks of data for storage on tape or in the public cloud.

##Index

Data in backups is retained purely to facilitate recovery.  As a result, data protection systems need to be able to retrieve that data at some future point.  This requirement has two processing aspects.  Firstly, an index of backup content needs to know where to find the backup copy.  Historically, this might mean a tape in the data centre or stored offsite at a 3rd party management company.  Today, backup data could be stored on an object store in the public cloud.  

The second reason for indexing is to find data that may no longer have a primary copy.  For example, imagine refactoring an application onto the public cloud from an on-premises virtual server.  Although the application functionality remains the same, the data may now be in a virtual cloud instance with a different name, location and running on an updated application (such as a structured database).  If data from before the refactoring is needed, then some system of record is required to know that prior to the refactoring, the data and application existed elsewhere within the “virtual” data centre that could span on-premises and multiple public clouds.  Without a system of record, any recovery would require site knowledge that is easily lost over time.

##Load

Once data has been extracted from a primary application, the transformed copy must be stored somewhere.  Unlike primary copies of data, backup copies (sometimes referred to as secondary copies) are generally stored on storage media suitable for long-term and low-cost retention.  Historically this has meant sequential access technology like magnetic tape, although modern backup solutions use a mix of media types to facilitate quick restores of the most recently protected data.

The format for long-term retention of backups is an important aspect to consider, when building a data protection strategy.  We will dig into this topic in much more detail later.  However, it is worth highlighting that many businesses fail to implement a strategic approach to long-term data backup management, leaving a legacy of ageing tapes that may contain unknown content.

The answer to this problem is, in many instances, to “kick the can down the road” and leave the problem to some future date.  That strategy isn’t always the right approach, as it introduces the risk of compliance and regulatory issues that could include financial penalties.

