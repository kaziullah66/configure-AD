<p align="center">
<img src="https://i.imgur.com/pU5A58S.png" alt="Microsoft Active Directory Logo"/>
</p>

<h1>On-premises Active Directory Deployed in the Cloud (Azure)</h1>
This tutorial outlines the implementation of on-premises Active Directory within Azure Virtual Machines.<br />


<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Active Directory Domain Services
- PowerShell

<h2>Operating Systems Used </h2>

- Windows Server 2022
- Windows 10 (21H2)

<h2>Deployment and Configuration Steps</h2>

<p>
<img src="https://i.imgur.com/DNioZgA.png"/>
</p>
<p>
We created two virtual machines. One acts as a domain controller, and the other acts as a normal user.
</p>
<br />
<br />

<p>
<img src=https://i.imgur.com/bc845ur.jpeg"/>
</p>
<p>
We deactivated the firewalls.
</p>
<br />
<br />

<p>
<img src="https://i.imgur.com/6M9jKwI.png"/>
</p>
<p>
We reconfigured the DNS settings on the Network Interface Card (NIC) to point from the Microsoft DNS server to our domain controller (dc-1).
</p>
<br />
<br />

<p>
<img src="https://i.imgur.com/Fp1PM1F.png"/>
</p>
<p>
We pinged dc-1(domain controller).
</p>
<br />
<br />

<p>
<img src="https://i.imgur.com/Jsp3CqR.png"/>
<img src="https://i.imgur.com/K2oJ0kh.png"/>
</p>
<p>
We confirmed the connection to the domain controller by ensuring it is mapped to its private IP address.
</p>
<br />
<br />

<p>
<img src="https://i.imgur.com/eLSkfNl.png"/>
</p>
<p>
Creating new Organizational Units for new users.
</p>
<br />
<br />

<p>
<img src="https://i.imgur.com/GnRRes6.png"/>
</p>
<p>
Creating a new user in our _ADMINS organizational unit.
</p>
<br />
<br />

<p>
<img src="https://i.imgur.com/5ayJx2t.png"/>
</p>
<p>
We created a user and assigned him domain admin privileges.
</p>
<br />
<br />


<p>
<img src="https://i.imgur.com/NAPpVfp.png"/>
</p>
<p>
Joining client-1(our other virtual machine) to the domain.
</p>
<br />
<br />


<p>
<img src="https://i.imgur.com/vNYEZps.png"/>
</p>
<p>
We have gone into the domain controller and verified that client-1 is part of our domain.
</p>
<br />
<br />

<p>
<img src="https://i.imgur.com/tsizrod.png"/>
</p>
<p>
We are allowing all domain users to remotely access the PC.
</p>
<br />
<br />

<p>
<img src="https://i.imgur.com/15r18B3.png"/>
</p>
<p>
We executed a script in PowerShell ISE to generate users automatically.
</p>
<br />
<br />

<p>
<img src="https://i.imgur.com/NxMdLTU.png"/>
</p>
<p>
Configuring account lockout using group policy.
</p>
<br />
<br />

<p>
<img src="https://i.imgur.com/0lZrwux.png"/>
</p>
<p>
The settings we have configured.
</p>
<br />
<br />

<p>
<img src="https://i.imgur.com/jUn5tpB.png"/>
</p>
<p>
We purposefully entered the password wrong more than 5 times to see if our policy is working.
</p>
<br />
<br />

<p>
<img src="https://i.imgur.com/bpCUNjC.png"/>
</p>
<p>
We went into active directory users and computers to unlock the account.
</p>
<br />
<br />

<p>
<img src="https://i.imgur.com/9kiPm60.png"/>
</p>
<p>
We have gained access to this account.
</p>
<br />
<br />

