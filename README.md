# panel

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
