<h1>Hacking an Active Directory VM</h1>

<h2>Description</h2>
This project demonstrates how to set up an Active Directory via Oracle Virtual Box. With it's own network set up for a mock corporation to showcase how an organization utilizes an (IAM) system. Also, how to use a hacking tool called Mimikatz to exploit and show vulnerabilites. 


<b>WARNING</b>
This presentation was in a virtual environment, the use if this tool is highly illigal and dangerous. 
<br />


<h2>Languages and Utilities Used</h2>

- <b>Oracle Virtual Box</b>
- <b>PowerShell</b> 
- <b>GUI</b>
- <b>GitHub</b>

<h2>Environments Used </h2>

- <b>Windows 10 ISO</b> 
- <b>Windows Server 2019 ISO</b>

<h2>Program walk-through:</h2>

<p align="center">
Presentation: <br/>
<img src="https://i.imgur.com/V5MgNvN.png" height="80%" width="80%" alt="Project4"/>
<br />
<br />

<img src="https://i.imgur.com/Si3gMTs.png" height="80%" width="80%" alt="Project4"/>
<br />
<br />
This presentation consists of: a brief refresher of Microsoft’s Active Directory, including setting up two lab environments that we created using Oracle’s Virtual Machine: one for our Domain Controller, which houses Active Directory, and a Client server that we used to attack our Domain Controller (DC) server using Mimikatz. We will also be sharing a scenario that we created virtually and demonstrating three exploits that you could do with Mimikatz: credential dumping, pass-the-hash, and the Kerberos Golden Ticket. Lastly, we will be sharing some mitigation techniques and ending our presentation with a summary of our findings.

<br/>
<br/>
<img src="https://i.imgur.com/X2hqJsM.png" height="80%" width="80%" alt="Project4"/>
<br />
<br />

<img src="https://i.imgur.com/pPlqEfD.png" height="80%" width="80%" alt="Project 4"/>
<br />
<br />
So, what is the importance of Active Directory? Microsoft’s Active Directory is widely used among many companies, from large corporations like 95% of the Fortune 1000 Companies, to small businesses like start-up organizations. It is a crucial part of Identity and Access Management (IAM) because it determines user and group access and privileges.
Building your own Active Directory Lab is important in gaining experience with Ethical Hacking and Penetration Testing. With an Active Directory Lab, one can execute AD DS attack scenarios (without actually committing anything illegal) and be familiar with mitigation tactics for such attacks.

<br />
<br />
<img src="https://i.imgur.com/7NSOlYy.png" height="80%" width="80%" alt="Project4"/>
<br />
<br />
Sanitization complete:  <br/>
<br />
<br />
<img src="https://i.imgur.com/Z5mdR4u.png" height="80%" width="80%" alt="Project4"/>
<br />
<br />
Observe the wiped disk:  <br/>
<br />
<br />
<img src="https://i.imgur.com/YSCSvgz.png" height="80%" width="80%" alt="Project4"/>
<br />
<br />
Sanitization complete:  <br/>
<br />
<br />
<img src="https://i.imgur.com/KoALKNt.png" height="80%" width="80%" alt="Project4"/>
<br />
<br />
Sanitization complete:  <br/>
<br />
<br />
<img src="https://i.imgur.com/tSE178V.png" height="80%" width="80%" alt="Project4"/>
<br />
<br />
Sanitization complete:  <br/>
<br />
<br />
<img src="https://i.imgur.com/Vb9BGBS.png" height="80%" width="80%" alt="Project4"/>
<br />
<br />
Sanitization complete:  <br/>
<img src="https://i.imgur.com/kLbCawX.png" height="80%" width="80%" alt="Project4"/>
<br />
<br />
Sanitization complete:  <br/>
<img src="https://i.imgur.com/6ikJnez.png" height="80%" width="80%" alt="Project4"/>
<br />
<br />
Sanitization complete:  <br/>
<img src="https://i.imgur.com/sV7jUKZ.png" height="80%" width="80%" alt="Project4"/>
<br />
<br />
Sanitization complete:  <br/>
<img src="https://i.imgur.com/n5REmUr.png" height="80%" width="80%" alt="Project4"/>
<br />
<br />
Sanitization complete:  <br/>
<img src="https://i.imgur.com/hC3ZeMf.png" height="80%" width="80%" alt="Project4"/>
<br />
<br />
Sanitization complete:  <br/>
<img src="https://i.imgur.com/c5IQkio.png" height="80%" width="80%" alt="Project4"/>
<br />
<br />
Sanitization complete:  <br/>
<img src="https://i.imgur.com/x5n4VRa.png" height="80%" width="80%" alt="Project4"/>
<br />
<br />
Sanitization complete:  <br/>
<img src="https://i.imgur.com/i9jYekz.png" height="80%" width="80%" alt="Project4"/>
<br />
<br />
Sanitization complete:  <br/>
<img src="https://i.imgur.com/1xM1T2E.png" height="80%" width="80%" alt="Project4"/>
<br />
<br />
Sanitization complete:  <br/>
<img src="https://i.imgur.com/GZaG0Yv.png" height="80%" width="80%" alt="Project4"/>
<br />
<br />
Sanitization complete:  <br/>
<img src="https://i.imgur.com/XH2qcuL.png" height="80%" width="80%" alt="Project4"/>
<br />
<br />
Sanitization complete:  <br/>
<img src="https://i.imgur.com/7MxhyhF.png" height="80%" width="80%" alt="Project4"/>
<br />
<br />
Sanitization complete:  <br/>
<img src="https://i.imgur.com/hXVTiqY.png" height="80%" width="80%" alt="Project4"/>

</p>

<!--
 ```diff
- text in red
+ text in green
! text in orange
# text in gray
@@ text in purple (and bold)@@
```
--!>
