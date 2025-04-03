# panel



SELECT 
    d.Name AS [Device Hostname],
    CASE 
        WHEN os.OSType = 'Windows' THEN 'Windows'
        ELSE 'Unix'
    END AS [Class],
    'BLOGGS – EUCS' AS [Vendor],
    d.SerialNumber AS [Serial Number],
    d.AssetTag AS [Asset tag],
    d.FITSCode AS [FITS Code],
    d.Manufacturer AS [Manufacturer],
    CONCAT(d.Manufacturer, ' ', d.Model) AS [Model ID],
    CASE 
        WHEN d.Status = 1 THEN 'In Use'
        ELSE 'In Maintenance (offline)'
    END AS [Status],
    d.Comments AS [Comments],
    d.Description AS [Description],
    d.FQDN AS [FQDN],
    CASE 
        WHEN d.IsVirtual = 1 THEN 'Yes'
        ELSE 'No'
    END AS [Virtual],
    'Production' AS [Environment],
    os.OSName AS [Operating System]
INTO 
    OUTFILE '/path/to/output.csv'
    FIELDS TERMINATED BY ',' 
    ENCLOSED BY '"'
    LINES TERMINATED BY '\n'
FROM 
    Device d
JOIN 
    OperatingSystem os ON d.OSId = os.Id
WHERE 
    d.Environment = 'Production';



https://community.spiceworks.com/t/wds-fails-to-start-when-obtain-ip-address-from-dchp-is-enabled/803866

SQL dig

select * from MTV_Computer 

select * from INFORMATION_SCHEMA.TABLES
where TABLE_NAME like '%computer%'
select * from INFORMATION_SCHEMA.COLUMNS
where COLUMN_NAME  like '%mac%'

https://kevinholman.com/2016/11/11/scom-sql-queries/




Get-SCOMGroup -DisplayName "UR Computer Group" | Get-SCOMClassInstance | GM

Get-SCOMGroup -DisplayName "UR Computer Group" | Get-SCOMClassInstance | sort DisplayName |FT DisplayName

How many cores does the WDS server have? We could try to limit the number of logical processors by using the BCDEDIT command-line tool together with the NUMPROC setting. For example, run the following command:
BCDEDIT /set NUMPROC 20

https://flylib.com/books/en/1.158.1.37/1/

https://www.red-gate.com/hub/product-learning/redgate-monitor/monitoring-your-servers-and-databases-scom-and-sql-monitor

https://learn.microsoft.com/zh-cn/training/modules/implement-common-integration-features-finance-ops/10-exercise-1

https://ccmexec.com/2019/11/how-to-provision-a-modern-application-during-osd/

https://lazyadmin.nl/office-365/smtp-relay-in-office-365/

https://learn.microsoft.com/en-us/system-center/scsm/service-catalog?view=sc-sm-2019&tabs=CopyRequestOffering%2CEditRequestOffering

Automation of Service Requests
https://marcelzehner.ch/2011/10/28/news-in-scsm12-beta-3-automation-of-service-requests/

[https://www.scsm.se/](https://www.scsm.se/?s=runbook)


You should be looking for the documentation for running the installation using a response file.
Running Oracle Universal Installer Using the Response File

After creating the response file, run Oracle Univeral Installer at the command line, specifying the response file you created, to perform the installation.

DRIVE_LETTER:\setup.exe_location setup [-silent] "variable=setting" [-nowelcome] [-noconfig] [-nowait] -responseFile filename 
Here is an example of a batch script that I use.

The script runs with a single click to install the Oracle Client.

cd "c:\src\oracle"
powershell Expand-Archive c:\src\oracle\V982658-01.zip c:\src\oracle\
c:\src\oracle\client\setup.exe -silent -showprogress -nowait -noconfig -responseFile C:\src\oracle\client.rsp

Here are some lines from my response file

 ORACLE_HOME=C:\oracle\product\19.0.0\client_1
 oracle.install.client.customComponents=oracle.rdbms.util:19.0.0.0.0,oracle.sqlplus:19.0.0.0.0,oracle.network.client:19.0.0.0.0,oracle.odbc:19.0.0.0.0,oracle.ntoledb.odp_net_2:19.0.0.0.0
 installing Oracle Client for Windows
 https://www.reddit.com/r/oracle/comments/sy8eda/installing_oracle_client_for_windows/

 Database Client Installation Guide for Microsoft Windows
 https://docs.oracle.com/en/database/oracle/oracle-database/19/ntcli/reasons-for-using-silent-mode-or-response-file-mode.html



 How does CPU monitoring work in the Windows Server 2016 management pack?
 https://kevinholman.com/2017/05/13/how-does-cpu-monitoring-work-in-the-windows-server-2016-management-pack/

 SCOM 2016 dashboard view to display resource utilization of all servers
 https://learn.microsoft.com/en-us/answers/questions/400683/scom-2016-dashboard-view-to-display-resource-utili



 https://kevinholman.com/2022/07/14/scom-dashboards-using-the-powershell-grid-widget/
