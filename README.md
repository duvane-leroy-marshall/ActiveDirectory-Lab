# ActiveDirectory-Lab
A HackTheBox Academy module focusing on authentication, authorization, and accounting within a domain.

<h1>Introduction to Active Directory</h1>

[Module Link](https://academy.hackthebox.com/course/preview/intro-to-network-traffic-analysis)

<h2>Description</h2>
This module covers the following:

- <b>The history of Active Directory</b>
- <b>Active Directory objects and structures</b>
- <b>Authentication protocols used</b>
- <b>An understanding of the difference between rights and privileges</b>
- <b>Practice executing common Active Directory tasks</b>

<h2>Tools Used</h2>

- <b>Active Directory</b>
- <b>Powershell</b>

<h2>Environments Used </h2>

- <b>HackTheBox Pwnbox Linux</b>
- <b>Windows Server 2019 Standard</b>

<h2>Guided Lab: Active Directory Administration</h2>
In this guided lab scenario, we will serve as domain administrators to Inlanefrieght for a day. We have been tasked to help the IT department close some work orders. We will be performing actions such as adding and removing users and groups, managaing group policy, and more.
<br />
<br />
We will remote into a windows server to peform these tasks.
<br />
<br />

<p align="center">
Our tasks for the day: <br/>
<img src="https://i.imgur.com/ybLM5US.jpg" height="80%" width="80%" alt="Email"/>
<br />
<br />
inlanefreight.local structure: <br/>
<img src="https://i.imgur.com/RjpI9tW.jpg" height="80%" width="80%" alt="Domain"/>
<br />
<br />
Adding a user account inside the IT container: <br/>
<img src="https://i.imgur.com/9DvdESr.jpg" height="80%" width="80%" alt="Add User"/>
<br />
<b>We will be adding three users to the IT container: Andromeda Cepheus, Orion Starchaser, Artemis Callisto. In the above screenshot we added Andromeda Cepheus with the follow attributes: their full name, a.cepheus@inlanefreight.local email, and acepheus as their logon.</b>
<br />
<br />
<img src="https://i.imgur.com/AfuSKUM.jpg" height="80%" width="80%" alt="User Password"/> 
</br>
<b>We will be assign a temporary password of NewP@ssw0rd123! to the user and select the option for them to change the password at next logon.</b>
<br />
<br />
All new users added: <br/>
<img src="https://i.imgur.com/FcdoEAh.jpg" height="80%" width="80%" alt="Users Added"/>
<br />
<br />
Deleting a user account: <br/>
<img src="https://i.imgur.com/WtFkTJJ.jpg" height="80%" width="80%" alt="Delete User"/> 
<br />
<b>Our next step is to remove the user that is no longer with the company. This user's name is Paul Valencia. We can find Paul by doing a find search under the Employees container. Then we type their full name to get the correct user. Then we will delete the user.</b>
<br />
<br />
Unlocking a user account: <br/>
<img src="https://i.imgur.com/MsZfH1v.jpg" height="80%" width="80%" alt="Unlock User"/> 
<br />
<b>A user by the name of Adam Masters has been locked out of his account because of multiple failed logins. We will simply reset Adam's password, as well as select the option to unlock the user's account.</b>
<br />
<br />
Adding a new organizational unit in the IT container: <br/>
<img src="https://i.imgur.com/b3rdNtk.jpg" height="80%" width="80%" alt="OU"/> 
<br />
<b>Our next task is to create an organizational unit in the IT container for our new users.</b>
<br />
<br />

<!--
 ```diff
- text in red
+ text in green
! text in orange
# text in gray
@@ text in purple (and bold)@@
```
--!>
