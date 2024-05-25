<h1>Challenge Lab A: User Management</h1>

 ### [YouTube Demonstration](https://youtu.be/7eJexJVCqJo)

<h2>Description</h2>
** This lab reflects Challenge Lab A in the 'Linux Essentials' course from the Network Development Group. **

The purpose of this lab is to demonstrate proficiency while creating new user accounts and directories, modifying the permissions of the newly created accounts and directories, and creating files which belong to each separate directory. In this lab, we are tasked with adding three new departments to the Linux server that meet the following requirements:

- Each department will have its own directory at the root of the filesystem, as well as its own group. Each department will have three members: one administrative users, and two normal users. The default shell of each created user will be /bin/bash.
- For security reasons, ensure that the owner of each group and directory is the respective department administrator. Also ensure that all users who belong to a department have full read, write, and execute within their respective directories.
- Lastly, ensure that department directories are not accessibly by users who belong to other departments. Ensure that each directory has ownership of their respective files, and ensure that the files within a directory can only be deleted by their owners.  

<h2>Key Points Within Lab: </h2>

- <b>Creation of three new departments by creating three new directories and groups, with three users in each group.</b>
- <b>Setting directory permissions which grant users full access in departments they belong to and no access in other departments.  </b>
- <b>Creating files that are owned by each department and utilizing sticky bit to ensure the protection of those files. </b>

<h2>Lab walk-through:</h2>

<p align="center">
To begin the lab, I utilize mkdir to create the three new directories of Engineering, Sales, and IT, which are the departments that are being added to the Linux server. Please note that for the completion of this lab, I am using the root account to avoid having any permissions denied. Freely using the root account is considered a bad security practice and is not advised in situations where security is a prime concern. However, I am working within a protected lab environment where the use of root is not so dangerous. <br/>
<img src="https://i.imgur.com/OBocBYB.png" height="80%" width="80%" alt="LinChallLab"/>
<br />
<br />

<p align="center">
In addition to directories, I also need to create specific groups for each department that will house the users which belong to those departments. By using a string of the groupadd commands, I am able to create a group for Engineering, Sales, and IT. Additionally, I am able to verify that those groups were created properly by checking the /etc/group file.  <br/>
<img src="https://i.imgur.com/OAZucGb.png" height="80%" width="80%" alt="LinChallLab"/>
<br />
<br />

<p align="center">
By running "cat /etc/group", I am able to check the contents of the /etc/group file. Denoted in the highlighted portion of the screenshot is an entry for each group that we created, meaning that they were successfully added to the system. <br/>
<img src="https://i.imgur.com/diJqe7a.png" height="80%" width="80%" alt="LinChallLab"/>
<br />
<br />

<p align="center">
At this point in the lab, it is time to create the user accounts that will be added to the groups that we made. Utilizing the useradd command, I am able to add two regular users and one administrative user to each group. By using the tags -m, -s, and -g, I am able to designate a home directory for each user, make each users default shell /bin/bash, and ensure that the group that they have been added to is their primary group. After administering these commands, we are able to see the existence of all the created users when looking inside of /home.<br/>
<img src="https://i.imgur.com/daHmp6x.png" height="80%" width="80%" alt="LinChallLab"/>
<br />
<br />

<p align="center">
With the users, directories, and groups all created, it is time to assign ownership of each directory to the respective admin of each department. By employing the chown command, I am able to make the following changes: placing ownership of the engineering directory with the engineering admin, placing ownership of the sales directory with the sales admin, and placing ownership of the IT directory with the IT admin. Now, when checking the permissions of these directories, we are able to confirm that each department belongs to the appropriate group and owner.  <br/>
<img src="https://i.imgur.com/L8T4RPl.png height="80%" width="80%" alt="LinChallLab"/>
<br />
<br />

<p align="center">
In this screenshot, I am controlling directory access by adjusting the permissions that are associated with each directory. The lab tasked us with setting permissions so that department members have full access to their own directory, but no access in directories that they do not belong to. By administering 'chmod 1770' to each directory, I am able to grant full read, write, and execute permissions to the owner and group members of a directory, while also disabling access to individuals who are not within that department group. Additionally, that command also applies the sticky bit to each directory, meaning that files within the directory can only be deleted by their respective owners, thus helping to protect info that belongs to each department.  <br/>
<img src="https://i.imgur.com/pAdFmz3.png" height="80%" width="80%" alt="LinChallLab"/>
<br />
<br />

<p align="center">
In this screenshot, I am creating a simple text file and placing it within the directory of each department. Although the content of each text file is the same, they are three different files which simply serve to showcase that each department possesses some sort of their own information. By checking the output and the path of each file, I am able to confirm that all of the text files were properly created and assigned to the appropriate departments.<br/>
<img src="https://i.imgur.com/DcLt3dC.png" height="80%" width="80%" alt="LinChallLab"/>
<br />
<br />

<p align="center">
88888888  <br/>
<img src="https://i.imgur.com/AJiP1Mk.png" height="80%" width="80%" alt="LinChallLab"/>
<br />
<br />

<p align="center">
99999999  <br/>
<img src="https://i.imgur.com/xN7jJhO.png" height="80%" width="80%" alt="LinChallLab"/>
<br />
<br />

<p align="center">
100000000000  <br/>
<img src="https://i.imgur.com/pSKzpu8.png" height="80%" width="80%" alt="LinChallLab"/>
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
