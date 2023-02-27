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
We created our Active Directory Lab environment using this Network Diagram. In the center, we have our DC (or Domain Controller) where we installed a Server 2019 ISO with 2 Network Interface Card (NIC): the Internet (Network Address Translation (NAT)) and an Internal Network. We configured the Internal Network’s IP, Mask, and DNS information so that we could connect our Client server through the same Internal Network. We did not configure the Internet Network information as that is the router-to-VM connection. We gave this DC server a basic domain name and that is mydomain.com.
So, after creating our DC server, we created a second virtual environment, our Client1 server. We installed a Windows 10 ISO in this server, and through the Virtual Box Network, we are connected to the DC server through the Internal network connection.

<br />
<br />
<img src="https://i.imgur.com/Z5mdR4u.png" height="80%" width="80%" alt="Project4"/>

<br />
<br />
This slide shows the two virtual machines that created (ignore the linux one that we use for this class). The Domain Contorller (or DC) server, on the left, shows that under Network, we have those two connections: the Internet NAT, and an Internal Network. Meanwhile, the Client1 server on the right (that we use for attacks) only shows one network connection, and that’s the Internal Network, through the Domain Controller.  

<br />
<br />
<img src="https://i.imgur.com/YSCSvgz.png" height="80%" width="80%" alt="Project4"/>

<br />
<br />
In the Domain Controller (or DC) server, we have this Server Manager where we are able to add and change roles and features as we see fit. That includes configuring The Active Directory.

<br />
<br />
<img src="https://i.imgur.com/KoALKNt.png" height="80%" width="80%" alt="Project4"/>

<br />
<br />
And here we see the Active Directory Users and Computers feature where we are able to use Advanced Features to see user privileges that could be exploited in attacks, one of which is the KRBTGT user (or Kerberos Ticket-Get-Ticket user), that we will mention later in our Kerberos Golden Ticket attack scenario.

<br />
<br />
<img src="https://i.imgur.com/tSE178V.png" height="80%" width="80%" alt="Project4"/>

<br />
<br />
<img src="https://i.imgur.com/Vb9BGBS.png" height="80%" width="80%" alt="Project4"/>

<br />
<br />
Its primary objective is to gain unauthorized access to networks, systems, or applications, or to perform malicious activities such as privilege escalation or network traversal.
Mimikatz's capabilities depend on the attacker's goals, and it can be used in different ways, such as:

- Extracting passwords and credentials from a system's memory to gain access to networks, systems, or applications.
- Stealing credentials and bypassing authentication mechanisms, such as multi-factor authentication, to gain entry to sensitive data.
- Escalating privileges on a system, providing the attacker with access to critical data or enabling other malicious activities.
- Moving laterally within a network, enabling attackers to access additional systems or networks.
We created a scenario to show what can happen when information falls into the wrong hands.

<br />
<br />
<img src="https://i.imgur.com/kLbCawX.png" height="80%" width="80%" alt="Project4"/>

<br />
<br />
Aside from Mimikatz sounding like a fun group project, we chose to  demonstrate a few exploits that can be executed using this tool in an Active Directory environment. We will not be demonstrating where you can download this tool as it is super dangerous outside of a virtual environment. In this demonstration we will provide a scenario that could happen in real time when there isn’t  a set security infrastructure in place after starting a business. Also, adequate staffing and knowledgeable personnel to manage it.

<br />
<br />
<img src="https://i.imgur.com/6ikJnez.png" height="80%" width="80%" alt="Project4"/>

<br />
<br />
The Mimikatz exploits that we will be showcasing today are: “Clear-text credential dumping,” “Passing-the-hash,” and “Golden Ticket.”

- Dumping clear text credentials is obtaining account login and password information in the form of a hash or a clear text password.
- Pass-the-hash is an attack where a threat actor steals a hashed user credential and uses it to create a new user session on the same network. Most likely an admin user account.
- The Kerberos Golden Ticket is an attack used to impersonate any user in the domain, as a member of any group in the domain to provide access to anything in Active Directory at any time.

<br />
<br />
<img src="https://i.imgur.com/sV7jUKZ.png" height="80%" width="80%" alt="Project4"/>

<br />
<br />
<img src="https://i.imgur.com/n5REmUr.png" height="80%" width="80%" alt="Project4"/>

<br />
<br />
Scenario

