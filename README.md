<h1>Challenge Lab A: User Management</h1>

 ### [YouTube Demonstration](https://youtu.be/7eJexJVCqJo)

<h2>Description</h2>
** This lab reflects Challenge Lab A in the 'Linux Essentials' course from the Network Development Group. **

The purpose of this lab is to demonstrate proficiency while creating new user accounts and directories, creating files with specific group ownership, and modifying the permissions of those files, user accounts, and directories. In this lab, we are tasked with adding three new departments to the Linux server that meet the following requirements:

- Each department must belong to a unique group and is to be given its own directory at the root of the filesystem. Each department will have three members: one administrative user, and two normal users. Each user will be placed in the default directory /home, and be given the default shell of /bin/bash.
- Ownership of each group and directory is to be given to the respective department administrator. Ensure that all users within a department are given the appropriate permissions to access their directory and any necessary contents within.
- Set permissions which block directory access to outside users. Give each group ownership of the files within their directory.
- Lastly, encourage data protection by ensuring that files can only be deleted by their owner. 


<h2>Key Points Within Lab: </h2>

- <b>Demonstrate ability to create directories, groups, and users within a Linux server.</b>
- <b>Demonstrate ability to adjust and manage both regular and special permissions of directories, users, and files.  </b>
- <b>Demonstrate ability to create a text file and edit its attributes. </b>


<h2>Lab walk-through:</h2>

<p align="center">
To begin the lab, I utilize 'mkdir' to create three new directories called "Engineering", "Sales", and "IT". These are the departments which I will be adding to the Linux server. Please note that for the completion of this lab, I am using the root account to avoid having any permissions denied while running certain commands. But it is important to remember that root should be used with caution, and freely executing commands as root is generally a bad security practice.  <br/>
<img src="https://i.imgur.com/OBocBYB.png" height="80%" width="80%" alt="LinChallLab"/>
<br />
<br />

<p align="center">
After creating the directories, I need to create the groups that will house the members of each department. With a string of 'groupadd' commands, I am able to create one group each for Engineering, Sales, and IT. By checking the /etc/group file, I am able to verify that those groups were properly added to the server.  <br/>
<img src="https://i.imgur.com/OAZucGb.png" height="80%" width="80%" alt="LinChallLab"/>
<br />
<br />

<p align="center">
In this image, I am displaying the contents of the /etc/group file to the screen. Within the highlighted portion of the screenshot is an entry for Engineering, Sales, and IT. This means that the groups were successfully added to the system. <br/>
<img src="https://i.imgur.com/diJqe7a.png" height="80%" width="80%" alt="LinChallLab"/>
<br />
<br />

<p align="center">
At this point in the lab, I will be creating the user accounts that will belong to the groups that were created. With the 'useradd' command, I create three users for each group; one administrative user, and two regular users. By using the tags -m, -s, and -g with 'useradd', I assign each user to the default /home directory, I assign their default shell to be /bin/bash, and I ensure that the group that they belong to (Engineering, Sales, or IT) is their primary group. After administering these commands, I am able to verify the existence of these users by checking within /home.<br/>
<img src="https://i.imgur.com/daHmp6x.png" height="80%" width="80%" alt="LinChallLab"/>
<br />
<br />

<p align="center">
With the users, directories, and groups all created, I must now give ownership of each group and directory to the respective department admin. By using the 'chown' command, I am able to give engineering directory and group ownership to the engineering admin, give sales directory and group ownership to the sales admin, and give IT directory and group ownership to the IT admin. Now, when viewing directory permissions, we can verify that each department belongs to the appropriate group and owner.  <br/>
<img src="https://i.imgur.com/L8T4RPl.png height="80%" width="80%" alt="LinChallLab"/>
<br />
<br />

<p align="center">
In this screenshot, I am adjusting the permissions of each directory. The lab tasked us with setting permissions so that department members have full access to their own directory, but no access in directories that they do not belong to. By administering 'chmod 1770' to each directory, I am able to grant full read, write, and execute permissions to the owner and group members of a directory, while also disabling access to individuals who are not within that department group. Additionally, that command also applies the sticky bit to each directory, meaning that files within the directory can only be deleted by their respective owners, thus helping to protect info that belongs to each department.  <br/>
<img src="https://i.imgur.com/pAdFmz3.png" height="80%" width="80%" alt="LinChallLab"/>
<br />
<br />

<p align="center">
In this screenshot, I am creating a simple text file and placing it within the directory of each department. Although the content of each text file is the same, they are three different files which simply serve to showcase that each department possesses some sort of their own information. By checking the output and the path of each file, I am able to confirm that all of the text files were properly created and assigned to the appropriate departments.<br/>
<img src="https://i.imgur.com/DcLt3dC.png" height="80%" width="80%" alt="LinChallLab"/>
<br />
<br />

<p align="center">
In this image, I am adjusting both the ownership of the files that I previously created, and altering the permissions of those files as well. Since I created the files while on the root account, they initially belong to the user and group of 'root'. By using the chown command again, I am able to place the files within the group that they should belong to (Engineering, Sales, or IT), and I am also able give file ownership to the respective administrative user. After applying this first change, we can now see that instead of belonging to 'root', each file now belongs to a specific department and is owned by the admin of that department. In order to adjust the permissions of the files, I used the command "chmod 740". This changes the file permissions so that the administrative users have full ability to read, change, or delete the document; other department members are able to access the document for reading purposes but are unable to alter the document in any fashion; and all other users who do not belong to the department have no access to the file whatsoever.  <br/>
<img src="https://i.imgur.com/xN7jJhO.png" height="80%" width="80%" alt="LinChallLab"/>
<br />
<br />

<p align="center">
This final screenshot is meant to serve as a full breakdown of the lab by showcasing the following information: <br />

- FILL IN WITH WHAT THE PIC SHOWS AND THE REQUIREMENTS THAT YOU MET
- NEXT
- NEXT
<p align="center">
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
