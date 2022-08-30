![](graphics/microsoftlogo.png?raw=true)

# Workshop: Modernizing Your Data Estate With SQL Ground-to-Cloud

#### <i>A Microsoft Workshop</i>

<p style="border-bottom: 1px solid lightgrey;"></p>

<h2><img style="float: left; margin: 0px 15px 15px 0px;" src="https://github.com/microsoft/sqlworkshops/blob/master/graphics/textbubble.png?raw=true"> About this Workshop</h2>

Welcome to this Microsoft solutions workshop on creating a modern data estate using SQL Server in on-premises, in-cloud and hybrid solutions. In this one-day workshop, you'll learn how to use the latest improvements in SQL Server and Azure SQL help you solve real-world challenges. 

The Modules in this workshop lead you through conceptual and hands-on topics ranging from the newest technical features in SQL Server to its implementation in all the platforms it runs on. You'll learn not only specific technologies, but how to assemble them into a complete solution based on customer needs and requests.   

You'll start by learning about auditing your current data estate and how to evaluate any gaps, moving on to understanding the latest improvements in SQL Server, and then learn about the ways you can leverage SQL in Microsoft Azure (and how to get there) - all with a focus on how to extrapolate what you have learned to create other solutions for your organization. You'll end the day with a "What to Use When" module explaining how to create your own data estate architecture.

This Workshop contains lecture and hands on lab work, and is particularly useful for Solution Architects, Data Architects, Application Architects, Technical Sellers, and Application Developers. A laptop, Microsoft Azure account, and experience with SQL is considered a prerequisite.

This README.MD file explains how the workshop is laid out, what you will learn, and the technologies you will use in this solution.

