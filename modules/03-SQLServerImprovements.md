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

  <dt><a href="#3.1" target="_blank">3.1 - Deployment Options<dt>
  <dt><a href="#3.2" target="_blank">3.2 - Manageability<dt>
  <dt><a href="#3.3" target="_blank">3.3 - Availability<dt>
  <dt><a href="#3.4" target="_blank">3.4 - Performance<dt>
  <dt><a href="#3.5" target="_blank">3.5 - Security<dt>
  <dt><a href="#3.6" target="_blank">3.6 - Development<dt>

</dl>

SQL Server 2019 is a modern data platform designed to tackle the challenges of today's data professional. SQL Server 2019 is not just an upgrade option from previous releases of SQL Server.

The WideWorldImporters company has been evaluating upgrading several SQL Server 2008 instances along with some instances of SQL Server 2012, 2014, and even 2016. WideWorldImporters wants to know whether SQL Server 2022 will solve some of the challenges they face.

<p style="border-bottom: 1px solid lightgrey;"></p>

<h2 id="3.1"><img style="float: left; margin: 0px 15px 15px 0px;" src="https://github.com/microsoft/sqlworkshops/blob/master/graphics/pencil2.png?raw=true">3.1 Deployment Options</h2>

Since SQL Server 2017 users have had the option of deploying SQL Server on Windows and in Linux.  Current deployment scenarios include Windows, Linux, Docker containers, and Kubernetes. 

Regardless of the deployment scenario there are some key items to keep in mind.


<h3>SQL Server on Windows</h3>

SQL Server has traditionally been a Windows only product.  

<h2><img style="float: left; margin: 0px 15px 15px 0px;" src="https://github.com/microsoft/sqlworkshops/blob/master/graphics/point1.png?raw=true"><b>     Activity: Review SQL Server Installation Key Terms Lab</a></b></h2>

In this activity, you will review key terms and concepts related to SQL Server Installations.


<h3><img style="margin: 0px 15px 15px 0px;" src="https://github.com/microsoft/sqlworkshops/blob/master/graphics/checkmark.png?raw=true"><b>Activity Steps</b></h3>

