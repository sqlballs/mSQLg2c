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

SQL Server has traditionally been a Windows only product.  

<p>

SQL Server Editions

https://learn.microsoft.com/en-us/sql/sql-server/editions-and-components-of-sql-server-2019?view=sql-server-ver16#-editions


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
  <th align="center" colspan=4>SQL Server 2017</th>
</tr>
  <tr>
    <td>Platform</td>	
    <td>File System	</td>	
    <td>Installation Guide</td>
  </tr>
   <tr>
    <td>Red Hat Enterprise Linux 7.7 - 7.9, or 8.0 - 8.5 Server</td>	
    <td>XFS or EXT4</td>	
    <td><a href="https://learn.microsoft.com/en-us/sql/linux/quickstart-install-connect-red-hat?view=sql-server-ver16">Installation Guide</a></td>
  </tr>
   <tr>
    <td>SUSE Enterprise Linux Server v12 (SP3 - SP5)</td>	
    <td>XFS or EXT4</td>	
    <td><a href="https://learn.microsoft.com/en-us/sql/linux/quickstart-install-connect-suse?view=sql-server-ver16">Installation Guide</a></td>
  </tr>
   <tr>
    <td>Ubuntu 16.04 LTS 1, 18.04 LTS</td>	
    <td>XFS or EXT4</td>	
    <td><a href="https://learn.microsoft.com/en-us/sql/linux/quickstart-install-connect-ubuntu?view=sql-server-ver16">Installation Guide</a></td>
  </tr>
   <tr>
    <td>Docker Engine 1.8+ on Linux</td>	
    <td>N/A</td>	
    <td><a href="https://learn.microsoft.com/en-us/sql/linux/quickstart-install-connect-docker?view=sql-server-ver16&pivots=cs1-bash">Installation Guide</a></td>
  </tr>
</table>


<table border=1>
<tr>
  <th align="center" colspan=4>SQL Server 2019</th>
</tr>
  <tr>
    <td>Platform</td>	
    <td>File System	</td>	
    <td>Installation Guide</td>
  </tr>
   <tr>
    <td>Red Hat Enterprise Linux 7.7 - 7.9, or 8.0 - 8.5 Server</td>	
    <td>XFS or EXT4</td>	
    <td><a href="https://learn.microsoft.com/en-us/sql/linux/quickstart-install-connect-red-hat?view=sql-server-ver16">Installation Guide</a></td>
  </tr>
   <tr>
    <td>SUSE Enterprise Linux Server v12 (SP3 - SP5) or v15</td>	
    <td>XFS or EXT4</td>	
    <td><a href="https://learn.microsoft.com/en-us/sql/linux/quickstart-install-connect-suse?view=sql-server-ver16">Installation Guide</a></td>
  </tr>
   <tr>
    <td>Ubuntu 16.04 LTS 1, 18.04 LTS, 20.04 LTS</td>	
    <td>XFS or EXT4</td>	
    <td><a href="https://learn.microsoft.com/en-us/sql/linux/quickstart-install-connect-ubuntu?view=sql-server-ver16">Installation Guide</a></td>
  </tr>
   <tr>
    <td>Docker Engine 1.8+ on Linux</td>	
    <td>N/A</td>	
    <td><a href="https://learn.microsoft.com/en-us/sql/linux/quickstart-install-connect-docker?view=sql-server-ver16&pivots=cs1-bash">Installation Guide</a></td>
  </tr>
</table>

<table border=1>
<tr>
  <th align="center" colspan=4>SQL Server 2022</th>
</tr>
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



SQL Server 2022
- Regularly updated with CUs
- SQL server on Multipl OS containers: Red Hat, Ubuntu, Windows
- Machine Learning, Polybase, MSDTC, & Replication in Linux Containers




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
SQL Server continues to add advances towards deployment managability

https://learn.microsoft.com/en-us/sql/sql-server/what-s-new-in-sql-server-2022?view=sql-server-ver16#management

<h3>Tools</h3>

TODO: Topic Description

<h4>SQL Server Management Studio</h4>

TODO: Topic Description



<h4>Command-Line Utilities</h4>

TODO: Topic Description



<p><img style="float: left; margin: 0px 15px 15px 0px;" src="https://github.com/microsoft/sqlworkshops/blob/master/graphics/point1.png?raw=true"><b>Activity: TODO: Activity Name</b></p>

TODO: Activity Description and tasks

<p><b>Description</b></p>

TODO: Enter activity description with checkbox

<p><img style="margin: 0px 15px 15px 0px;" src="https://github.com/microsoft/sqlworkshops/blob/master/graphics/checkmark.png?raw=true"><b>Steps</b></p>

