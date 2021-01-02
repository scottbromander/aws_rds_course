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
