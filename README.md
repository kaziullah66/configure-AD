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

1<p>
<img src="https://scontent-lga3-1.xx.fbcdn.net/v/t1.15752-9/462544246_1235664007678390_3086403986479741365_n.png?_nc_cat=106&ccb=1-7&_nc_sid=9f807c&_nc_ohc=Wg-0S3w1jAwQ7kNvgESYs3T&_nc_zt=23&_nc_ht=scontent-lga3-1.xx&_nc_gid=Abqi_KPEuNkhc_Q1aQhrpse&oh=03_Q7cD1QHqPYx5Gvyk2Uzcotw6cuqlSRtbYxKBNNr8WpKj1UfJzQ&oe=6740F7A2"/>
</p>
<p>
We created two virtual machines. One acts as a domain controller, and the other acts as a normal user.
</p>
<br />
<br />

2<p>
<img src="https://scontent-lga3-1.xx.fbcdn.net/v/t1.15752-9/462584693_1563216618411905_1197264063529969099_n.jpg?_nc_cat=103&ccb=1-7&_nc_sid=9f807c&_nc_ohc=Xdy7NWlB2JcQ7kNvgEwbnLe&_nc_zt=23&_nc_ht=scontent-lga3-1.xx&_nc_gid=APcWv6vKB8j5iRj-SIDU8RJ&oh=03_Q7cD1QGL-UAavLY1X2k0rZFJXDoPktf-VeSHOoF6lkwDCO3YZg&oe=6741BD0F"/>
</p>
<p>
We deactivated the firewalls.
</p>
<br />
<br />

3<p>
<img src="https://scontent-lga3-1.xx.fbcdn.net/v/t1.15752-9/462576843_893760036047622_1531729058594363453_n.png?_nc_cat=111&ccb=1-7&_nc_sid=9f807c&_nc_ohc=4d8UTaWqaycQ7kNvgG_mgP1&_nc_zt=23&_nc_ht=scontent-lga3-1.xx&_nc_gid=A5ZSr92FivegmYKc48b3HQB&oh=03_Q7cD1QG-oLXdVZge4Vc-YWyCYPDucL8gOndOB_Bj2y554oVvUA&oe=6741C258"/>
</p>
<p>
We reconfigured the DNS settings on the Network Interface Card (NIC) to point from the Microsoft DNS server to our domain controller (dc-1).
</p>
<br />
<br />

4<p>
<img src="https://scontent-lga3-2.xx.fbcdn.net/v/t1.15752-9/462636456_1342098450508508_8958125043448141698_n.png?_nc_cat=100&ccb=1-7&_nc_sid=9f807c&_nc_ohc=AqRXO0Icq0QQ7kNvgHcdPWy&_nc_zt=23&_nc_ht=scontent-lga3-2.xx&_nc_gid=A5igbUa9pEBNEwwwVdVNYAS&oh=03_Q7cD1QEdm998OOGCLmBky-SdUqEkNx8xkSaOBnaEcWzQ7KVcLQ&oe=6741ACF9"/>
</p>
<p>
We pinged dc-1(domain controller).
</p>
<br />
<br />

5<p>
<img src="https://scontent-lga3-1.xx.fbcdn.net/v/t1.15752-9/462570300_861697029095701_4025974581568336172_n.png?_nc_cat=110&ccb=1-7&_nc_sid=9f807c&_nc_ohc=sUdf3pnGtRMQ7kNvgHCLaTO&_nc_zt=23&_nc_ht=scontent-lga3-1.xx&_nc_gid=A-VNK-1O5OuqOBDcpb9rMGm&oh=03_Q7cD1QHPDSUXXyX-tzQt0u66CjscBH4kgeQkVdV3HNrAEf8ABQ&oe=6741CFD3"/>
<img src="https://scontent-lga3-1.xx.fbcdn.net/v/t1.15752-9/462564925_338946755945928_4190073136591104224_n.png?_nc_cat=111&ccb=1-7&_nc_sid=9f807c&_nc_ohc=8I7ZuQ_2w1wQ7kNvgGRknEj&_nc_zt=23&_nc_ht=scontent-lga3-1.xx&_nc_gid=Au4ySySSOypp8cbvMxPqSkr&oh=03_Q7cD1QG75sPUbm9m-e0vQA6JVK7mZ46-ph9zQZ1QRc__QMsH1w&oe=67419F67"/>
</p>
<p>
We confirmed the connection to the domain controller by ensuring it is mapped to its private IP address.
</p>
<br />
<br />

