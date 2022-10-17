![](https://github.com/microsoft/sqlworkshops/blob/master/graphics/microsoftlogo.png?raw=true)![](../graphics/microsoftlogo.png)

# Workshop: Modernizing Your Data Estate With SQL Ground-to-Cloud
#### <i>A Microsoft workshop from the SQL Server team</i>

<p style="border-bottom: 1px solid lightgrey;"></p>

<img style="float: left; margin: 0px 15px 15px 0px;" src="https://github.com/microsoft/sqlworkshops/blob/master/graphics/textbubble.png?raw=true"> <h2>03 - SQL Server Improvements</h2>

In this workshop you'll cover how to systematically create a modern data estate using SQL Server in on-premises, in-cloud and hybrid solutions. 

In each module you'll get more references, which you should follow up on to learn more. Also watch for links within the text - click on each one to explore that topic.

(<a href="file:///url" target="_blank">Make sure you check out the <b>Pre-Requisites</b> page before you start</a>. You'll need all of the items loaded there before you can proceed with the workshop.)

Using the <a href="https://github.com/sqlballs/mSQLg2c/blob/main/modules/02-AuditingYour%20DataEstateArchitecture.md">processes, tools and procedures from the Auditing  Module</a>, the WideWorldImporters company has completed an initial audit of their data estate.They found multiple sources of data in their organization, including text files, spreadsheets, and Relational Database Management Systems (RDBMS) including SQL Server 2008 Instances along with some Instances of SQL Server 2012, 2014, and 2016 versions. 

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

<TODO: Review - Add - Edit Main Themes>

- Perf 
  - https://learn.microsoft.com/en-us/sql/sql-server/what-s-new-in-sql-server-2019?view=sql-server-ver15#intelligent-database
  - https://learn.microsoft.com/en-us/sql/sql-server/what-s-new-in-sql-server-2022?view=sql-server-ver15#performance
  - https://learn.microsoft.com/en-us/sql/sql-server/what-s-new-in-sql-server-2022?view=sql-server-ver15#query-store-and-intelligent-query-processing 
- Security 
  - https://learn.microsoft.com/en-us/sql/sql-server/what-s-new-in-sql-server-2019?view=sql-server-ver15#mission-critical-security
  - https://learn.microsoft.com/en-us/sql/sql-server/what-s-new-in-sql-server-2022?view=sql-server-ver15#security 
- Developer 
  - https://learn.microsoft.com/en-us/sql/sql-server/what-s-new-in-sql-server-2019?view=sql-server-ver15#developer-experience 
  - https://learn.microsoft.com/en-us/sql/sql-server/what-s-new-in-sql-server-2019?view=sql-server-ver15#ml
  - https://learn.microsoft.com/en-us/sql/sql-server/what-s-new-in-sql-server-2022?view=sql-server-ver15#platform
  - https://learn.microsoft.com/en-us/sql/sql-server/what-s-new-in-sql-server-2022?view=sql-server-ver15#sql-machine-learning-services 
- Analytics 
  - https://learn.microsoft.com/en-us/sql/sql-server/what-s-new-in-sql-server-2019?view=sql-server-ver15#sql-server-analysis-services
  - https://learn.microsoft.com/en-us/sql/sql-server/what-s-new-in-sql-server-2019?view=sql-server-ver15#sql-server-integration-services
  - https://learn.microsoft.com/en-us/sql/sql-server/what-s-new-in-sql-server-2019?view=sql-server-ver15#sql-server-
  - https://learn.microsoft.com/en-us/sql/sql-server/what-s-new-in-sql-server-2019?view=sql-server-ver15#sql-server-reporting-services
  - https://learn.microsoft.com/en-us/sql/sql-server/what-s-new-in-sql-server-2022?view=sql-server-ver15#analytics
  - https://learn.microsoft.com/en-us/sql/sql-server/what-s-new-in-sql-server-2022?view=sql-server-ver15#sql-server-analysis-services
  - https://learn.microsoft.com/en-us/sql/sql-server/what-s-new-in-sql-server-2022?view=sql-server-ver15#sql-server-reporting-services 

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
- Linux distributions supported

There are specific versions and support considerations for each distrivution of Linux. A <a href="https://learn.microsoft.com/en-us/sql/linux/sql-server-linux-whats-new-2019?view=sql-server-ver16">list of these requirements is available at this reference</a>, and a <a href="https://learn.microsoft.com/en-us/sql/linux/sql-server-linux-editions-and-components-2022?view=sql-server-ver16">list of Editions and supported features for SQL Server on Linux is at this reference</a>. 

You can <a href="https://learn.microsoft.com/en-us/sql/linux/sql-server-linux-overview?view=sql-server-ver16">learn more about the SQL Server on Linux architecture at this reference</a>.

<h3>SQL Server in Containers</h3>
The introduction of SQL Server running on Linux allows for the next level of hardware abstraction, called a Container. There are various types of Container technologies, in this workshop, you will focus on the docker container format, as implemented in the Moby framework.

A Container is provided by the Container Runtime (Such as containerd]) runtime engine, which sits above the operating system (Windows or Linux). In this abstraction, you do not control the hardware or the operating system. The Container has a very small Kernel in it, and can contain binaries such as Python, R, SQL Server, or other binaries. A Container with all its binaries is called an Image. You create a container from a file.

You can see the difference between Virtual Machines and Container technologies here: 

<img src="https://cloudblogs.microsoft.com/uploads/prod/sites/37/2019/07/Demystifying-containers_image1.png" width=600>


This abstraction holds everything for an application to isolate it from other running processes. It is also completely portable - you can create an image on one system, and another system can run it so long as the Container Runtimes (Such as Docker) Runtime is installed. Containers also start very quickly, are easy to create (called Composing) using a simple text file with instructions of what to install on the image. The instructions pull the base Kernel, and then any binaries you want to install. Several pre-built Containers are already available, SQL Server is one of these. You can <a href="https://docs.microsoft.com/en-us/sql/linux/quickstart-install-connect-docker?view=sql-server-2017">read more about installing SQL Server on Container Runtimes (Such as Docker) at this reference</a>.

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
- <i>Optional</i>: If time permits, you can install the Docker platform on your test system and complete the steps to depploy SQL Server on Linux and connect with a test to that environment.

<p style="border-bottom: 1px solid lightgrey;"></p>

<h2 id="3.2"><img style="float: left; margin: 0px 15px 15px 0px;" src="https://github.com/microsoft/sqlworkshops/blob/master/graphics/pencil2.png?raw=true">3.2 Manageability</h2>

For the administration team for the Data Estate, manageability includes everything from the interface to the system, to being able to deploy and configure it. The latest version of SQL Server includes the following improvements:

- An integrated setup experience for the Azure extension for SQL Server	Install the Azure extension for SQL Server at setup. Required for Azure integration features
- Using the SQL Server Configuration Manager to manage an Azure extension for SQL Server service, allowing you to create Azure Arc-enabled SQL Server instances, and for other Azure connected features
- Upgraded max server memory calculations
- There are several improvements to address persistent version store (PVS) storage and improve overall scalability, including a persistent version store cleaner thread per database instead of per instance and the memory footprint for PVS page tracker has been improved. There are also a number of ADR efficiency improvements, such as concurrency improvements that help the cleanup process to work more efficiently. ADR cleans pages that couldn't previously be cleaned due to locking
- Shrink database WAIT_AT_LOW_PRIORITY
- XML compression
- Asynchronous auto update statistics concurrency

<h3>Tools</h3>
There are several tools you can use to connect to, query, and manage a SQL Server Instance. The two broad groups are Graphical User Interfaces (GUI) and Command-Line or Scripting Interfaces. 

New improvements include:

- Azure Data Studio includes connection and management support for the latest version of SQL Server
- SQL Server Management Studio connects and manages the latest version of SQL Server, and includes several other improvements
- SqlPackage.exe provides support for the latest version of SQL Server
- VS Code	The latest release of VS Code now supports the latest version of SQL Server

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
- Object Explorer	Dropped Columns folder now exists under the Columns folder for Ledger tables, which have been altered to remove one or more columns
- Scripting	Compatibility level defaults to 160 when scripting
- Added Showplan support for Hyperscale Optimized Query Processing
- Analysis Services	Connection to Analysis Services is now available
- Added missing options in SqlParser for CREATE USER and CREATE LOGIN.
- The “Schedule…” menu item in SQL Server Integration Services is now visible in the Azure SSIS Catalog
- Added the ability to explicitly configure an attestation protocol in the "Connect To Server" dialog when using Always Encrypted with secure enclaves (column encryption).
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

<p style="border-bottom: 1px solid lightgrey;"></p>

<h2 id="3.3"><img style="float: left; margin: 0px 15px 15px 0px;" src="https://github.com/microsoft/sqlworkshops/blob/master/graphics/pencil2.png?raw=true">3.3 Availability</h2>

One of the important considerations for WideWorld Importers is ensuring Business Continuity. As part of their strategy, the Data Estate is an important component. The general area for Business Continuity in Data is <i>High Availablity</i>, which in turn contains important concepts such as Recovery Point Objectives (RPO) and Recovery Time Objectives (RTO). A few key terms are important to note as we dsicuss the improvements in this area of the latest version of SQL Server: 

- <b>High Availability</b> (HA): The ability for your systems to recover from localized events in an automated way
- <b>Disaster Recovery</b> (DR): The process of recoving from a diaster of some sort.  A natural or man-made disaster has occured and manual intervention may be required.  While some things can be automated, other items may require manual intervention  
- <b>Business Continuity</b>: The planning process for how businesses and their IT systems will react in the event of an outage.  This planning will typically be for DR, but it could also include HA planning

There are multiple capabilities in SQL Server that serve as part of an overall Availability strategy, including several that have new improvements in the latest version:
- Database Backups
  - <a href="https://learn.microsoft.com/en-us/sql/relational-databases/integrated-acceleration/overview?view=sql-server-ver16">Intel QAT backup hardware offloading support</a> 
  - T-SQL Snapshot Backup, <a href="https://learn.microsoft.com/en-us/sql/relational-databases/backup-restore/create-a-transact-sql-snapshot-backup?view=sql-server-ver16">adding Transact-SQL support for freezing and thawing I/O without requiring a VDI client</a>
  - <i>backupset</i> (Transact-SQL) improvements to add additional columns
  - <a href="https://learn.microsoft.com/en-us/sql/relational-databases/backup-restore/sql-server-backup-to-url-s3-compatible-object-storage?view=sql-server-ver16">Backup and restore to S3-compatible object storage</a>
- Database and Database article Replication
  - "Last Writer Wins" conflict detection
- Database Log Shipping 
- Failover Clustering 
  - simplfied Failover Clustering setup for Virtual Machines 
- Always-On Availability Groups - <a href="https://learn.microsoft.com/en-us/sql/database-engine/availability-groups/windows/contained-availability-groups-overview?view=sql-server-ver16">Improvements in the latest version of SQL Server include</a>:
  - Up to five synchronous replicas	<a href="https://learn.microsoft.com/en-us/sql/database-engine/availability-groups/windows/secondary-replica-connection-redirection-always-on-availability-groups?view=sql-server-ver16">starting in SQL Server 2019 (15.x) increases the maximum number of synchronous replicas to 5, up from 3 in SQL Server 2017 (14.x)</a>. You can configure this group of five replicas to have automatic failover within the group. There is one primary replica, plus four synchronous secondary replicas
  - Secondary-to-primary replica connection redirection	allows client application connections to be directed to the primary replica regardless of the target server specified in the connection string
  - Create an <a href="https://learn.microsoft.com/en-us/sql/database-engine/availability-groups/windows/contained-availability-groups-overview?view=sql-server-ver16">Always On Contained Availability Group</a> that manages its own metadata objects (users, logins, permissions, SQL Agent jobs etc.) at the availability group level in addition to the instance level, and includes specialized contained system databases within the availability group

> The latest version of SQL Server also has the ability to participate in Availablity to and from the Microsoft Azure Platform. These improvements will be detailed in the last Module of this Workshop.

<p><img style="float: left; margin: 0px 15px 15px 0px;" src="https://github.com/microsoft/sqlworkshops/blob/master/graphics/point1.png?raw=true"><b>Activity: Examine the new Information in the backupset system table</b></p>

The <i>backupset</i> table in the <i>msdb</i> system database contains a row for each backup set. A backup set contains the backup from a single, successful backup operation. You can use this information to check for your backup status, time to run, and much more.

<p><img style="margin: 0px 15px 15px 0px;" src="https://github.com/microsoft/sqlworkshops/blob/master/graphics/checkmark.png?raw=true"><b>Steps</b></p>

- Back Up your WideWorld Importers database to disk
- <a href="https://learn.microsoft.com/en-us/sql/relational-databases/system-tables/backupset-transact-sql?view=sql-server-ver16#examples">Open this link and perform the steps you see there</a> to revoiew the new information for backups. Bookmark for later reference.

<p style="border-bottom: 1px solid lightgrey;"></p>

<h2 id="3.4"><img style="float: left; margin: 0px 15px 15px 0px;" src="https://github.com/microsoft/sqlworkshops/blob/master/graphics/pencil2.png?raw=true">3.4 Performance</h2>
The latest version of SQL Server includes multiple features to enable higher performance, some without even altering your code. These improvements include: 

- Online clustered columnstore index build and rebuild
- Resumable online rowstore index build	See Perform Index Operations Online.
- Suspend and resume initial scan for Transparent Data Encryption (TDE)
- In-Memory Database - leverages memory to store more data in memory to to unlock a new level of scalability across all your database workloads. Improvements in the latest version of SQL Server include:
  - In-memory online transaction processing (OLTP)
  - <a href="https://learn.microsoft.com/en-us/sql/database-engine/configure-windows/hybrid-buffer-pool?view=sql-server-ver15">Hybrid buffer pool</a>, where database pages sitting on database files placed on a persistent memory (PMEM) device will be directly accessed when required
  - <a href="https://learn.microsoft.com/en-us/sql/relational-databases/databases/tempdb-database?view=sql-server-ver15#memory-optimized-tempdb-metadata">Memory-optimized TempDB metadata</a> allows effectively removes tempDB metadata bottlenecks and unlocks a new level of scalability for TempDB heavy workloads. The system tables involved in managing temporary table metadata can be moved into latch-free non-durable memory-optimized tables
  - <a href="https://learn.microsoft.com/en-us/sql/relational-databases/databases/database-snapshots-sql-server?view=sql-server-ver15">In-Memory OLTP support for Database Snapshots</a> which includes memory-optimized filegroups
- Intelligent performance - These improvements help overcome known resource bottlenecks and provide options for configuring your database server to provide predictable performance across all your workloads. New improvements include:
  - OPTIMIZE_FOR_SEQUENTIAL_KEY	whcih turns on an optimization within the SQL Server Database Engine that helps improve throughput for high-concurrency inserts into the index. This option is intended for indexes that are prone to last-page insert contention, which is typically seen with indexes that have a sequential key, such as an identity column, sequence, or date/time column
  - Forcing fast forward and static cursors, which provides Query Store plan forcing support for fast forward and static cursors. See Plan forcing support for fast forward and static cursors
  - Resource governance has a new configurable value for the REQUEST_MAX_MEMORY_GRANT_PERCENT option of CREATE WORKLOAD GROUP and ALTER WORKLOAD GROUP has been changed from an integer to a float data type, to allow more granular control of memory limits. See ALTER WORKLOAD GROUP and CREATE WORKLOAD GROUP
  - Reduced recompilations for workloads which improves performance when using temporary tables across multiple scopes by reducing unnecessary recompilations
  - Indirect checkpoint scalability
  - Concurrent Page Free Space (PFS) pages, which are special pages within a database file that SQL Server uses to help locate free space when it allocates space for an object
  - Scheduler worker migration allows an idle scheduler to migrate a worker from the runnable queue of another scheduler on the same NUMA node and immediately resume the task of the migrated worker. This enhancement provides more balanced CPU usage in situations where long-running tasks happen to be assigned to the same scheduler

You can <a href="https://learn.microsoft.com/en-us/sql/sql-server/what-s-new-in-sql-server-2022?view=sql-server-ver16#performance">find more information on features at this reference</a>.

<h4>Intelligent Query Processing</h3>
https://learn.microsoft.com/en-us/sql/sql-server/what-s-new-in-sql-server-2019?view=sql-server-ver15#intelligent-database 
https://learn.microsoft.com/en-us/sql/relational-databases/performance/intelligent-query-processing?view=sql-server-ver15

Of special importance in the newest performance improvements is a family of features in the SQL Server Database Engine called <i>Intelligent Query Processing</i> (IQP). Introduced in the latest versions of SQL Server, this family of features constantly adapts to queries in the safest way to ensure that your workloads get the highest possible performance, all without adding indexes or changing code. Some of the latest improvements in SQL Server in the IQP include:


Row mode memory grant feedback	Expands on the batch mode memory grant feedback feature by adjusting memory grant sizes for both batch and row mode operators. This adjustment can automatically correct excessive grants, which result in wasted memory and reduced concurrency. It can also correct insufficient memory grants that cause expensive spills to disk. See Row mode memory grant feedback.
Batch mode on rowstore	Enables batch mode execution without requiring columnstore indexes. Batch mode execution uses CPU more efficiently during analytical workloads but, until SQL Server 2019 (15.x), it was used only when a query included operations with columnstore indexes. However, some applications might use features that aren't supported with columnstore indexes and, therefore, can't leverage batch mode. Starting with SQL Server 2019 (15.x), batch mode is enabled on eligible analytical workloads whose queries include operations with any type of index (rowstore or columnstore). See Batch mode on rowstore.
Scalar UDF Inlining	Automatically transforms scalar UDFs into relational expressions and embeds them in the calling SQL query. This transformation improves the performance of workloads that take advantage of scalar UDFs. See Scalar UDF Inlining.
Table variable deferred compilation	Improves plan quality and overall performance for queries that reference table variables. During optimization and initial compilation, this feature propagates cardinality estimates that are based on actual table variable row counts. This accurate row count information optimizes downstream plan operations. See Table variable deferred compilation.
Approximate query processing with APPROX_COUNT_DISTINCT	For scenarios when absolute precision isn't important but responsiveness is critical, APPROX_COUNT_DISTINCT aggregates across large datasets while using fewer resources than COUNT(DISTINCT()) for superior concurrency. See Approximate query processing.



<p><img src="https://learn.microsoft.com/en-us/sql/relational-databases/performance/media/iqp-feature-family.svg?view=sql-server-ver16" width=600></p>

The intelligent query processing (IQP) feature family includes features with broad impact that improve the performance of existing workloads with minimal implementation effort to adopt. The following graphic details the family of IQP features and when they were first introduced for SQL Server. All IQP features are available in Azure SQL Managed Instance and Azure SQL Database. Some features depend on the database's compatibility level.
<p>
To read more about IQP read this MS Learn article https://learn.microsoft.com/en-us/sql/relational-databases/performance/intelligent-query-processing?view=sql-server-ver16
<p>
To read about the new features that are a part of IQP read this MS Learn article https://learn.microsoft.com/en-us/sql/sql-server/what-s-new-in-sql-server-2022?view=sql-server-ver16#query-store-and-intelligent-query-processing

<p>
<p>
<h3>The Query Data Store </h3>
<p>
The Query Store feature provides you with insight on query plan choice and performance for SQL Server, Azure SQL Database, Azure SQL Managed Instance, and Azure Synapse Analytics. The Query Store simplifies performance troubleshooting by helping you quickly find performance differences caused by query plan changes. Query Store automatically captures a history of queries, plans, and runtime statistics, and retains these for your review. It separates data by time windows so you can see database usage patterns and understand when query plan changes.  To read more about the Query Data Store see this MS Learn article https://learn.microsoft.com/en-us/training/modules/explore-query-performance-optimization/5-explore-query-store


<p>

<p><img style="float: left; margin: 0px 15px 15px 0px;" src="https://github.com/microsoft/sqlworkshops/blob/master/graphics/point1.png?raw=true"><b>Activity: Learn about the Query Data Store</b></p>



<p><b>Description</b></p>

Learn about the Query Data Store

<p><img style="margin: 0px 15px 15px 0px;" src="https://github.com/microsoft/sqlworkshops/blob/master/graphics/checkmark.png?raw=true"><b>Steps</b></p>

Click on this <a href="https://learn.microsoft.com/en-us/training/modules/explore-query-performance-optimization/5-explore-query-store">link</a> and go to Unit 5 of the Explore query performance optimization Learn module and read about the Query Data Store (13 minutes) 





<p style="border-bottom: 1px solid lightgrey;"></p>

<h2 id="3.5"><img style="float: left; margin: 0px 15px 15px 0px;" src="https://github.com/microsoft/sqlworkshops/blob/master/graphics/pencil2.png?raw=true">3.5 Security</h2>

Over the past ten years, SQL Server has had fewer vulnerabilities than the <a href="https://nvd.nist.gov/">competition</a>. Building on this, the new ledger feature creates an immutable track record of data modifications over time. This protects data from tampering by malicious actors and is beneficial for scenarios such as internal and external audits.

SQL Server is integrated with Azure and brings the capabilities of Azure Defender where ever your SQL Server resides. 

<h4>Data Classification</h4>

<h4>Always Encrypted with Secure Enclaves</h4>


<h4>Ledger</h4>

<p><img style="margin: 0px 15px 15px 0px;" src="https://learn.microsoft.com/en-us/sql/relational-databases/security/ledger/media/ledger/ledger-table-architecture.png?view=sql-server-ver16">
</p>

Establishing trust around the integrity of data stored in database systems has been a longstanding problem for all organizations that manage financial, medical, or other sensitive data. The ledger feature provides tamper-evidence capabilities in your database. You can cryptographically attest to other parties, such as auditors or other business parties, that your data hasn't been tampered with.
<p>
To read more about how to use Ledger in SQL read this MS Learn article https://learn.microsoft.com/en-us/sql/relational-databases/security/ledger/ledger-overview?view=sql-server-ver16
<p>
To understand how to configure Ledger on a SQL Server read this MS Learn article https://learn.microsoft.com/en-us/sql/relational-databases/security/ledger/ledger-how-to-configure-ledger-database?view=sql-server-ver16&tabs=Portal&pivots=as1-sql-server


<h2 id="3.6"><img style="float: left; margin: 0px 15px 15px 0px;" src="https://github.com/microsoft/sqlworkshops/blob/master/graphics/pencil2.png?raw=true">3.6 Development</h2>

SQL Server continues to expand its T-SQL foot print to assist developers of all types.  New time series, JSON, aggregate, T-SQL, and Bit manipulation functions have all been added. 

To read more about each individual update read this MS Learn article https://learn.microsoft.com/en-us/sql/sql-server/what-s-new-in-sql-server-2022?view=sql-server-ver16#language

<p><img style="float: left; margin: 0px 15px 15px 0px;" src="https://github.com/microsoft/sqlworkshops/blob/master/graphics/point1.png?raw=true"><b>Activity: TODO: Activity Name</b></p>

Open the the GENERATE_SERIES MS Learn article and execute the demos (2 minutes)
https://learn.microsoft.com/en-us/sql/t-sql/functions/generate-series-transact-sql?view=sql-server-ver16

<p><b>Description</b></p>

TODO: Enter activity description with checkbox

<p><img style="margin: 0px 15px 15px 0px;" src="https://github.com/microsoft/sqlworkshops/blob/master/graphics/checkmark.png?raw=true"><b>Steps</b></p>

Open the the JSON_OBJECT MS Learn article and execute the demos (2 minutes)
https://learn.microsoft.com/en-us/sql/t-sql/functions/json-object-transact-sql?view=sql-server-ver16

<h2 id="3.7"><img style="float: left; margin: 0px 15px 15px 0px;" src="https://github.com/microsoft/sqlworkshops/blob/master/graphics/pencil2.png?raw=true">3.7 Analytics</h2>

Content


<p><img style="float: left; margin: 0px 15px 15px 0px;" src="https://github.com/microsoft/sqlworkshops/blob/master/graphics/point1.png?raw=true"><b>Activity: TODO: Activity Name</b></p>

<p><img style="margin: 0px 15px 15px 0px;" src="https://github.com/microsoft/sqlworkshops/blob/master/graphics/checkmark.png?raw=true"><b>Steps</b></p>

Open the the JSON_OBJECT MS Learn article and execute the demos (2 minutes)
https://learn.microsoft.com/en-us/sql/t-sql/functions/json-object-transact-sql?view=sql-server-ver16

<p></p>

<p><img style="float: left; margin: 0px 15px 15px 0px;" src="https://github.com/microsoft/sqlworkshops/blob/master/graphics/owl.png?raw=true"><b>For Further Study</b></p>
<br>
<ul>
    <li><a href="https://learn.microsoft.com/en-us/training/modules/introduction-sql-server-linux/" target="_blank">Introduction to SQL Server on Linux</a></li>
    <li><a href="https://learn.microsoft.com/en-us/training/modules/explore-query-performance-optimization/" target="_blank">Explore query performance optimization</a></li>
    <li><a href="https://learn.microsoft.com/en-us/training/modules/azure-security-center/" target="_blank">Enable and manage Microsoft Defender for Cloud</a></li>
    <li><a href="https://learn.microsoft.com/en-us/sql/relational-databases/security/ledger/ledger-overview?view=sql-server-ver16" target="_blank">Ledger overview</a></li>
    <li><a href="https://learn.microsoft.com/en-us/sql/database-engine/sql-server-business-continuity-dr?view=sql-server-ver16#sql-server-scenarios-using-the-availability-features" target="_blank">Business continuity and database recovery - SQL Server</a></li>
        <li><a href = "https://docs.microsoft.com/en-us/sql/samples/wide-world-importers-what-is?view=sql-server-2017" target="_blank">Official Documentation for this section - Wide World Importers Data Dictionary and company description</a></li>
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