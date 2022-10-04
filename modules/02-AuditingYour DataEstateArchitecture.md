![](https://github.com/microsoft/sqlworkshops/blob/master/graphics/microsoftlogo.png?raw=true)

# Workshop: Modernizing Your Data Estate With SQL Ground-to-Cloud
#### <i>A Microsoft workshop from the SQL Server team</i>

<p style="border-bottom: 1px solid lightgrey;"></p>

<img style="float: left; margin: 0px 15px 15px 0px;" src="https://github.com/microsoft/sqlworkshops/blob/master/graphics/textbubble.png?raw=true"> <h2>02 - Auditing Your Data Estate Architecture</h2>

In this workshop you'll cover how to systematically create a modern data estate using SQL Server in on-premises, in-cloud and hybrid solutions.In each module you'll get more references, which you should follow up on to learn more. Also watch for links within the text - right-click each one and select "Open in New Tab" to explore that topic.

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
  
One of those tools is to use an IT Framework to create an ontology and process map for your data estate. There are many different IT Frameworks for organizing your Information Technology platforms for your organization. While almost no one can fully implement a framework completely, they still have great value in creating a structure that you can use to get started and modify your own map. 

A few primary industry IT Frameworks are:

<table style="tr:nth-child(even) {background-color: #f2f2f2;}; text-align: left; display: table; border-collapse: collapse; border-spacing: 2px; border-color: gray;">
<tr><th style="background-color: #1b20a1; color: white;">Framework</th><th style="background-color: #1b20a1; color: white;">Use</th></tr>
<tr><td style="vertical-align: top">The<a href="https://www.zachman.com/about-the-zachman-framework"> Zachman Framework for Enterprise Architecture</a></td><td style="vertical-align: top">Creates a common "vocabulary" using perspectives/views: Planner, Owner, Designer, Builder, Subcontractor, and User. The second dimension implements the six basic questions: what, how, where, who, when and why. This Framework is more of a description and language than a process. It's a good place to start understanding your organization's IT estate, including the data aspects.</td></tr>
<tr><td style="vertical-align: top">The<a href="#"> Open Group Architectural Framework (TOGAF)</a></td><td style="vertical-align: top">Description</td></tr>
</table>

And of course there are many other Frameworks, some general-purpose, others specific to a particular use or industry. You can <a href="https://en.wikipedia.org/wiki/Enterprise_architecture_framework">see a list of more Frameworks here</a>. 

Some of these Frameworks focus on a top-down, central IT team approach, providing a consolidated view of the entire estate - including the data platforms. Other that are more data-centric, such as the Data Mesh, push the responsibilities for each data area out to the affected part of the organization. In any case, these frameworks are ideals - and a complete and comprehensive view of any single aspect (compute, security, file storage, etc) is fairly rare. It is a huge effort to locate and catalog each and every facet of the IT infrastructure. 
  
Whichever framework your organization uses - even if there is no defined framework - you should have a general map of your Data Estate. A Data Estate (for the purposes of this workshop) is the processes, platforms, and people involved in creating, storing, processing and disposing of organizational data. This includes not only the data your organization maintains, but the 
  
<h2 id="2.1"><img style="float: left; margin: 0px 15px 15px 0px;" src="https://github.com/microsoft/sqlworkshops/blob/master/graphics/pencil2.png?raw=true">2.1 Business Process Analysis</h2>

Business Process Analysis (BPA) evaluates an organization's actions to achieve a goal. You can use this discipline to discover the sequences the organization's members (employees) are using to get things done. While BPA is most often used to improve the efficiency of a business or organization, you can leverage the results of BPA to find data <i>Sources</i> (where data originates) and <i>Sinks</i> (the destination(s) the data moves to next) in your data estate.

You can <a href="https://www.frevvo.com/blog/business-process-analysis/">learn more about Business Process Analysis and find a simple checklist to start this process at this reference</a>. 

<h3>Working with a Business Analyst</h3>
In many cases your organization will already have a BPA completed. If your organization has a Business Analyst role, you should contact that team to start your data investigation. Data discovery and movement is at the core of this discipline. You can <a href="https://www.indeed.com/hire/job-description/business-analyst">read more about the Business Analyst role here</a>. 

<h3>Mapping Business Processes to data with Business Process Model and Notation</h3>
You may not have a Business Analyst (BA)at your organization or have had a BPA completed. In this case, you can start with the main applications you are aware of in your organization and create a data map from there. If you do have a BA in your organization, they will often document processes using a specific tool.

Other professionals in your organization may not be as familiar with database and other technologies, and will normally describe these systems in terms if what actions they take, rather than in the systems they use. To bridge the gap between business processes and communicate effectively with your BA's, you can use <i>Business Process Model and Notation</i> (BPMN). BPMN uses a series of "swimlanes" or rectangles that capture a particular process, person, or group, and the actions they take represented by icons. When the process, person or group completes part of their process, another icon is added. If one swimlane passes off the results of an action to another process, person, or group, another rectangle is documented and arrows show the direction of flow. 

<img src="https://user-images.githubusercontent.com/517325/191271646-1d4d8d1d-7cdf-40fd-a785-10459a5a710f.png" alt="BA" width="600">

You can <a href="https://en.wikipedia.org/wiki/Business_Process_Model_and_Notation">read more about Business Process Model and Notation here<a>.
  
<br>

<p><img style="float: left; margin: 0px 15px 15px 0px;" src="https://github.com/microsoft/sqlworkshops/blob/master/graphics/point1.png?raw=true"><b>Activity: TODO: Activity Name</b></p>

TODO: Activity Description and tasks

<p><b>Description</b></p>

TODO: Enter activity description with checkbox

<p><img style="margin: 0px 15px 15px 0px;" src="https://github.com/microsoft/sqlworkshops/blob/master/graphics/checkmark.png?raw=true"><b>Steps</b></p>

TODO: Enter activity steps description with checkbox

<p style="border-bottom: 1px solid lightgrey;"></p>

<h2 id="2.2"><img style="float: left; margin: 0px 15px 15px 0px;" src="https://github.com/microsoft/sqlworkshops/blob/master/graphics/pencil2.png?raw=true">2.2 Identify Data Sources and Sinks</h2>

Data Storage versus Data Processing
  
Data Architecture Options 
  
<h3>Tools</h3>
<TODO:> Description
  
<img src="https://user-images.githubusercontent.com/517325/189189782-892a92dd-c54d-4f32-adac-ee3463e171ac.png" alt="Graphic" width="600">

<h4>MAP</h4>
Map Toolkit - https://docs.microsoft.com/en-us/previous-versions/bb977556(v=technet.10) 

<img src="https://user-images.githubusercontent.com/517325/189189344-e3e95758-91ca-4e41-8597-fdf35e50d2c7.png" alt="Graphic" width="600">

<h4>SQL Server Migration Assistant</h4>
https://docs.microsoft.com/en-us/sql/ssma/sql-server-migration-assistant?view=sql-server-ver15

<img src="https://user-images.githubusercontent.com/517325/189189438-f0679b21-3723-498d-8be3-97b6a689bab2.png" alt="Graphic" width="600">
  
<h4>Microsoft Purview Data Map</h4>

https://learn.microsoft.com/en-us/purview/purview

https://learn.microsoft.com/en-us/azure/purview/microsoft-purview-connector-overview

<img src="https://learn.microsoft.com/en-us/azure/purview/media/overview/high-level-overview-large.png#lightbox" alt="Graphic" width="600">

  
TODO: Topic Description

<p><img style="float: left; margin: 0px 15px 15px 0px;" src="https://github.com/microsoft/sqlworkshops/blob/master/graphics/point1.png?raw=true"><b>Activity: TODO: Activity Name</b></p>

TODO: Activity Description and tasks

<p><b>Description</b></p>

TODO: Enter activity description with checkbox

<p><img style="margin: 0px 15px 15px 0px;" src="https://github.com/microsoft/sqlworkshops/blob/master/graphics/checkmark.png?raw=true"><b>Steps</b></p>

TODO: Enter activity steps description with checkbox

<p style="border-bottom: 1px solid lightgrey;"></p>

<h2 id="2.3"><img style="float: left; margin: 0px 15px 15px 0px;" src="https://github.com/microsoft/sqlworkshops/blob/master/graphics/pencil2.png?raw=true">2.3 Map Data Paths</h2>
Earlier in the process you identified the sources and sinks for your data based on the applications that use them. Now you'll want to trace the path the data takes from creation to consumption. In some cases this inolves mapping the network path of the creation of the data asset from the application directly to the sink, and in other cases you will need to trace the paths the data takes during backup operations, Extract, Transform and Load operations (ETL), and any cross-system queries that occur. This is one the most involved parts of the auditing process. 

You can start with the application paths, documenting the connections that are made from the application to the data source. In some cases this will be a direct connection, and in others there are layers of systems that take data requests, process them, and return the result to the application. 

For the systems that move data from one sink to another, there are more options for that process. 

<h3>Data Movement options</h3>
There are multiple options your organization likely has to move data from one location to another. They are grouped into two general toolsets: a manual, scripted, or platform-specific tool (such as PowerShell or SQL Server Integration Services) and a system specifically designed to move data, called a Pipeline.

<h4>Independent data movement systems</h4>
Processes, Scripts, and Platform-Specific tools move data from a sink to another sink either on a schedule, manually, or through some data trigger. They can push the data from one system to another, or pull the data from one system into another. 

The process to locate these processes and tools are to engage with the team that is repsonsible for creating and running them. You can often find those systems when you look at your Reporting and Business Intelligence outputs. 

<h4>Pipelines</h4>
  
<h3>Security</h3>
  
<h3>Performance</h3>
  
<h3>Cost</h3>

<h3>Tools</h3>

<h4>Microsoft Purview</h4>

<p><img style="float: left; margin: 0px 15px 15px 0px;" src="https://github.com/microsoft/sqlworkshops/blob/master/graphics/point1.png?raw=true"><b>Activity: TODO: Activity Name</b></p>

TODO: Activity Description and tasks

<p><b>Description</b></p>

TODO: Enter activity description with checkbox

<p><img style="margin: 0px 15px 15px 0px;" src="https://github.com/microsoft/sqlworkshops/blob/master/graphics/checkmark.png?raw=true"><b>Steps</b></p>

TODO: Enter activity steps description with checkbox

<p style="border-bottom: 1px solid lightgrey;"></p>
  
<h2 id="2.4"><img style="float: left; margin: 0px 15px 15px 0px;" src="https://github.com/microsoft/sqlworkshops/blob/master/graphics/pencil2.png?raw=true">2.4 Gap Analysis</h2>

  Creating a Gap Analysis for data intelligence
  
TODO: Topic Description

<p><img style="float: left; margin: 0px 15px 15px 0px;" src="https://github.com/microsoft/sqlworkshops/blob/master/graphics/point1.png?raw=true"><b>Activity: TODO: Activity Name</b></p>

TODO: Activity Description and tasks

<p><b>Description</b></p>

TODO: Enter activity description with checkbox

<p><img style="margin: 0px 15px 15px 0px;" src="https://github.com/microsoft/sqlworkshops/blob/master/graphics/checkmark.png?raw=true"><b>Steps</b></p>

TODO: Enter activity steps description with checkbox

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
