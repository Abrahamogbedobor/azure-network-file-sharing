<p align="center">
<img src="https://i.imgur.com/EqUaRWN.png" alt="Azure Network File Sharing and Permission"/>
</p>

<h1>Network File Sharing and Permission</h1>
In this project, files was shared on azure network with different level of users permission<br />

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Active Directory running in Azure on a Virtual Machine (DC_1)
- A client machine running in Azure on a virtual machine (Client_1) and joined to the domain

<h2>Operating Systems Used</h2>

- Windows 10 (21H2)
- Window Server 2022

<h2>High-Level Steps</h2>

- General overview of network file sharing such as: (what, when, where, why, and how)
- Create and test some file shares
- Security groups such as 'Windows and Active Directory'
- Create and test some security groups
- Resource Cleaning

<h2>Actions and Observations</h2>

<p>
<img src="https://i.imgur.com/XXCCKwM.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
The above figure was used to illustrate a general overview of network file sharing in an organsation using an employee named Bob as a case study. From the figure, three files was shared coming from three different sources (named server x, y, and z). These files was shared to Bob with different level of permission granted as the files are coming from different department. With the files coming from server x, bob could only READ. Those coming from server y, Bob could READ and WRITE, and finally files coming from server z, Bob have no ACCESS to them whatsoever. File sharing could be implemented when creating documents for the public such as youtube whereby viewers can only view/read contents. Also, during team collaboration files could be share for everyone to read and write. This lab further uses window in active directory to explain this file sharing concept.
</p>
<br />

<p>
<img src="https://i.imgur.com/KKaXkE0.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
The above figures outlines the steps used to create some files and share with permission. First, connection was made to DC-1 using the domain admin account that was created bryanogbe.com\abraham_admin, then a connection into Client-1 using one of those random user that was created. Then on DC-1 on C:DRIVE, four folders was then created which includes "read-access", "write-access", "no-access", and "acounting". Again, share the following permission and folder created on DC-1 to the 'Domain Users' group 1. Read-access FOLDER to domain users permission GROUP READ 2. Write-access FOLDER to domain users permission GROUP READ/WRITE 3. No-access FOLDER to domain admins permission GROUP READ/WRITE. Then SKIP accounting for the now. Notice, the network file sharing part each time a file has been shared.
</p>
<br />

<p>
<img src="https://i.imgur.com/QcT4OzG.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/5SgRiiO.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/X9pKe10.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Furthermore, Client-1 was logged into as a normal user then an observation was made to one of those shared folders with the aim of knowing which files users could access and which files users are unable to access. The folder with read only Cloient-1 was truly only to open it but unable to write on it as access was denied. Second figure is read/write meaning client-1 was able to open the file and add his/her contribution as shown above. Third figure Client-1 was unable to open it because it was given no access to read/write.
</p>
<br />

<p>
<img src="https://i.imgur.com/4XVCYbE.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/2mONjWS.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/Aordyjj.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
The accounting folder that was previously created was used as a file sharing security group on this lab. Meaning, only individuals who are in the accounting group would have access to read/write on that folder. Firstly, in Active Directory on DC-1 a new OU was created called 'SECURITY GROUPS' and then ACCOUNTANTS and CYBERSECURITY was created as a new groups inside that OU security groups. Then, the accounting folder that was created in c:drive\\, the accountants security group was assigned to it and a read/write access was granted as shown in figure2.Then, in Client-1 computer a user tried accessing the accounting folder but his access was denied. Hence, that user needed to be added to the accountants security grop on DC-1 computer so as many other users in a real life scenario. Meaning, instead of adding just badi.vag, we could add 'domain users' if we are to give access to all users into accountants SG.
</p>
<br />

<p>
<img src="https://i.imgur.com/yl2Lepb.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/ezj6pBm.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
The name of the user who failed to access the accountants folder security groups was badi vag thus, he was added to the security groups on DC-1 as shown above. Theoretically, Badi Vag was now able to open the accounting folder but, he must first sign-out and sign back for the changes made to be effective. Badi Vag is now able to read/write on the accountants folder.
</p>
<br />

<p>
<img src="https://i.imgur.com/kPaz05h.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/071H6Ti.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/slDhMOL.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Lastly, on this lab a folder called Helpdesk was created and a random user from Client-1 (Baj Ter) tried to access it but access was denied. Thus, his permission was granted on DC-1 Cybercurity SG which then enabled him to gain access to Helpdesk folder and files. User Baj.ter is now able to open and write on the folder helpdesk as shown above.
</p>
<br />
