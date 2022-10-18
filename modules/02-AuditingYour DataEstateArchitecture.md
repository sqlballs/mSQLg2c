![](https://github.com/microsoft/sqlworkshops/blob/master/graphics/microsoftlogo.png?raw=true)
# Workshop: Modernizing Your Data Estate With SQL Ground-to-Cloud
#### <i>A Microsoft workshop from the SQL Server team</i>

<p style="border-bottom: 1px solid lightgrey;"></p>

<img style="float: left; margin: 0px 15px 15px 0px;" src="https://github.com/microsoft/sqlworkshops/blob/master/graphics/textbubble.png?raw=true"> <h2>02 - Auditing Your Data Estate Architecture</h2>

In this workshop you'll cover how to systematically create a modern data estate using SQL Server in on-premises, in-cloud and hybrid solutions. In each module you'll get more references, which you should follow up on to learn more. Also watch for links within the text - right-click each one and select "Open in New Tab" to explore that topic.

(<a href="https://github.com/sqlballs/mSQLg2c/blob/Buck/modules/01-SetupandWorkshopMethodology.md" target="_blank">Make sure you check out the <b>Pre-Requisites</b> page before you start</a>. You'll need all of the items loaded there before you can proceed with the workshop.)

You'll cover these topics in the workshop:
<dl>
  <dt><a href="#2.1" target="_blank">2.1 - Business Process Analysis</a></dt>
  <dt><a href="#2.2" target="_blank">2.2 - Identify Data Sources and Sinks</a></dt>
  <dt><a href="#2.3" target="_blank">2.3 - Map Data Paths</a></dt>
  <dt><a href="#2.4" target="_blank">2.4 - Gap Analysis</a></dt>
</dl>

<p style="border-bottom: 1px solid lightgrey;"></p>

An audit of a data estate is a massive undertaking. It's rare to start with a new implementation, so in most cases you are asked to be a detective in locating your organization's current data elements so that you can most effectively secure, tune, and update them. In smaller organizations there are fewer people that can take on the task, and in larger organizations there are so many elements that even the most dedicated team finds it difficult to be successful. However, there are tools, processes and techniques you can use to create a useful audit.

<h3>Scenario: Wide World Importers</h3>
The Setup section introduced Wide World Importers and their growing challenges.

The IT team has begun a modernization effort, and the Data Team has been asked to survey their users to see if there are improvements that need to be considered. The Data Estate at Wide World Importers is a mix of 3rd-party applications which cannot be altered, custom applications that have legacy code that is being evaluated for security, performance and availability improvements, and also analytic workloads such as Business Intelligence and Data Science projects. The organization would also like to understand more about the Data Lake architecture to see if it would help in their environment.

The Data Team has compiled a list of objectives for evaluation to see if newer versions or platforms would be useful:

- The ability to audit and track their Data Estate components
- Improving query performance without having to make application changes
- Classifying key data columns and being able to audit access to these columns to meet the needs of GDPR compliance
- Providing better database availability when applications use long-running transactions
- Allowing the WideWorldImporters team to access data from sources like Oracle, Azure SQL Database, and Azure CosmosDB without having to develop expensive ETL jobs
- The database team at WideWorldImporters has evaluated SQL Server on Linux but SQL Server 2017 didn't include Replication, a feature they need for their application. They would like to evaluate how SQL Server Replication on Linux works. They also want to understand more about container technology and how it can be used with SQL Server
- WideWorldImporters also would like to know other capabilities exist in the latest versions of SQL Server that might help them before more efficient and extend the capabilities of T-SQL
- WideWorldImporters also would like to learn more about how they can plan and execute a migration to the latest version of SQL Server and reduce their risk for upgrades
- WideWorldImporters is also evaluating Azure SQL so they want to know what features in SQL Server also work in Azure

To begin those improvements, the Wide World Importers (WWI) leadership team has tasked the Information Technology organization to create a comprehensive plan to audit where they are now, and how to accomplish all of the goals stated above.

One of the tools WWI (and your organization) can use an IT Framework to create an ontology and process map for your data estate. There are many different IT Frameworks for organizing your Information Technology platforms for your organization. While almost no one can fully implement a framework completely, they still have great value in creating a structure that you can use to get started and modify your own map.

A few primary industry IT Frameworks are:

<table style="tr:nth-child(even) {background-color: #f2f2f2;}; text-align: left; display: table; border-collapse: collapse; border-spacing: 2px; border-color: gray;">
  <tr><th style="background-color: #1b20a1; color: white;">Framework</th><th style="background-color: #1b20a1; color: white;">Use</th></tr>
  <tr><td style="vertical-align: top">The<a href="https://www.zachman.com/about-the-zachman-framework"> Zachman Framework for Enterprise Architecture</a></td><td style="vertical-align: top">Creates a common "vocabulary" using perspectives/views: Planner, Owner, Designer, Builder, Subcontractor, and User. The second dimension implements the six basic questions: what, how, where, who, when and why. This Framework is more of a description and language than a process. It's a good place to start understanding your organization's IT estate, including the data aspects.</td></tr>
  <tr><td style="vertical-align: top">The<a href="https://www.opengroup.org/togaf"> Open Group Architectural Framework (TOGAF)</a></td><td style="vertical-align: top">Allows you to customize an approach for design through governing an enterprise IT architecture, modeled at four levels: Business, Application, Data, and Technology. </td></tr>
</table>

And of course there are many other Frameworks, some general-purpose, others specific to a particular use or industry. You can <a href="https://en.wikipedia.org/wiki/Enterprise_architecture_framework">see a list of more Frameworks here</a>.

Some of these Frameworks focus on a top-down, central IT team approach, providing a consolidated view of the entire estate - including the data platforms. Other that are more data-centric, such as the Data Mesh, push the responsibilities for each data area out to the affected part of the organization. In any case, these frameworks are ideals - and a complete and comprehensive view of any single aspect (compute, security, file storage, etc) is fairly rare. It is a huge effort to locate and catalog each and every facet of the IT infrastructure. 
  
Whichever framework your organization uses - even if there is no defined framework - you should have a general map of your Data Estate. A Data Estate (for the purposes of this workshop) is the processes, platforms, and people involved in creating, storing, processing and disposing of organizational data. This includes not only the data your organization maintains, but the data your organization leverages.
  
<h2 id="2.1"><img style="float: left; margin: 0px 15px 15px 0px;" src="https://github.com/microsoft/sqlworkshops/blob/master/graphics/pencil2.png?raw=true">2.1 Business Process Analysis</h2>

Business Process Analysis (BPA) evaluates an organization's actions to achieve a goal. You can use this discipline to discover the sequences the organization's members (employees) are using to get things done. While BPA is most often used to improve the efficiency of a business or organization, you can leverage the results of BPA to find data <i>Sources</i> (where data originates) and <i>Sinks</i> (the destination(s) the data moves to next) in your data estate.

You can <a href="https://www.frevvo.com/blog/business-process-analysis/">learn more about Business Process Analysis and find a simple checklist to start this process at this reference</a>.

<h3>Working with a Business Analyst</h3>
In many cases your organization will already have a BPA completed. If your organization has a Business Analyst role, you should contact that team to start your data investigation. Data discovery and movement is at the core of this discipline. You can <a href="https://www.indeed.com/hire/job-description/business-analyst">read more about the Business Analyst role here</a>.

<h3>Mapping Business Processes to data with Business Process Model and Notation</h3>
You may not have a Business Analyst (BA)at your organization or have had a BPA completed. In this case, you can start with the main applications you are aware of in your organization and create a data map from there. If you do have a BA in your organization, they will often document processes using a specific tool.

Other professionals in your organization may not be as familiar with database and other technologies, and will normally describe these systems in terms if what actions they take, rather than in the systems they use. To bridge the gap between business processes and communicate effectively with your BA's, you can use <i>Business Process Model and Notation</i> (BPMN). BPMN uses a series of "swimlanes" or rectangles that capture a particular process, person, or group, and the actions they take represented by icons. When the process, person or group completes part of their process, another icon is added. If one swimlane passes off the results of an action to another process, person, or group, another rectangle is documented and arrows show the direction of flow.

<img src="https://user-images.githubusercontent.com/517325/191271646-1d4d8d1d-7cdf-40fd-a785-10459a5a710f.png" alt="BA" width="600">

You can <a href="https://en.wikipedia.org/wiki/Business_Process_Model_and_Notation">read more about Business Process Model and Notation here</a>.
  
<br>

<p><img style="float: left; margin: 0px 15px 15px 0px;" src="https://github.com/microsoft/sqlworkshops/blob/master/graphics/point1.png?raw=true"><b>Activity: Detail your Orgnaization's Data Estate Goals</b></p>
<br>
In this Activity, you will create a list of goals for your Data Estate similar to the one WWI created above.. You can use any tool for this Activity, including paper and pencil. This Activity can be completed alone or as a group.

<p><img style="margin: 0px 15px 15px 0px;" src="https://github.com/microsoft/sqlworkshops/blob/master/graphics/checkmark.png?raw=true"><b>Steps</b></p>

- Review the Wide World Importers Scenario above.
- Briefly review the IT Frameworks described above, and bookmark them for later reference for a discussion with your larger IT organization to see if you are using any of them, or should be leveraging them.
- Open [this reference in a new tab](https://i.pinimg.com/originals/3b/58/d7/3b58d79b6b60a579f4ea9635d910977e.png) to see some basic BPMN icons.
- Review the Contoso graphic shown earlier and review how the data elements show a process flow.
- Document at least three areas of emphasis for your data estate for your current organization. 

<p style="border-bottom: 1px solid lightgrey;"></p>

<h2 id="2.2"><img style="float: left; margin: 0px 15px 15px 0px;" src="https://github.com/microsoft/sqlworkshops/blob/master/graphics/pencil2.png?raw=true">2.2 Identify Data Sources and Sinks</h2>
The focus of your design is locating where data originates, and how it moves through the applications and processes in your organization. In general, your organization's data resides in data storage, and some systems also include a data processing engine or engines. Identifying these locations is essential to proper security, processing, reporting and applications. 
<p></p>
Creating a data map is a non-trivial task, and you should bias towards having the tier-1 application's data documented at the very least, as opposed to only creating the Architecture Diagram if everything is documented. You can always add information later.

<h3>Tools</h3>
You can create a <a href="https://learn.microsoft.com/en-us/azure/architecture/data-guide/databases-architecture-design">Data Architecture Diagram</a> using many different tools, from manual-entry systems or spreadsheets through automated systems that collect the location and information about your data Sinks and Sources. In any case, the discovery of data sources is the most labor-intensive part of the effort, followed by ensuring the Diagram is up to date, discoverable, and usable by those who need to access it.
<p></p>
You can see an example of a Data Architecture Diagram below: 

<img style="margin: 0px 15px 15px 0px;" src="https://techcommunity.microsoft.com/t5/image/serverpage/image-id/80143iA887B1C81ADBBA8D">

For data source discovery, you can often start with the tier-1 applications you organization uses, and find the Sources and Sinks they use by tracing their path. You can also check with your storage team to evaluate data storage elements that do not fall within a data processing engine.  

<h4>The MAP Toolkit</h4>
To discover database engines, there are multiple tools you can use. One of the oldest and simplest is the Microsoft Assessment and Planning (MAP) Toolkit. You can <a href="https://docs.microsoft.com/en-us/previous-versions/bb977556(v=technet.10)"> read more about it here</a>.
<br>
<img src="https://user-images.githubusercontent.com/517325/189189344-e3e95758-91ca-4e41-8597-fdf35e50d2c7.png" alt="Graphic" width="600">

The MAP Toolkit involves several Phases, which starts with collecting the data across your network or enterprise and creating several reports that you can customize.
<br>
<img src="https://social.technet.microsoft.com/wiki/cfs-filesystemfile.ashx/__key/communityserver-components-imagefileviewer/communityserver-wikis-components-files-00-00-00-00-05/5545.Phases.PNG_2D00_550x0.png" alt="Graphic" width="600">

Once you start the Collection action, the Toolkit produces several reports that you can review for the SQL Servers in your environment.
<br>
<img src="https://th.bing.com/th/id/R.d903b7cb753f85ca93280b71deaad375?rik=exKbfXl8xryqxQ&riu=http%3a%2f%2fsocial.technet.microsoft.com%2fwiki%2fcfs-file.ashx%2f__key%2fcommunityserver-wikis-components-files%2f00-00-00-00-05%2f4846.MAPUI.PNG&ehk=o0ldFgKymvCecw3IG5EwkKX%2fdokj%2f9bcCbfolbzCIuM%3d&risl=&pid=ImgRaw&r=0" alt="Graphic" width="600">

<p><img style="float: left; margin: 0px 15px 15px 0px;" src="https://github.com/microsoft/sqlworkshops/blob/master/graphics/point1.png?raw=true"><b>Activity: Evaluate and Bookmark the MAP Toolkit</b></p>
<br>
In this Activity, you will will complete a Learning Path for the MAP Toolkit. If time is limited, bookmark this Path for future use.
This Activity can be completed alone or as a group.

<p><img style="margin: 0px 15px 15px 0px;" src="https://github.com/microsoft/sqlworkshops/blob/master/graphics/checkmark.png?raw=true"><b>Steps</b></p>

- Open <a href="https://learn.microsoft.com/en-us/training/modules/sql-server-discovery-using-map/">this reference in a new tab</a> and complete the Learning Path.

<p style="border-bottom: 1px solid lightgrey;"></p>
<h4>Microsoft Purview Data Map</h4>
<a href="https://learn.microsoft.com/en-us/purview/purview">Microsoft Purview</a> is a suite of tools for data governance, risk assessment and management, and compliance that allow you to   govern, protect, and manage your entire data estate. For Data Discovery, this section focuses on the <i>Data Map</i> feature.

<img src="https://learn.microsoft.com/en-us/azure/purview/media/overview/high-level-overview-large.png#lightbox" alt="Graphic" width="600">

The Process to create a Data Map using Purview involves:

- Create an account in the Microsoft Purview governance portal
- Create a collection and assign permissions
- Create and manage Sources and Scan operations
- Apply classifications and Labels on assets
- Edit Data Catalog to add Information for the collected assets
- Review Asset insights on your data in Microsoft Purview

You can see <a href="https://learn.microsoft.com/en-us/azure/purview/microsoft-purview-connector-overview">a list of supported sources here, and this list</a> is constantly being expanded.

<p><img style="float: left; margin: 0px 15px 15px 0px;" src="https://github.com/microsoft/sqlworkshops/blob/master/graphics/point1.png?raw=true"><b>Activity: Complete an Overview of Microsoft Purview</b></p>

In this Activity you will review the process for creating an on-premises or in-VM SQL Server Instance Data Source, and if time permits, complete an Overview Learning Path for Microsoft Purview. This Activity can be done individually or as a group.

<p><img style="margin: 0px 15px 15px 0px;" src="https://github.com/microsoft/sqlworkshops/blob/master/graphics/checkmark.png?raw=true"><b>Steps</b></p>

- <a href="https://learn.microsoft.com/en-us/azure/purview/register-scan-on-premises-sql-server">Open this link and review the steps you see there</a>. Bookmark for later reference.
- <a href="https://learn.microsoft.com/en-us/training/modules/intro-to-microsoft-purview/">If time permits, open this Learning Path and complete only the Introduction</a>. Bookmark for later reference.

<p style="border-bottom: 1px solid lightgrey;"></p>

<h2 id="2.3"><img style="float: left; margin: 0px 15px 15px 0px;" src="https://github.com/microsoft/sqlworkshops/blob/master/graphics/pencil2.png?raw=true">2.3 Map Data Paths</h2>
Earlier in the process you identified the sources and sinks for your data based on the applications that use them. Now you'll want to trace the path the data takes from creation to consumption. In some cases this inolves mapping the network path of the creation of the data asset from the application directly to the sink, and in other cases you will need to trace the paths the data takes during backup operations, Extract, Transform and Load operations (ETL), and any cross-system queries that occur. This is one the most involved parts of the auditing process. 

You can start with the application paths, documenting the connections that are made from the application to the data source. In some cases this will be a direct connection, and in others there are layers of systems that take data requests, process them, and return the result to the application. 

For the systems that move data from one sink to another, there are more options for that process.

<h3>Data Movement options</h3>
There are multiple options your organization likely has to move data from one location to another. They are grouped into two general toolsets: a manual, scripted, or platform-specific tool (such as PowerShell or SQL Server Integration Services) and a system specifically designed to move and ppotentially operate on data, called a <i>Pipeline</i>.

The process to locate these processes and tools are to engage with the team that is repsonsible for creating and running them. You can often find those systems when you look at your Reporting and Business Intelligence outputs.

<h4>Pipelines</h4>
A <i>Data Pipeline</i> is any process or set of processes that moves data along a processing path. It might be as simple as copying data from one storage location to another, or as complex as extracting data from a database system, altering that data in some fashion, distributing it to several locations, all with retry logic, notification systems, and scheduling.  

There are several decision points to consider when designing or purchasing a Data Pipeline:

- Security: Does the system take into account the sensitivity of the data and ensure that security as it moves through the pipeline
- Complexity: Is the system simple enough to ensure that it can be monitored and maintained
- Interoperability: Does the system interact with all of the data sources and sinks you have, and will it interface with the ingestion and exports of other systems in a seamless way
- Performance: Can the system move the data quickly enough through the Data Pipeline such that the ingestion and refresh of data sources do not clash
- Cost: What is the budget of the organization - not just the licensing costs of the system, but the costs it generates and the personnel costs to operate it

<h3>Tools</h3>
There are various levels of tools you can use to build a pipeline, from using a scripting or command language, all the way to a fully dedicated Data Pipeline environment. Each has benefits and costs to consider.

<h4>Non-Dedicated Data Movement Systems</h4>
Processes, Scripts, and Platform-Specific tools move data from a sink to another sink either on a schedule, manually, or through some data trigger. They can push the data from one system to another, or pull the data from one system into another.

PowerShell is a tool shipped with all modern version of Microsoft Windows, and it is available for other platforms as well. It has the ability to work with files, e-mail, schedules, cloud environments such as Microsoft Azure, it can interface with SQL Server on-premises as well as all major database vendors, and much more. It is possibile to build a complete Data Piepeline with a scripting language such as PowerShell, but care should be taken to ensure that security and maintainability are considered when defining a manual Data Pipeline. 

You can find a <a href="https://www.powershellgallery.com/">large variety of code examples and libraries in the PowerShell Gallery</a>.

<h4>SQL Server Integration Services</h4>
One of the most mature tools in the SQL Server ecostructure is <a href="https://learn.microsoft.com/en-us/sql/integration-services/sql-server-integration-services?view=sql-server-ver16">SQL Server Integration Services</a>, or SSIS. SSIS can run in an on-premises and in-VM SQL Server, and its packages can also work within the Azure Data Factory tool described next. SSIS is a complete platform for building data integration and data transformations solutions. SSIS can copy or extract files, load data into databases or data warehouses, clean and mine data, and manage SQL Server objects and data.
<p></p>
In SSIS, you define data connections, and tie them together with tasks. You have full visibility into the metadata of SSIS, and it has routing, notification, alerting, retry logic, and rudimentary path logic included.
<p></p>

<img src="https://learn.microsoft.com/en-us/sql/integration-services/media/mw-dts-01.gif?view=sql-server-ver16" alt="Graphic" width="300">

You can find a complete <a href="https://learn.microsoft.com/en-us/sql/integration-services/integration-services-programming-overview?view=sql-server-ver16">programming overview of SQL Server Integration Services at this reference</a>.

<h4>Microsoft Azure Data Factory</h4>
Microsoft Azure Data Factory is a managed cloud service in Azure that's built for complex hybrid extract-transform-load (ETL), extract-load-transform (ELT), and data integration projects.
<p></p>
<img src="https://learn.microsoft.com/en-us/azure/data-factory/media/data-flow/overview.svg" alt="Graphic" width="600">
<p></p>

Although complex in its implementation, Azure Data Factory (ADF) has a simple set of primitives to learn: 
<p></p>
<img src="https://learn.microsoft.com/en-us/azure/data-factory/media/concepts-pipelines-activities/relationship-between-dataset-pipeline-activity.png" alt="Graphic" width="600">
<p></p>

You can <a href="https://learn.microsoft.com/en-us/azure/data-factory/introduction ">learn more about Azure Data Factory at this reference</a>.

<p><img style="float: left; margin: 0px 15px 15px 0px;" src="https://github.com/microsoft/sqlworkshops/blob/master/graphics/point1.png?raw=true"><b>Activity: SSIS and ADF Overview</b></p>

In this Activity you have a choice of reviewing one of two training modules: one for Azure Data Factory, and the other for SQL Server Integration Services. You can bookmark this reference to do both courses on your own schedule later.

<p><img style="margin: 0px 15px 15px 0px;" src="https://github.com/microsoft/sqlworkshops/blob/master/graphics/checkmark.png?raw=true"><b>Steps</b></p>

- Open <a href="https://learn.microsoft.com/en-us/training/modules/intro-to-azure-data-factory/">this reference on Azure Data Factory and review the Module you see there</a>.
- Open <a href="https://learn.microsoft.com/en-us/sql/integration-services/ssis-how-to-create-an-etl-package?view=sql-server-ver16">this reference on SQL Server Integration Services and review the Lessons you see there</a>.

<p style="border-bottom: 1px solid lightgrey;"></p>
  
<h2 id="2.4"><img style="float: left; margin: 0px 15px 15px 0px;" src="https://github.com/microsoft/sqlworkshops/blob/master/graphics/pencil2.png?raw=true">2.4 Gap Analysis</h2>

Gap Analysis is simply comparing your current state with the desired state in your organization. For the Data Estate, you began this process with the first Activity where you detailed some concerns you wanted to address using this Workshop.

<a href="https://www.smartsheet.com/gap-analysis-method-examples">You can read more about performing a Gap Analysis at this reference</a>.

After you complete the rest of the Modules in this Workshop, you should return to this section to develop your Gap Analysis using your system audit you created using this Module, and then create a business plan for your modernization effort. 

<p style="border-bottom: 1px solid lightgrey;"></p>
  
<p><img style="float: left; margin: 0px 15px 15px 0px;" src="https://github.com/microsoft/sqlworkshops/blob/master/graphics/owl.png?raw=true"><b>For Further Study</b></p>
<br>
<ul>
    <li><a href="https://docs.microsoft.com/en-us/azure/architecture/framework/" target="_blank">The Microsoft Well-Architected Framework</a></li>
    <li><a href="https://docs.microsoft.com/en-us/azure/architecture/data-guide/" target="_blank">Azure Data Architecture Guide</a></li>
    <li><a href="https://docs.microsoft.com/en-us/azure/architecture/data-guide/relational-data/online-transaction-processing" target="_blank">Online transaction processing (OLTP)</a></li>
    <li><a href="https://docs.microsoft.com/en-us/azure/architecture/data-guide/big-data/non-relational-data" target="_blank">Non-relational data and NoSQL</a></li>
    </ul>

Next, continue on to [Module 03 - SQL Server Improvements](https://github.com/sqlballs/mSQLg2c/blob/main/modules/03-SQLServerImprovements.md)
