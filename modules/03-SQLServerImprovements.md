![](https://github.com/microsoft/sqlworkshops/blob/master/graphics/microsoftlogo.png?raw=true)![](../graphics/microsoftlogo.png)

# Workshop: Modernizing Your Data Estate With SQL Ground-to-Cloud
#### <i>A Microsoft workshop from the SQL Server team</i>

<p style="border-bottom: 1px solid lightgrey;"></p>

<img style="float: left; margin: 0px 15px 15px 0px;" src="https://github.com/microsoft/sqlworkshops/blob/master/graphics/textbubble.png?raw=true"> <h2>03 - SQL Server Improvements</h2>

In this workshop you'll cover how to systematically create a modern data estate using SQL Server in on-premises, in-cloud and hybrid solutions. 

In each module you'll get more references, which you should follow up on to learn more. Also watch for links within the text - click on each one to explore that topic.

(<a href="file:///url" target="_blank">Make sure you check out the <b>Pre-Requisites</b> page before you start</a>. You'll need all of the items loaded there before you can proceed with the workshop.)

You'll cover these topics in the workshop:
<dl>

  <dt><a href="#3.1" target="_blank">3.1 - Deployment Options<dt></a>
  <dt><a href="#3.2" target="_blank">3.2 - Manageability<dt></a>
  <dt><a href="#3.3" target="_blank">3.3 - Availability<dt></a>
  <dt><a href="#3.4" target="_blank">3.4 - Performance<dt></a>
  <dt><a href="#3.5" target="_blank">3.5 - Security<dt></a>
  <dt><a href="#3.6" target="_blank">3.6 - Development<dt></a>

</dl>

SQL Server is a modern data platform designed to tackle the challenges of today's data professional. SQL Server is not just an upgrade option from previous releases of SQL Server.

The WideWorldImporters company has been evaluating upgrading several SQL Server 2008 instances along with some instances of SQL Server 2012, 2014, and even 2016. WideWorldImporters wants to know whether SQL Server 2022 will solve some of the challenges they face.

<p style="border-bottom: 1px solid lightgrey;"></p>

<h2 id="3.1"><img style="float: left; margin: 0px 15px 15px 0px;" src="https://github.com/microsoft/sqlworkshops/blob/master/graphics/pencil2.png?raw=true">3.1 Deployment Options</h2>

Since SQL Server 2017 users have had the option of deploying SQL Server on Windows and in Linux.  Current deployment scenarios include Windows, Linux, Docker containers, and Kubernetes. 

Regardless of the deployment scenario there are some key items to keep in mind.


<h3>SQL Server on Windows</h3>

The development teams have collaborated closely to ensure that the very best experience for data professionals emerges when you take advantage of the synergies built into the Windows Server OS and the SQL Server data platform.  

<p>

<h3>SQL Server Editions</h3>
Installation requirements vary based on your application needs. The different editions of SQL Server accommodate the unique performance, runtime, and price requirements of organizations and individuals. The SQL Server components that you install also depend on your specific requirements. The following sections help you understand how to make the best choice among the editions and components available in SQL Server.



<h2><img style="float: left; margin: 0px 15px 15px 0px;" src="https://github.com/microsoft/sqlworkshops/blob/master/graphics/point1.png?raw=true"><b>     Activity: Review SQL Server Editions Lab</a></b></h2>

In this activity, you will review the different editions of SQL Server.


<h3><img style="margin: 0px 15px 15px 0px;" src="https://github.com/microsoft/sqlworkshops/blob/master/graphics/checkmark.png?raw=true"><b>Activity Steps</b></h3>

To complete this activity, go to [https://learn.microsoft.com/en-us/sql/sql-server/editions-and-components-of-sql-server-2019?view=sql-server-ver16#-editions](https://learn.microsoft.com/en-us/sql/sql-server/editions-and-components-of-sql-server-2019?view=sql-server-ver16#-editions).

Review the Editions available for SQL Server.



<h3>SQL Server on Linux</h3>

SQL Server now runs on the Linux Platform.  It runs on the Red Hat, SUSE, Ubuntu, & Docker platform.  You can learn more about that architecture here https://learn.microsoft.com/en-us/sql/linux/sql-server-linux-overview?view=sql-server-ver16

<p>
Some reasons to consider SQL Server on Linux could be if your orginization is more familar with running Linux than Windows, command line installation on Linux platform, and quick deployments of non-production environments.

<h2><img style="float: left; margin: 0px 15px 15px 0px;" src="https://github.com/microsoft/sqlworkshops/blob/master/graphics/point1.png?raw=true"><b>     Activity: Review SQL Server on Linux Lab</a></b></h2>

In this activity, you will review the Introduction to SQL Server on Linux MS Learn Module, Unit 2.


<h3><img style="margin: 0px 15px 15px 0px;" src="https://github.com/microsoft/sqlworkshops/blob/master/graphics/checkmark.png?raw=true"><b>Activity Steps</b></h3>

To complete this activity, go to [https://learn.microsoft.com/en-us/training/modules/introduction-sql-server-linux/2-what-sql-server-linux
](https://learn.microsoft.com/en-us/training/modules/introduction-sql-server-linux/2-what-sql-server-linux
).

Review Unit 2 What is SQL Server on Linux? (5 minutes)




<h3>SQL Server in Containers</h3>

SQL Server runs in containers on the Docker platform. 

SQL Server 2022
- Regularly updated with CUs
- SQL server on Multipl OS containers: Red Hat, Ubuntu, Windows
- Machine Learning, Polybase, MSDTC, & Replication in Linux Containers

To understand how to deploy SQL Server to a Docker container see following Microsoft Learn article: https://learn.microsoft.com/en-us/sql/linux/quickstart-install-connect-docker?view=sql-server-ver16&pivots=cs1-powershell

<p>

<h3>SQL Server on Kubernetes</h3>

SQL Server containers can also be deployed to Kubernetes using Helm charts.  To understand how to deploy a container to Kubernetes see this Microsoft Learn article: https://learn.microsoft.com/en-us/sql/linux/sql-server-linux-containers-deploy-helm-charts-kubernetes?view=sql-server-ver16

<p>


<p style="border-bottom: 1px solid lightgrey;"></p>


<h2 id="3.2"><img style="float: left; margin: 0px 15px 15px 0px;" src="https://github.com/microsoft/sqlworkshops/blob/master/graphics/pencil2.png?raw=true">3.2 Manageability</h2>

Once we Deploy SQL Server how do we access it and manage it?  

<p height="10">

<h3>Tools</h3>
We have some key tools that you should understand how to use.  A quick note we will be talking about Azure Data Studio later in this course, for now we will  discuss SQL Server Management Studio & Copmmand-Line Utilities.


<p height="10">
<h4>SQL Server Management Studio</h4>
SQL Server Management Studio, SSMS, has been in use since 2005 and is a staple of any orginization with DBA's running SQL Server.
<p>
It is key understand <a href="https://learn.microsoft.com/en-us/sql/ssms/quickstarts/ssms-connect-query-sql-server?view=sql-server-ver16">how to connect to SSMS</a> to any SQL Server Instance.

<p>
SSMS can be used to <a href="https://learn.microsoft.com/en-us/sql/ssms/tutorials/scripting-ssms?view=sql-server-ver16">script out objects</a>, <a href="https://learn.microsoft.com/en-us/sql/relational-databases/import-export/import-flat-file-wizard?view=sql-server-ver16">import flat files</a>, and <a href="https://learn.microsoft.com/en-us/sql/ssms/tutorials/ssms-tricks?view=sql-server-ver16">we even have some tips and tricks documented</a>.
<p>
Additional actvities you can use SSMS to do:
<li>Write Queries
<li>View the AlwaysOn AG Dashboard
<li>View SQL Server Log Files
<li>Crete & Schedule SQL Agent Jobs
<li>Create Extended Events
<li>Generate and evaluate execution plans
<li>View Query Data Store Built In Reports

<p>
<p>
<h4>Command-Line Utilities</h4>
<p>
SQLCMD is an importiant tool because it allows you to connect to SQL Instances via a command-line utility in Windows or in Linux.  To learn more about installing sqlcmd go to the following MS Learn article <a href="https://learn.microsoft.com/en-us/sql/tools/sqlcmd-utility?view=sql-server-ver16#download-and-install-sqlcmd">https://learn.microsoft.com/en-us/sql/tools/sqlcmd-utility?view=sql-server-ver16#download-and-install-sqlcmd</a> . 

<p>
If your SQL Server installation is set up to support remote connects than you can use the dedicated adminstrative connect, DAC, with sqlcmd.  To learn more about how to connect to the DAC see this MS Learn article <a href="https://learn.microsoft.com/en-us/sql/database-engine/configure-windows/diagnostic-connection-for-database-administrators?view=sql-server-ver16#connect-with-dac">https://learn.microsoft.com/en-us/sql/database-engine/configure-windows/diagnostic-connection-for-database-administrators?view=sql-server-ver16#connect-with-dac</a>


SQL Server Management Studio: Tips & Tricks


<p><img style="float: left; margin: 0px 15px 15px 0px;" src="https://github.com/microsoft/sqlworkshops/blob/master/graphics/point1.png?raw=true"><b>Tips and Tricks for SSMS</b></p>

Go to the link provided and execute the scripts in the exercises

<p><b>Description</b></p>

Find some tips and tricks for working with SSMS

<p><img style="margin: 0px 15px 15px 0px;" src="https://github.com/microsoft/sqlworkshops/blob/master/graphics/checkmark.png?raw=true"><b>Steps</b></p>

Go to this <a href="https://learn.microsoft.com/en-us/sql/ssms/tutorials/ssms-tricks?view=sql-server-ver16">link</a>.  Copy code from the link and execute as instructed in SSMS.

<p style="border-bottom: 1px solid lightgrey;"></p>

<h2 id="3.3"><img style="float: left; margin: 0px 15px 15px 0px;" src="https://github.com/microsoft/sqlworkshops/blob/master/graphics/pencil2.png?raw=true">3.3 Availability</h2>

Once we have deployed and connected to our SQL Server instance we must have a conversation about Availability.  SQL Server has many capabilities to extend your availability.
<p>
There are some very importiant terms and concepts for us to cover.  High Availability, Disaster Recovery, & Business Continutiy. 
<p>
<b>High Availability</b>, HA, is the ability for your systems to recover from localized events in an automated way.
<p>
<b>Disaster Recovery</b>, DR, is the process of recoving from a diaster of some sort.  A natural or man-made disaster has occured and manual intervention may be required.  While some things can be automated, other items may require manual intervention.  
<p>
<b>Business Continuity</b> is the planning process for how businesses and their IT systems will react in the event of an outage.  This planning will typically be for DR, but it could also include HA planning. 

<h3>Always On</h3>
<img src="https://learn.microsoft.com/en-us/sql/database-engine/availability-groups/windows/media/aoag-agintrofigure.gif?view=sql-server-ver16">

<p>
Always On Availability Groups are a key capability used by customers when planning High Availability or Business Continuity process for SQL Server Instances.

To learn more about Always On Availability Groups read this MS Learn article https://learn.microsoft.com/en-us/sql/database-engine/availability-groups/windows/overview-of-always-on-availability-groups-sql-server?view=sql-server-ver16


<p>
<h3>Link to Azure SQL Managed Instance</h3>
<img src="https://learn.microsoft.com/en-us/azure/azure-sql/managed-instance/media/managed-instance-link-feature-overview/mi-link-ag-dag.png?view=azuresql">
<p>
The new link feature in Azure SQL Managed Instance connects your SQL Servers hosted anywhere to SQL Managed Instance, providing hybrid flexibility and database mobility. With an approach that uses near real-time data replication to the cloud, you can offload workloads to a read-only secondary in Azure to take advantage of Azure-only features, performance, and scale.

To learn more about Link to Azure SQL Managed Instance read this MS Learn article https://learn.microsoft.com/en-us/azure/azure-sql/managed-instance/managed-instance-link-feature-overview?view=azuresql

<p>

<p><img style="float: left; margin: 0px 15px 15px 0px;" src="https://github.com/microsoft/sqlworkshops/blob/master/graphics/point1.png?raw=true"><b>Activity: Understand how synchronization works on a secondary replica</b></p>



<p><b>Description</b></p>

Gain an understanding of how synchronization works on a secondary replica

<p><img style="margin: 0px 15px 15px 0px;" src="https://github.com/microsoft/sqlworkshops/blob/master/graphics/checkmark.png?raw=true"><b>Steps</b></p>

Click on this <a href="https://learn.microsoft.com/en-us/sql/database-engine/availability-groups/windows/availability-modes-always-on-availability-groups?view=sql-server-ver16#HowSyncWorks">link</a> and read How Synchronization Works on a Secondary Replica

<p style="border-bottom: 1px solid lightgrey;"></p>

<h2 id="3.4"><img style="float: left; margin: 0px 15px 15px 0px;" src="https://github.com/microsoft/sqlworkshops/blob/master/graphics/pencil2.png?raw=true">3.4 Performance</h2>

SQL Server is one of the most widely used Enterprise relational database platforms because of the high level of performance that can be achieved.  
<p>
Enhancements are made in SQL Server to imporve function over previous releases for more on these features read the following MS Learn article https://learn.microsoft.com/en-us/sql/sql-server/what-s-new-in-sql-server-2022?view=sql-server-ver16#performance
<p>

<h3>Intelligent Query Processing</h3>




<p><img src="https://learn.microsoft.com/en-us/sql/relational-databases/performance/media/iqp-feature-family.svg?view=sql-server-ver16">

<p>
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

<h3>Ledger</h3>

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


<p><img style="float: left; margin: 0px 15px 15px 0px;" src="https://github.com/microsoft/sqlworkshops/blob/master/graphics/owl.png?raw=true"><b>For Further Study</b></p>
<ul>
    <li><a href="https://learn.microsoft.com/en-us/training/modules/introduction-sql-server-linux/" target="_blank">Introduction to SQL Server on Linux</a></li>
    <li><a href="https://learn.microsoft.com/en-us/training/modules/explore-query-performance-optimization/" target="_blank">Explore query performance optimization</a></li>
    <li><a href="https://learn.microsoft.com/en-us/training/modules/azure-security-center/" target="_blank">Enable and manage Microsoft Defender for Cloud</a></li>
    <li><a href="https://learn.microsoft.com/en-us/sql/relational-databases/security/ledger/ledger-overview?view=sql-server-ver16" target="_blank">Ledger overview</a></li>
    <li><a href="https://learn.microsoft.com/en-us/sql/database-engine/sql-server-business-continuity-dr?view=sql-server-ver16#sql-server-scenarios-using-the-availability-features" target="_blank">Business continuity and database recovery - SQL Server</a></li>
</ul>


Next, continue on to [Module 04 - SQL Server on the Microsoft Azure Platform](https://github.com/sqlballs/mSQLg2c/blob/main/modules/04-ImprovementsInSQLOnTheMicrosoftAzurePlatform.md)