- Openbook Corp is a start-up company that specializes in vacation home rentals. They just hired 2 new employees to take incoming calls and bookings online.
- Kirk Kingston and Antonio Bargo are the new hires. They both have the same title and should have user only access.
- Since this company is new they have a laxed IT/security policy and procedure protocol with a two person IT team for set-up and issues. They do not utilize a cloud IaaS system and everything is done manually onsite. Active Directory is the system used to manage access to their access accounts.

The first week Antonio notices his profile has admin access. After he knew the ethical thing to do was report it. He sent an email advising of the issue to his manager and went on about his day. He mentioned this to Kirk in the breakroom and this peaked Kirk’s Interest.  After this encounter Kirk noticed Antonio’s car license plate was Marvel inspired.  With these clues he decided to attempt to exploit Antonio’s privileges and take advantage of his access. He thought it would bring him fast money on the dark web. After multiple guessing attempts, he obtained Antonio’s password. Due to a low grade culture for security, Kirk was able to successfully download a tool called MimiKatz and gather more credential information.

<br />
<br />
<img src="https://i.imgur.com/hC3ZeMf.png" height="80%" width="80%" alt="Project4"/>

<br />
<br />
NOTE: Before we proceed we want to stress this warning. This was executed in a virtual lab environment. All data was made for this simulation and does not have any ties to active organizations. This scenario was made up for the sole purpose of this project.
The tool can be used for malicious purposes and engaging in other illegal activities.
Using Mimikatz may be considered a violation of laws and regulations, such as the Computer Fraud and Abuse Act (CFAA) and the General Data Protection Regulation (GDPR).
It can also compromise the confidentiality, integrity, and availability of an organization's data and systems. 

<br />
<br />
<img src="https://i.imgur.com/c5IQkio.png" height="80%" width="80%" alt="Project4"/>
<br />
<br />