To complete this module, go to [https://learn.microsoft.com/en-us/sql/database-engine/install-windows/install-sql-server?view=sql-server-ver16#installation-media](https://learn.microsoft.com/en-us/sql/database-engine/install-windows/install-sql-server?view=sql-server-ver16#installation-media).

Review the following:
- Installation media
- Considerations
- SQL Server installation
- Individual component installation


When you are done with the SQL Server lab you have completed Module 02 of the SQL Server Ground to Cloud Workshop! Proceed to the next module using the link in Next Steps below.




<h3>SQL Server on Linux</h3>

SQL Server on Linux is supported by the following platforms.

<table border=1>
  <tr>
    <td>Platform</td>	
    <td>File System	</td>	
    <td>Installation Guide</td>
  </tr>
   <tr>
    <td>Red Hat Enterprise Linux 8.0 - 8.5 Server</td>	
    <td>XFS or EXT4</td>	
    <td><a href="https://learn.microsoft.com/en-us/sql/linux/quickstart-install-connect-red-hat?view=sql-server-ver16">Installation Guide</a></td>
  </tr>
   <tr>
    <td>SUSE Enterprise Linux Server v15 (SP1 - SP3)</td>	
    <td>XFS or EXT4</td>	
    <td><a href="https://learn.microsoft.com/en-us/sql/linux/quickstart-install-connect-suse?view=sql-server-ver16">Installation Guide</a></td>
  </tr>
   <tr>
    <td>Ubuntu 20.04 LTS</td>	
    <td>XFS or EXT4</td>	
    <td><a href="https://learn.microsoft.com/en-us/sql/linux/quickstart-install-connect-ubuntu?view=sql-server-ver16">Installation Guide</a></td>
  </tr>
   <tr>
    <td>Docker Engine 1.8+ on Linux</td>	
    <td>N/A</td>	
    <td><a href="https://learn.microsoft.com/en-us/sql/linux/quickstart-install-connect-docker?view=sql-server-ver16&pivots=cs1-bash">Installation Guide</a></td>
  </tr>
</table>


<h3>SQL Server in Containers</h3>

TODO: Topic Description

<h3>SQL Server on Kubernetes</h3>

TODO: Topic Description



<p><img style="float: left; margin: 0px 15px 15px 0px;" src="https://github.com/microsoft/sqlworkshops/blob/master/graphics/point1.png?raw=true"><b>Activity: TODO: Activity Name</b></p>

TODO: Activity Description and tasks

<p><b>Description</b></p>

TODO: Enter activity description with checkbox

<p><img style="margin: 0px 15px 15px 0px;" src="https://github.com/microsoft/sqlworkshops/blob/master/graphics/checkmark.png?raw=true"><b>Steps</b></p>

TODO: Enter activity steps description with checkbox


<h2 id="3.2"><img style="float: left; margin: 0px 15px 15px 0px;" src="https://github.com/microsoft/sqlworkshops/blob/master/graphics/pencil2.png?raw=true">3.2 Manageability</h2>

TODO: Topic Description

<h3>Tools</h3>

TODO: Topic Description

<h4>SQL Server Management Studio</h4>

TODO: Topic Description



<h4>Command-Line Utilities</h4>

TODO: Topic Description

<br>

<img style="height: 400; box-shadow: 0 4px 8px 0 rgba(0, 0, 0, 0.2), 0 6px 20px 0 rgba(0, 0, 0, 0.19);" src="https://docs.microsoft.com/en-us/sql/big-data-cluster/media/concept-security/cluster_endpoints.png">

<br>

<p><img style="float: left; margin: 0px 15px 15px 0px;" src="https://github.com/microsoft/sqlworkshops/blob/master/graphics/point1.png?raw=true"><b>Activity: TODO: Activity Name</b></p>

TODO: Activity Description and tasks

<p><b>Description</b></p>

TODO: Enter activity description with checkbox

<p><img style="margin: 0px 15px 15px 0px;" src="https://github.com/microsoft/sqlworkshops/blob/master/graphics/checkmark.png?raw=true"><b>Steps</b></p>

TODO: Enter activity steps description with checkbox

<p style="border-bottom: 1px solid lightgrey;"></p>

<h2 id="3.3"><img style="float: left; margin: 0px 15px 15px 0px;" src="https://github.com/microsoft/sqlworkshops/blob/master/graphics/pencil2.png?raw=true">3.3 Availability</h2>

TODO: Topic Description

<p><img style="float: left; margin: 0px 15px 15px 0px;" src="https://github.com/microsoft/sqlworkshops/blob/master/graphics/point1.png?raw=true"><b>Activity: TODO: Activity Name</b></p>

TODO: Activity Description and tasks

<p><b>Description</b></p>

TODO: Enter activity description with checkbox

<p><img style="margin: 0px 15px 15px 0px;" src="https://github.com/microsoft/sqlworkshops/blob/master/graphics/checkmark.png?raw=true"><b>Steps</b></p>

TODO: Enter activity steps description with checkbox

<p style="border-bottom: 1px solid lightgrey;"></p>

<h2 id="3.4"><img style="float: left; margin: 0px 15px 15px 0px;" src="https://github.com/microsoft/sqlworkshops/blob/master/graphics/pencil2.png?raw=true">3.4 Performance</h2>

TODO: Topic Description

<p><img style="float: left; margin: 0px 15px 15px 0px;" src="https://github.com/microsoft/sqlworkshops/blob/master/graphics/point1.png?raw=true"><b>Activity: TODO: Activity Name</b></p>

TODO: Activity Description and tasks

<p><b>Description</b></p>

TODO: Enter activity description with checkbox

<p><img style="margin: 0px 15px 15px 0px;" src="https://github.com/microsoft/sqlworkshops/blob/master/graphics/checkmark.png?raw=true"><b>Steps</b></p>

TODO: Enter activity steps description with checkbox

<p style="border-bottom: 1px solid lightgrey;"></p>

<h2 id="3.5"><img style="float: left; margin: 0px 15px 15px 0px;" src="https://github.com/microsoft/sqlworkshops/blob/master/graphics/pencil2.png?raw=true">3.5 Security</h2>

TODO: Topic Description

<p><img style="float: left; margin: 0px 15px 15px 0px;" src="https://github.com/microsoft/sqlworkshops/blob/master/graphics/point1.png?raw=true"><b>Activity: TODO: Activity Name</b></p>

TODO: Activity Description and tasks

<p><b>Description</b></p>

TODO: Enter activity description with checkbox

<p><img style="margin: 0px 15px 15px 0px;" src="https://github.com/microsoft/sqlworkshops/blob/master/graphics/checkmark.png?raw=true"><b>Steps</b></p>

TODO: Enter activity steps description with checkbox

<p><img style="margin: 0px 15px 15px 0px;" src="https://github.com/microsoft/sqlworkshops/blob/master/graphics/checkmark.png?raw=true"><b>Steps</b></p>

TODO: Enter activity steps description with checkbox

<p style="border-bottom: 1px solid lightgrey;"></p>

<h2 id="3.6"><img style="float: left; margin: 0px 15px 15px 0px;" src="https://github.com/microsoft/sqlworkshops/blob/master/graphics/pencil2.png?raw=true">3.6 Development</h2>

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

Next, continue on to [Module 04 - SQL Server on the Microsoft Azure Platform](https://github.com/sqlballs/mSQLg2c/blob/main/modules/04-ImprovementsInSQLOnTheMicrosoftAzurePlatform.md)


# Workshop: SQL Ground-to-Cloud

#### <i>A Microsoft workshop from the SQL Server team</i>

<p style="border-bottom: 1px solid lightgrey;"></p>

<h2><img style="float: left; margin: 0px 15px 15px 0px;" src="https://github.com/microsoft/sqlworkshops/blob/master/graphics/textbubble.png?raw=true"><b>     02 - Modernizing Your Data Estate with SQL Server 2019</b></h2>



- Improving query performance without having to make application changes
- Classifying key data columns and being able to audit access to these columns to meet the needs of GDPR compliance.
- Providing better database availability when applications use long-running transactions.
- Allowing the WideWorldImporters team to access data from sources like Oracle, Azure SQL Database, and Azure CosmosDB without having to develop expensive ETL jobs.
- The database team at WideWorldImporters has evaluated SQL Server on Linux but SQL Server 2017 didn't include Replication, a feature they need for their application. They would like to evaluate how SQL Server Replication on Linux works. They also want to understand more about container technology and how it can be used with SQL Server
- WideWorldImporters also would like to know other capabilities exist in SQL Server 2019 that might help them before more efficient and extend the capabilities of T-SQL.
- WideWorldImporters also would like to learn more about how they can plan and execute a migration to SQL Server 2019 and reduce their risk for upgrades.
- WideWorldImporters is also evaluating Azure SQL so wants to know what features in SQL Server 2019 also work in Azure.

In this workshop module, you will see the capabilities in SQL Server 2019 that can provide solutions for these challenges.

> **NOTE**: <a href="https://github.com/microsoft/sqlworkshops-sqlg2c/blob/master/sqlgroundtocloud/00-prerequisites.md" target="_blank">Make sure you check out the <b>prerequisite</b> page before you start.</a> You'll need all of the items loaded there before you can proceed with the workshop. Instructor led workshops may have provided all the resources in the prerequisites.

<p style="border-bottom: 1px solid lightgrey;"></p>

<h2><img style="float: left; margin: 0px 15px 15px 0px;" src="https://github.com/microsoft/sqlworkshops/blob/master/graphics/point1.png?raw=true"><b>     Activity: SQL Server 2019 Lab</a></b></h2>

In this activity, you will complete a series of modules from the **SQL Server 2019 Lab**.

Instructor led workshops will use modules from the SQL Server 2019 lab along with the PowerPoint slides <a href="https://github.com/microsoft/sqlworkshops/blob/master/SQLGroundToCloud/slides/SQL%20Server%202019%20Modern%20Data%20Platform.pptx">SQL Server 2019 Modern Data Platform</a>. Instructor led labs may not go through all modules in the SQL Server 2019 lab.

<h3><img style="margin: 0px 15px 15px 0px;" src="https://github.com/microsoft/sqlworkshops/blob/master/graphics/checkmark.png?raw=true"><b>Activity Steps</b></h3>

To complete this module, go to [https://github.com/microsoft/sqlworkshops/blob/master/sql2019lab/README.md](https://github.com/microsoft/sqlworkshops-sql2019lab).

When you are done with the SQL Server 2019 lab you have completed Module 02 of the SQL Server Ground to Cloud Workshop! Proceed to the next module using the link in Next Steps below.

<p style="border-bottom: 1px solid lightgrey;"></p>

<h2><img style="float: left; margin: 0px 15px 15px 0px;" src="https://github.com/microsoft/sqlworkshops/blob/master/graphics/owl.png?raw=true"><b>     For Further Study</b></h2>

<ul>
    <li><a href="https://docs.microsoft.com/en-us/sql/sql-server/what-s-new-in-sql-server-ver15" target="_blank">What's new in SQL Server 2019</a></li>
    <li><a href="https://github.com/microsoft/sqlworkshops/tree/master/sql2019lab" target="_blank">The SQL Server 2019 Lab</a></li>
    <li><a href="https://aka.ms/ss19
" target="_blank">Download and try SQL Server 2019</a></li>
</ul>

<p style="border-bottom: 1px solid lightgrey;"></p>

<h2><img style="float: left; margin: 0px 15px 15px 0px;" src="https://github.com/microsoft/sqlworkshops/blob/master/graphics/geopin.png?raw=true"><b>  Next Steps</b></h2>

Next, Continue to <a href="https://github.com/microsoft/sqlworkshops-sqlg2c/blob/master/sqlgroundtocloud/03-WorkingWithBigDataAndDataScienceBigDataClustersForSQLServer2019.md" target="_blank"><i> 03 - Working with Big Data Clusters on SQL Server 2019</i></a>.