(You can view all of the [source files for this workshop on this GitHub site, along with other workshops as well. Open this link in a new tab to find out more.](https://github.com/microsoft/sqlworkshops-sqlg2c))

<p style="border-bottom: 1px solid lightgrey;"></p>


<h3><img style="float: left; margin: 0px 15px 15px 0px;" src="https://github.com/microsoft/sqlworkshops/blob/master/graphics/checkmark.png?raw=true"> Learning Objectives</h3>

In this day-long, hands-on Workshop you’ll learn how to:

<br>

 - Evaluate your current data estate and identify any gaps you have for leveraging data to make intelligent decisions
 - Articulate the key differentiators between SQL Server on-prem, in an Azure Virtual Machine, in Azure SQL Managed Instance, Azure SQL offerings, and hybrid configurations
 - Explain the different service tiers within Azure SQL, and what to choose when
 - Understand how Azure SQL is secured and address security concerns
 - Explain hybrid configurations for Azure SQL and SQL Server in common examples
 - Experiment with various new features of SQL Server and Azure SQL
 - Understand additional Azure platform features for data pipelines and security
 - Understand what services are available to migrate and modernize your entire SQL Server stack
 - Make informed decisions about how your business or customers should modernize their data estate

<h3><img style="float: left; margin: 0px 15px 15px 0px;" src="https://github.com/microsoft/sqlworkshops/blob/master/graphics/checkmark.png?raw=true"> Role Applications</h3>

The concepts and skills taught in this workshop form the starting points for:

- Solution Architects and Developers, to understand how to put together an end to end solution.
- Data Professionals and DevOps teams, to implement and operate SQL Server systems on premises and in the cloud.
- Data Scientists, to understand the environment used to analyze and solve specific predictive problems.

<p style="border-bottom: 1px solid lightgrey;"></p>
<h2><img style="float: left; margin: 0px 15px 15px 0px;" src="https://github.com/microsoft/sqlworkshops/blob/master/graphics/building1.png?raw=true"> Business Applications of this Workshop</h2>

Businesses require near real-time insights from ever-larger sets of data from a variety of sources. Many have not explored the improvements made in the latest versions of SQL Server, and some are only now exploring the cloud as a computing platform. As time has progressed, a more dramatic upgrade process may be required.

In addition to traditional Online Transaction Processing (OLTP) and Online Analytic Processing (OLAP) workloads, some industry examples of data processing from multiple sources of data at scale are:
<table style="tr:nth-child(even) {background-color: #f2f2f2;}; text-align: left; display: table; border-collapse: collapse; border-spacing: 2px; border-color: gray;">
<tr><th style="background-color: #1b20a1; color: white;">Industry</th><th style="background-color: #1b20a1; color: white;">Example</th></tr>
<tr><td style="vertical-align: top">Retail</td><td style="vertical-align: top">Demand Prediction<br/>Market-Basket Analysis</td></tr>
<tr><td style="vertical-align: top">Finance</td><td style="vertical-align: top">Fraud detection<br/>customer segmentation</td></tr>
<tr><td style="vertical-align: top">Healthcare</td><td style="vertical-align: top">Fiscal control analytics<br/>Disease Prevention prediction and classification<br/> Clinical Trials optimization</td></tr>
<tr><td style="vertical-align: top">Public Sector</td><td style="vertical-align: top">Revenue prediction<br/>Education effectiveness analysis</td></tr>
<tr><td style="vertical-align: top">Manufacturing</td><td style="vertical-align: top">Predictive Maintenance<br/>Anomaly Detection</td></tr>
<tr><td style="vertical-align: top">Agriculture</td><td style="vertical-align: top">Food Safety analysis<br/>Crop forecasting</td></tr>
</table>

<p style="border-bottom: 1px solid lightgrey;"></p>

<h2><img style="float: left; margin: 0px 15px 15px 0px;" src="https://github.com/microsoft/sqlworkshops/blob/master/graphics/listcheck.png?raw=true"> <a name="technologies">Technologies and Topics covered in this Workshop</a></h2>

The information covered in this workshop includes the following technologies and topics - although you are not limited to these, they form the basis of the workshop. At the end of the workshop you will learn how to extrapolate these components into other solutions. You will cover these at an overview level, with references to much deeper training provided.

 <table style="tr:nth-child(even) {background-color: #f2f2f2;}; text-align: left; display: table; border-collapse: collapse; border-spacing: 2px; border-color: gray;">

  <tr><th style="background-color: #1b20a1; color: white;">Technology/Concept</th> <th style="background-color: #1b20a1; color: white;">Description</th></tr>
  <tr><td style="vertical-align: top">Creating a Data Estate Architecture Audit</i></td><td style="vertical-align: top">Explains how to evaluate the current data estate in your organization and how to identify and document gaps</td></tr>
  <tr><td style="vertical-align: top">SQL Server improvements (on-prem and in-cloud)</i></td><td style="vertical-align: top">Covers challenges and solutions in management, reliability, performance, security, data virtualization, and Linux for SQL Server spanning on-premise, Virtual Machines, Containers, Kubernetes, and cloud platforms.</td></tr>
  <tr><td style="vertical-align: top">SQL Server Virtual Machines in Microsoft Azure </i></td><td style="vertical-align: top">Covers the tools, processes and procedures for SQL Server Virtual Machines on the Microsoft Azure platform </td></tr>
  <tr><td style="vertical-align: top">Azure SQL </i></td><td style="vertical-align: top">Covers the tools, processes and procedures for Azure SQL (Managed Instance, Single Database, and Elastic Pool)</td></tr>
  <tr><td style="vertical-align: top">Migrating SQL Server installations to Microsoft Azure </i></td><td style="vertical-align: top">Explains the tools and processes to extend on-premises SQL Server installations to the Microsoft Azure platform </td></tr>

</table>

<p style="border-bottom: 1px solid lightgrey;"></p>

<h2><img style="float: left; margin: 0px 15px 15px 0px;" src="https://github.com/microsoft/sqlworkshops/blob/master/graphics/owl.png?raw=true"> <a name="prereqs">Before Taking this Workshop</a></h2>

You'll need a local system or Virtual Machine that you are able to install software on. The workshop demonstrations use Microsoft Windows as an operating system and all examples use Windows for the workshop. Optionally, you can use a Microsoft Azure Virtual Machine (VM) to install the software on and work with the solution.

You must have a Microsoft Azure account with the ability to create assets, specifically the Azure Kubernetes Service (AKS).

This workshop expects that you understand data structures and working with SQL Server and computer networks. This workshop does not expect you to have any prior data science knowledge, but a basic knowledge of statistics and data science is helpful in the Data Science sections. Knowledge of SQL Server, Azure Data and AI services, Python, and Jupyter Notebooks is helpful but not required. AI techniques are implemented in R and Python packages. Solution templates are implemented using Azure services, development tools, and SDKs. You should have experience working with the Microsoft Azure Platform.

If you are new to these, here are a few references you can complete prior to class: 

-  [Microsoft SQL Server](https://docs.microsoft.com/en-us/sql/relational-databases/database-engine-tutorials?view=sql-server-ver15)
-  [Microsoft Azure](https://docs.microsoft.com/en-us/learn/paths/azure-fundamentals/)


<h3><img style="float: left; margin: 0px 15px 15px 0px;" src="https://github.com/microsoft/sqlworkshops/blob/master/graphics/bulletlist.png?raw=true"> Setup</h3>

<a href="https://github.com/sqlballs/mSQLg2c/blob/Buck/modules/01-SetupandWorkshopMethodology.md" target="_blank">A full prerequisites document is located here</a>. These instructions should be completed before the workshop starts, since you will not have time to cover these in class. <i>Remember to "Stop" any Virtual Machines from the Azure Portal when not taking the class so that you do incur charges (shutting down the machine in the VM itself is not sufficient)</i>.

<p style="border-bottom: 1px solid lightgrey;"></p>

<h3><img style="float: left; margin: 0px 15px 15px 0px;" src="https://github.com/microsoft/sqlworkshops/blob/master/graphics/bulletlist.png?raw=true"> Intended Audience</h3>

<p>The following roles will find this workshop useful. Others may also attend, as described in the Secondary Audience section.</p>

<table style="tr:nth-child(even) {background-color: #f2f2f2;}; text-align: left; display: table; border-collapse: collapse; border-spacing: 5px; border-color: gray;">

  <tr><td style="background-color: Cornsilk; color: black; padding: 5px 5px;">Primary Audience:</td><td style="background-color: Cornsilk; color: black; padding: 5px 5px;">Solution Architects and Data Professionals tasked with implementing modern Data Systems, Data Virtualization, Machine Learning and AI solutions</td></tr>
  <tr><td>Secondary Audience:</td><td> Security Architects, Developers, and Data Scientists</td></tr>
  <tr><td style="background-color: Cornsilk; color: black; padding: 5px 5px;">Level: </td><td style="background-color: Cornsilk; color: black; padding: 5px 5px0;"> 300</td></tr>
  <tr><td>Type:</td><td>In-Person or Self-Paced</td></tr>
  <tr><td style="background-color: Cornsilk; color: black; padding: 5px 5px;">Length: </td><td style="background-color: Cornsilk; color: black; padding: 5px 5px;">8-9 hours</td></tr>

</table>

<p style="border-bottom: 1px solid lightgrey;"></p>

<h3><img style="float: left; margin: 0px 15px 15px 0px;" src="https://github.com/microsoft/sqlworkshops/blob/master/graphics/bookpencil.png?raw=true"> Workshop Modules and In-Class Agenda</h3>

This is a modular workshop, and in each section, you'll learn concepts, technologies and processes to help you complete the solution. The times shown below are for an instructor-led course, you may also take the modules in a self-paced fashion.

<table style="tr:nth-child(even) {background-color: #f2f2f2;}; text-align: left; display: table; border-collapse: collapse; border-spacing: 5px; border-color: gray;">

  <tr><td style="background-color: AliceBlue; color: black;"><b>Module</b></td>
  <td style="background-color: AliceBlue; color: black;"><b>Topics</b></td></tr>

  <tr><td style="vertical-align: top;"><a href="https://github.com/sqlballs/mSQLg2c/blob/Buck/modules/01-SetupandWorkshopMethodology.md" target="_blank">01 - Setup and Workshop Methodology </a></td><td> Workshop introduction, logistics, setup checks</td></tr>
  
  <tr><td style="vertical-align: top;background-color: AliceBlue; color: black;"><a href="https://github.com/sqlballs/mSQLg2c/blob/Buck/modules/02-AuditingYour%20DataEstateArchitecture.md" target="_blank">02 - Auditing your Data Estate Architecture</a> <td style="vertical-align: top;background-color: AliceBlue; color: black;"> This module covers the processes and tools you can use to audit your current data estate and how to identify gaps for leveraging data to make intelligent decisions </td></tr>
  <tr><td style="vertical-align: top;"><a href="https://github.com/sqlballs/mSQLg2c/blob/Buck/modules/03-SQLServerImprovements.md" target="_blank"> 03 - SQL Server Improvements </a></td><td>Improvements in SQL Server's manageability, availability, performance, security and more, including:
        <ul style="list-style-type:disc;">
        <li>Tools such as SQL Server Management Studio, Azure Data Studio, and more</li>
    </ul>
  </td></tr>
  <tr><td style="vertical-align: top;background-color: AliceBlue; color: black;"><a href="https://github.com/sqlballs/mSQLg2c/blob/Buck/modules/04-ImprovementsInSQLOnTheMicrosoftAzurePlatform.md" target="_blank">04 - Improvements in SQL on the Microsoft Azure Platform </a> </td><td style="background-color: AliceBlue; color: black;"> Covers the improvements in SQL Server technologies on the Microsoft Azure Platform, along with the fundamentals of SQL in Azure with additional deeper resources provided. Topics covered include:
      <ul style="list-style-type:disc;">
        <li>Azure SQL: SQL VMs, Single instance, Single database, Elastic pools</li>
    </ul>
  </td></tr>  

  <tr><td style="vertical-align: top;"><a href="https://github.com/sqlballs/mSQLg2c/blob/Buck/modules/05-ExtendingSQLServerToAzure.md" target="_blank"> 05 - Extending SQL Server to Azure </a></td><td>Covers the methods of connecting your on-premises data systems to cloud platforms such as Microsoft Azure and Amazon's AWS, migration workflows and tools for assessing, planning, and connecting and/or migrating SQL workloads to Azure that meets the business requirements.</td></tr>

</table>

<p style="border-bottom: 1px solid lightgrey;"></p>

<h2><img style="float: left; margin: 0px 15px 15px 0px;" src="https://github.com/microsoft/sqlworkshops/blob/master/graphics/pinmap.png?raw=true"> Related Workshops</h2>

 - [Other SQL Workshops by Microsoft](https://aka.ms/sqlworkshops)

<p style="border-bottom: 1px solid lightgrey;"></p>

<h2><img style="float: left; margin: 0px 15px 15px 0px;" src="https://github.com/microsoft/sqlworkshops/blob/master/graphics/geopin.png?raw=true">Next Steps</h2>

Next, Continue to <a href="https://github.com/sqlballs/mSQLg2c/blob/Buck/modules/01-SetupandWorkshopMethodology.md" target="_blank"><i> Prerequisites</i></a>

