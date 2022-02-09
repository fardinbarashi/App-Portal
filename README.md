# App-Portal




<!-- TABLE OF CONTENTS -->
<details>
  <summary>Table of Contents</summary>
  <ol>
    <li>
      <a href="#AppPortal">About The Project</a>
    </li>
    <li>
      <a href="#install">Install</a>
      <ul><li><a href="#create-database">Create Database</a></li></ul>
      <ul><li><a href="#monitorobjects">MonitorObjects</a></li></ul>
      <ul><li><a href="#bot">Bot</a></li></ul>
    <li><a href="#roadmap">Roadmap</a></li>
    <li><a href="#contributing">Contributing</a></li>
    <li><a href="#license">License</a></li>
    <li><a href="#contact">Contact</a></li>
    <li><a href="#acknowledgments">Acknowledgments</a></li>
  </ol>
</details>

<!-- APPPORTAL  -->
## AppPortal 
is a concept on how to monitor Data by using MS-SQL and Powershell, so it is necessary to install 
MS-SQL and Invoke-SQL module ( Download SQL Studio managment or download the modules from 
https://docs.microsoft.com/en-us/sql/powershell/download-sql-server-ps-module?view=sql-server-ver15 ) 
recommended Powershell version 7, Works with powershell 5.1.
Office 365 is required for the bot and Teamsfunction.

<!-- INSTALL -->
## Install 

<!-- DATABASE -->
## Create Database 
To create database AppPortal Run the code in MS T-SQL 

```
-- Create Database Start
CREATE DATABASE AppPortal
-- Create Database End
```

<!-- MONITOROBJECTS -->
## MonitorObjects
This Table contains objects like files,licence, certification and much more that which need to be monitored.
Install MS-SQL and Invoke-SQL module ( Download SQL Studio managment or download the modules from 
https://docs.microsoft.com/en-us/sql/powershell/download-sql-server-ps-module?view=sql-server-ver15 ) 
recommended Powershell version 7, Works with powershell 5.1.
```
- Column       -     Contains           -     Example
- ID          -     Primary Key         -     Example : 1
- ServerName  -     ServerName          -     Example : Web01.Google.com
- ExpireDate  -     Object Expire Date  -     Example : The date on which the object will expire, Example : 2022-03-24 00:00:00.000
- ObjectName  -     Name on the object  -     Example : Web-DNS-Certification
- Enviroment  -     Enviroment type     -     Example : Sandbox
- Template    -     TemplateType        -     Example : WebServer
- Description -     Description         -     Example : This i a Certification
- Office      -     Office              -     Example : Google HQ Second Floor
- System      -     SystemName          -     Example : GCP Google Cloud Platform
- Message     -     Specfic message     -     Example : Check FAQ for solution   
 ```
---------------------------------------------

## Create Table MonitorObjects
Run the code in MS T-SQL 
```
-- Create Table MonitorObjects Start
CREATE TABLE MonitorObjects (
 ID bigint PRIMARY KEY NOT NULL,
 ServerName varchar(MAX) NULL,
 ExpireDate datetime NOT NULL,
 ObjectName varchar(MAX) NULL,
 Enviroment varchar(MAX) NULL,
 Template varchar(MAX) NULL,
 Description varchar(MAX) NULL,
 Office varchar(MAX) NULL,
 System varchar(MAX) NULL,
 SharePointUrl varchar(MAX) NULL,
 Message varchar(MAX)
);
-- Create Table MonitorObjects End
```

## Script MonitorObjects
Download the latest MonitorObjects Year-Month-Date.zip.
 
Change the Strings 

``` 
Row - String 
16 - $Mailto = "" 
17 - $MailFrom = "" 
18 - $SmtpServer = ""
```

<!-- BOT -->
## Bot
This Table contains contains objects that will start the same day as todaydate.
Install MS-SQL and Invoke-SQL module ( Download SQL Studio managment or download the modules from 
https://docs.microsoft.com/en-us/sql/powershell/download-sql-server-ps-module?view=sql-server-ver15 ) 
recommended Powershell version 7, Works with powershell 5.1.
```
- Column                -     Contains               -     Example
- ID                    -     Primary Key            -     Example : 1
- TodaysEvent           -     Todays Event           -     Example : 2022-02-08 00:00:00.000
- TodaysEventDateStart  -     When the event starts  -     Example : 2022-02-08 09:00:00.000
- TodaysEventDateEnd    -     When the event end     -     Example : 2022-02-08 16:15:00.000
- System                -     System Name            -     Example : Micrsoft Exchange
- CurrentVersion        -     Current Version        -     Example : Version 1.0
- UpgradeVersion        -     Upgrade Version        -     Example : Version 1.1
- TaskDescription       -     Description of Task    -     Example : Upgrade from 1.0 to 1.1
- SupplierTicket        -     Supplier Ticket        -     Example : 123456872
- ChangeRequest         -     Change Request Nr      -     Example : CR123412349
- SandBox               -     Name on the enviroment -     Example : Sandbox01
- Production            -     Name on the enviroment -     Example : Production01
- Message               -     Message                -     Example : Today we are going to upgrade our Exchange in Sandbox
 ```

## Create Table BOT
Run the code in MS T-SQL 
```
-- Create Table Bot Start
CREATE TABLE Bot (
 ID bigint PRIMARY KEY NOT NULL,
 TodaysEvent  datetime NOT NULL,
 TodaysEventDateStart  datetime NOT NULL,
 TodaysEventDateEnd  datetime NOT NULL,
 System varchar(MAX) NULL,
 CurrentVersion varchar(MAX) NULL,
 UpgradeVersion varchar(MAX) NULL,
 TaskDescription varchar(MAX) NULL,
 SupplierTicket varchar(MAX) NULL,
 ChangeRequest varchar(MAX) NULL,
 SandBox varchar(MAX) NULL,
 Production varchar(MAX) NULL,
 Message varchar(MAX) NOT NULL
);
-- Create Table Bot End
```

## Script BOT
Download the latest BOT Year-Month-Date.zip.
 
Change the Strings 

``` 
Row - String 
16 - $Mailto = "" 
17 - $MailFrom = "" 
18 - $SmtpServer = ""
247 - summary
249 - title
256 - URI
```
