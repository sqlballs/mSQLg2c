![](https://github.com/microsoft/sqlworkshops/blob/master/graphics/microsoftlogo.png?raw=true)

# Workshop: Modernizing Your Data Estate With SQL Ground-to-Cloud
#### <i>A Microsoft workshop from the SQL Server team</i>

<p style="border-bottom: 1px solid lightgrey;"></p>

<img style="float: left; margin: 0px 15px 15px 0px;" src="https://github.com/microsoft/sqlworkshops/blob/master/graphics/textbubble.png?raw=true"> <h2>04 - Microsoft Azure SQL Improvements</h2>

In the previous modules, you learned about how to <a href="https://github.com/sqlballs/mSQLg2c/blob/Josh/modules/02-AuditingYourDataEstateArchitecture.md" target="_blank"> <b>audit your data estate</b></a>, and the most recent <a href="https://github.com/sqlballs/mSQLg2c/blob/Josh/modules/03-SQLServerImprovements.md" target="_blank"><b>SQL Server improvements</a>.</b> In this module, you will learn about the different options available for running SQL Server in Azure and all the considerations that are involved with running an architecture in the cloud, like Manageability, Availability, Performance, Security, and Deployment.

(As a reminder, make sure you check out the <a href="https://github.com/sqlballs/mSQLg2c/blob/Josh/modules/01-SetupandWorkshopMethodology.md" target="_blank"><b>Pre-Requisites</b></a> page before you start. You'll need all of the items loaded there before you can proceed with the workshop.)

You'll cover these topics in the workshop:
<dl>

  <dt><a href="#4.1" target="_blank">4.1 - Deployment Options<dt>
  <dt><a href="#4.2" target="_blank">4.2 - Manageability<dt>
  <dt><a href="#4.3" target="_blank">4.3 - Availability<dt>
  <dt><a href="#4.4" target="_blank">4.4 - Performance<dt>
  <dt><a href="#4.5" target="_blank">4.5 - Security<dt>
  <dt><a href="#4.6" target="_blank">4.6 - Development<dt>

</dl>

<p style="border-bottom: 1px solid lightgrey;"></p>

<h2 id="4.1"><img style="float: left; margin: 0px 15px 15px 0px;" src="https://github.com/microsoft/sqlworkshops/blob/master/graphics/pencil2.png?raw=true">4.1 Deployment Options</h2></a>


![Azure SQL Overview](https://github.com/microsoft/sqlworkshops-azuresqllabs/blob/master/graphics/azuresql-overview.png?raw=true)  

<h3>SQL Server on Microsoft Azure VM's</h3>

Azure SQL VMs don't have specific service tiers, but there are decisions to be made around which images to choose, how to configure storage and what sizes, etc. This isn't the focus of this workshop, but if you're considering Azure SQL VMs, you'll want to review the [guidance on images to choose from](https://docs.microsoft.com/en-us/azure/virtual-machines/windows/sql/virtual-machines-windows-sql-server-iaas-overview), the [quick checklist](https://docs.microsoft.com/en-us/azure/virtual-machines/windows/sql/virtual-machines-windows-sql-performance) to obtain optimal performance of Azure SQL VMs, and the guidance for [storage configuration](https://docs.microsoft.com/en-us/azure/virtual-machines/windows/sql/virtual-machines-windows-sql-server-storage-configuration).  

Recently, [Resource Provider](http://www.aka.ms/sqlvm_rp_documentation) was [announced](http://www.aka.ms/sqlvm_rp), which brings the functionality of Azure Marketplace images to SQL Server instances self-installed on Azure VMs.  

> Note: If you're specifically looking at SQL Server on RHEL Azure VMs, there's a full operations guide available [here](https://azure.microsoft.com/en-us/resources/sql-server-on-rhel-azure-vms-operations-guide/
).  
  
> Note: In an earlier module of this workshop, you learned about some of the problems SQL Server 2019 is solving. The same applies in an Azure SQL VM (if you choose 2019 as the target).  

<h3>SQL Server Managed Instance</h3>

Azure SQL Managed Instance is the intelligent, scalable cloud database service that combines the broadest SQL Server database engine compatibility with all the benefits of a fully managed and evergreen platform as a service. SQL Managed Instance has near 100% compatibility with the latest SQL Server (Enterprise Edition) database engine, providing a native virtual network (VNet) implementation that addresses common security concerns, and a business model favorable for existing SQL Server customers. SQL Managed Instance allows existing SQL Server customers to lift and shift their on-premises applications to the cloud with minimal application and database changes. At the same time, SQL Managed Instance preserves all PaaS capabilities (automatic patching and version updates, automated backups, high availability) that drastically reduce management overhead and TCO.

<h3>Azure SQL Database</h3>

For Azure SQL Database, there are several options and tiers available, and the choices will depend on the scenario.  

There are a few main decisions to be made, which will be explored next.    

*Decision 1: Choose the purchasing model*  
You have two options, [virtual core (vCore)-based](https://docs.microsoft.com/en-us/azure/sql-database/sql-database-service-tiers-vcore) (recommended) or [Database transaction unit (DTU)-based](https://docs.microsoft.com/en-us/azure/sql-database/sql-database-service-tiers-dtu
).     

The vCore-based model is recommended because it allows you to independently choose compute and storage resources, while the DTU-based model is a bundled measure of compute, storage and I/O resources, which means you have less control over paying only for what you need. This model also allows you to use [Azure Hybrid Benefit for SQL Server](https://azure.microsoft.com/pricing/hybrid-benefit/) to gain cost savings. In the [vCore model](https://docs.microsoft.com/en-us/azure/sql-database/sql-database-service-tiers-vcore), you pay for:  

* Compute resources (the service tier + the number of vCores and the amount of memory + the generation of hardware).
* The type and amount of data and log storage.
* Backup storage ([read-access, geo-redundant storage (RA-GRS)](https://docs.microsoft.com/en-us/azure/storage/common/storage-designing-ha-apps-with-ragrs)).  

For the purposes of this workshop, we'll focus on the vCore purchasing model (recommended), but you can [compare vCores and DTUs here](https://docs.microsoft.com/en-us/azure/sql-database/sql-database-purchase-models
).

*Decision 2: Choose service tier for performance and availability*  
There are three tiers available in the vCore model for Azure SQL Database:
* **[General purpose](https://docs.microsoft.com/en-us/azure/sql-database/sql-database-service-tier-general-purpose)**: Most business workloads. Offers budget-oriented, balanced, and scalable compute and storage options.
* **[Business critical](https://docs.microsoft.com/en-us/azure/sql-database/sql-database-service-tier-business-critical)**: Business applications with low-latency response requirements. Offers highest resilience to failures by using several isolated replicas. This is the only tier that can leverage [in-memory OLTP](https://docs.microsoft.com/en-us/azure/sql-database/sql-database-in-memory) to improve performance.
* **[Hyperscale](https://docs.microsoft.com/en-us/azure/sql-database/sql-database-service-tier-hyperscale)**: Most business workloads with highly scalable storage and read-scale requirements. *Currently only available for single databases, not managed instances*. We'll talk more about this in separate section specifically for Hyperscale.

A member of the Product Group recently released a [blog](https://azure.microsoft.com/en-gb/blog/understanding-and-leveraging-azure-sql-database-sla/) and [video](https://www.youtube.com/watch?v=l7FUNJd5TSE) explaining the SLA (service level agreements that set an expectation for uptime and performance). This resource will help you make an informed decision about which tier to move to.  

For a deeper explanation between the three tiers (including scenarios), you can also refer to the [service-tier characteristics](https://docs.microsoft.com/en-us/azure/sql-database/sql-database-service-tiers-vcore#service-tier-characteristics) in the documentation.  

*Decision 3: Provisioned or serverless compute?*  
If you choose **General Purpose within Single databases** and the **vCore-based model**, you have an additional decision to make regarding the compute that you pay for:
* **Provisioned compute** is meant for more regular usage patterns with higher average compute utilization over time, or multiple databases using elastic pools. 
* **Serverless compute** is meant for intermittent, unpredictable usage with lower average compute utilization over time. Serverless has auto-pause and resume capabilities (with a time delay you set), meaning when your database is paused, you only pay for storage. 
![Serverless Compute Analysis](https://learn.microsoft.com/en-us/azure/azure-sql/database/media/serverless-tier-overview/serverless-billing.png?view=azuresql)

For a deeper explanation between the two compute options (including scenarios), you can refer to the detailed [comparison in the documentation](https://docs.microsoft.com/en-us/azure/sql-database/sql-database-serverless#comparison-with-provisioned-compute-tier).  

> If you're looking for compute cost saving opportunities, you can prepay for compute resources with [Azure SQL Database reserved capacity](https://docs.microsoft.com/en-us/azure/sql-database/sql-database-reserved-capacity).

*Decision 4: Choose hardware generation*  
The vCore model lets you choose the generation of hardware:  
* **Gen4**: Up to 24 logical CPUs based on Intel E5-2673 v3 (Haswell) 2.4-GHz processors, vCore = 1 PP (physical core), 7 GB per core, attached SSD
* **Gen5**: Up to 80 logical CPUs based on Intel E5-2673 v4 (Broadwell) 2.3-GHz processors, vCore = 1 LP (hyper-thread), 5.1 GB per core, fast eNVM SSD  

Basically, Gen4 hardware offers substantially more memory per vCore. However, Gen5 hardware allows you to scale up compute resources much higher. 

> Note: If you choose General Purpose within Single databases and want to use the serverless compute tier, Gen5 hardware is the only option.  

<h3>Azure SQL Database Hyperscale</h3>

TODO: Topic Description

<h3>Microsoft Azure Synapse</h3>

TODO: Topic Description


<p><img style="float: left; margin: 0px 15px 15px 0px;" src="https://github.com/microsoft/sqlworkshops/blob/master/graphics/point1.png?raw=true"><b>Activity: TODO: Activity Name</b></p>

TODO: Activity Description and tasks

<p><b>Description</b></p>

TODO: Enter activity description with checkbox

<p><img style="margin: 0px 15px 15px 0px;" src="https://github.com/microsoft/sqlworkshops/blob/master/graphics/checkmark.png?raw=true"><b>Steps</b></p>

TODO: Enter activity steps description with checkbox

### *Summary*  
As you've hopefully noticed, while there are a lot of options, Azure is able to provide flexibility so you get exactly what you need, nothing less. A summary of the service tier options with some additional considerations is included below, but be sure to check out [pricing information](https://azure.microsoft.com/en-us/pricing/details/sql-database/managed/) for the latest details.

<p style="border-bottom: 1px solid lightgrey;"></p>

<p style="border-bottom: 1px solid lightgrey;"></p>



<h2 id="4.2"><img style="float: left; margin: 0px 15px 15px 0px;" src="https://github.com/microsoft/sqlworkshops/blob/master/graphics/pencil2.png?raw=true">4.2 Manageability</h2>

While managing SQL Server in the cloud is somewhat different than managing on premises instances, the tools and methodologies that you will use are mostly the same tools and methodologies that you used in your on premises environment. In this module, we'll walk through some of the tools. Some you will be familiar with, and some will be new.

<h3>Tools</h3>

Depending on the deployment option of Azure SQL you choose, the manageability tools are the same or very similar to the tools you are already used to. In this section, we'll go through the different options show an overview of the tool, what you would use it for, and what tool it would be comparable to in your on premises environment.

<h4>Azure Portal</h4>

![Azure Portal](../modules/graphics/azure_portal.png)

The Azure Portal is the first stop in managing your Azure environment. The portal to allows you to deploy, manage, monitor, or delete resources in your subscription. From a hands-on perspective, it is one of the most powerful single tools in your "tool belt".

* [Built-in monitoring](https://docs.microsoft.com/en-us/azure/log-analytics/log-analytics-azure-sql) capabilities enable you to get the insights into performance of your databases and workload, and troubleshoot the performance issues.

<h4>Azure Data Studio</h4>

![Azure Data Studio](../modules/graphics/azure_data_studio.png)

Azure Data Studio is a highly extensible tool that helps developers to manage and develop against multiple data processing and storage engines. Its versatility through the use of application extensions allows it to be as useful as the developer can make it.

For instance, there are extensions for helping developers to migrate to Azure SQL, develop "clean" looking code, monitor and manage Azure Synapse, work on PostgreSQL instances, or even develop using Jupyter Notebooks

<h4>Command-Line Utilities</h4>

##### Azure CLI

The Azure command-line interface ([Azure CLI](https://learn.microsoft.com/en-us/cli/azure/)) is a set of commands used to create and manage Azure resources. The Azure CLI is available across Azure services and is designed to get you working quickly with Azure, with an emphasis on automation. 

With this utility, developers can do almost everything that can be done in the Azure portal, and codify it so that it can be automated for consistent and repeatable execution.

##### SQLCMD ?

SQLCMD is a versatile tool that allows developers to get command line access to SQL Server, without using a tool like Azure Data Studio.

<br>

<br>

<p><img style="float: left; margin: 0px 15px 15px 0px;" src="https://github.com/microsoft/sqlworkshops/blob/master/graphics/point1.png?raw=true"><b>Activity: Overview of Azure Data Studio</b></p>

<p><b>Walkthrough of Azure Data Studio and installation guidance</b></p>

Azure Data Studio is a great cross platform management tool for your Azure data services like Azure SQL, Azure Database for Postgres, and Azure Data Explorer. There are also custom extensions for customer to use, or create, to simplify their day-to-day activities.

<p><img style="margin: 0px 15px 15px 0px;" src="https://github.com/microsoft/sqlworkshops/blob/master/graphics/checkmark.png?raw=true"><b>Steps</b></p>

<p><b>Watch the following YouTube Video</p></b>

[Overview of Azure Data Studio](https://www.youtube.com/watch?v=Orv7fptVoUA)

<p><b>Overview of and Install Azure Data Studio</p></b>

[Overview of Azure Data Studio](https://learn.microsoft.com/en-us/sql/azure-data-studio/what-is-azure-data-studio)

[Install Azure Data Studio](https://learn.microsoft.com/en-us/sql/azure-data-studio/download-azure-data-studio)


<p style="border-bottom: 1px solid lightgrey;"></p>



<h2 id="4.3"><img style="float: left; margin: 0px 15px 15px 0px;" src="https://github.com/microsoft/sqlworkshops/blob/master/graphics/pencil2.png?raw=true">4.3 Availability</h2>

* [Business continuity](https://docs.microsoft.com/en-us/azure/sql-database/sql-database-business-continuity) enables your business to continue operating in the face of disruption, particularly to its computing infrastructure.
* [High availability](https://docs.microsoft.com/en-us/azure/sql-database/sql-database-high-availability) of Azure SQL Database guarantees your databases are up and running 99.99% of the time, no need to worry about maintenance/downtimes.
* [Automated backups](https://docs.microsoft.com/en-us/azure/sql-database/sql-database-automated-backups) are created and use Azure read-access geo-redundant storage (RA-GRS) to provide geo-redundancy.
* [Long term backup retention](https://docs.microsoft.com/en-us/azure/sql-database/sql-database-long-term-retention) enables you to store specific full databases for up to 10 years.
* [Geo-replication](https://docs.microsoft.com/en-us/azure/sql-database/sql-database-active-geo-replication) by creating readable replicas of your database in the same or different data center (region).
![Active Geo Replication](https://learn.microsoft.com/en-us/azure/azure-sql/database/media/active-geo-replication-overview/geo-replication-updated.png?view=azuresql)

<p><img style="float: left; margin: 0px 15px 15px 0px;" src="https://github.com/microsoft/sqlworkshops/blob/master/graphics/point1.png?raw=true"><b>Activity: Azure SQL Availability</b></p>

Watch video from Anna Hoffman and Bob Ward

<p><b>Description</b></p>

This video will walk you through considerations for when looking at high availability and disaster recovery needs and features in Azure SQL.

<p><img style="margin: 0px 15px 15px 0px;" src="https://github.com/microsoft/sqlworkshops/blob/master/graphics/checkmark.png?raw=true"><b>Steps</b></p>

[Availability Capabilities and Tasks Video](https://www.youtube.com/watch?v=OJVXH_dPAEA
)

[Azure Docs: High Availability for Azure SQL Database and SQL Managed Instance](https://learn.microsoft.com/en-us/azure/azure-sql/database/high-availability-sla?view=azuresql&tabs=azure-powershell)

<p style="border-bottom: 1px solid lightgrey;"></p>

<h2 id="4.4"><img style="float: left; margin: 0px 15px 15px 0px;" src="https://github.com/microsoft/sqlworkshops/blob/master/graphics/pencil2.png?raw=true">4.4 Performance</h2>

* [Scale](https://docs.microsoft.com/en-us/azure/sql-database/sql-database-scale-resources) by easily adding more resources (CPU, memory, storage) without long provisioning.
* [Automatic tuning](https://docs.microsoft.com/en-us/azure/sql-database/sql-database-automatic-tuning) analyzes your workload and provides you the recommendations that can optimize performance of your applications by adding indexes, removing unused indexes, and automatically fixing the query plan issues.
* [Built-in intelligence](https://docs.microsoft.com/en-us/azure/sql-database/sql-database-intelligent-insights) automatically identifies the potential issues in your workload and provides you the recommendations that can [help you to fix the problems](https://azure.microsoft.com/en-us/blog/ai-helped-troubleshoot-an-intermittent-sql-database-performance-issue-in-one-day/). 
<p><img style="float: left; margin: 0px 15px 15px 0px;" src="https://github.com/microsoft/sqlworkshops/blob/master/graphics/point1.png?raw=true"><b>Activity: Performance Improvements</b></p>

Watch videos

<p><b>Automatic Tuning</b></p>

Automatic tuning in Azure SQL is a great feature that analyzes your workload and gives recommndations on configuration changes you can make to improve performance. In this video, you are given an overview of the feature.

<p><img style="margin: 0px 15px 15px 0px;" src="https://github.com/microsoft/sqlworkshops/blob/master/graphics/checkmark.png?raw=true"><b>Steps</b></p>

 [Improve Performance Tuning with Automatic Tuning](https://www.youtube.com/watch?v=HQantpWg3sg)

<p style="border-bottom: 1px solid lightgrey;"></p>

<h2 id="4.5"><img style="float: left; margin: 0px 15px 15px 0px;" src="https://github.com/microsoft/sqlworkshops/blob/master/graphics/pencil2.png?raw=true">4.5 Security</h2>

* <b>[Advanced security](https://docs.microsoft.com/en-us/azure/sql-database/sql-database-security-index)</b> detects threats and vulnerabilities in your databases and enables you to secure your data.
* <b>[Virtual Network Service Endpoints](https://learn.microsoft.com/en-us/azure/virtual-network/virtual-network-service-endpoints-overview)</b> extend your virtual network over the Azure networking backbone and identify, and block if need be, traffic from a specific azure virtual network subnet that the traffic is originating from.
* <b>[Authentication](https://learn.microsoft.com/en-us/azure/azure-sql/database/security-overview?view=azuresql#authentication) is the process of validating users/services that connect to Azure 

<p><img style="float: left; margin: 0px 15px 15px 0px;" src="https://github.com/microsoft/sqlworkshops/blob/master/graphics/point1.png?raw=true"><b>Activity: TODO: Activity Name</b></p>

TODO: Activity Description and tasks

<p><b>Description</b></p>

TODO: Enter activity description with checkbox

<p><img style="margin: 0px 15px 15px 0px;" src="https://github.com/microsoft/sqlworkshops/blob/master/graphics/checkmark.png?raw=true"><b>Steps</b></p>

TODO: Enter activity steps description with checkbox

<p><img style="margin: 0px 15px 15px 0px;" src="https://github.com/microsoft/sqlworkshops/blob/master/graphics/checkmark.png?raw=true"><b>Steps</b></p>

TODO: Enter activity steps description with checkbox

<p style="border-bottom: 1px solid lightgrey;"></p>

<h2 id="4.6"><img style="float: left; margin: 0px 15px 15px 0px;" src="https://github.com/microsoft/sqlworkshops/blob/master/graphics/pencil2.png?raw=true">4.6 Development</h2>

TODO: Topic Description

<p><img style="float: left; margin: 0px 15px 15px 0px;" src="https://github.com/microsoft/sqlworkshops/blob/master/graphics/point1.png?raw=true"><b>Activity: TODO: Activity Name</b></p>

TODO: Activity Description and tasks

<p><b>Description</b></p>

TODO: Enter activity description with checkbox

<p><img style="margin: 0px 15px 15px 0px;" src="https://github.com/microsoft/sqlworkshops/blob/master/graphics/checkmark.png?raw=true"><b>Steps</b></p>

TODO: Enter activity steps description with checkbox


<p><img style="float: left; margin: 0px 15px 15px 0px;" src="https://github.com/microsoft/sqlworkshops/blob/master/graphics/owl.png?raw=true"><b>For Further Study</b></p>
<ul>
    <li><a href="url" target="_blank">TODO: Enter courses, books, posts, whatever the student needs to extend their study</a></li>
</ul>


Next, continue on to [Module 05 - Extending SQL Server to the Microsoft Azure Platform](https://github.com/sqlballs/mSQLg2c/blob/main/modules/05-ExtendingSQLServerToAzure.md)

  


Azure SQL Database (including single databases, elastic pools, and managed instances) is a fully managed Database Engine that automates most of the database management functions such as upgrading, patching, backups, and monitoring. Some of the built-in capabilities include:  






> Note: Many benefits typically thought of as Platform as a Service (PaaS) are surfacing in Infrastructure as a Service (IaaS). You can learn more about automated updates, automated backups, high availability, and performance provided in Azure SQL VMs [here](https://docs.microsoft.com/en-us/azure/virtual-machines/windows/sql/virtual-machines-windows-sql-server-iaas-overview).  

In addition to the resources linked to above, several [slide decks](https://aka.ms/azuresqlslides) are available (with notes and animations) that you can review to learn more. You can also check out the [Core Cloud Services - Azure architecture and service guarantees](https://docs.microsoft.com/en-us/learn/modules/explore-azure-infrastructure/) module from Microsoft Learn.  
<br>

<p style="border-bottom: 1px solid lightgrey;"></p>
