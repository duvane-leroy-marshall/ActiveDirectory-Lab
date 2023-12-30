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
 
<h2>Task 1: Manage Users</h2>
Our first task is to add some new hires. We will add them under the <b>"inlanefrieght.local"</b> scope, into the <b>"Corp -> Employees -> HQ-NYC -> IT"</b> folder structure. The users we will be adding are:

- <b>Andromeda Cepheus</b>
- <b>Orion Starchaser</b>
- <b>Artemis Callisto</b>

Each user will have the following attributes set with it, along with their full name:

- <b>full name</b>
- <b>email (first-inital.lastname@inlanefrieght.local)</b>
- <b>display name</b>
- <b>User must change password at next logon</b>

After that we will be removing two users who are no longer with the company. Their names are:

- <b>Mike O'Hare</b>
- <b>Paul Valencia</b>

And lastly we will be resetting the password of <b>Adam Masters</b>, who was locked out of his account after multiple failed logins.
<br />
<br />

<p align="center">
Adding a user account inside the IT container: <br/>
<img src="https://i.imgur.com/9DvdESr.jpg" height="80%" width="80%" alt="Add User"/>
<br />
<b>Here we are adding Andromeda Cepheus with the correct attributes</b>
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
<b>Our next step is to remove the users that are no longer with the company. We can find them by doing a find search under the Employees container. Next we type their full name to get the correct users. Then we will delete the users.</b>
<br />
<br />
Unlocking a user account: <br/>
<img src="https://i.imgur.com/MsZfH1v.jpg" height="80%" width="80%" alt="Unlock User"/> 
<br />
<b>We will simply reset Adam's password, as well as select the option to unlock the user's account.</b>
<br />
<br />

<h2>Task 2: Manage Groups and Other Organizational Units</h2>
In our second task, we are tasked with creating a new <b>Security Group</b> called <b>Security Analysts</b> and then add our new three hires into it. The group will be nested in an organizational unit by the same name under the IT hive.
<br />
<br />

<p align="center">
Adding a new organizational unit in the IT container: <br/>
<img src="https://i.imgur.com/b3rdNtk.jpg" height="80%" width="80%" alt="OU"/> 
<br />
<b>We create an organizational unit in the IT container for our new users.</b>
<br />
<br />
Adding a security group inside the OU: <br/>
<img src="https://i.imgur.com/47k7LEO.jpg" height="80%" width="80%" alt="Group"/> 
<br />
<b>Next we will create a security group inside the OU. It will have a Domain Local scope with the Security group type.</b>
<br />
<br />
Moving a user to a group: <br/>
<img src="https://i.imgur.com/gbfoWox.jpg" height="80%" width="80%" alt="User to Group"/> 
<br />
<b>We will now move our three new users into the Security Analysts group.</b>
<br />
<br />

<h2>Task 3: Manage Group Policy Objects</h2>
In our third task, we are asked to duplicate the group policy <b>Logon Banner</b>, rename it <b>Security Analysts Control</b>, and modfiy it to work for the new Analysts OU. We will need to make the following changes to the Policy Object:

- <b>modify the Password policy settings for users in the group and allowing users to access Powershell and CMD since their daily duties requires it.</b>
- <b>For computer settings, we need to ensure Logon Banner is applied and that removeable media is blocked from access.</b>
<br />
<br />
<p align="center">
Duplicating the Logon Banner group policy with Powershell: <br/>
<img src="https://i.imgur.com/fUax6ib.jpg" height="80%" width="80%" alt="Duplicate GPO"/> 
<br />
<b>We can use the Powershell cmdlet Copy-GPO to make a duplicate of the group policy with the same attributes.</b>
<br />
<br />
Linking the Security Analysts Control to an OU: <br/>
<img src="https://i.imgur.com/fbKinlG.jpg" height="80%" width="80%" alt="Linking GPO"/> 
<br />
<b>We will have to link the new GPO we created to the OU. We use the New-GPLink cmdlet in Powershell to do this.</b>
<br />
<br />
The Group Policy Management Console: <br/>
<img src="https://i.imgur.com/fkoAVno.jpg" height="80%" width="80%" alt="GPM"/> 
<br />
<b>We will have to modify the new GPO in the Group Policy Management console.</b>
<br />
<br />
Granting Powershell and CMD access to the new GPO: <br/>
Powershell: <br/>
<img src="https://i.imgur.com/Nn0kmu3.jpg" height="80%" width="80%" alt="GPO Access"/> 
<br />
<b>We will have to nagivate to the removeable media policy settings by this route: User Configuration -> Policies -> Administrative Templates -> System -> Removeable Storage Access. There we will enable it to grant access.</b>
<br />
CMD: <br/>
<img src="https://i.imgur.com/zqCY4x7.jpg" height="80%" width="80%" alt="GPO Access"/> 
<br />
<b>We will have to nagivate to the Command Prompt settings by this route: User Configuration -> Policies -> Administrative Templates -> System. There we will disable it since it prevents users from running the Command Prompt.</b>
<br />
<br />
Double checking the security policies: <br/>
<img src="https://i.imgur.com/N79G4aN.jpg" height="80%" width="80%" alt="Linking GPO"/> 
<br />
<b>We will navigate to: Computer Configuration -> Policies -> Windows Settings -> Security Settings -> Local Policies -> Security Options to double check to see if the security polices from the Logon Banner was duplicated to the new GPO.</b>
<br />
<img src="https://i.imgur.com/S5V5FpM.jpg" height="80%" width="80%" alt=Check 1"/> 
<br />
<img src="https://i.imgur.com/Ww2TWxI.jpg" height="80%" width="80%" alt="Check 2"/> 
<br />
<b>Everything is in working order!</b>
<br />
<br />
The Password Policy: <br/>
<img src="https://i.imgur.com/zAGo4oo.jpg" height="80%" width="80%" alt="Password Policy"/> 
<br />
<b>Next we will navigate to: Computer Configuration > Policies > Windows Settings > Security Settings > Account Policies > Password Policy.</b>
<br />
<br />
Updated Password Policy: <br/>
<img src="https://i.imgur.com/RFHGNuN.jpg" height="80%" width="80%" alt="Updated Password Policy"/> 
<br />
<b>At the final part of our task, we configured the password policy that was required.</b>
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