TODO: Enter activity steps description with checkbox

<p style="border-bottom: 1px solid lightgrey;"></p>

<h2 id="3.3"><img style="float: left; margin: 0px 15px 15px 0px;" src="https://github.com/microsoft/sqlworkshops/blob/master/graphics/pencil2.png?raw=true">3.3 Availability</h2>

SQL Server has multiple availability features

https://learn.microsoft.com/en-us/sql/sql-server/what-s-new-in-sql-server-2022?view=sql-server-ver16#availability

<p><img style="float: left; margin: 0px 15px 15px 0px;" src="https://github.com/microsoft/sqlworkshops/blob/master/graphics/point1.png?raw=true"><b>Activity: TODO: Activity Name</b></p>

TODO: Activity Description and tasks

<p><b>Description</b></p>

TODO: Enter activity description with checkbox

<p><img style="margin: 0px 15px 15px 0px;" src="https://github.com/microsoft/sqlworkshops/blob/master/graphics/checkmark.png?raw=true"><b>Steps</b></p>

TODO: Enter activity steps description with checkbox

<p style="border-bottom: 1px solid lightgrey;"></p>

<h2 id="3.4"><img style="float: left; margin: 0px 15px 15px 0px;" src="https://github.com/microsoft/sqlworkshops/blob/master/graphics/pencil2.png?raw=true">3.4 Performance</h2>

Performance is key for any SQL Server installation.

https://learn.microsoft.com/en-us/sql/sql-server/what-s-new-in-sql-server-2022?view=sql-server-ver16#performance

Additionally, performance is enhanced by the Query Store and intelligent query processing

https://learn.microsoft.com/en-us/sql/sql-server/what-s-new-in-sql-server-2022?view=sql-server-ver16#query-store-and-intelligent-query-processing

<p><img src="https://learn.microsoft.com/en-us/sql/relational-databases/performance/media/iqp-feature-family.svg?view=sql-server-ver16">

<p><img style="float: left; margin: 0px 15px 15px 0px;" src="https://github.com/microsoft/sqlworkshops/blob/master/graphics/point1.png?raw=true"><b>Activity: TODO: Activity Name</b></p>

Go to this link and read the MS Learn Article on using the Query Data Store

https://learn.microsoft.com/en-us/training/modules/explore-query-performance-optimization/5-explore-query-store

<p><b>Description</b></p>

TODO: Enter activity description with checkbox

<p><img style="margin: 0px 15px 15px 0px;" src="https://github.com/microsoft/sqlworkshops/blob/master/graphics/checkmark.png?raw=true"><b>Steps</b></p>

TODO: Enter activity steps description with checkbox

<p style="border-bottom: 1px solid lightgrey;"></p>

<h2 id="3.5"><img style="float: left; margin: 0px 15px 15px 0px;" src="https://github.com/microsoft/sqlworkshops/blob/master/graphics/pencil2.png?raw=true">3.5 Security</h2>

The integration of Azure and SQL Server has been enhanced to its best level yet. 

https://learn.microsoft.com/en-us/sql/sql-server/what-s-new-in-sql-server-2022?view=sql-server-ver16#security


<p><img style="float: left; margin: 0px 15px 15px 0px;" src="https://github.com/microsoft/sqlworkshops/blob/master/graphics/point1.png?raw=true"><b>Activity: TODO: Activity Name</b></p>

TODO: Activity Description and tasks

<p><b>Description</b></p>

TODO: Enter activity description with checkbox

<p><img style="margin: 0px 15px 15px 0px;" src="https://github.com/microsoft/sqlworkshops/blob/master/graphics/checkmark.png?raw=true"><b>Steps</b></p>

TODO: Enter activity steps description with checkbox

<p>
<img src="https://cloudblogs.microsoft.com/uploads/prod/sites/32/2022/05/SQL-Server-2022-slide_2022.05.22-update.webp">

<p><img style="margin: 0px 15px 15px 0px;" src="https://github.com/microsoft/sqlworkshops/blob/master/graphics/checkmark.png?raw=true"><b>Steps</b></p>

TODO: Enter activity steps description with checkbox

<p style="border-bottom: 1px solid lightgrey;"></p>

<h2 id="3.6"><img style="float: left; margin: 0px 15px 15px 0px;" src="https://github.com/microsoft/sqlworkshops/blob/master/graphics/pencil2.png?raw=true">3.6 Development</h2>

There are many advancements that assist with development.

https://learn.microsoft.com/en-us/sql/sql-server/what-s-new-in-sql-server-2022?view=sql-server-ver16#language


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