6<p>
<img src="https://scontent-lga3-2.xx.fbcdn.net/v/t1.15752-9/462534228_1670737330151926_3810997668420009357_n.png?_nc_cat=109&ccb=1-7&_nc_sid=9f807c&_nc_ohc=tfZdSdpmMtEQ7kNvgF87LQy&_nc_zt=23&_nc_ht=scontent-lga3-2.xx&_nc_gid=AiFolAgaIYVvfbMiBqYPO8p&oh=03_Q7cD1QGu-LNsqsQ_fPQpC3ByNMo3P7baXisfS0BHTZFS3lGSbQ&oe=6741BE88"/>
</p>
<p>
Creating new Organizational Units for new users.
</p>
<br />
<br />

7<p>
<img src="https://scontent-lga3-2.xx.fbcdn.net/v/t1.15752-9/462636456_1342098450508508_8958125043448141698_n.png?_nc_cat=100&ccb=1-7&_nc_sid=9f807c&_nc_ohc=AqRXO0Icq0QQ7kNvgHcdPWy&_nc_zt=23&_nc_ht=scontent-lga3-2.xx&_nc_gid=A5igbUa9pEBNEwwwVdVNYAS&oh=03_Q7cD1QEdm998OOGCLmBky-SdUqEkNx8xkSaOBnaEcWzQ7KVcLQ&oe=6741ACF9"/>
</p>
<p>
We pinged dc-1(domain controller).
</p>
<br />
<br />

8<p>
<img src="https://scontent-lga3-2.xx.fbcdn.net/v/t1.15752-9/462636456_1342098450508508_8958125043448141698_n.png?_nc_cat=100&ccb=1-7&_nc_sid=9f807c&_nc_ohc=AqRXO0Icq0QQ7kNvgHcdPWy&_nc_zt=23&_nc_ht=scontent-lga3-2.xx&_nc_gid=A5igbUa9pEBNEwwwVdVNYAS&oh=03_Q7cD1QEdm998OOGCLmBky-SdUqEkNx8xkSaOBnaEcWzQ7KVcLQ&oe=6741ACF9"/>
</p>
<p>
We pinged dc-1(domain controller).
</p>
<br />
<br />


9<p>
<img src="https://scontent-lga3-2.xx.fbcdn.net/v/t1.15752-9/462636456_1342098450508508_8958125043448141698_n.png?_nc_cat=100&ccb=1-7&_nc_sid=9f807c&_nc_ohc=AqRXO0Icq0QQ7kNvgHcdPWy&_nc_zt=23&_nc_ht=scontent-lga3-2.xx&_nc_gid=A5igbUa9pEBNEwwwVdVNYAS&oh=03_Q7cD1QEdm998OOGCLmBky-SdUqEkNx8xkSaOBnaEcWzQ7KVcLQ&oe=6741ACF9"/>
</p>
<p>
We pinged dc-1(domain controller).
</p>
<br />
<br />


10<p>
<img src="https://scontent-lga3-2.xx.fbcdn.net/v/t1.15752-9/462636456_1342098450508508_8958125043448141698_n.png?_nc_cat=100&ccb=1-7&_nc_sid=9f807c&_nc_ohc=AqRXO0Icq0QQ7kNvgHcdPWy&_nc_zt=23&_nc_ht=scontent-lga3-2.xx&_nc_gid=A5igbUa9pEBNEwwwVdVNYAS&oh=03_Q7cD1QEdm998OOGCLmBky-SdUqEkNx8xkSaOBnaEcWzQ7KVcLQ&oe=6741ACF9"/>
</p>
<p>
We pinged dc-1(domain controller).
</p>
<br />
<br />

11<p>
<img src="https://scontent-lga3-2.xx.fbcdn.net/v/t1.15752-9/462636456_1342098450508508_8958125043448141698_n.png?_nc_cat=100&ccb=1-7&_nc_sid=9f807c&_nc_ohc=AqRXO0Icq0QQ7kNvgHcdPWy&_nc_zt=23&_nc_ht=scontent-lga3-2.xx&_nc_gid=A5igbUa9pEBNEwwwVdVNYAS&oh=03_Q7cD1QEdm998OOGCLmBky-SdUqEkNx8xkSaOBnaEcWzQ7KVcLQ&oe=6741ACF9"/>
</p>
<p>
We pinged dc-1(domain controller).
</p>
<br />
<br />

12<p>
<img src="https://scontent-lga3-2.xx.fbcdn.net/v/t1.15752-9/462636456_1342098450508508_8958125043448141698_n.png?_nc_cat=100&ccb=1-7&_nc_sid=9f807c&_nc_ohc=AqRXO0Icq0QQ7kNvgHcdPWy&_nc_zt=23&_nc_ht=scontent-lga3-2.xx&_nc_gid=A5igbUa9pEBNEwwwVdVNYAS&oh=03_Q7cD1QEdm998OOGCLmBky-SdUqEkNx8xkSaOBnaEcWzQ7KVcLQ&oe=6741ACF9"/>
</p>
<p>
We pinged dc-1(domain controller).
</p>
<br />
<br />

