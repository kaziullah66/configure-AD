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
<img src="https://scontent-lga3-1.xx.fbcdn.net/v/t1.15752-9/462582425_1222415168882979_7355444991904108241_n.png?_nc_cat=102&ccb=1-7&_nc_sid=9f807c&_nc_ohc=Y29y7jAnSVUQ7kNvgHGqsc-&_nc_zt=23&_nc_ht=scontent-lga3-1.xx&_nc_gid=AnFKE3kHVPt-YrXO53Bl-7a&oh=03_Q7cD1QEB9U5-WLuih82L_OOX8659UaoZo46sHzZNXvZGi18HJQ&oe=6741BA82"/>
</p>
<p>
We have gone into the domain controller and verified that client-1 is part of our domain.
</p>
<br />
<br />

<p>
<img src="https://scontent-lga3-1.xx.fbcdn.net/v/t1.15752-9/462554686_924252013141893_7102575562790680270_n.png?_nc_cat=111&ccb=1-7&_nc_sid=9f807c&_nc_ohc=Tm3jwZfoOXwQ7kNvgH6-WIm&_nc_zt=23&_nc_ht=scontent-lga3-1.xx&_nc_gid=AIh6LNamIj0y6xWKNrVVmQc&oh=03_Q7cD1QH0BtYNRNQZnhlXuE9kmWFXNoBUiJTyVU09Z-fMWSFsfQ&oe=6741A79A"/>
</p>
<p>
We are allowing all domain users to remotely access the PC.
</p>
<br />
<br />

<p>
<img src="https://scontent-lga3-2.xx.fbcdn.net/v/t1.15752-9/462576772_2506724679533735_4117456061274827569_n.png?_nc_cat=100&ccb=1-7&_nc_sid=9f807c&_nc_ohc=11pieaCYzRIQ7kNvgHLnt_r&_nc_zt=23&_nc_ht=scontent-lga3-2.xx&_nc_gid=A1mZ_U4Rr-kQ5xH7SzLigPT&oh=03_Q7cD1QGZgWZUms03YZBS5DtAoaEsy5cevSEp4Z-vbNWI5l7WFA&oe=6741C684"/>
</p>
<p>
We executed a script in PowerShell ISE to generate users automatically.
</p>
<br />
<br />

<p>
<img src="https://scontent-lga3-2.xx.fbcdn.net/v/t1.15752-9/462550929_1066804998186675_9130706739649671000_n.png?_nc_cat=104&ccb=1-7&_nc_sid=9f807c&_nc_ohc=l55lZavBLLoQ7kNvgGnYBtm&_nc_zt=23&_nc_ht=scontent-lga3-2.xx&_nc_gid=A2WjZtejZI6vJZX7Byz83kI&oh=03_Q7cD1QFREgmdE2vLabkE6cVBOotWuNH-PyreqUK2o1bh-5x7iA&oe=6741DB4C"/>
</p>
<p>
Configuring account lockout using group policy.
</p>
<br />
<br />

<p>
<img src="https://scontent-lga3-1.xx.fbcdn.net/v/t1.15752-9/462543821_421692060729740_5854094042945118481_n.png?_nc_cat=106&ccb=1-7&_nc_sid=9f807c&_nc_ohc=_O9HU4pd0qQQ7kNvgEfZbnE&_nc_zt=23&_nc_ht=scontent-lga3-1.xx&_nc_gid=AGtl4b9bG67MgpjRyh6WePd&oh=03_Q7cD1QGIJHZmwixlK0VZJZyiDJrRnGj88Mm4htk_o80Woj9FHw&oe=6741BFEC"/>
</p>
<p>
The settings we have configured.
</p>
<br />
<br />

<p>
<img src="https://scontent-lga3-1.xx.fbcdn.net/v/t1.15752-9/462545433_1600878863838658_8253734063730560181_n.png?_nc_cat=106&ccb=1-7&_nc_sid=9f807c&_nc_ohc=f5fZej0IPO4Q7kNvgHVx3zw&_nc_zt=23&_nc_ht=scontent-lga3-1.xx&_nc_gid=ACWQWmnoOgmOSFY6N4GNff7&oh=03_Q7cD1QGdBFzryJle8R-4jtOuzy7CvLCXNrq4ltfPoHzE_QtMOg&oe=6741BAE7"/>
</p>
<p>
We purposefully entered the password wrong more than 5 times to see if our policy is working.
</p>
<br />
<br />

<p>
<img src="https://scontent-lga3-1.xx.fbcdn.net/v/t1.15752-9/462557084_8829009907120859_2819970291575015900_n.png?_nc_cat=106&ccb=1-7&_nc_sid=9f807c&_nc_ohc=ZBUTTXL5GLIQ7kNvgHF-MCh&_nc_zt=23&_nc_ht=scontent-lga3-1.xx&_nc_gid=AHl_TuGCRgjMfpuiLDL7s27&oh=03_Q7cD1QH-wPE480CI8PjerReLGNLBScGkdipYTP_wTL1vwJsMng&oe=6741D106"/>
</p>
<p>
We went into active directory users and computers to unlock the account.
</p>
<br />
<br />

<p>
<img src="https://scontent-lga3-2.xx.fbcdn.net/v/t1.15752-9/462573099_1301300307706458_7735234221026851475_n.png?_nc_cat=104&ccb=1-7&_nc_sid=9f807c&_nc_ohc=iPaQFCw4HJ8Q7kNvgHLo92K&_nc_zt=23&_nc_ht=scontent-lga3-2.xx&_nc_gid=AKYZaqb1wNAoZwz4d-YXrB8&oh=03_Q7cD1QG_rwN6YO1SxtuNkGCR3ZB78DUKN64kd7JJ0j7w_WGOVg&oe=6741B05E"/>
</p>
<p>
We have gained access to this account.
</p>
<br />
<br />

