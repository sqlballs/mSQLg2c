![](../graphics/microsoftlogo.png)

# Workshop: Modernizing Your Data Estate With SQL Ground-to-Cloud
#### <i>A Microsoft workshop from the SQL Server team</i>

<p style="border-bottom: 1px solid lightgrey;"></p>

<img style="float: left; margin: 0px 15px 15px 0px;" src="./graphics/textbubble.png"> <h2>02 - Auditing Your Data Estate Architecture</h2>

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
  
<h2 id="2.1"><img style="float: left; margin: 0px 15px 15px 0px;" src="./graphics/pencil2.png">2.1 Business Process Analysis</h2>

TODO: Topic Description

BA

BPMN

Data Mapping from BPMN
  
<br>

<p><img style="float: left; margin: 0px 15px 15px 0px;" src="./graphics/point1.png"><b>Activity: TODO: Activity Name</b></p>

TODO: Activity Description and tasks

<p><b>Description</b></p>

TODO: Enter activity description with checkbox

<p><img style="margin: 0px 15px 15px 0px;" src="./graphics/checkmark.png"><b>Steps</b></p>

TODO: Enter activity steps description with checkbox

<p style="border-bottom: 1px solid lightgrey;"></p>

<h2 id="2.2"><img style="float: left; margin: 0px 15px 15px 0px;" src="./graphics/pencil2.png">2.2 Identify Data Sources and Sinks</h2>

Data Storage versus Data Processing
  
Data Architecture Options 
  
<h3>Tools</h3>

<img width="1176" alt="image" src="https://user-images.githubusercontent.com/517325/189189782-892a92dd-c54d-4f32-adac-ee3463e171ac.png">


<h4>MAP</h4>
Map Toolkit - https://docs.microsoft.com/en-us/previous-versions/bb977556(v=technet.10) 

![image](https://user-images.githubusercontent.com/517325/189189344-e3e95758-91ca-4e41-8597-fdf35e50d2c7.png)

<h4>SQL ServerMigration Assistant</h4>
https://docs.microsoft.com/en-us/sql/ssma/sql-server-migration-assistant?view=sql-server-ver15

![image](https://user-images.githubusercontent.com/517325/189189438-f0679b21-3723-498d-8be3-97b6a689bab2.png)

<h4>Database Experimentation Assistant</h4>
https://www.microsoft.com/en-us/download/details.aspx?id=54090 

![image](https://user-images.githubusercontent.com/517325/189189486-1a13ed80-17c4-4f31-8607-7c15c5642315.png)

<h4>Azure Database Migration Service</h4>
https://docs.microsoft.com/en-us/azure/dms/

![image](https://user-images.githubusercontent.com/517325/189189527-3554ff5b-0f0c-4ef1-8164-51bf74f2af2a.png)

<h4>Data Migration Assistant</h4>
https://docs.microsoft.com/en-us/sql/dma/dma-overview?view=sql-server-ver15#see-also

![image](https://user-images.githubusercontent.com/517325/189189603-599d1fc8-5297-453d-a83d-5a9bc6c6d2c6.png)

<h4>Azure Data Studio Migration Extension</h4>
https://docs.microsoft.com/en-us/sql/azure-data-studio/extensions/azure-sql-migration-extension?view=sql-server-ver15 

![image](https://user-images.githubusercontent.com/517325/189189647-bb1e5857-3ba4-416f-987e-c68812587d47.png)

<h4>Azure Synapse Pathway</h4>
https://docs.microsoft.com/en-us/sql/tools/synapse-pathway/azure-synapse-pathway-overview?view=azure-sqldw-latest

![image](https://user-images.githubusercontent.com/517325/189189253-ae26dfec-3484-4fd1-8373-79ef9e0f3b1b.png)

<h4>Azure Migrate</h4>
https://docs.microsoft.com/en-us/azure/migrate/

![image](https://user-images.githubusercontent.com/517325/189189693-c88cf4c0-90f4-45b0-91bb-8993796593ee.png)


TODO: Topic Description

<p><img style="float: left; margin: 0px 15px 15px 0px;" src="./graphics/point1.png"><b>Activity: TODO: Activity Name</b></p>

TODO: Activity Description and tasks

<p><b>Description</b></p>

TODO: Enter activity description with checkbox

<p><img style="margin: 0px 15px 15px 0px;" src="./graphics/checkmark.png"><b>Steps</b></p>

TODO: Enter activity steps description with checkbox

<p style="border-bottom: 1px solid lightgrey;"></p>

<h2 id="2.3"><img style="float: left; margin: 0px 15px 15px 0px;" src="./graphics/pencil2.png">2.3 Map Data Paths</h2>
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

<p><img style="float: left; margin: 0px 15px 15px 0px;" src="./graphics/point1.png"><b>Activity: TODO: Activity Name</b></p>

TODO: Activity Description and tasks

<p><b>Description</b></p>

TODO: Enter activity description with checkbox

<p><img style="margin: 0px 15px 15px 0px;" src="./graphics/checkmark.png"><b>Steps</b></p>

TODO: Enter activity steps description with checkbox

<p style="border-bottom: 1px solid lightgrey;"></p>
  
<h2 id="2.4"><img style="float: left; margin: 0px 15px 15px 0px;" src="./graphics/pencil2.png">2.4 Gap Analysis</h2>

  Creating a Gap Analysis for data intelligence
  
TODO: Topic Description

<p><img style="float: left; margin: 0px 15px 15px 0px;" src="./graphics/point1.png"><b>Activity: TODO: Activity Name</b></p>

TODO: Activity Description and tasks

<p><b>Description</b></p>

TODO: Enter activity description with checkbox

<p><img style="margin: 0px 15px 15px 0px;" src="./graphics/checkmark.png"><b>Steps</b></p>

TODO: Enter activity steps description with checkbox

<p style="border-bottom: 1px solid lightgrey;"></p>
  
<p><img style="margin: 0px 15px 15px 0px;" src="./graphics/owl.png"><b>For Further Study</b></p>
<ul>
    <li><a href="https://docs.microsoft.com/en-us/azure/architecture/framework/" target="_blank">The Microsoft Well-Architected Framework</a></li>
    <li><a href="https://docs.microsoft.com/en-us/azure/architecture/data-guide/" target="_blank">Azure Data Architecture Guide</a></li>
    <li><a href="https://docs.microsoft.com/en-us/azure/architecture/data-guide/relational-data/online-transaction-processing" target="_blank">Online transaction processing (OLTP)</a></li>
    <li><a href="https://docs.microsoft.com/en-us/azure/architecture/data-guide/big-data/non-relational-data" target="_blank">Non-relational data and NoSQL</a></li>
    </ul>

Next, continue on to [Module 03 - SQL Server Improvements](https://github.com/sqlballs/mSQLg2c/blob/main/modules/03-SQLServerImprovements.md)
