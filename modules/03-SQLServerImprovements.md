![](https://github.com/microsoft/sqlworkshops/blob/master/graphics/microsoftlogo.png?raw=true)![](../graphics/microsoftlogo.png)

# Workshop: Modernizing Your Data Estate With SQL Ground-to-Cloud
#### <i>A Microsoft workshop from the SQL Server team</i>

<p style="border-bottom: 1px solid lightgrey;"></p>

<img style="float: left; margin: 0px 15px 15px 0px;" src="https://github.com/microsoft/sqlworkshops/blob/master/graphics/textbubble.png?raw=true"> <h2>03 - SQL Server Improvements</h2>

In this workshop you'll cover how to systematically create a modern data estate using SQL Server in on-premises, in-cloud and hybrid solutions.

In each module you'll get more references, which you should follow up on to learn more. Also watch for links within the text - click on each one to explore that topic.

(<a href="file:///url" target="_blank">Make sure you check out the <b>Pre-Requisites</b> page before you start</a>. You'll need all of the items loaded there before you can proceed with the workshop.)

Using the <a href="https://github.com/sqlballs/mSQLg2c/blob/main/modules/02-AuditingYour%20DataEstateArchitecture.md">processes, tools and procedures from the Auditing  Module</a>, the WideWorldImporters company has completed an initial audit of their data estate.They found multiple sources of data in their organization, including text files, spreadsheets, and Relational Database Management Systems (RDBMS) including SQL Server 2012 Instances along with some Instances of SQL Server 2017 for <a href = "https://docs.microsoft.com/en-us/sql/samples/wide-world-importers-what-is?view=sql-server-2017" target="_blank">their primary Line of Business (LOB) databases</a>.

WideWorldImporters <a href="https://learn.microsoft.com/en-us/sql/sql-server/end-of-support/sql-server-end-of-support-overview?view=sql-server-ver16#lifecycle-dates">needs to upgrade the software that is out of support</a> and also evaulate which versions and editions will solve their problems. They have settled on evaulating the delta between SQL Server 2017 and the latest version of the on-premises SQL Server product, and they have divided their evaluation into various categories that they are interested in:

<dl>
  <dt><a href="#3.1" target="_blank">3.1 - Deployment Options</dt></a>
  <dt><a href="#3.2" target="_blank">3.2 - Manageability</dt></a>
  <dt><a href="#3.3" target="_blank">3.3 - Availability</dt></a>
  <dt><a href="#3.4" target="_blank">3.4 - Performance</dt></a>
  <dt><a href="#3.5" target="_blank">3.5 - Security</dt></a>
  <dt><a href="#3.6" target="_blank">3.6 - Development</dt></a>
  <dt><a href="#3.7" target="_blank">3.7 - Analytics</dt></a>
</dl>

<p style="border-bottom: 1px solid lightgrey;"></p>

<h2 id="3.1"><img style="float: left; margin: 0px 15px 15px 0px;" src="https://github.com/microsoft/sqlworkshops/blob/master/graphics/pencil2.png?raw=true">3.1 Deployment Improvements</h2>
In the latest version, you can deploy SQL Server to the Microsoft Windows operating systems as well as various distributions of the Linux operating system.  Newer deployment scenarios also include deploying SQL Server on Containers, Kubernetes, and new options in the Microsoft Azure platform such as Azure SQL Edge.
<p></p>

> WideWorld Importers has decided to evaluate the on-premises latest version of SQL Server separately from the Microsoft Azure platform deployment options. They also want to evaluate the on-premises to cloud and cloud to on-premises interactions separately.

<p></p>

<h3>SQL Server on Windows</h3>
The latest version of SQL Server is supported on all current Microsoft Windows desktop and server operating systems, including Windows 11 (Developer and Express Editions) and Windows 2022 Server. You can <a href="https://learn.microsoft.com/en-us/troubleshoot/sql/general/use-sql-server-in-windows">learn more about each version of the Microsoft Windows operating system and the SQL Server version it supports at this reference</a>.

Your selection of features and components should be based on your application needs. The different <i>Editions</i> of SQL Server have unique features, performance, runtime, and cost implications. You can <a href="https://learn.microsoft.com/en-us/sql/sql-server/editions-and-components-of-sql-server-2019?view=sql-server-ver16#-editions">learn more about the Editions of SQL Server and the features supported in each at this reference</a>.

All features in each Edition for the latest version of SQL Server are supported on the Microsoft Windows operating system, including:
- Hybrid buffer pool with direct write, which reduces the number of memcpy commands that need to be performed on modified data or index pages residing on PMEM devices
- Integrated acceleration & offloading acceleration technologies from partners such as Intel to provide extended capabilities, such as Intel® QuickAssist Technology (QAT) which provides backup compression and hardware offloading
- Leverages new hardware capabilities, including the Advanced Vector Extension (AVX) 512 extension to improve batch mode operations

<h3>SQL Server on Virtual Machines</h3>
Bare-metal installations of an operating system such as Windows are deployed on hardware using an operating system <i>Kernel</i>, and additional software to bring all of the hardware into a set of calls to the "Big Four": CPU, Memory, Storage, and Networking.

One abstraction layer above installing software directly on hardware is using a <i>Hypervisor</i>. In essence, this layer uses the base operating system to emulate hardware. You install an operating system (called a Guest OS) on the Hypervisor (called the Host), and the Guest OS acts as if it is on bare-metal.

<img src="https://techcommunity.microsoft.com/t5/image/serverpage/image-id/44539iF185A2EF8FFAB4FF?v=1.0" width=400>

In this abstraction level, you have full control (and responsibility) for the entire operating system, but not the hardware. This isolates all process space and provides an entire "Virtual Machine" to applications. For scale-out systems, a Virtual Machine allows for a distribution and control of complete computer environments using only software.

You can read <a href="https://docs.microsoft.com/en-us/virtualization/hyper-v-on-windows/reference/tlfs">the details of Microsoft's Hypervisor at this reference</a>.

The latest version of SQL Server supports all of the features associated with the applicable Edition for both Windows and Linux in a Virtualized environemnt, with <a href="https://learn.microsoft.com/en-us/troubleshoot/sql/general/support-policy-hardware-virtualization-product">the considerations described at this reference</a>.

<h3>SQL Server on Linux</h3>
In the latest version, SQL Server runs on Red Hat Enterprise Linux, SUSE Linux Enterprise Server, and Ubuntu Linux. WideWorld Importers is currently running Red Hat Linux at one of their processing plants, and is interested in some of the workloads that might be useful on that platform. As they test, their primary concern is the performance aspect of SQL Server in Linux, and they find that performance is on-par with the Windows deployments due to the architecture of the Platform Abstration Layer (PAL) implemented to run the SQL Server Engine code on Linux:

<p></p>
<img src="https://cloudblogs.microsoft.com/uploads/prod/2016/12/04_thumb.png" width=300>
<p></p>

The latest version of SQL Server on Linux supports the following improvements:
- Replication
- Support for the Microsoft Distributed Transaction Coordinator (MSDTC)
- OpenLDAP support for third-party AD providers
- Machine Learning Services on Linux
- TempDB improvements, such as multiple TempDB data files, similar to the default SQL Server installation on Windows
- PolyBase
- PolyBase type mapping
- Change Data Capture (CDC) support

There are specific versions and support considerations for each distribution of Linux. A <a href="https://learn.microsoft.com/en-us/sql/linux/sql-server-linux-whats-new-2019?view=sql-server-ver16">list of these requirements is available at this reference</a>, and a <a href="https://learn.microsoft.com/en-us/sql/linux/sql-server-linux-editions-and-components-2022?view=sql-server-ver16">list of Editions and supported features for SQL Server on Linux is at this reference</a>. 

You can <a href="https://learn.microsoft.com/en-us/sql/linux/sql-server-linux-overview?view=sql-server-ver16">learn more about the SQL Server on Linux architecture at this reference</a>.

<h3>SQL Server in Containers</h3>
The introduction of SQL Server running on Linux allows for the next level of hardware abstraction, called a <i>Container</i>. There are various types of Container technologies, in this workshop, you will focus on the Docker container format, as implemented in Windows using the <i>Moby</i> framework.

A Container is provided by the Container Runtime (Such as <i>containerd</i>) runtime engine, which sits above the operating system (Windows or Linux). In this abstraction, you do not control the hardware or the operating system. The Container has a specific protected memory space, and can contain binaries such as Python, R, SQL Server, or other binaries. A Container with all its binaries is called an Image. You create a container from a file.

You can see the difference between Virtual Machines and Container technologies here:

<img src="https://cloudblogs.microsoft.com/uploads/prod/sites/37/2019/07/Demystifying-containers_image1.png" width=600>

This abstraction holds everything for an application to isolate it from other running processes. It is also completely portable - you can create an image on one system, and another system can run it so long as the same Container Runtime (Such as Docker) is installed. Containers also start very quickly, are easy to create (called Composing) using a simple text file with instructions of what to install (called a manifest or Dockerfile) on the image. The instructions pull the base image, and then any binaries you want to install. Several pre-built Containers are already available, and SQL Server is one of these. You can <a href="https://docs.microsoft.com/en-us/sql/linux/quickstart-install-connect-docker?view=sql-server-2017">read more about installing SQL Server on Container Runtimes (Such as Docker) at this reference</a>.

You can have several Containers running at any one time, based on the amount of hardware resources where you run it. For scale-out systems, a Container allows for distribution and control of complete applications using only declarative commands.

You can <a href="https://hackernoon.com/docker-commands-the-ultimate-cheat-sheet-994ac78e2888">read more about Container Runtimes (Such as Docker) at this reference</a>.

<h3>SQL Server on Kubernetes</h3>
For Big Data systems, having lots of Containers is very advantageous to segment purpose and performance profiles. However, dealing with many Container Images, allowing persisted storage, and interconnecting them for network and internetwork communications is a complex task. One such Container Orchestration tool is <i>Kubernetes</i>, an open source Container orchestrator, which can scale Container deployments according to need. The following table defines some important Container Orchestration Tools (Such as Kubernetes or OpenShift) terminology:

<table style="tr:nth-child(even) {background-color: #f2f2f2;}; text-align: left; display: table; border-collapse: collapse; border-spacing: 5px; border-color: gray;">
  <tr><td style="background-color: AliceBlue; color: black;"><b>Component</b></td><td style="background-color: AliceBlue; color: black;"><b>Used for</b></td></tr>
  <tr><td>Cluster</td><td> Container Orchestration (Such as Kubernetes or OpenShift) cluster is a set of machines, known as nodes. One node controls the cluster and is designated the master node; the remaining nodes are worker nodes. The Container Orchestration *master* is responsible for distributing work between the workers, and for monitoring the health of the cluster.</td></tr>
  <tr><td style="background-color: AliceBlue; color: black;">Node</td><td td style="background-color: AliceBlue; color: black;"> A node runs containerized applications. It can be either a physical machine or a virtual machine. A Cluster can contain a mixture of physical machine and virtual machines as Nodes.</td></tr>
  <tr><td>Pod</td><td> A Pod is the atomic deployment unit of a Cluster. A pod is a logical group of one or more Containers and associated resources needed to run an application. Each Pod runs on a Node; a Node can run one or more Pods. The Cluster master automatically assigns Pods to Nodes in the Cluster.</td></tr>
</table>
	
<br> 
<img src="https://github.com/microsoft/sqlworkshops-bdc/blob/master/graphics/KubernetesCluster.png?raw=true" width=600>
<br>

You can <a href="https://kubernetes.io/docs/tutorials/kubernetes-basics/" target="_blank">learn much more about Container Orchestration systems here</a>. You can implement a Kubernetes environment using the Azure Kubernetes Service (AKS), and <a href="https://aksworkshop.io/" target="_blank">you can find a set of tutorials for you to learn more at this reference</a>.

> You can <a href="https://kubernetes.io/docs/tutorials/kubernetes-basics/create-cluster/cluster-interactive/">practice with Kubernetes using online emulator to work with the `minikube` platform</a>.  

You can deploy the latest version of SQL Server deployments on Kubernetes. In this case, the Container Orchestration system (Such as Kubernetes or OpenShift) is responsible for the state of the BDC; it is responsible for building and configuring the Nodes, assigns Pods to Nodes,creates and manages the Persistent Volumes (durable storage), and manages the operation of the Cluster.

You can learn more about <a href="https://learn.microsoft.com/en-us/shows/data-exposed/deploying-sql-server-2019-in-kubernetes">deploying SQL Server to Kubernetes at this reference</a>. SQL Server containers can also be deployed to Kubernetes using Helm charts.  To understand how to deploy a container to Kubernetes see this Microsoft Learn article: https://learn.microsoft.com/en-us/sql/linux/sql-server-linux-containers-deploy-helm-charts-kubernetes?view=sql-server-ver16

<p></p>

<p><img style="float: left; margin: 0px 15px 15px 0px;" src="https://github.com/microsoft/sqlworkshops/blob/master/graphics/point1.png?raw=true"><b>Activity: Review the process for running SQL Server in a Container</b></p>

In this Activity you will review the process for pulling the latest version of a SQL Server container and running it on the Docker platform, and connecting to it with a query. 

> If you have a Linux or Windows operating system with Docker installed and running, you can implement this tutorial, otherwise watch the instructor as they perform the pull.

<p><img style="margin: 0px 15px 15px 0px;" src="https://github.com/microsoft/sqlworkshops/blob/master/graphics/checkmark.png?raw=true"><b>Steps</b></p>

- <a href="https://learn.microsoft.com/en-us/sql/linux/quickstart-install-connect-docker?view=sql-server-ver16&pivots=cs1-powershel">Open this link and review the steps you see there</a>. Bookmark for later reference.
- <i>Optional</i>: If time permits, you can install the Docker platform on your test system and complete the steps to deploy SQL Server on Linux and connect with a test to that environment.

<p style="border-bottom: 1px solid lightgrey;"></p>

<h2 id="3.2"><img style="float: left; margin: 0px 15px 15px 0px;" src="https://github.com/microsoft/sqlworkshops/blob/master/graphics/pencil2.png?raw=true">3.2 Manageability</h2>

For the administration team for the Data Estate, manageability includes everything from the interface to the system, to being able to deploy and configure it. The latest version of SQL Server includes the following improvements:

- An integrated setup experience for the Azure extension for SQL Server which installs the Azure extension for SQL Server at setup
- You can now use the SQL Server Configuration Manager to manage an Azure extension for SQL Server service, allowing you to create Azure Arc-enabled SQL Server instances, and for other Azure connected features
- There are new upgraded max server memory calculations
- There are several improvements to address persistent version store (PVS) storage and improve overall scalability, including a persistent version store cleaner thread per database instead of per instance and the memory footprint for PVS page tracker has been improved. There are also a number of ADR efficiency improvements, such as concurrency improvements that help the cleanup process to work more efficiently. ADR cleans pages that couldn't previously be cleaned due to locking
- A new shrink database option has been added: WAIT_AT_LOW_PRIORITY
- XML compression is now available
- There is a new improvement for asynchronous auto update statistics concurrency

<h3>Tools</h3>
There are several tools you can use to connect to, query, and manage a SQL Server Instance. The two broad groups are Graphical User Interfaces (GUI) and Command-Line or Scripting Interfaces.

New improvements include:

- Azure Data Studio includes connection and management support for the latest version of SQL Server
- SQL Server Management Studio connects and manages the latest version of SQL Server, and includes several other improvements
- SqlPackage.exe provides support for the latest version of SQL Server
- VS Code now supports the latest version of SQL Server

<p></p>

> This Module focuses on the use and improvements in the SQL Server Management Studio (SSMS) and Command-Line utilities. The Azure SQL Module will focus more on the Azure Data Studio (ADS) tool, although both SSMS and ADS can be used to connect to and manage either platform.

<p></p>

<h4>SQL Server Management Studio</h4>
SQL Server Management Studio (SSMS) is a graphical interface for the Microsoft Windows operating system used to manage, monitor and program SQL Server Instances. The latest version of this tool supports connecting to and managing the latest versions of SQL Server for the following activities:
- Connect to SQL Server and see object status
- Creation of databases and database objects
- Configuration of connection options
- Scripting database options
- Creation of SQL Server Agent Jobs and Schedules
- Creation of Maintance plans, backup and restore operations
- Multiple out-of-the-box reports and the ability to create custom reports
- Multiple "wizards" for tasks such as security compliance and risk reports
- Multiple graphical tools to view and report performance and query plans and the query store feature
- View the AlwaysOn AG Dashboard
- View SQL Server Log Files
- Create Extended Events

New and enhanced features in SQL Server Management Studio include: 
- Support for Azure AD authentication, including Multi-Factor Authentication (MFA) 
- Azure Data Studio installation integration	Installation of SSMS installs Azure Data Studio
- The Object Explorer	Dropped Columns folder now exists under the Columns folder for Ledger tables, which have been altered to remove one or more columns
- Scripting	Compatibility level now defaults to 160 when scripting
- Added Showplan support for Hyperscale Optimized Query Processing
- Analysis Services	Connection to Analysis Services is now available
- Added missing options in SqlParser for CREATE USER and CREATE LOGIN.
- The “Schedule…” menu item in SQL Server Integration Services is now visible in the Azure SSIS Catalog
- Added the ability to explicitly configure an attestation protocol in the "Connect To Server" dialog when using Always Encrypted with secure enclaves (column encryption)
- Client Driver changed to Microsoft.Data.SqlClient
- Added support for Contained Always On Availability Groups
- Improvements to Data Classification user interface
- Added support for Ledger feature Database ledger
- Improved checks for open connections.
- Updated Query Tuning Assistant user interface for improved accessibility
- The showplan XML schema has been updated

You can <a href="https://learn.microsoft.com/en-us/sql/ssms/sql-server-management-studio-ssms?view=sql-server-ver16">find a complete overview of the SSMS product at this reference</a>.

<h4>Command-Line Utilities</h4>
<p>
The SQLCMD utility allows you to connect to SQL Instances via a command-line utility in Windows or in Linux. It allows you to send commands to the Instance in an immediate query/response mode, or send in scripts, and will also create output streams in an automated way.

Improvements to SQLCMD include:
- Support for Azure AD authentication, including Multi-Factor Authentication (MFA) 
- Support for SQL Database, Azure Synapse Analytics, and Always Encrypted features

You can <a href="https://learn.microsoft.com/en-us/sql/tools/sqlcmd-utility?view=sql-server-ver16">learn more about the SQLCMD utility at this reference</a>.

<p></p>

<p><img style="float: left; margin: 0px 15px 15px 0px;" src="https://github.com/microsoft/sqlworkshops/blob/master/graphics/point1.png?raw=true"><b>Activity: SQL Server Management Studio Tips</b></p>

In this Activity you will review a few tips and tricks you may not have been familiar with in SQL Server Management Studio. The instructor may also reference additional interesting tasks and features you might not be familiar with.  

<p><img style="margin: 0px 15px 15px 0px;" src="https://github.com/microsoft/sqlworkshops/blob/master/graphics/checkmark.png?raw=true"><b>Steps</b></p>

- <a href="https://learn.microsoft.com/en-us/sql/ssms/tutorials/ssms-tricks?view=sql-server-ver16">Open this link and perform the steps you see there</a>. Bookmark for later reference.

<p></p>
<p style="border-bottom: 1px solid lightgrey;"></p>
<p></p>

<h2 id="3.3"><img style="float: left; margin: 0px 15px 15px 0px;" src="https://github.com/microsoft/sqlworkshops/blob/master/graphics/pencil2.png?raw=true">3.3 Availability</h2>

One of the important considerations for WideWorld Importers is ensuring Business Continuity. As part of their strategy, the Data Estate is an important component. The general area for Business Continuity in Data is <i>High Availablity</i>, which in turn contains important concepts such as Recovery Point Objectives (RPO) and Recovery Time Objectives (RTO). A few key terms are important to note as we dsicuss the improvements in this area of the latest version of SQL Server: 

- <b>High Availability</b> (HA): The ability for your systems to recover from localized events in an automated way
- <b>Disaster Recovery</b> (DR): The process of recoving from a diaster of some sort.  A natural or man-made disaster has occured and manual intervention may be required.  While some things can be automated, other items may require manual intervention  
- <b>Business Continuity</b>: The planning process for how businesses and their IT systems will react in the event of an outage.  This planning will typically be for DR, but it could also include HA planning

There are multiple capabilities in SQL Server that serve as part of an overall Availability strategy, including several that have new improvements in the latest version:
- <b>Database Backups</b>
  - <a href="https://learn.microsoft.com/en-us/sql/relational-databases/integrated-acceleration/overview?view=sql-server-ver16">Intel QAT backup hardware offloading support</a> 
  - T-SQL Snapshot Backup, <a href="https://learn.microsoft.com/en-us/sql/relational-databases/backup-restore/create-a-transact-sql-snapshot-backup?view=sql-server-ver16">adding Transact-SQL support for freezing and thawing I/O without requiring a VDI client</a>
  - <i>backupset</i> (Transact-SQL) improvements to add additional columns
  - <a href="https://learn.microsoft.com/en-us/sql/relational-databases/backup-restore/sql-server-backup-to-url-s3-compatible-object-storage?view=sql-server-ver16">Backup and restore to S3-compatible object storage</a>
- <b>Database and Database article Replication</b>
  - "Last Writer Wins" conflict detection
- <b>Database Log Shipping</b>
- <b>Failover Clustering</b> 
  - Simplfied Failover Clustering setup for Virtual Machines 
- <b>Always-On Availability Groups</b> - <a href="https://learn.microsoft.com/en-us/sql/database-engine/availability-groups/windows/contained-availability-groups-overview?view=sql-server-ver16">Improvements in the latest version of SQL Server include</a>:
  - Up to five synchronous replicas	<a href="https://learn.microsoft.com/en-us/sql/database-engine/availability-groups/windows/secondary-replica-connection-redirection-always-on-availability-groups?view=sql-server-ver16">starting in SQL Server 2019 (15.x) increases the maximum number of synchronous replicas to 5, up from 3 in SQL Server 2017 (14.x)</a>. You can configure this group of five replicas to have automatic failover within the group. There is one primary replica, plus four synchronous secondary replicas
  - Secondary-to-primary replica connection redirection	allows client application connections to be directed to the primary replica regardless of the target server specified in the connection string
  - Create an <a href="https://learn.microsoft.com/en-us/sql/database-engine/availability-groups/windows/contained-availability-groups-overview?view=sql-server-ver16">Always On Contained Availability Group</a> that manages its own metadata objects (users, logins, permissions, SQL Agent jobs etc.) at the availability group level in addition to the instance level, and includes specialized contained system databases within the availability group

> The latest version of SQL Server also has the ability to participate in Availablity to and from the Microsoft Azure Platform. These improvements will be detailed in the last Module of this Workshop.

<p><img style="float: left; margin: 0px 15px 15px 0px;" src="https://github.com/microsoft/sqlworkshops/blob/master/graphics/point1.png?raw=true"><b>Activity: Examine the new Information in the backupset system table</b></p>

The <i>backupset</i> table in the <i>msdb</i> system database contains a row for each backup set. A backup set contains the backup from a single, successful backup operation. You can use this information to check for your backup status, time to run, and much more. These checks should be integrated into your overall Disaster Recovery strategy.

<p><img style="margin: 0px 15px 15px 0px;" src="https://github.com/microsoft/sqlworkshops/blob/master/graphics/checkmark.png?raw=true"><b>Steps</b></p>

- Back Up your WideWorld Importers database to disk
- <a href="https://learn.microsoft.com/en-us/sql/relational-databases/system-tables/backupset-transact-sql?view=sql-server-ver16#examples">Open this link and perform the steps you see there</a> to revoiew the new information for backups. Bookmark for later reference.

<p style="border-bottom: 1px solid lightgrey;"></p>

<h2 id="3.4"><img style="float: left; margin: 0px 15px 15px 0px;" src="https://github.com/microsoft/sqlworkshops/blob/master/graphics/pencil2.png?raw=true">3.4 Performance</h2>
The latest version of SQL Server includes multiple features to enable higher performance, some without even altering your code. These improvements include: 

- Online clustered columnstore index build and rebuild
- Resumable online rowstore index build	See Perform Index Operations Online
- Suspend and resume initial scan for Transparent Data Encryption (TDE)
- In-Memory Database - leverages memory to store more data in memory to to unlock a new level of scalability across all your database workloads. Improvements in the latest version of SQL Server include:
  - In-memory online transaction processing (for OLTP)
  - <a href="https://learn.microsoft.com/en-us/sql/database-engine/configure-windows/hybrid-buffer-pool?view=sql-server-ver15">Hybrid buffer pool</a>, where database pages sitting on database files placed on a persistent memory (PMEM) device will be directly accessed when required
  - <a href="https://learn.microsoft.com/en-us/sql/relational-databases/databases/tempdb-database?view=sql-server-ver15#memory-optimized-tempdb-metadata">Memory-optimized TempDB metadata</a> allows effectively removes tempDB metadata bottlenecks and unlocks a new level of scalability for TempDB heavy workloads. The system tables involved in managing temporary table metadata can be moved into latch-free non-durable memory-optimized tables
  - <a href="https://learn.microsoft.com/en-us/sql/relational-databases/databases/database-snapshots-sql-server?view=sql-server-ver15">In-Memory OLTP support for Database Snapshots</a> which includes memory-optimized filegroups

You can <a href="https://learn.microsoft.com/en-us/sql/sql-server/what-s-new-in-sql-server-2022?view=sql-server-ver16#performance">find more information on features at this reference</a>.

Two "families" of performance improvement in the newest version of SQL Server are important to call out: 

1. Intelligent Performance
2. Intelligent Query Processing

<h4>Intelligent Performance</h4>
This <a href="https://www.linkedin.com/pulse/sql-server-2019-intelligent-performance-bob-ward/">group of improvements</a> help overcome known resource bottlenecks and provide options for configuring your database server to provide predictable performance across all your workloads. 

<br>
<img src="https://media-exp1.licdn.com/dms/image/C4E12AQGrvOC-No_rTg/article-inline_image-shrink_1000_1488/0/1568637964576?e=1671667200&v=beta&t=6yv0A0sjfnzOI3EQmnGdd-5aB-jlL8VIZE4cch1wh9U" width=400>
<br>

New improvements include:

  - <a href="https://techcommunity.microsoft.com/t5/sql-server-blog/behind-the-scenes-on-optimize-for-sequential-key/ba-p/806888">OPTIMIZE_FOR_SEQUENTIAL_KEY</a>	which turns on an optimization within the SQL Server Database Engine that helps improve throughput for high-concurrency inserts into the index. This option is intended for indexes that are prone to last-page insert contention, which is typically seen with indexes that have a sequential key, such as an identity column, sequence, or date/time column
  - <a href="https://techcommunity.microsoft.com/t5/sql-server-blog/understanding-sql-server-fast-forward-server-cursors/ba-p/383556">Forcing fast forward and static cursors</a>, which provides Query Store plan forcing support for fast forward and static cursors. See Plan forcing support for fast forward and static cursors
  - Resource governance has a new configurable value for the <a href="https://techcommunity.microsoft.com/t5/sql-server-blog/understanding-sql-server-memory-grant/ba-p/383595">REQUEST_MAX_MEMORY_GRANT_PERCENT option of CREATE WORKLOAD GROUP and ALTER WORKLOAD GROUP</a> has been changed from an integer to a float data type, to allow more granular control of memory limits. See ALTER WORKLOAD GROUP and CREATE WORKLOAD GROUP
  - <a href="https://techcommunity.microsoft.com/t5/azure-sql-blog/reduced-recompilations-for-workloads-using-temporary-tables/ba-p/388391">Reduced recompilations for workloads</a> which improves performance when using temporary tables across multiple scopes by reducing unnecessary recompilations
  - <a href="https://cloudblogs.microsoft.com/sqlserver/2022/07/21/improve-scalability-with-system-page-latch-concurrency-enhancements-in-sql-server-2022/">Concurrent Page Free Space (PFS) pages</a>, which are special pages within a database file that SQL Server uses to help locate free space when it allocates space for an object
  - <a href="https://techcommunity.microsoft.com/t5/sql-server-blog/sql-server-2019-intelligent-performance-worker-migration/ba-p/939610">Scheduler worker migration</a> allows an idle scheduler to migrate a worker from the runnable queue of another scheduler on the same NUMA node and immediately resume the task of the migrated worker. This enhancement provides more balanced CPU usage in situations where long-running tasks happen to be assigned to the same scheduler

<h4>Intelligent Query Processing</h4>
Of special importance in the newest performance improvements is a family of features in the SQL Server Database Engine called <a href="https://learn.microsoft.com/en-us/sql/relational-databases/performance/intelligent-query-processing?view=sql-server-ver15">Intelligent Query Processing</a> (IQP). Introduced in the latest versions of SQL Server, this family of features constantly adapts to queries in the safest way to ensure that your workloads get the highest possible performance, all without adding indexes or changing code. Some of the latest improvements in SQL Server in the IQP include:

- <a href="https://learn.microsoft.com/en-us/sql/relational-databases/performance/intelligent-query-processing-details?view=sql-server-ver15#batch-mode-adaptive-joins">Adaptive Joins (Batch Mode)</a> dynamically select a join type during runtime based on actual input rows
- <a href="https://learn.microsoft.com/en-us/sql/relational-databases/performance/intelligent-query-processing-details?view=sql-server-ver15#approximate-query-processing">Approximate Count Distinct</a> provides approximate COUNT DISTINCT for big data scenarios with the benefit of high performance and a low memory footprint
- <a href="https://learn.microsoft.com/en-us/sql/relational-databases/performance/intelligent-query-processing-details?view=sql-server-ver15#batch-mode-on-rowstore">Batch Mode on Rowstore</a> provides batch mode for CPU-bound relational DW workloads without requiring columnstore indexes
- <a href="https://learn.microsoft.com/en-us/sql/relational-databases/performance/intelligent-query-processing-feedback?view=sql-server-ver15#cardinality-estimation-ce-feedback">Cardinality estimation (CE) feedback</a> automatically adjusts cardinality estimates for repeating queries to optimize workloads where inefficient CE assumptions cause poor query performance. CE feedback will identify and use a model assumption that better fits a given query and data distribution to improve query execution plan quality
- <a href="https://learn.microsoft.com/en-us/sql/relational-databases/performance/intelligent-query-processing-details?view=sql-server-ver15#dop-feedback">Degrees of Parallelism (DOP) feedback</a> automatically adjusts degree of parallelism for repeating queries to optimize for workloads where inefficient parallelism can cause performance issues
- <a href="https://learn.microsoft.com/en-us/sql/relational-databases/performance/intelligent-query-processing-details?view=sql-server-ver15#interleaved-execution-for-mstvfs">Interleaved Execution</a> uses the actual cardinality of the multi-statement table valued function encountered on first compilation instead of a fixed guess
- <a href="https://learn.microsoft.com/en-us/sql/relational-databases/performance/intelligent-query-processing-feedback?view=sql-server-ver15#batch-mode-memory-grant-feedback">Memory grant feedback (Batch Mode)</a> is used if a batch mode query has operations that spill to disk, adding more memory for consecutive executions. If a query wastes > 50% of the memory allocated to it, it reduces the memory grant size for consecutive executions
- <a href="https://learn.microsoft.com/en-us/sql/relational-databases/performance/intelligent-query-processing-feedback?view=sql-server-ver15#row-mode-memory-grant-feedback">Memory grant feedback (Row Mode)</a> is used if row mode query has operations that spill to disk, add more memory for consecutive executions. If a query wastes > 50% of the memory allocated to it, it reduces the memory grant size for consecutive executions.
- <a href="https://learn.microsoft.com/en-us/sql/relational-databases/performance/intelligent-query-processing-feedback?view=sql-server-ver15#percentile-and-persistence-mode-memory-grant-feedback">Memory grant feedback (Percentile)</a> addresses existing limitations of memory grant feedback in a non-intrusive way by incorporating past query execution to refine feedback
- <a href="https://learn.microsoft.com/en-us/sql/relational-databases/performance/intelligent-query-processing-feedback?view=sql-server-ver15#percentile-and-persistence-mode-memory-grant-feedback">Memory Grant, CE, and DOP feedback persistence</a> provides new functionality to persist memory grant feedback. CE and DOP feedback is always persisted. Requires Query Store to be enabled for the database and in READ_WRITE mode
- <a href="https://learn.microsoft.com/en-us/sql/relational-databases/performance/optimized-plan-forcing-query-store?view=sql-server-ver15">Optimized plan forcing</a> reduces compilation overhead for repeating forced queries. For more information, see Optimized plan forcing with Query Store
- <a href="https://learn.microsoft.com/en-us/sql/relational-databases/performance/intelligent-query-processing-details?view=sql-server-ver15#scalar-udf-inlining">Scalar UDF Inlining</a> transforms Scalar UDFs into equivalent relational expressions that are "inlined" into the calling query, often resulting in significant performance gains
- <a href="https://learn.microsoft.com/en-us/sql/relational-databases/performance/parameter-sensitivity-plan-optimization?view=sql-server-ver15">Parameter Sensitivity Plan Optimization</a> addresses the scenario where a single cached plan for a parameterized query is not optimal for all possible incoming parameter values, for example non-uniform data distributions
- <a href="https://learn.microsoft.com/en-us/sql/relational-databases/performance/intelligent-query-processing-details?view=sql-server-ver15#table-variable-deferred-compilation">Table Variable Deferred Compilation</a> uses the actual cardinality of the table variable encountered on first compilation instead of a fixed guess

The following graphic details the family of IQP features and when they were first introduced for SQL Server. All IQP features are available in Azure SQL Managed Instance and Azure SQL Database (Some features depend on the database's compatibility level):

<p><img src="https://learn.microsoft.com/en-us/sql/relational-databases/performance/media/iqp-feature-family.svg?view=sql-server-ver16" width=600></p>

<h4>The Query Data Store </h4>
The Query Store feature provides you with insight on query plan choice and performance for SQL Server, Azure SQL Database, Azure SQL Managed Instance, and Azure Synapse Analytics. The Query Store simplifies performance troubleshooting by helping you quickly find performance differences caused by query plan changes. Query Store automatically captures a history of queries, plans, and runtime statistics, and retains these for your review. It separates data by time windows so you can see database usage patterns and understand when query plan changes. the Query Store is used by all the Intelligent Database and Intelligent Query Performance improvements. Improvements in the latest version of SQL Server for Query Store include:

- <a href="https://learn.microsoft.com/en-us/sql/relational-databases/performance/monitoring-performance-by-using-the-query-store?view=sql-server-ver15#query-store-for-secondary-replicas">Query Store on secondary replicas</a> enables the same Query Store functionality on secondary replica workloads that is available for primary replicas
- <a href="https://learn.microsoft.com/en-us/sql/relational-databases/performance/query-store-hints?view=sql-server-ver15">Query Store hints</a> leverage the Query Store to provide a method to shape query plans without changing application code. Previously only available on Azure SQL Database and Azure SQL Managed Instance, Query Store hints are now available in the latest version of on-premises SQL Server
- Query Store is enabled by default for newly created databases int he latest version of SQL Server
- Every query recompilation SQL Server compares the runtime stats of the query using existing feedback to the runtime stats of the previous compilation with the existing feedback

You can <a href="https://learn.microsoft.com/en-us/training/modules/explore-query-performance-optimization/5-explore-query-store">learn more about the Query Data Store at this reference</a>.

<p><img style="float: left; margin: 0px 15px 15px 0px;" src="https://github.com/microsoft/sqlworkshops/blob/master/graphics/point1.png?raw=true"><b>Activity: Learn and use Query Data Store</b></p>
<br>
In this Activity, you will learn more about the Query Data Store, and find a resource to implement it on your test system.

<p><img style="margin: 0px 15px 15px 0px;" src="https://github.com/microsoft/sqlworkshops/blob/master/graphics/checkmark.png?raw=true"><b>Steps</b></p>

- Open this <a href="https://learn.microsoft.com/en-us/training/modules/explore-query-performance-optimization/5-explore-query-store">resource and move to Unit 5 of the "Explore query performance optimization" Learn module to learn more about the Query Data Store.
- Open <a href = "https://learn.microsoft.com/en-us/sql/relational-databases/performance/tune-performance-with-the-query-store?view=sql-server-ver16">this reference and run the queries you see there</a>. Bookmark for later reference. 

<p style="border-bottom: 1px solid lightgrey;"></p>

<h2 id="3.5"><img style="float: left; margin: 0px 15px 15px 0px;" src="https://github.com/microsoft/sqlworkshops/blob/master/graphics/pencil2.png?raw=true">3.5 Security</h2>
Over the past ten years, <a href="https://nvd.nist.gov/">SQL Server has had fewer vulnerabilities than any other major database platform </a>. Building on this security posture, several new improvements and features have been added to increase security for the platform.

<h4>Data Classification and Access Control Enhancements</h4>
Data Discovery and Classification is a new set of commands and metadata that allow you to "tag" columns of data in your databases with standard or configurable labels, from Transact-SQL statements or by using the graphical interface in SQL Server Management Studio (SSMS).
<p></p>
<img src="https://learn.microsoft.com/en-us/sql/relational-databases/security/media/sql-data-discovery-and-classification/0-data-classification-explorer.png?view=sql-server-ver16" width=600>
<p></p>
You can <a href="https://learn.microsoft.com/en-us/sql/relational-databases/security/sql-data-discovery-and-classification?view=sql-server-ver16&tabs=t-sql">learn more about Data Classification and Discovery at this reference.</a>
<p></p>
There are a new set of Server-level Roles in the newest version of SQL Server to enable least privileged access for administrative tasks that apply to the whole SQL Server Instance. You can <a href="https://learn.microsoft.com/en-us/sql/relational-databases/security/authentication-access/server-level-roles?view=sql-server-ver15#fixed-server-level-roles-introduced-in-sql-server-2022">learn more about these roles at this reference</a>.

<h4>Dynamic Data Masking, Row-Level Security and Always Encrypted Improvements</h4>
Fine-grained encryption and data-level masking are important tools for the administrators and developers of data applications to completely secure data access, all while reducing the coding load. Several new improvements provide these capabilities.

<b>Dynamic Data Masking</b>
Dynamic data masking (DDM) helps prevent unauthorized access to sensitive data by enabling you to specify how much sensitive data to reveal, all with minimal impact on the application layer. DDM can be configured on designated database fields to hide sensitive data in the result sets of queries. 

> With DDM, the data in the database isn't changed. DDM is easy to use with existing applications, since masking rules are applied in the query results.

<p></p>
<img src="https://learn.microsoft.com/en-us/sql/relational-databases/security/media/dynamic-data-masking.png?view=sql-server-ver16" width=300>
<p></p>

You can <a href="https://learn.microsoft.com/en-us/sql/relational-databases/security/dynamic-data-masking?view=sql-server-ver16">learn more about Dynamic Data Masking and find a tutorial on implementing it at this reference</a>.

<b>Row-Level Security</b>
Row-Level Security enables you to use Role membership or execution context to control access to rows in a database table. Row-Level Security (RLS) simplifies the design and coding of security in your application, since the access restriction logic is located in the database tier rather than away from the data in another application tier.

<p></p>
<img src="https://learn.microsoft.com/en-us/sql/relational-databases/security/media/row-level-security/row-level-security-graphic.png?view=sql-server-ver16" width=300>
<p></p>

You can <a href="https://learn.microsoft.com/en-us/sql/relational-databases/security/row-level-security?view=sql-server-ver16">learn more about Row-Level Security and find a tutorial on implementing it at this reference</a>.

<b>Always Encrypted with Secure Enclaves</b>
the latest version of SQL Server expands on the <i>Always Encrypted</i> fesatures with in-place encryption and rich computations by enabling computations on plaintext data inside a server-side secure enclave. In-place encryption improves the performance and the reliability of cryptographic operations (encrypting columns, rotating columns, encryption keys, and so on), because it avoids moving data out of the database.

This improvement also supports rich computations (pattern matching and comparison operations) which unlocks Always Encrypted to a much broader set of scenarios and applications that demand sensitive data protection, while also requiring richer functionality in Transact-SQL queries.

You can <a href="https://learn.microsoft.com/en-us/sql/relational-databases/security/encryption/always-encrypted-enclaves?view=sql-server-ver15">read more about Always Encrypted with Secure Enclaves at this reference</a>.

<h4>Auditing Enhancements</h4>
Auditing in SQL Server is now improved to include a new field called <i>data_sensitivity_information</i> in the audit log record, which contains the sensitivity classifications (labels) of the actual data that was returned by the query, which leverages the Data Classification features shown earlier.

You can <a href="https://learn.microsoft.com/en-us/sql/relational-databases/security/auditing/sql-server-audit-database-engine?view=sql-server-ver15">learn more about Auditing in SQL Server at this reference</a>.

<h4>Ledger</h4>
Establishing trust around the integrity of data stored in database systems has been a longstanding problem for all organizations that manage financial, medical, or other sensitive data. The ledger feature provides tamper-evidence capabilities in your database. You can cryptographically attest to other parties, such as auditors or other business parties, that your data hasn't been tampered with.

The latest version of SQL Server includes a new feature called <i>Ledger</i> which, once enabled on a table, adds a hashed value (a Block) at the end of each row of data, and a computed hashed value from those Blocks (representing a Chain of Blocks) to uniquely identify the data in the database. A Digest is created for those values, which can be in separate, protected storage, to compare the state of the internal blockchain to an immutable copy, which can prove whether data has been tampered with.

<p><img src="https://learn.microsoft.com/en-us/sql/relational-databases/security/ledger/media/ledger/ledger-table-architecture.png?view=sql-server-ver16" width=400></p>

You can <a href="https://learn.microsoft.com/en-us/sql/relational-databases/security/ledger/ledger-overview?view=sql-server-ver16">read more about how to use Ledger in SQL Server at this reference</a>.

<p><img style="float: left; margin: 0px 15px 15px 0px;" src="https://github.com/microsoft/sqlworkshops/blob/master/graphics/point1.png?raw=true"><b>Activity: Implement a Ledger on your Test Database</b></p>
In this Activity, you will implement Ledger for SQL Server on your test system. You can use any sample database, or make one specifically for this exercise.

<p><img style="margin: 0px 15px 15px 0px;" src="https://github.com/microsoft/sqlworkshops/blob/master/graphics/checkmark.png?raw=true"><b>Steps</b></p>
- Open this <a href="https://learn.microsoft.com/en-us/sql/relational-databases/security/ledger/ledger-how-to-append-only-ledger-tables?view=sql-server-ver16">resource and complete the steps you see there</a>.
<p></p>
<p style="border-bottom: 1px solid lightgrey;"></p>

<h2 id="3.6"><img style="float: left; margin: 0px 15px 15px 0px;" src="https://github.com/microsoft/sqlworkshops/blob/master/graphics/pencil2.png?raw=true">3.6 Development</h2>
Developer enhancements include not only new Transact-SQL (T-SQL) changes including new time series, JSON improvments, aggregate changes, and Bit manipulation functions, but also data types and changes to features such as using SQL Server as a Graph Database and new Unicode feature support. A few of the improvements in the latest version of SQL Server are:

- Graph enhancements
  - <a href="https://learn.microsoft.com/en-us/sql/relational-databases/tables/graph-edge-constraints?view=sql-server-ver15">Edge constraint cascade delete actions</a> allow you to define cascaded delete actions on an edge constraint in a graph database
  - A new graph function - SHORTEST_PATH - exists inside MATCH to find the shortest path between any two nodes in a graph or to perform arbitrary length traversals
  - Graph tables now support table and index partitioning
  - You can now use derived tables or view aliases in a <a href="https://learn.microsoft.com/en-us/sql/t-sql/queries/match-sql-graph?view=sql-server-ver15">graph match query</a>
- Unicode support improvements include <a href="https://learn.microsoft.com/en-us/sql/relational-databases/collations/collation-and-unicode-support?view=sql-server-ver15">support for UTF-8 character encoding</a> for import and export encoding, and as database-level or column-level collation for string data. Support includes PolyBase external tables, and Always Encrypted (when not used with Enclaves)
- Language extensions
  - A new <a href="https://learn.microsoft.com/en-us/sql/language-extensions/how-to/extensibility-sdk-java-sql-server?view=sql-server-ver15">Java language SDK</a> that simplifies the development of Java programs that can be run from SQL Server
  - The Microsoft Extensibility SDK for Java for Microsoft SQL Server is now <a href="https://github.com/microsoft/sql-server-language-extensions">open source and available on GitHub</a>
  - Support for <a href="https://learn.microsoft.com/en-us/sql/language-extensions/how-to/java-to-sql-data-types?view=sql-server-ver15">new Java data types</a>
  - SQL Server <a href="https://cloudblogs.microsoft.com/sqlserver/2019/07/24/free-supported-java-in-sql-server-2019-is-now-available/">now includes Azul Systems Zulu Embedded</a> for Java support throughout the product
  - SQL Server <a href="https://learn.microsoft.com/en-us/sql/language-extensions/language-extensions-overview?view=sql-server-ver15">Language Extensions</a> allows you to execute external code with the extensibility framework
  - A new Data Definition Language (DDL), <a href="https://learn.microsoft.com/en-us/sql/t-sql/statements/create-external-language-transact-sql?view=sql-server-ver15">CREATE EXTERNAL LANGUAGE</a>, registers external languages, such as Java, in SQL Server
- New spatial reference identifiers (SRIDs), <a href="http://www.ga.gov.au/scientific-topics/positioning-navigation/geodesy/datums-projections/gda2020">using the Australian GDA2020 which provides a more robust and accurate datum</a> that's more closely aligned with global positioning systems. The new SRIDs are: 7843 for geographic 2D, 7844 for geographic 3D
- Error messages include <a href="https://learn.microsoft.com/en-us/sql/t-sql/statements/alter-database-scoped-configuration-transact-sql?view=sql-server-ver15#verbose-truncation">verbose truncation warnings</a> - the data truncation error message defaults to include table and column names, and the truncated value

You can <a href="https://learn.microsoft.com/en-us/sql/sql-server/what-s-new-in-sql-server-2022?view=sql-server-ver16#language">learn more details about each individual language improvement at this reference</a>. 

<h4>SQL Server Machine Learning Services</h4>
SQL Server Machine Learning Services provides a mechanism to create, train, and deploy Machine Learning models that stay in the database where the source data lives. It can use the R, Java, and Python languages and libraries, and includes the ability to add other languages if desired. Improvements to this feature in the latest version of SQL Server include:
	
- You can process external scripts per partition of your data by using the new parameters added to <i>sp_execute_external_script</i>. This functionality supports training many small models (one model per partition of data) instead of one large model
- You can configure high availability for Machine Learning Services on a Windows Server Failover Cluster

You can <a href="https://www.bing.com/ck/a?!&&p=a1c642dd7492b7a8JmltdHM9MTY2NjA1MTIwMCZpZ3VpZD0yZjZmYzk3Ni1jZGE5LTYzZDMtMmY2NC1kOWY1Y2M2YjYyMzgmaW5zaWQ9NTQ0Mg&ptn=3&hsh=3&fclid=2f6fc976-cda9-63d3-2f64-d9f5cc6b6238&psq=sql+server+machine+learning++site%3amicrosoft.com&u=a1aHR0cHM6Ly9sZWFybi5taWNyb3NvZnQuY29tL2VuLXVzL3NxbC9tYWNoaW5lLWxlYXJuaW5nL3NxbC1zZXJ2ZXItbWFjaGluZS1sZWFybmluZy1zZXJ2aWNlcz92aWV3PXNxbC1zZXJ2ZXItdmVyMTYjOn46dGV4dD1NYWNoaW5lJTIwTGVhcm5pbmclMjBTZXJ2aWNlcyUyMGlzJTIwYSUyMGZlYXR1cmUlMjBpbiUyMFNRTCxSJTIwcGFja2FnZXMlMkMlMjBmb3IlMjBwcmVkaWN0aXZlJTIwYW5hbHl0aWNzJTIwYW5kJTIwbWFjaGluZSUyMGxlYXJuaW5nLg&ntb=1">learn more about Machine Learning Services in SQL Server at this reference, which also contains multiple tutorials</a>.

<p><img style="float: left; margin: 0px 15px 15px 0px;" src="https://github.com/microsoft/sqlworkshops/blob/master/graphics/point1.png?raw=true"><b>Activity: Work with a Graph Database</b></p>

One of the new enhancements in the latest version of SQL Server is in the <i>SQL Graph</i> feature. Many data professionals have not worked with a Graph database before, and are not aware of how powerful it can be. In this Activity you will create a simple Graph database, and run a simple MATCH query on it. 

<br>
<img src="https://learn.microsoft.com/en-us/sql/relational-databases/graphs/media/person-cities-restaurants-tables.png?view=sql-server-ver16" width=300>
<br>

<p><img style="margin: 0px 15px 15px 0px;" src="https://github.com/microsoft/sqlworkshops/blob/master/graphics/checkmark.png?raw=true"><b>Steps</b></p>

- Open <a href="https://learn.microsoft.com/en-us/sql/relational-databases/graphs/sql-graph-sample?source=recommendations&view=sql-server-ver16">the following reference and follow all the steps you see there</a>. 

<p></p>
<p style="border-bottom: 1px solid lightgrey;"></p>
<p></p>

<h2 id="3.7"><img style="float: left; margin: 0px 15px 15px 0px;" src="https://github.com/microsoft/sqlworkshops/blob/master/graphics/pencil2.png?raw=true">3.7 Analytics</h2>
SQL Server contains not only Transact-SQL statements that facilitate data analysis, but also the integration of R, Python, and Java with the Extensibility Framework for extended data analysis. There are also various services included with SQL Server that provide advanced analytic capabilities, and these have had significant improvements in the latest version. 
<p></p>

- <b>SQL Server Analysis Services</b>
  - <a href="https://learn.microsoft.com/en-us/analysis-services/tabular-models/calculation-groups">Calculation groups in tabular models</a> can significantly reduce the number of redundant measures by grouping common measure expressions as calculation items
  - <a href="https://learn.microsoft.com/en-us/analysis-services/tabular-models/query-interleaving">Query interleaving is a new tabular mode system configuration</a> that can improve user query response times in high-concurrency scenarios
  - <a href="https://learn.microsoft.com/en-us/analysis-services/tabular-models/relationships-ssas-tabular">Many-to-many relationships in tabular models</a> allows many-to-many relationships between tables where both columns are non-unique
  - <a href="https://learn.microsoft.com/en-us/analysis-services/server-properties/memory-properties">New Property settings for resource governance</a> includes new memory settings: Memory\QueryMemoryLimit, DbpropMsmdRequestMemoryLimit, and OLAP\Query\RowsetSerializationLimit for resource governance
  - <a href="https://learn.microsoft.com/en-us/analysis-services/server-properties/general-properties">Governance setting for Power BI cache refreshes</a> introduces the ClientCacheRefreshPolicy property, which overrides caching dashboard tile data and report data for initial load of Live connect reports by the Power BI service
  - <a href="https://learn.microsoft.com/en-us/analysis-services/what-s-new-in-sql-server-analysis-services#online-attach">Online attach	Online attach</a> can be used for synchronization of read-only replicas in on-premises query scale-out environments
  - <a href="https://learn.microsoft.com/en-us/azure/synapse-analytics/synapse-link/sql-synapse-link-overview">Azure Synapse Link for SQL</a> provides near real time analytics over operational data in SQL Server with a seamless integration between operational stores in SQL Server and Azure Synapse Analytics dedicated SQL pools, Azure Synapse Link for SQL enables you to run analytics, business intelligence and machine learning scenarios on your operational data with minimum impact on source databases with a new change feed technology
  - A new object storage integration is now added to the data platform, enabling you to integrate SQL Server with S3-compatible object storage, in addition to Azure Storage. <a href="https://learn.microsoft.com/en-us/sql/relational-databases/backup-restore/sql-server-backup-to-url-s3-compatible-object-storage?view=sql-server-ver15">The first is backup to URL</a> and the second is <a href="https://learn.microsoft.com/en-us/sql/relational-databases/polybase/polybase-configure-s3-compatible?view=sql-server-ver15">Data Lake Virtualization</a>. Data Lake Virtualization integrates PolyBase with S3-compatible object storage, adds support for to querying parquet files with T-SQL
  - Data Virtualization allows you to query different types of data on different types of data sources from SQL Server
  - SuperDAX for multidimensional models (SuperDAXMD) allows DAX-based clients to use SuperDAX functions and query patterns against multidimensional models, providing improved performance when querying model data. SuperDAX first introduced DAX query optimizations for tabular models with Power BI and SQL Server Analysis Services 2016. SuperDAXMD now brings these improvements to multidimensional models
  - Horizontal fusion is a new query execution plan optimization aimed at reducing the number of data source queries required to generate and return results. Multiple smaller data source queries are fused together into a larger data source query. Fewer data source queries mean fewer round trips and fewer expensive scans over large data sources, which results in sizeable DAX performance gains and reduced processing demand at the data source. DAX queries run faster with Horizontal Fusion, especially in DirectQuery mode. In addition, scalability also increases

<p></p>

- <b>SQL Server Integration Services</b>
  - <a href="https://learn.microsoft.com/en-us/sql/integration-services/control-flow/flexible-file-task?view=sql-server-ver15">Flexible file task</a> allows you to perform file operations on Local File System, Azure Blob Storage, and Azure Data Lake Storage Gen2
  - <a href="https://learn.microsoft.com/en-us/sql/integration-services/data-flow/flexible-file-destination?view=sql-server-ver15">Flexible file source and destination</a> adds read and write data for Azure Blob Storage, and Azure Data Lake Storage Gen2

<p></p>

- <b>SQL Server Master Data Services</b>
  - <a href="https://learn.microsoft.com/en-us/sql/master-data-services/master-data-services-installation-and-configuration?view=sql-server-ver15#SetUpWeb">Support for Azure SQL Managed Instance databases</a> now allows you to host Master Data Services on Azure SQL Managed Instance
  - HTML controls replace all former Silverlight components. Silverlight dependency removed.

<p></p>

- <b>SQL Server Reporting Services</b>
   - Azure SQL Managed Instance support means that you can now host a database catalog used for SQL Server Reporting Services (SSRS) in an Azure SQL Managed Instance (MI) that's hosted either in a VM or in your data center
  - Power BI Premium dataset support allows you to connect to Power BI datasets using either Microsoft Report Builder or SQL Server Data Tools (SSDT). Then you can publish those reports to SSRS using SQL Server Analysis Services connectivity
  - AltText (alternative text) support for report elements, so that when authoring reports, you can use tooltips to specify text for each element on the report. Screen reader technology identifies these tooltips properly
  - Azure Active Directory Application Proxy support means that you no longer need to manage your own web application proxy in order to allow secure access via the web or mobile apps
  - New Custom headers sets header values for all URLs matching the specified regex pattern. Users can update the custom header value with valid XML to set header values for selected request URLs. Admins can add any number of headers in the XML
  - SQL Server now supports Transparent Database Encryption for the SSRS catalog database
  - The newly released version of Report Builder is fully compatible with the 2016, 2017, 2019 and versions of Reporting Services. It's also compatible with all released and supported versions of Power BI Report Server

<p></p>
<p style="border-bottom: 1px solid lightgrey;"></p>
<p></p>

<p><img style="float: left; margin: 0px 15px 15px 0px;" src="https://github.com/microsoft/sqlworkshops/blob/master/graphics/owl.png?raw=true"><b>For Further Study</b></p>
<br>
<ul>
    <li><a href="https://learn.microsoft.com/en-us/training/modules/introduction-sql-server-linux/" target="_blank">Introduction to SQL Server on Linux</a></li>
    <li><a href="https://learn.microsoft.com/en-us/training/modules/explore-query-performance-optimization/" target="_blank">Explore query performance optimization</a></li>
    <li><a href="https://learn.microsoft.com/en-us/training/modules/azure-security-center/" target="_blank">Enable and manage Microsoft Defender for Cloud</a></li>
    <li><a href="https://learn.microsoft.com/en-us/sql/relational-databases/security/ledger/ledger-overview?view=sql-server-ver16" target="_blank">Ledger overview</a></li>
    <li><a href="https://learn.microsoft.com/en-us/sql/database-engine/sql-server-business-continuity-dr?view=sql-server-ver16#sql-server-scenarios-using-the-availability-features" target="_blank">Business continuity and database recovery - SQL Server</a></li>
    <li><a href = "https://www.simplilearn.com/data-science-vs-big-data-vs-data-analytics-article" target="_blank">Understanding the Big Data Landscape</a></li>
    <li><a href = "http://www.admin-magazine.com/Articles/Linux-Essentials-for-Windows-Admins-Part-1" target="_blank">Linux for the Windows Admin</a></li>
    <li><a href = "https://docs.docker.com/v17.09/engine/userguide/" target="_blank">Container Runtimes (Such as Docker) Guide</a></li>
    <li><a href = "https://www.youtube.com/playlist?list=PLLasX02E8BPCrIhFrc_ZiINhbRkYMKdPT" target="_blank">Video introduction to Kubernetes</a></li>
    <li><a href = "https://github.com/vlele/k8onazure" target="_blank">Complete course on the Azure Kubernetes Service (AKS)</a></li>
    <li><a href = "https://kube.academy/courses" target="_blank">KubeAcademy</a></li>
     <li><a href = "https://www.kdnuggets.com/2019/01/practical-apache-spark-10-minutes.html" target="_blank">Working with Spark</a></li>
    <li><a href="https://realpython.com/jupyter-notebook-introduction/" target="_blank">Full tutorial on Jupyter Notebooks</a></li>
</ul>

Next, continue on to <a href="https://github.com/sqlballs/mSQLg2c/blob/main/modules/04-ImprovementsInSQLOnTheMicrosoftAzurePlatform.md">Module 04 - SQL Server on the Microsoft Azure Platform</a>
