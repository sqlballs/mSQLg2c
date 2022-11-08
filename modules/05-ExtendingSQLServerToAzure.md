![](https://github.com/microsoft/sqlworkshops/blob/master/graphics/microsoftlogo.png?raw=true)

# Workshop: Modernizing Your Data Estate With SQL Ground-to-Cloud
#### <i>A Microsoft workshop from the SQL Server team</i>

<p style="border-bottom: 1px solid lightgrey;"></p>

<img style="float: left; margin: 0px 15px 15px 0px;" src="https://github.com/microsoft/sqlworkshops/blob/master/graphics/textbubble.png?raw=true"> <h2>05 - Extending SQL Server to Microsoft Azure</h2>

In this workshop you'll cover how to systematically create a modern data estate using SQL Server in on-premises, in-cloud and hybrid solutions. In each module you'll get more references, which you should follow up on to learn more. Also watch for links within the text - right-click each one and select "Open in New Tab" to explore that topic.

(<a href="https://github.com/sqlballs/mSQLg2c/blob/main/modules/01-SetupandWorkshopMethodology.md" target="_blank">Make sure you check out the <b>Pre-Requisites</b> page before you start</a>. You'll need all of the items loaded there before you can proceed with the workshop.)

You'll cover these topics in the workshop:
<dl>
  <dt><a href="#5.1" target="_blank">5.1 - Extending on-Premises SQL Server Instances to Microsoft Azure</a></dt>
  <dt><a href="#5.2" target="_blank">5.2 - Extending Microsoft Azure services to on-Premises environments</a></dt>
  <dt><a href="#5.3" target="_blank">5.3 - Migrating SQL Server Instances to the Microsoft Azure Platform</a></dt>
</dl>

<p style="border-bottom: 1px solid lightgrey;"></p>

<h2 id="5.1"><img style="float: left; margin: 0px 15px 15px 0px;" src="https://github.com/microsoft/sqlworkshops/blob/master/graphics/pencil2.png?raw=true">5.1 - Extending on-Premises SQL Server Instances to Microsoft Azure</h2>

In many cases you may find that staying on-premises for your SQL Server and other data processing systems is the correct architecture for at least part of your data estate. You may, however, still want to leverage a cloud service as part of your modernization. There are many options you can use to connect your SQL Server Instances to the Microsoft Azure platform, giving you advantages in disaster recovery, replication, security and other considerations for your architecture.

<h4>Backup/Restore to URL</h4>
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

<h4>Use Microsoft Azure as a Disaster Recovery site</h4>
For a complete Disaster Recovery strategy at your organization, you should consider that the geographic location of your datacenter could be compromised, and even a comprehensive backup/restore strategy would not be sufficient to guarantee your Recovery Point Objective (RPO) and Recovery Time Objective (RTO). It's a best-practice to ensure that you have a separate location to fall back to for your organization's operations.
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
Like the Always On Availability Group feature, Failover Clustering was originally introduced for on-premises SQL Server Instances, and leverages Windows Server Failover Clustering (WSFC) to provide high availability through redundancy at the server-Instance level, called a <i>failover cluster Instance</i> (FCI). An FCI is a single Instance of SQL Server that is installed across Windows Server Failover Clustering (WSFC) nodes. An FCI appears to be an Instance of SQL Server running on a single computer, but the FCI provides failover from one WSFC node to another if the current node becomes unavailable. This feature is now enhanced to allow the Microsoft Azure platform to provide nodes and networks as part of the FCI infrastructure. An FCI can also leverage Availability Groups to provide remote disaster recovery at the database level.

<p></p>
<img src="https://learn.microsoft.com/en-us/sql/sql-server/failover-clusters/windows/media/alwaysoncomponentcontextdiagram.gif?view=sql-server-ver16" width=500>
<p></p>

You can <a href="https://learn.microsoft.com/en-us/azure/azure-sql/virtual-machines/windows/failover-cluster-Instance-overview?view=azuresql">learn more about FCI using Microsoft Azure at this reference</a>.

<h4>Link for Managed Instance feature</h4>
The Link feature for SQL Server Managed Instance allows a connection between a SQL Server Instance and the fully managed PaaS service Azure SQL Managed InstanceIt uses near real-time data replication to Azure using Always On technology so that you can offload workloads to read-only secondaries on Azure to take advantage of a fully managed database platform, performance, and scale. The link can be operated for as long as you need it. 

The Primary database on a SQL Server Instance can be used for read/write operations and the replicated database on the Managed Instance can be used for read access. Changes to the primary database in SQL Server are transferred near real-time to the secondary Managed Instance in Azure.

Each link is database-scoped, meaning that one link connects a single database. You can use multiple links to connect multiple databases. Through making the link database scoped, it is now possible to consolidate and deconsolidate your workloads in many-to-many relationships between SQL Server and Managed Instance. This allows you to replicate data from multiple SQL Servers to a single Managed Instance in Azure, or replicate from a single SQL Server to multiple Managed Instances to any of Azure’s 60+ regions worldwide.

<p></p>
<img src="https://techcommunity.microsoft.com/t5/image/serverpage/image-id/323023i2A489D1FF2149CF9/image-dimensions/777x369?v=v2" width=500>
<p></p>

You can <a href="https://learn.microsoft.com/en-us/azure/azure-sql/managed-Instance/managed-Instance-link-preparation?view=azuresql">learn more about Managed Instance Link at this reference</a>.

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

<h4>Data Virtualization</h4>
SQL Server has long had the ability to query data outside of a specific database. Cross-database queries, Linked Servers, and Open Database Connectivity (ODBC) data sources are all available from all currently supported versions.
<p></p>
Starting in SQL Server 2019, new methods and capabilities have been added to allow you to have a single language, security model, and query mechanism to allow SQL Server to become a "Data Hub", even without ingesting the data. Two of these changes are improvements to the ODBC function, and the <i>EXTERNAL DATA SOURCE</i> T-SQL statement.
<p></p>

<b>ODBC</b>
Open Database Connectivity (ODBC) is a driver system application programming interface (API) for accessing data. Depending on the source and target software using the driver, ODBC provides a translation layer for data. Data targets can be anything from a text file to Microsoft Excel spreadsheets, other Relational Database Management Systems (RDBMS) such as SQL Server or Oracle, and dozens of other sources. 

The latest versions of SQL Server make use of an ODBC connection directly within code using a connection string, or using the EXTERNAL DATA SOURCE commands. You can learn more about <a href="https://learn.microsoft.com/en-us/sql/integration-services/connection-manager/odbc-connection-manager?view=sql-server-ver16">accessing data in other systems using ODBC at this reference</a>. 

> A third-party company called <a href="https://www.cdata.com/odbc/">CDATA has created dozens of ODBC drivers which can greatly expand your data access within SQL Server</a>.

You can <a href="https://learn.microsoft.com/en-us/sql/relational-databases/polybase/data-virtualization?view=sql-server-ver16">learn more about creating an External table with a wizard in the tools for SQL Server at this reference</a>.

<b>PolyBase and EXTERNAL DATA</b>
PolyBase is a feature that enables you to query data with T-SQL in your current Instance from sources such as SQL Server, Oracle, Teradata, MongoDB, Hadoop clusters, Cosmos DB, and S3-compatible object storage. You do not have to install client connection software for these systems. You can also use an ODBC connector to query additional providers. PolyBase allows your T-SQL queries to join the data from external sources to relational tables stored in an Instance of SQL Server.

One key use-case for data virtualization with the PolyBase feature is to allow the data to stay in its original location and format. You can virtualize the external data through the SQL Server Instance, so that it can be queried in place like any other table in SQL Server.

You can <a href="https://learn.microsoft.com/en-us/sql/relational-databases/polybase/polybase-guide?view=sql-server-ver16">learn more about PolyBase in for SQL Server at this reference</a>.

To use PolyBase, you need to set up a network connection between the source and your SQL Server Instance, provide any credentials, set a format for the data (if required) and then create an External Table to the source. You can <a href="https://learn.microsoft.com/en-us/sql/relational-databases/polybase/polybase-t-sql-objects?source=recommendations&view=sql-server-ver16">learn more about that process and the T-SQL commands used at this reference</a>.

<h4>Linked Servers</h4>
The Linked Servers feature enables SQL Server to execute a Transact-SQL statement that references tables in another Instance of SQL Server or other specific database engines such as Oracle. Many types of data sources can be configured as linked servers, including third-party database providers and Azure Cosmos DB. After a linked server is created, distributed queries can be run against this server, and queries can join tables from more than one data source. If the linked server is defined as an Instance of SQL Server or an Azure SQL Managed Instance, you can also execute remote stored procedures. The capabilities and required arguments of the linked server can vary significantly, based on the target you are connecting to.
<p></p>

> Linked Servers can have significant security and performance implications, and you should carefully review the documentation below prior to implementing them.

<p></p>
<img src="https://learn.microsoft.com/en-us/sql/relational-databases/linked-servers/media/lsvr.gif?view=sql-server-ver16" width=400>
<p></p>

You can <a href="https://learn.microsoft.com/en-us/sql/relational-databases/linked-servers/linked-servers-database-engine?view=sql-server-ver16">learn more about the Linked Servers feature at this reference</a>.

<h4>Azure Data Sync</h4>
Another connection mechanism between a SQL Server Instance and Azure SQL Database is Azure Data Sync.  SQL Data Sync is a Microsoft Azure service that can synchronize data bi-directionally  - across multiple databases, both on-premises and in the cloud.

<p></p>
<img src="https://learn.microsoft.com/en-us/azure/azure-sql/database/media/sql-data-sync-data-sql-server-sql-database/sync-data-overview.png?view=azuresql" width=500>
<p></p>

You can <a href="https://learn.microsoft.com/en-us/azure/azure-sql/database/sql-data-sync-data-sql-server-sql-database?view=azuresql">learn more about the Linked Servers feature at this reference</a>.

<h4>Azure Key Vault</h4> 
Keys are used throughout a Data Estate, inside and outside SQL Server for purposes as varied as database backups and connections to other systems. SQL Server has various keys it uses from a Service Master Key (SMK) to a Database Master Key (DBMK). Those keys, in turn, should be protected outside of the system to prevent high-level compromise. The system that allows this separation of protection is called <i>Extensible Key Management</i> (EKM). 

The EKM system with the latest versions of SQL Server can leverage the Azure Key Vault, an Azure service that provides high-grade protection of secrets and allows separation of duties.  

<p></p>
<img src="https://learn.microsoft.com/en-us/sql/relational-databases/security/encryption/media/ekm-key-hierarchy-traditional.png?view=sql-server-ver16" width=400>
<p></p>

You can <a href="https://learn.microsoft.com/en-us/sql/relational-databases/security/encryption/extensible-key-management-using-azure-key-vault-sql-server?view=sql-server-ver16">learn more about using Azure Key Vault with SQL Server at this reference</a>.

<h4>Synapse Link</h4> 
Setting up a <i>link connection</i> maps a connection between SQL Server and an Azure Synapse Analytics dedicated SQL pool. You can use the Synapse Portal to create, manage, monitor and delete link connections in your Synapse workspace. This allows the operational data from your source database to be automatically replicated to the destination Synapse dedicated SQL pool. This gives you near-real time analytics from ground to cloud.

<p></p>
<img src="https://learn.microsoft.com/en-us/azure/synapse-analytics/media/sql-synapse-link-overview/synapse-link-sql-architecture.png" width=400>
<p></p>

You can <a href="https://learn.microsoft.com/en-us/azure/synapse-analytics/synapse-link/sql-server-2022-synapse-link">learn more about using SQL Server Synapse Link at this reference</a>.

<p><img style="float: left; margin: 0px 15px 15px 0px;" src="https://github.com/microsoft/sqlworkshops/blob/master/graphics/point1.png?raw=true"><b>Activity: Detail Ground-to-Cloud features of Interest</b></p>

In this Activity, you will continue your notes from the first Activity, and record any areas of interest for follow-up study.

<p><img style="margin: 0px 15px 15px 0px;" src="https://github.com/microsoft/sqlworkshops/blob/master/graphics/checkmark.png?raw=true"><b>Steps</b></p>

- Using the notes you made in the first Activity, record any of the features that work from a SQL Server Instance to the Microsoft Azure platform that you think might assist your organization in their Data Estate. Make note of the resources in this section for follow-up study on those features. 

<p style="border-bottom: 1px solid lightgrey;"></p>

<h2 id="5.2"><img style="float: left; margin: 0px 15px 15px 0px;" src="https://github.com/microsoft/sqlworkshops/blob/master/graphics/pencil2.png?raw=true">5.2 - Extending Microsoft Azure services to on-Premises environments</h2>

In some cases you will want to leverage cloud services in your on-premises environment. This can be as little as creating an inventory of your Instances, up to using a security platform that is always up to date, all the way to a completely managed Instance of SQL Server, residing not only in your on-premises data center, but even other cloud providers.

<h4>Microsoft Defender, Microsoft SQL Defender, and Advanced Threat Protection</h4>
Computing security, and in specific data security, is essential in any organization. However, keeping on top of methods and processes to secure computing and data security elements, along with keeping up with threats and mitigations is very difficult and time-consuming. As covered in an earlier Module, SQL Server Management Studio (SSMS) has a built-in vulnerability scanner, and there are also older tools you can use to detect issues and protect your servers.

<p></p>
A better solution is a dedicated service that is kept up-to-date in a central location, where the latest protections and detections are stored and updated constantly. Microsoft Azure Defender has a full set of features that extend the power of the protections and monitoring offered in Azure to your on-premises systems.  

<p></p>
Microsoft Defender for SQL servers on machines extends the protections for your Azure-native SQL Servers to fully support hybrid environments and protect SQL servers (all supported version) hosted in Azure, other cloud environments, and even on-premises machines.

<p></p>
<img style="margin: 0px 15px 15px 0px;" src="https://learn.microsoft.com/en-us/azure/defender-for-cloud/media/security-center-advanced-iaas-data/data-and-storage-sqldb-vulns-on-vm.png" width=800>
<p></p>

Microsoft Defender for SQL Servers on machines provides protection support for hybrid environments, and protects SQL Server Instances (all supported version) hosted in Azure, other cloud environments, and even on-premises machines. The integrated vulnerability assessment scanner discovers, tracks, and helps you remediate potential database vulnerabilities. Assessment scans findings provide an overview of your SQL machines' security state, and details of any security findings.

> Scans are lightweight, safe, and normally only takes a few seconds per database to run. They are entirely read-only. Scans do not make any changes to your database.

<p></p>
<img style="margin: 0px 15px 15px 0px;" src="https://learn.microsoft.com/en-us/azure/defender-for-cloud/media/defender-for-sql-on-machines-vulnerability-assessment/sql-vulnerability-findings.png" width=800>
<p></p>

You can <a href="https://learn.microsoft.com/en-us/azure/defender-for-cloud/defender-for-sql-introduction">learn more about Microsoft Defender for SQL at this reference</a>, and you can <a href="https://learn.microsoft.com/en-us/azure/defender-for-cloud/defender-for-sql-usage">find the steps for implementing the service on your Instances at this reference</a>.

<p><img style="float: left; margin: 0px 15px 15px 0px;" src="https://github.com/microsoft/sqlworkshops/blob/master/graphics/point1.png?raw=true"><b>Activity: Review a Deployment of Microsoft Defender</b></p>

In this Activity, you will review a section of the <i>Deployment of Microsoft Defender</i> training series. 

<p><img style="margin: 0px 15px 15px 0px;" src="https://github.com/microsoft/sqlworkshops/blob/master/graphics/checkmark.png?raw=true"><b>Steps</b></p>

- Open <a href="https://learn.microsoft.com/en-us/training/modules/azure-security-center/3-implement-azure-security-center">this reference for the training module called Implement Microsoft Defender for Cloud</a>, and continue through the Module called <a href="https://learn.microsoft.com/en-us/training/modules/azure-security-center/7-azure-defender">Deploy Microsoft Defender for Cloud</a>.
- Bookmark these pages if you would like to return and complete the entire training plan. 

<p style="border-bottom: 1px solid lightgrey;"></p>

<h4>Data Governance with Microsoft Purview</h4>
In the first Module you learned how to create a Data Catalog with Microsoft Purview. You can also govern your on-premises latest version SQL Server Instances with Purview Policies. 
<p></p>
Purview Policies allow you to define a range of SQL Server Instances, set up Policies for access (such as Read, Write and so on), and then publish the policies down to the Instances. The latest version of SQL Server is instrumented to accept these policies and handle the Data Control Language (DCL) T-SQL Statements to apply the applicable permissions and user logins to the Instance. 
<p></p> 

You can <a href="https://cloudblogs.microsoft.com/sqlserver/2022/08/11/microsoft-purview-access-policies-for-sql-server-2022/">learn more about Microsoft Purview Policies for SQL at this reference</a>.

<h4>Azure Arc and SQL Server</h4>
Microsoft Azure Arc is a set of technologies that allow you to manage your entire environment together by projecting your existing non-Azure and/or on-premises resources into Azure Resource Manager. It can help you manage virtual machines, Kubernetes clusters, and databases as if they are running in Azure, using familiar Azure services and management capabilities, regardless of where they live. Azure Arc technologies allow you to continue using traditional ITOps while introducing DevOps practices to support new cloud native patterns in your environment, configure custom locations as an abstraction layer on top of Azure Arc-enabled Kubernetes clusters and cluster extensions.
<p></p>
Azure Arc allows you to manage various resources hosted outside of Azure including Servers, Kubernetes clusters, Azure data services such as SQL Managed Instance and PostgreSQL server, SQL Server Instances, and Virtual machines.

<p></p>
<img style="margin: 0px 15px 15px 0px;" src="https://learn.microsoft.com/en-us/azure/azure-arc/media/overview/azure-arc-control-plane.png" width=800>
<p></p>

You can <a href="https://learn.microsoft.com/en-us/azure/azure-arc/overview">learn more about Microsoft Azure Arc at this reference</a>.

There are two Azure Arc implementations that allow you to extend various Microsoft Azure resources to your on-premises environment.

<b>Microsoft Azure Arc-enabled SQL Server</b>
The first method you can use to extend Microsoft Azure resources to your environment is Microsoft Azure Arc-enabled SQL Server. This deployment method allows you to use monitoring, security, and inventory systems in Microsoft Azure on your local SQL Servers. 

To enable Azure services, you <i>onboard</i> a  SQL Server Instance to Azure Arc. The onboarding process installs an Azure extension for SQL Server to the Connected Machine agent, which in turn will create an Azure resource for each SQL Server Instance.

You can <a href="https://learn.microsoft.com/en-us/sql/sql-server/azure-arc/overview?view=sql-server-ver16">learn more about Microsoft Azure Arc-enabled SQL Server at this reference</a>.

<b>Microsoft Azure Arc-enabled data services</b>
Azure Arc-enabled data services uses your Kubernetes environment to run SQL managed Instance and PostgreSQL server. They will automatically receive updates on a frequent basis including servicing patches and new features similar to the experience in Azure. Updates from the Microsoft Container Registry are provided to you and deployment cadences are set by you in accordance with your policies. You also get elasticity for your on-premises systems which enables you to scale databases up or down dynamically in much the same way as they do in Azure, based on the available capacity of your infrastructure. 

Azure Arc also provides other cloud benefits such as fast deployment and automation at scale. You can deploy a database in seconds using either GUI or CLI tools. It also allows you to use familiar tools such as the Azure portal, Azure Data Studio, and the Azure CLI to get a unified view of all your data assets deployed with Azure Arc. You also get logs and telemetry from Kubernetes APIs to analyze the underlying infrastructure capacity and health. Besides having localized log analytics and performance monitoring, you can now leverage Azure Monitor for comprehensive operational insights across your entire estate.

You can <a href="https://learn.microsoft.com/en-us/azure/azure-arc/data/overview">learn more about Microsoft Azure Arc-enabled SQL Server at this reference</a>.

You can try these scenarios using the <a href="https://azurearcjumpstart.io/overview/"> Azure Arc Jumpstart</a> site. There are also <a href="https://learn.microsoft.com/en-us/azure/cloud-adoption-framework/scenarios/hybrid/enterprise-scale-landing-zone">additional learning resources for Azure Arc at this reference</a>. 
 
<h4>Connect with Azure Active Directory</h4>
Fully securing your Data Estate requires strong access and authentication mechanisms. The newest versions of SQL Server now support connecting to SQL Server using Azure AD identities with Azure Active Directory Password, Azure Active Directory Integrated, Azure Active Directory Universal with Multi-Factor Authentication, and Azure Active Directory access token authentication modes. 

> Current connection methods such as SQL authentication and Windows authentication remain unchanged

As a central authentication repository used by Azure, Azure AD allows you to store objects such as users, groups, or service principals as identities. Azure AD also allows you to use those identities to authenticate with different Azure services.

You can <a href="https://learn.microsoft.com/en-us/sql/relational-databases/security/authentication-access/azure-ad-authentication-sql-server-overview?view=sql-server-ver16">learn more about Microsoft Azure Arc-enabled SQL Server at this reference</a>.

<h2 id="5.3"><img style="float: left; margin: 0px 15px 15px 0px;" src="https://github.com/microsoft/sqlworkshops/blob/master/graphics/pencil2.png?raw=true">5.3 - Migrating SQL Server Instances to the Microsoft Azure Platform</h2>
In some cases, you may decide that a particular data workload should move to the cloud. Benefits of using a cloud service include enhanced security, cost optimization, and elastic scale. It also assists with licensing and monitoring and management centralization. 

<h4>Process and Planning</h4> 
Planning is essential for successful migrations. You should thoroughly document your application and database engine versions, settings and options installed, and understand how they are used. Of special importance are the HA/DR and security implications in each application to data path. 

You should also careful check any automated scripts, SQL Server Agent Jobs, and other connection points into the data engine so that you plan for their migration as well.

Building on your audit from the first Module in this course, your first decision when you upgrade is whether the upgrade can be performed online or offline. In the case of an offline migration, it can be as simple a matter as backing up the local database and restoring it to any of the Azure SQL platforms in the Microsoft Azure environment. From there, you hook up your connections from the applications and then set the security (logins, users, and so on) and begin your unit, functional, and acceptance testing. 

For online (and offline) migrations, Microsoft provides various tools to assist you not only in the migration effort, but in much of the planning such as recommending the proper version and size of the target, and much more. Also, the features you learned earlier (such as Link for Managed Instance) can assist you in your migration. 

<h4>Azure Data Studio Migration Extension</h4>
In a previous Module you learned about the <a href="https://learn.microsoft.com/en-us/sql/azure-data-studio/?view=sql-server-ver15">Azure Data Studio tool</a> that you can use to manage, monitor and program your SQL Server and Azure SQL database environments. This tool also includes a full migration extension you can use to assess your migration, get advice on the Azure recommendations for sizing and migrate your SQL Server databases to Azure.

<p></p>
<img src="https://user-images.githubusercontent.com/517325/189189647-bb1e5857-3ba4-416f-987e-c68812587d47.png" width=800>
<p></p>

You can <a href="https://docs.microsoft.com/en-us/sql/azure-data-studio/extensions/azure-sql-migration-extension?view=sql-server-ver15 ">learn more about the Azure SQL migration extension for Azure Data Studio at this reference</a>.

The Azure SQL migration extension for Azure Data Studio uses the Azure Database Migration Service (DMS). The DMS enables migrations from multiple database sources to Azure Data platforms with minimal downtime. The service uses the Data Migration Assistant to generate assessment reports that provide recommendations to guide you through the changes required before performing a migration. When you're ready to begin the migration process, Azure Database Migration Service performs all the required steps.

<p></p>
<img src="https://user-images.githubusercontent.com/517325/189189527-3554ff5b-0f0c-4ef1-8164-51bf74f2af2a.png" width=800>
<p></p>

You can <a href="https://docs.microsoft.com/en-us/azure/dms/)">learn more about the Azure Database Migration Service at this reference</a>.

<h4>Azure Migrate</h4>
Azure Migrate is a very comprehensive service that provides a simplified migration, modernization, and optimization of data sources to Azure. All pre-migration steps such as discovery, assessments, and right-sizing of on-premises resources are included for infrastructure, data, and applications. Azure Migrate’s extensible framework allows for integration of third-party tools, thus expanding the scope of supported use-cases. You should consider starting with this service if you have an Enterprise or complex migration.

<p></p>
<img src="https://user-images.githubusercontent.com/517325/189189693-c88cf4c0-90f4-45b0-91bb-8993796593ee.png" width=800>
<p></p>

You can <a href="https://docs.microsoft.com/en-us/azure/migrate/)">learn more about Azure Migrate at this reference</a>.

<p><img style="float: left; margin: 0px 15px 15px 0px;" src="https://github.com/microsoft/sqlworkshops/blob/master/graphics/point1.png?raw=true"><b>Activity: Formalize your Modernization Plan</b></p>

In the first Module of this course, you laid out a few areas you would like to focus on for your organization's modernization efforts. In this last Activity, you will take what you have learned and expand that list with a more formal set of objectives to take back to your office. 

<p><img style="margin: 0px 15px 15px 0px;" src="https://github.com/microsoft/sqlworkshops/blob/master/graphics/checkmark.png?raw=true"><b>Steps</b></p>

- Open the document you started in Module 1
- Add any new objectives, areas, or functions you think would be valuable to research further, and link the modules and resources you have found in this course that would assist you in that exploration. 

<p style="border-bottom: 1px solid lightgrey;"></p>

<p><img style="float: left; margin: 0px 15px 15px 0px;" src="https://github.com/microsoft/sqlworkshops/blob/master/graphics/owl.png?raw=true"><b>For Further Study</b></p>
<ul>
    <li><a href="[url](https://azure.microsoft.com/en-us/resources/five-steps-to-modernizing-your-data/)" target="_blank">A whitepaper on <i>Five Steps to Modernizing Your Data</i> is available here</a>.</li>
</ul>

Congratulations! You have completed this workshop on Modernizing Your Data Estate With SQL Ground-to-Cloud. You now have the tools, assets, and processes you need to extrapolate this information into other applications.
