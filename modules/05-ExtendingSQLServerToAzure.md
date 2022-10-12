![](https://github.com/microsoft/sqlworkshops/blob/master/graphics/microsoftlogo.png?raw=true)

# Workshop: Modernizing Your Data Estate With SQL Ground-to-Cloud
#### <i>A Microsoft workshop from the SQL Server team</i>

<p style="border-bottom: 1px solid lightgrey;"></p>

<img style="float: left; margin: 0px 15px 15px 0px;" src="https://github.com/microsoft/sqlworkshops/blob/master/graphics/textbubble.png?raw=true"> <h2>Extending SQL Server to Microsoft Azure</h2>

In this workshop you'll cover how to systematically create a modern data estate using SQL Server in on-premises, in-cloud and hybrid solutions. In each module you'll get more references, which you should follow up on to learn more. Also watch for links within the text - right-click each one and select "Open in New Tab" to explore that topic.

(<a href="https://github.com/sqlballs/mSQLg2c/blob/Buck/modules/01-SetupandWorkshopMethodology.md" target="_blank">Make sure you check out the <b>Pre-Requisites</b> page before you start</a>. You'll need all of the items loaded there before you can proceed with the workshop.)

You'll cover these topics in the workshop:
<dl>
  <dt><a href="#5.1" target="_blank">5.1 - Extending on-Premises SQL Server Instances to Microsoft Azure</a><dt>
  <dt><a href="#5.2" target="_blank">5.2 - Extending Microsoft Azure services to on-Premises environments</a><dt>
  <dt><a href="#5.3" target="_blank">5.3 - Migrating SQL Server Instances to the Microsoft Azure Platform</a><dt>
</dl>

<p style="border-bottom: 1px solid lightgrey;"></p>

<h2 id="5.1"><img style="float: left; margin: 0px 15px 15px 0px;" src="https://github.com/microsoft/sqlworkshops/blob/master/graphics/pencil2.png?raw=true">5.1 - Extending on-Premises SQL Server Instances to Microsoft Azure</h2>

In many cases you may find that staying on-premises for your SQL Server and other data processing systems is the correct architecture for at least part of your data estate. You may, however, still want to leverage a cloud service as part of your modernization. There are many options you can use to connect your SQL Server Instances to the Microsoft Azure platform, giving you advantages in disaster recovery, replication, security and other considerations for your architecture.

<h3>Backup/Restore to URL</h3>
One of the simplest methods you can use to extend your Data Estate to Microsoft Azure is to leverage the triple-redundant, secure, and geo-replicated storage as a backup location for your databases using the "Backup to URL" feature in SQL Server. 

Ater you <a href="https://learn.microsoft.com/en-us/sql/relational-databases/backup-restore/sql-server-backup-to-url?view=sql-server-ver16">set up a Shared Access Key, an example of that syntax</a> is here:
<pre>
BACKUP DATABASE AdventureWorks2012   
TO URL = 'https://<mystorageaccountname>.blob.core.windows.net/<mycontainername>/AdventureWorks2012.bak';  
GO
</pre>
<p></p>

You have two options for the storage types, a <a href="https://azure.microsoft.com/pricing/details/storage/page-blobs/">Page Blob</a> or a <a href="https://azure.microsoft.com/pricing/details/storage/blobs/">Block Blob</a>. In general, a Block Blob is less expensive and is preferrable for your database backups. You can <a href="https://learn.microsoft.com/en-us/sql/relational-databases/backup-restore/sql-server-backup-to-url?view=sql-server-ver16">learn more about that process at this reference</a>.
<p></p>
<img src="https://learn.microsoft.com/en-us/sql/relational-databases/backup-restore/media/backuptocloud-blobarchitecture.gif?view=sql-server-ver16" width=500>
<p></p>

> You can also use backups to Azure Storage in Azure SQL DB. You can <a href="https://learn.microsoft.com/en-us/azure/azure-sql/virtual-machines/windows/azure-storage-sql-server-backup-restore-use?view=azuresql">learn more about that process at this reference</a>.
<p></p>

Starting in SQL Server 2022, you can also use backup and restore to Object Stores, such as the S3 API. You can <a href="https://learn.microsoft.com/en-us/sql/relational-databases/backup-restore/sql-server-backup-and-restore-with-s3-compatible-object-storage?view=sql-server-ver16 ">learn more about that process at this reference</a>.

<h3>Use Microsoft Azure as a Disaster Recovery site</h3>
For a complete Disaster Recovery strategy at your organization, you should consider that the geographic location of your datacenter could be compromized, and even a comprehensive backup/restore strategy would not be sufficient to guarantee your Recovery Point Objective (RPO) and Recovery Time Objective (RTO). It's a best-practice to ensure that you have a separate location to fall back to for your organization's operations.
<p></p>
Microsoft Azure has a series of tools you can use for a more complete strategy for Disaster Recovery, starting with <i>Azure Site Recovery</i>.
<p></p>

<h4>Azure Site Recovery</h4>

Azure Site Recovery is a Microsoft Azure service</a> that replicates your workloads running on physical and virtual machines (VMs) from a primary site to a secondary location in the Azure platform that you choose. When an outage occurs at your primary site, you fail over to a secondary location, and access apps from there. After the primary location is running again, you can fail back to it.
 
 You can find an <a href="https://infrastructuremap.microsoft.com/explore">interactive globe with more information for those locations at this reference,</a> along with a tour of a Microsoft datacenter.

<p></p>
<img src="https://learn.microsoft.com/en-us/azure/site-recovery/media/physical-azure-architecture/arch-enhanced.png" width=500>
<p></p>

You can <a href="https://learn.microsoft.com/en-us/sql/relational-databases/backup-restore/sql-server-backup-and-restore-with-s3-compatible-object-storage?view=sql-server-ver16 ">learn more about Azure Site Recovery at this reference</a>.

<b>Use Azure resources as part of an Always On Availability Group</b>

The Always On availability groups feature is a high-availability and disaster-recovery (HA/DR) solution that maximize the availability of a set of user databases. An availability group supports a failover environment for a discrete set of user databases, known as <i>availability databases</i>, that fail over together. An availability group supports a set of read-write primary databases and sets of corresponding secondary databases. The secondary databases can be made available for read-only access and/or some backup operations. An availability group fails over at the level of an availability replica. Failovers are not caused by database issues such as a database becoming suspect due to a loss of a data file, deletion of a database, or corruption of a transaction log.
<p></p>
Originally introduced for on-premises SQL Server Instances, the Always On Availability Group feature now extends to Microsoft Azure. 

<p></p>
<img src="https://learn.microsoft.com/en-us/azure/azure-sql/virtual-machines/windows/media/availability-group-overview/00-endstatesamplenoelb.png?view=azuresql" width=500>
<p></p>

You can <a href="https://learn.microsoft.com/en-us/azure/azure-sql/virtual-machines/windows/availability-group-overview?view=azuresql">learn more about Always On Availability Groups in Microsoft Azure at this reference</a>.

<h4>Use Azure resources in a Failover Cluster</h4>
Like the Always On Availability Group feature, Failover Clustering was originally introduced for on-premises SQL Server Instances, and leverages Windows Server Failover Clustering (WSFC) to provide high availability through redundancy at the server-instance level, called a <i>failover cluster instance</i> (FCI). An FCI is a single instance of SQL Server that is installed across Windows Server Failover Clustering (WSFC) nodes. An FCI appears to be an instance of SQL Server running on a single computer, but the FCI provides failover from one WSFC node to another if the current node becomes unavailable. This feature is now enhanced to allow the Microsoft Azure platform to provide nodes and networks as part of the FCI infrastre. An FCI can also leverage Availability Groups to provide remote disaster recovery at the database level.

<p></p>
<img src="https://learn.microsoft.com/en-us/sql/sql-server/failover-clusters/windows/media/alwaysoncomponentcontextdiagram.gif?view=sql-server-ver16" width=500>
<p></p>

You can <a href="https://learn.microsoft.com/en-us/azure/azure-sql/virtual-machines/windows/failover-cluster-instance-overview?view=azuresql">learn more about FCI using Microsoft Azure at this reference</a>.

<h4>Link for Managed Instance feature</h4>
The Link feature for SQL Server Managed Instance allows a connection between a SQL Server Instance and the fully managed PaaS service Azure SQL Managed InstanceIt uses near real-time data replication to Azure using Always On technology so that you can offload workloads to read-only secondaries on Azure to take advantage of a fully managed database platform, performance, and scale. The link can be operated for as long as you need it. 

The Primary database on a SQL Server Instance can be used for read/write operations and the replicated database on the Managed Instance can be used for read access. Changes to the primary database in SQL Server are transferred near real-time to the secondary Managed Instance in Azure.

Each link is database-scoped, meaning that one link connects a single database. You can use multiple links to connect multiple databases. Through making the link database scoped, it is now possible to consolidate and deconsolidate your workloads in many-to-many relationships between SQL Server and Managed Instance. This allows you to replicate data from multiple SQL Servers to a single Managed Instance in Azure, or replicate from a single SQL Server to multiple Managed Instances to any of Azure’s 60+ regions worldwide.

<p></p>
<img src="https://techcommunity.microsoft.com/t5/image/serverpage/image-id/323023i2A489D1FF2149CF9/image-dimensions/777x369?v=v2" width=500>
<p></p>

You can <a href="https://learn.microsoft.com/en-us/azure/azure-sql/managed-instance/managed-instance-link-preparation?view=azuresql">learn more about Managed Instance Link at this reference</a>.

<h4>Use Azure Resources as a Log Shipping or Replication target</h4>
SQL Server Log shipping allows you to automatically send all transaction log backups from a primary database on a primary server Instance to one or more secondary databases on separate secondary server Instances. The transaction log backups are applied to each of the secondary databases individually. An optional third server Instance, known as the monitor server, records the history and status of backup and restore operations and, optionally, raises alerts if these operations fail to occur as scheduled. You can use Log shipping to a Microsoft Azure Virtual Machine running SQL Server.

<p></p>
<img src="https://learn.microsoft.com/en-us/sql/database-engine/log-shipping/media/ls-typical-configuration.gif?view=sql-server-ver16" width=400>
<p></p>

You can <a href="https://learn.microsoft.com/en-us/sql/database-engine/log-shipping/about-log-shipping-sql-server?view=sql-server-ver16">learn more about Log Shipping at this reference</a>.

<b>Microsoft SQL Server Replication</b> is a publisher-subscriber model allowing you to replicate data from a database, but also from a query or other more specific data set. Microsoft Azure VM's or Azure SQL DB can be used as a target for one or more subscribers from your on-premises systems.

<p></p>
<img src="https://learn.microsoft.com/en-us/azure/azure-sql/database/media/replication-to-sql-database/replication-to-sql-database.png?view=azuresql" width=600>
<p></p>

You can <a href="https://learn.microsoft.com/en-us/azure/azure-sql/database/replication-to-sql-database?view=azuresql">learn more about SQL Server Replication to Azure at this reference</a>.

<p><img style="float: left; margin: 0px 15px 15px 0px;" src="https://github.com/microsoft/sqlworkshops/blob/master/graphics/point1.png?raw=true"><b>Activity: Review the Azure Site Recovery Tutorial</b></p>

In this Activity you will review the Tutorial provided for Azure Site Recovery. You can bookmark this reference to do both courses on your own schedule later.

<p><img style="margin: 0px 15px 15px 0px;" src="https://github.com/microsoft/sqlworkshops/blob/master/graphics/checkmark.png?raw=true"><b>Steps</b></p>

- Open <a href="https://learn.microsoft.com/en-us/azure/site-recovery/physical-azure-disaster-Recovery">this reference and review the Tutorial you see there</a>.

<p style="border-bottom: 1px solid lightgrey;"></p>

<h3>Data Virtualization</h3>
SQL Server has long had the ability to query data outside of a specific database. Cross-database queries, Linked Servers, and Open Database Connectivity (ODBC) data sources are all available from all currently supported versions.
<p></p>
Starting in SQL Server 2019, new methods and capabilities have been added to allow you to have a single language, security model, and query mechanism to allow SQL Server to become a "Data Hub", even without ingesting the data. Two of these changes are improvements to the ODBC function, and the <i>EXTERNAL DATA SOURCE</i> T-SQL statement.
<p></p>

<b>ODBC</b>
https://learn.microsoft.com/en-us/sql/relational-databases/polybase/data-virtualization?view=sql-server-ver16 
<p></p>

<b>PolyBase and EXTERNAL DATA</b>
https://learn.microsoft.com/en-us/sql/relational-databases/polybase/polybase-guide?view=sql-server-ver16
https://learn.microsoft.com/en-us/sql/t-sql/statements/create-external-data-source-transact-sql?view=sql-server-ver16&tabs=dedicated 

<h3>Linked Server</h3>
https://learn.microsoft.com/en-us/sql/relational-databases/linked-servers/create-linked-servers-sql-server-database-engine?view=sql-server-ver16 

<h3>Azure Data Sync</h3>
Between Instance and SQL DB 

https://learn.microsoft.com/en-us/azure/azure-sql/database/sql-data-sync-data-sql-server-sql-database?view=azuresql 

<h3>Azure Key Vault</h3> 
EKM - Always Encrypted
https://learn.microsoft.com/en-us/sql/relational-databases/security/encryption/extensible-key-management-using-azure-key-vault-sql-server?view=sql-server-ver16 

<h3>Synapse Link</h3> 
A very eye-opening chart. 
https://www.businessinsider.com/top-ceos-make-399-times-more-than-workers-2022-10 

<p><img style="float: left; margin: 0px 15px 15px 0px;" src="https://github.com/microsoft/sqlworkshops/blob/master/graphics/point1.png?raw=true"><b>Activity: TODO: Activity Name</b></p>

TODO: Activity Description and tasks

<p><b>Description</b></p>

TODO: Enter activity description with checkbox

<p><img style="margin: 0px 15px 15px 0px;" src="https://github.com/microsoft/sqlworkshops/blob/master/graphics/checkmark.png?raw=true"><b>Steps</b></p>

TODO: Enter activity steps description with checkbox

<p style="border-bottom: 1px solid lightgrey;"></p>

<h2 id="5.2"><img style="float: left; margin: 0px 15px 15px 0px;" src="https://github.com/microsoft/sqlworkshops/blob/master/graphics/pencil2.png?raw=true">5.2 - Extending Microsoft Azure services to on-Premises environments</h2>

In some cases you will want to leverage cloud services in your on-premises environment. This can be as little as inventoring your Instances, up to using a security platform that is always up to date, all the way to a completely managed Instance of SQL Server, residing not only in your on-premises data center, but even other cloud providers.

<h3>Microsoft Defender, Microsoft SQL Defender, and Advanced Threat Protection</h3>
https://learn.microsoft.com/en-us/azure/defender-for-cloud/defender-for-sql-usage 


<h3>Data Catalog and Governance with Microsoft Purview</h3>
https://cloudblogs.microsoft.com/sqlserver/2022/08/11/microsoft-purview-access-policies-for-sql-server-2022/ 
https://learn.microsoft.com/en-us/azure/purview/tutorial-register-scan-on-premises-sql-server 

<h3>Azure Arc and SQL Server</h3>
https://learn.microsoft.com/en-us/sql/sql-server/azure-arc/overview?view=sql-server-ver16 

<h3>Connect with Azure Active Directory</h3>
https://learn.microsoft.com/en-us/sql/relational-databases/security/authentication-access/azure-ad-authentication-sql-server-overview?view=sql-server-ver16

<p><img style="float: left; margin: 0px 15px 15px 0px;" src="https://github.com/microsoft/sqlworkshops/blob/master/graphics/point1.png?raw=true"><b>Activity: TODO: Activity Name</b></p>

TODO: Activity Description and tasks

<p><img style="margin: 0px 15px 15px 0px;" src="https://github.com/microsoft/sqlworkshops/blob/master/graphics/checkmark.png?raw=true"><b>Description</b></p>

TODO: Enter activity description with checkbox

<p><img style="margin: 0px 15px 15px 0px;" src="https://github.com/microsoft/sqlworkshops/blob/master/graphics/checkmark.png?raw=true"><b>Steps</b></p>

TODO: Enter activity steps description with checkbox

<h2 id="5.3"><img style="float: left; margin: 0px 15px 15px 0px;" src="https://github.com/microsoft/sqlworkshops/blob/master/graphics/pencil2.png?raw=true">5.3 - Migrating SQL Server Instances to the Microsoft Azure Platform</h2>

https://learn.microsoft.com/en-us/dotnet/azure/migration/sql

Offline or Online
RPO/RTO
App versioning - very important

Database - scripts and tools and Agents, etc. Planning is essential. AG planning. MI very handy here. 
Tools will do SKU reco

BU/Res
Online = tooling


Link for MI

Pay attention to versions

TODO: Topic Description
<h4>Azure Data Studio Migration Extension</h4>
https://docs.microsoft.com/en-us/sql/azure-data-studio/extensions/azure-sql-migration-extension?view=sql-server-ver15 

<img src="https://user-images.githubusercontent.com/517325/189189647-bb1e5857-3ba4-416f-987e-c68812587d47.png" alt="Graphic" width="600">

<h4>Azure Database Migration Service</h4>
https://docs.microsoft.com/en-us/azure/dms/
<br>

<img src="https://user-images.githubusercontent.com/517325/189189527-3554ff5b-0f0c-4ef1-8164-51bf74f2af2a.png" alt="Graphic" width="600">

<h4>Azure Migrate</h4>
https://docs.microsoft.com/en-us/azure/migrate/
<br>
<img src="https://user-images.githubusercontent.com/517325/189189693-c88cf4c0-90f4-45b0-91bb-8993796593ee.png" alt="Graphic" width="600">

    
    
<p style="border-bottom: 1px solid lightgrey;"></p>

<p><img style="float: left; margin: 0px 15px 15px 0px;" src="https://github.com/microsoft/sqlworkshops/blob/master/graphics/owl.png?raw=true"><b>For Further Study</b></p>
<ul>
    <li><a href="url" target="_blank">TODO: Enter courses, books, posts, whatever the student needs to extend their study</a></li>
</ul>

Congratulations! You have completed this workshop on Modernizing Your Data Estate With SQL Ground-to-Cloud. You now have the tools, assets, and processes you need to extrapolate this information into other applications.