[Demonstration video Credential Dumping ](https://youtu.be/eBQ7tkBQKQQ)
 
After Kirk successfully cracked Anton’s password he decided to execute his plan.

Having access to the admin privileges he was able to turn off his virus protection settings and anything that could detect his actions.

- Kirk has logged into his account and checks to see his access. it shows him as user only privilege.
- In order to run Mimikatz admin mode must be successfully accessible. He was able to bypass the UAC (User Account Control) pop up by entering in Antonio’s username and password he obtained.
- Once in, the syntax that Kirk uses is privilege::debug (PRIVILEGE::Debug) – gets debug rights (this or Local System rights is required for many Mimikatz commands).
      - A successful connection will display the following command privilege “20” OK
      - A failed attempt will display an error code. 
- The next syntax he enters is sekurlsa::longonpasswords (SEKURLSA::LogonPasswords) – lists all available provider credentials. This usually shows recently logged on user and computer credentials.
      - The clear text dump has been executed. 
- He now searches for the plaintext password and also gathers the hash to do the following exploit. 

<br />
<br />
<img src="https://i.imgur.com/x5n4VRa.png" height="80%" width="80%" alt="Project4"/>
<br />
<br />

 [Demonstration Pass-the-Hash](https://youtu.be/apYz6Yw24fg)
 
Pass-the-hash is another way to access the server without having a clear text password and can be done remotely. When entering the command line example in the demonstration it sends a request to the server and the server authenticates it with the stolen hash and grants permissions to move laterally to admin.

- The syntax he will use for this one is sekurlsa::pth /user:antbargo /domain:projectdomain.com /ntlm: paste the hash (SEKURLSA::Pth is for - Pass- the-Hash and Over-Pass-the-Hash. He entered the user, domain and hash to gain access to Antonio’s admin account. He is now in. 

With this information he can now conduct other exploits and cause more mayhem. 

<br />
<br />
<img src="https://i.imgur.com/i9jYekz.png" height="80%" width="80%" alt="Project4"/>
<br />
<br />
After running this command in the previous demonstration debug (PRIVILEGE::Debug) we are already in privilege access
The  sekurlsa::longonpasswords also displayed the admin users SID which is needed to complete the golden ticket attack.
To find the KRBTGT hash, use the comman lsadump::dcsync
LSADUMP::DCSync – (This asks the Domain Controller to synchronize an object (get password data for account)

- /all – DCSync pull data for the entire domain.
- /domain (optional) – FQDN of the Active Directory domain. Mimikatz will discover a DC in the domain to connect to. If this parameter is not provided, Mimikatz defaults to the current domain.
- /csv – export to csv (comma-separated values file)
KERBEROS::Golden – create golden tickets
The capability of this command is based on the password hash type retrieved.
A Golden Ticket can be created to impersonate any user in the domain as a member of any group in the domain, to any and every resource in the domain. Since the Golden Ticket is an authentication ticket, its scope is the entire domain. In short, once an attacker gets access to the KRBTGT password hash, they can create Golden Tickets (TGT) that provide access to anything in AD at any time.

<br />
<br />
<img src="https://i.imgur.com/1xM1T2E.png" height="80%" width="80%" alt="Project4"/>
<br />
<br />

<img src="https://i.imgur.com/GZaG0Yv.png" height="80%" width="80%" alt="Project4"/>
<br />
<br />
The action that antonio took by emailing his manager when noticing his access was a step in the right direction even though his password was not the strongest or the best. IT was escalated to the two person IT team and action was taken. In this  demonstration we will go over some steps to stop any further actions. 

- Debug Privilege - we will go to the Group Policy Management screen and locate the group policy. 
    - We will open in advanced view.
    - Window Settings - Security Settings - local policies - User rights assignment - debug programs 
- Make sure that define these policy settings is checked. Also make sure that any local admin users are removed. If needed - add in a group or person with debug access. This will block the privilege::debug command.

- Next we will Investigate the user and computers settings to see why Antonio had admin access when both Kirk and him should only have local user access. 
- The only other user that should have admin access is local admins. Another issue I see is that SQL Service has it’s password in the description which will also be updated.
		  - Users show that Antonio Bargo’s profile is present but not in the intended group. 
	  	- After verifying that Antonio has a duplicate account, the account with administration access will be deactivated and deleted. 
- After Investigating the user and computer settings we will go into the registry editor to disable the WDigest. 
- First we will got to HKEY_LOCAL_MACHINE - System - CurrentControlSet - Control - Security Provider and WDigest. There you will see UseLogonCredentials it’s currently on, hexadecimal is at “1”. We will now switch to “0” which is now turned off.  Completing this step willl block all open text information and set to “null” if previous securities are bypassed.
- We will then use powershell to put a local admin user  into the Protected Users Group, if there is a breach moving forward this specific user is protected and all credentials will be “null”.
   		-The command line for this is Add-ADGroupMember -Identity ‘Protected Users’ -Members (then the admin user name.)
Lastly there is no set step to stop a golden ticket attack. The best practice is to change the password for KEBTGT user frequently to disable any created tickets associated to this user. 

After these updates a system restart is need to activate the security changes. 

Now we will run Mimikatz in a-fernandez admin mode and run the same command as before.
			  - privilege::debug
		  	- debugged has been blocked showing an ERROR kuhl_privilege_simple ; RtladjustPrivilege (20) c0000061
- Next we will run command sekurlsa::Wdigest and the following error will show:
     - ERROR kuhl_sekurlsa_acquireLSA ; Handle on memory (0x00000005) 

Kirk will now log back in with Mimikatz to execute more exploits. As soon as he logs in, the antivirus detects an abnormality with the application Mimikatz and immediately quarantines/removes from his desktop. He then attempts to log in as Antonio and discovers that this account has been removed. With further review of the situation it was discovered that Kirk was an inside threat actor and immediately detained for investigation. 

<br />
<br />
<img src="https://i.imgur.com/XH2qcuL.png" height="80%" width="80%" alt="Project4"/>
<br />
<br />

<img src="https://i.imgur.com/7MxhyhF.png" height="80%" width="80%" alt="Project4"/>
<br />
<br />
Active Directory is a widely used Domain Service by companies, from large corporations such as hospitals and universities, to small businesses, like OpenBook Corp. Because of this, Active Directory is extensively exploited by threat actors for Privilege Escalation.
Mimikatz is a powerful open-source tool used by hackers to extract sensitive from a compromised Windows operating system. To protect against Mimikatz attacks, organizations should implement strong password policies, restrict local admin access and permissions, and regularly update their operating systems and security software. Implementing a strong security infrastructure is key for business continuity, preventing loss, supports compliance and preserving integrity for any organization.

<br />
<br />
<img src="https://i.imgur.com/hXVTiqY.png" height="80%" width="80%" alt="Project4"/>
<br />
<br />

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
