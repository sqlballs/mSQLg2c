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
<br>

<h3>Backup/Restore to URL</h3>
https://learn.microsoft.com/en-us/sql/relational-databases/backup-restore/sql-server-backup-to-url?view=sql-server-ver16 
https://learn.microsoft.com/en-us/azure/azure-sql/virtual-machines/windows/azure-storage-sql-server-backup-restore-use?view=azuresql 

<h3>Backup/Restore with Object Store (s3 only)</h3>
https://learn.microsoft.com/en-us/sql/relational-databases/backup-restore/sql-server-backup-and-restore-with-s3-compatible-object-storage?view=sql-server-ver16 

<h3>DR site</h3>
https://learn.microsoft.com/en-us/azure/site-recovery/physical-azure-disaster-Recovery
<p></p>

<b>Always On Availability Group</b>

https://learn.microsoft.com/en-us/azure/azure-sql/virtual-machines/windows/availability-group-overview?view=azuresql&viewFallbackFrom=sql-server-ver16 
https://learn.microsoft.com/en-us/azure/azure-sql/virtual-machines/windows/availability-group-overview?view=azuresql 
 replica in VM (license free)
<p></p>
<b>FCI</b>

https://learn.microsoft.com/en-us/azure/azure-sql/virtual-machines/windows/failover-cluster-instance-overview?view=azuresql 
<p></p>

<b>Link for MI feature</b>
https://techcommunity.microsoft.com/t5/azure-sql-blog/managed-instance-link-connecting-sql-server-to-azure-reimagined/ba-p/2911614#:~:text=Link%20feature%20for%20Managed%20Instance%20is%20a%20new,Instance%2C%20providing%20unprecedented%20hybrid%20flexibility%20and%20database%20mobility. 

Azure Site Recovery
https://learn.microsoft.com/en-us/azure/site-recovery/site-recovery-overview 

Log Shipping
https://learn.microsoft.com/en-us/sql/database-engine/log-shipping/about-log-shipping-sql-server?view=sql-server-ver16 

Replication
https://learn.microsoft.com/en-us/azure/azure-sql/database/replication-to-sql-database?view=azuresql

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


<h3>Azure Data Sync</h3>
Between Instance and SQL DB 

https://learn.microsoft.com/en-us/azure/azure-sql/database/sql-data-sync-data-sql-server-sql-database?view=azuresql 

<h3>Replication Subscriber</h3> 
in any Azure SQL
https://learn.microsoft.com/en-us/azure/azure-sql/database/replication-to-sql-database?view=azuresql 

<h3>Azure Key Vault</h3> 
EKM - Always Encrypted
https://learn.microsoft.com/en-us/sql/relational-databases/security/encryption/extensible-key-management-using-azure-key-vault-sql-server?view=sql-server-ver16 

<h3>Synapse Link</h3> 
A very eye-opening chart. 
https://www.businessinsider.com/top-ceos-make-399-times-more-than-workers-2022-10 

<h3>Linked Server</h3>
https://learn.microsoft.com/en-us/sql/relational-databases/linked-servers/create-linked-servers-sql-server-database-engine?view=sql-server-ver16 

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
