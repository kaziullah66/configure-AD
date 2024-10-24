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

<h2>High-Level Deployment and Configuration Steps</h2>

- Step 1
- Step 2
- Step 3
- Step 4

<h2>Deployment and Configuration Steps</h2>

<p>
<img src="https://scontent-lga3-1.xx.fbcdn.net/v/t1.15752-9/462544246_1235664007678390_3086403986479741365_n.png?_nc_cat=106&ccb=1-7&_nc_sid=9f807c&_nc_ohc=Wg-0S3w1jAwQ7kNvgESYs3T&_nc_zt=23&_nc_ht=scontent-lga3-1.xx&_nc_gid=Abqi_KPEuNkhc_Q1aQhrpse&oh=03_Q7cD1QHqPYx5Gvyk2Uzcotw6cuqlSRtbYxKBNNr8WpKj1UfJzQ&oe=6740F7A2"/>
</p>
<p>
We created two virtual machines. One acts as a domain controller, and the other acts as a normal user.
</p>
<br />
<br />

<p>
<img src=https://scontent-lga3-2.xx.fbcdn.net/v/t1.15752-9/462565431_1039634081231386_1070168697948150697_n.png?_nc_cat=105&ccb=1-7&_nc_sid=9f807c&_nc_ohc=Mrbxwd0sMP4Q7kNvgFFS_Or&_nc_zt=23&_nc_ht=scontent-lga3-2.xx&_nc_gid=ALYrKrFXQhRmCTTVt7-YFrY&oh=03_Q7cD1QGcKm2PAN2weC_aBbc2JY4crNqM4VGBq_CucNogoV5fUg&oe=6741D082
"/>
</p>
<p>
We deactivated the firewalls.
</p>
<br />
<br />

<p>
<img src="https://scontent-lga3-1.xx.fbcdn.net/v/t1.15752-9/462576843_893760036047622_1531729058594363453_n.png?_nc_cat=111&ccb=1-7&_nc_sid=9f807c&_nc_ohc=4d8UTaWqaycQ7kNvgG_mgP1&_nc_zt=23&_nc_ht=scontent-lga3-1.xx&_nc_gid=A5ZSr92FivegmYKc48b3HQB&oh=03_Q7cD1QG-oLXdVZge4Vc-YWyCYPDucL8gOndOB_Bj2y554oVvUA&oe=6741C258"/>
</p>
<p>
We reconfigured the DNS settings on the Network Interface Card (NIC) to point from the Microsoft DNS server to our domain controller (dc-1).
</p>
<br />
<br />

<p>
<img src="https://scontent-lga3-2.xx.fbcdn.net/v/t1.15752-9/462636456_1342098450508508_8958125043448141698_n.png?_nc_cat=100&ccb=1-7&_nc_sid=9f807c&_nc_ohc=AqRXO0Icq0QQ7kNvgHcdPWy&_nc_zt=23&_nc_ht=scontent-lga3-2.xx&_nc_gid=A5igbUa9pEBNEwwwVdVNYAS&oh=03_Q7cD1QEdm998OOGCLmBky-SdUqEkNx8xkSaOBnaEcWzQ7KVcLQ&oe=6741ACF9"/>
</p>
<p>
We pinged dc-1(domain controller).
</p>
<br />
<br />

<p>
<img src="https://scontent-lga3-1.xx.fbcdn.net/v/t1.15752-9/462570300_861697029095701_4025974581568336172_n.png?_nc_cat=110&ccb=1-7&_nc_sid=9f807c&_nc_ohc=sUdf3pnGtRMQ7kNvgHCLaTO&_nc_zt=23&_nc_ht=scontent-lga3-1.xx&_nc_gid=A-VNK-1O5OuqOBDcpb9rMGm&oh=03_Q7cD1QHPDSUXXyX-tzQt0u66CjscBH4kgeQkVdV3HNrAEf8ABQ&oe=6741CFD3"/>
<img src="https://scontent-lga3-1.xx.fbcdn.net/v/t1.15752-9/462564925_338946755945928_4190073136591104224_n.png?_nc_cat=111&ccb=1-7&_nc_sid=9f807c&_nc_ohc=8I7ZuQ_2w1wQ7kNvgGRknEj&_nc_zt=23&_nc_ht=scontent-lga3-1.xx&_nc_gid=Au4ySySSOypp8cbvMxPqSkr&oh=03_Q7cD1QG75sPUbm9m-e0vQA6JVK7mZ46-ph9zQZ1QRc__QMsH1w&oe=67419F67"/>
</p>
<p>
We confirmed the connection to the domain controller by ensuring it is mapped to its private IP address.
</p>
<br />
<br />

<p>
<img src="https://scontent-lga3-2.xx.fbcdn.net/v/t1.15752-9/462534228_1670737330151926_3810997668420009357_n.png?_nc_cat=109&ccb=1-7&_nc_sid=9f807c&_nc_ohc=tfZdSdpmMtEQ7kNvgF87LQy&_nc_zt=23&_nc_ht=scontent-lga3-2.xx&_nc_gid=AiFolAgaIYVvfbMiBqYPO8p&oh=03_Q7cD1QGu-LNsqsQ_fPQpC3ByNMo3P7baXisfS0BHTZFS3lGSbQ&oe=6741BE88"/>
</p>
<p>
Creating new Organizational Units for new users.
</p>
<br />
<br />

<p>
<img src="https://scontent-lga3-1.xx.fbcdn.net/v/t1.15752-9/462566814_1077870940654756_1348718392543597969_n.png?_nc_cat=102&ccb=1-7&_nc_sid=9f807c&_nc_ohc=tWfZioSrU8gQ7kNvgFNwhAP&_nc_zt=23&_nc_ht=scontent-lga3-1.xx&_nc_gid=AEsgu4C80ehadPXzPGcB2wd&oh=03_Q7cD1QHtg3cI53Gxo3gEPiIQttgU0s7_fkeonOGYQNdHY0B3Dw&oe=6741B26E"/>
</p>
<p>
Creating a new user in our _ADMINS organizational unit.
</p>
<br />
<br />

<p>
<img src="https://scontent-lga3-2.xx.fbcdn.net/v/t1.15752-9/462639871_1139665467515654_7889629944978758830_n.png?_nc_cat=105&ccb=1-7&_nc_sid=9f807c&_nc_ohc=qTArYS6yT6MQ7kNvgFxL9So&_nc_zt=23&_nc_ht=scontent-lga3-2.xx&_nc_gid=AJ65F8k0qIPrVwkgmb7687O&oh=03_Q7cD1QF55e_oGF5TAARtL7z_rQOYZQonVU2Xd8VvqnmdGI-4pw&oe=6741D521"/>
</p>
<p>
We created a user and assigned them domain admin privileges.
</p>
<br />
<br />


<p>
<img src="https://scontent-lga3-1.xx.fbcdn.net/v/t1.15752-9/462554852_8635879536500336_3794130011411122602_n.png?_nc_cat=111&ccb=1-7&_nc_sid=9f807c&_nc_ohc=zvziNb7TCBQQ7kNvgFX-kRi&_nc_zt=23&_nc_ht=scontent-lga3-1.xx&_nc_gid=AJJr5_rr4EscDFyG7kzBp7Z&oh=03_Q7cD1QHsFgreIdPv0biyKl5qqGDr_ybywP3cRd5-KEacIoxEpw&oe=6741AF34"/>
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

