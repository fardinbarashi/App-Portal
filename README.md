# App-Portal

## AppPortal 
is a concept on how to monitor Data by using MS-SQL and Powershell, so it is necessary to install 
MS-SQL and Invoke-SQL module ( Download SQL Studio managment or download the modules from 
https://docs.microsoft.com/en-us/sql/powershell/download-sql-server-ps-module?view=sql-server-ver15 ) 

## Create Database 
Run the code in MS T-SQL 

```
-- Create Database Start
CREATE DATABASE AppPortal
-- Create Database End
```


## Table MonitorObjects
This Table contains objects liks files,licence, certification and much more that which need to be monitored.
```
- Table       -     Contains            -     Example
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
 ExpireDate datetime NULL,
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
$Mailto = "" 
$MailFrom = "" 
$SmtpServer = ""
```
