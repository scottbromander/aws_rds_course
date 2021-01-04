# AWS RDS - Pluralsight Course

### What is Amazon RDS?

Amazon Realtion Database Service (Amazon RDS) is a web service that makes it easier to set up, operate, and scale a relational database in the cloud.

### DB Hosting Option

- Self Host - You manage hardware, OS, and DB
- IaaS (Infastructure as a Service) - AWS Manages Hardware, You manage OS Updates and DB
- Paas (Platform as a Service) - AWS Manages Hardware, OS, and DB

### Supported RDS DB Engines 

- Amazon Aurora
- MariaDB
- MySQL
- PostgreSQL
- Oracle
- Microsoft SQL Server

### Creating a RDS DB Instance

- Login to [AWS Console](https://aws.amazon.com/console/) - NOT ROOT USER! USE AN IAM USER!
- All Services -> Choose RDS
- Create Database
- Select DB Engine - Note your region. Latency is a consideration for where you create your DB. When you select your DB Engine, this is where your DB will be created.
- Note: Bottom of the screen, there is a check box for an RDS Free Usage Tier! Tick that if you are learning.
- Select a `Use Case` Scenario Option - Dev/Test
- DB Instance Class - Comp and Memory resources instanced to support the DB. 
  - 3 types:
    - Standard - `M Prefix` - Balance of Compute, Memory, and Network Resources
    - Memory Optimized - `X, R, and M2 Prefix` - Performance (Up to almost 4 GB of DRAM)
    - Burstable Performance - `T Prefix` - Good baseline, with ability to have burst of CPU through CPU credits.
- Multi Availablity Zone Deployment Option - Physical Locations - Do you want redundancy? Synchronous replication an option. RDS does manage all of this for you, which is awesome in a failover.
- Type of Storage - SSD or Provisioned IOPS - General purpose SSD allows for up to 3 IOPS/GiB, but you can bank credits, which you can use when you need to burst.
- Provisioned IOPS (more `$$$`) makes sense for when you need consistent performance, versus the general purpose SSD, which is good for inconsistent, non-patterned use. IOPS does not bank credits.

### Configure Advanced Settings

- Network and Security - All RDS instances reside on some VPC (Virtual Private Cloud) - Defaults are fine. But there may be a reason you need to set a different VPC. For example, if you have an EC2 instance, you may not want to have the RDS in another VPC, as communications would need to go through a public network to communicate between the two. So putting them in the same VPC, would make the communication between the two, occur through a private connection.
- Public Accessibility needs to be considered here. If you are testing from a local machine for example, but want to access the RDS DB, then you need to set this to `yes`, as you want to allow outside connections coming from outside the default VPC.
- VPC Security Group - In the case of just playing around, go ahead and use the `create new`. But if you were working within an existing VPC consideration, you would want to have this top of mind.
- Database options - Name the Database! Note that the steps completed create an instance of the Databse Engine. Without naming a database, no database is created. Just the engine. More Databases can be created in the engine. 
- You can edit the `PORT` of course - You can edit the DB parameter group - Finally, you can also edit the option group.
- Encryption is enabled by default.
- Backup - If you do not have another backup AZ, you may have lag when the backup is occuring.
- Enhance monitoring does have a default free option.
- Note that auto upgrading minor updates is set by default. 

### DB Parameter and Option Groups

- Parameter groups - Default parameter groups, one issue is that defaults cannot be editted. Custom parameter groups can be editted. 
- Once a custom group has been created, you can edit it. Tons of options! And then you can assign it to new DB instances.
- Option groups - Same deal, defaults cannot be editted. 
- `Add Option` - is a button available after you can highlight a box. Options are different and there are less of them than the parameters.
