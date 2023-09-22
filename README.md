<h1>Common Locations of Windows Artifacts Lab</h1>


<h2>Description</h2>
In this lab, I enumerate hosts on the network using various tools by evaluating event, web, and tasks. Also, I explore the startup, windows, and system32 folders. It includes the following tasks:
<br />
<br />
- <b>Examine Windows Event Logs, IIS Logs, and Scheduled Tasks</b> 
<br />
- <b>Examine the Startup, Windows, and System32 Folders</b>
<br />


<h2>Software and Utilities Used</h2>

- <b>BGInfo</b>

<h2>Environments Used </h2>
- <b>InfoSec Learning Labs</b> 
<br />
- <b>Kali Linux</b> 
<br />
- <b>Windows 7 Pro</b>


<h2>Lab Walkthrough:</h2>

<p align="center">

Log into Windows <br/>
<img src="https://i.imgur.com/DCG51zt.png" height="80%" width="80%" alt="Log into Windows"/>
<br />
<br />
Using the command prompt, add a guest user to the backup operators group.<br/>
<img src="https://i.imgur.com/dg2QUXk.png" height="80%" width="80%" alt="Investigate FAT32"/>
<br />
<br />
Open the Event Viewer <br/>
<img src="https://i.imgur.com/2F1cBm7.png" height="80%" width="80%" alt="check quota and security tabs"/>
<br />
<br />
Under Windows Logs > Security, use the find function to look for "guest"<br/>
<img src="https://i.imgur.com/IoiycH8.png" height="80%" width="80%" alt="hide file using ADS"/>
<br />
<br />
See the security group management event that logged when guest was added to the backup operators group.<br/>
<img src="https://i.imgur.com/8eoP93B.png" height="80%" width="80%" alt="check ads"/>
<br />
<br />
Use the command line to view the Event Viewer files on Windows 7 <br/>
<img src="https://i.imgur.com/WQnbsEa.png" height="80%" width="80%" alt="dir /r"/>
<br />
<br />
Log into Kali Linux<br/>
<img src="https://i.imgur.com/0jXsome.png" height="80%" width="80%" alt="dir /r"/>
<br />
<br />
On the IceWeasel browser, go to web server at http://216.5.1.200 <br/>
<img src="https://i.imgur.com/MNV2yDl.png" height="80%" width="80%" alt="dir /r"/>
<br />
<br />
On Windows 7, got to the folder C:\inetpub\logs\LogFiles\W3SVC1. This is the log file for the Web server hosted within Microsoft Internet Information Services (IIS). Open the log file and examine the IP address information<br/>
<img src="https://i.imgur.com/W3ARAkU.png" height="80%" width="80%" alt="analyze first partition"/>
<br />
<br />
Using the command prompt, create a scheduled task   <br/>
<img src="https://i.imgur.com/l4FrZcf.png" height="80%" width="80%" alt="analyze next 3 partitions"/>
<br />
<br />
Go to folder C:\Windows\Tasks. Open the At1.job file using WordPad. Notice the IP Address and the word SYSTEM. <br/>
<img src="https://i.imgur.com/pcxapfq.png" height="80%" width="80%" alt="log into Kali Linux"/>
<br />
<br />
Make BGInfo start with windows by copying the bginfo.exe files to the Startup folder using the command prompt <br/>
<img src="https://i.imgur.com/u9E3r51.png" height="80%" width="80%" alt="create admin user"/>
<br />
<br />
Log off and back on. The BGInfo - Default configuration window will appear on the screen, then shortly specific information about the system will appear on the desktop.<br/>
<img src="https://i.imgur.com/5ij5nu2.png" height="80%" width="80%" alt="check md5sum"/>
<br />
<br />
View the Windows PATH using the command prompt <br/>
<img src="https://i.imgur.com/S5NzqUv.png" height="80%" width="80%" alt="check sha1sum"/>
<br />
<br />
Create a batch file that will echo the dir command in the root of C<br/>
<img src="https://i.imgur.com/dYmQ0ra.png" height="80%" width="80%" alt="Autopsy"/>
<br />
<br />
Copy the batch file to the Windows directory and run it.
<img src="https://i.imgur.com/cjMypWw.png" height="80%" width="80%" alt="new case"/>
<br />
<br />
Go to the folder C:\Windows\System32 and sort by date modified, notice the batch file at the top. <br/>
<img src="https://i.imgur.com/WynQGlO.png" height="80%" width="80%" alt="add host"/>
<br />
<br />

<h2>Conclusion </h2>
In modern Windows systems (Vista and newer), Event Viewer logs are stored in EVTX format within Windows\System32\winevt\Logs, while older systems like Windows XP use the EVT format stored in Windows\System32\config alongside Windows registry files. These logs offer a chronological record of events, aiding forensic investigators in determining IP addresses, connection timestamps, and tracking suspicious activities. It's essential for investigators to pinpoint and scrutinize these files, as well as other system-generated artifacts such as those from service activations or tasks initiated with the "at" command. Frequently, investigators also assess recently added files, particularly in Windows' primary directories, given their inclusion in the system's PATH. On Linux systems, partitions are formatted using the "mkfs" command and then mounted for data storage purposes.
