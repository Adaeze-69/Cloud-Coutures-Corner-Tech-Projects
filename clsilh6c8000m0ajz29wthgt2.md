
 # Linux Commands
 
"So what is Linux? Can you explain to me like I am 5 years old?"

*Ps: I'll be using folders and directory interchangeably but they mean the same thing*

Suppose you own a large box filled with vibrant building blocks. These blocks have incredible power! They can construct robots, cars, planes, even houses. Linux can be thought of as a unique collection of instructions that explains how to use these blocks for play.

Now imagine that you want to use your building pieces to create a cool robot. Linux makes things easier for you by demonstrating exactly which blocks to use and how to combine them. It identifies the bricks that make up the robot's limbs, legs, eyes, and even brain!

However, Linux isn't limited to robot construction. It can also assist you in creating other enjoyable things out of your blocks, such as building a spaceship to travel across space or a fantastical palace to house your toys.

Thus, Linux may be thought of as a useful manual that demonstrates how to utilize your basic building blocks to create a plethora of beautiful things and have a great time!

Linux is ***an open-source operating system developed by Linus Torvalds. It is an operating system just like Windows and MacOS.***

I want to walk you through an exercise where you get to use linux commands to walk around especially if this is your first time. Try it and let me know how it goes!

## EXERCISE

Create your login name and name it anything. I name mine altschool i.e., home directory /home/altschool. The home directory contains the following sub-directories: code, tests, personal, misc Unless otherwise specified, you are running commands from the home directory.

*I will share each step with commands needed to run in the terminal. They will be embedded inline codes.*

i. Create a login name called Altschool on your terminal from your root user. You can use vagrant virtual machine or gitbash

`sudo useradd -Ums /bin/bash Altschool`

![sudoadd](https://cdn.hashnode.com/res/hashnode/image/upload/v1707514253793/5c84cfdd-394e-43ac-a45d-8c499944e8ee.png )

> `useradd` command helps you create a new login user

> \-Ums
> 
> `U` flag creates user and assign a group with same name as the user.
> 
> `m` flag creates the home directory.
> 
> `s` flag specifies the default login shell

ii. Switch user from vagrant (root user) to Altschool user created

`sudo su Altschool`

![sudo su](https://cdn.hashnode.com/res/hashnode/image/upload/v1707515755801/acdef3b7-f005-471e-9abc-9ad45d217618.png)

> `sudo` is the command that allows regular users to perform administrative tasks or commands that typically require root or superuser privileges
> 
> `su` allows you to switch to a different user account from the command line, including the root or superuser account.

iii. create sub directories named **code, tests, personal & misc**

`mkdir code tests personal misc`

Use `ls` to check that the list of the directories created are in the home directory.

![ls](https://cdn.hashnode.com/res/hashnode/image/upload/v1707516200431/fdba1a3f-713f-485c-98bf-3dc2ab611844.png)

> `mkdir` means make directory. It is a command in Linux for creating new directories or folders to organize your files and data.
> 
> `ls` means list. This is used to display a list of files and directories in the current directory or a specified directory.

## Instructions:

Just before we get to the exercise, let us discuss the difference between **Home Directory** (`cd /home`) and **Root Directory** (`cd /`).

The home directory is a directory connected to each user account, holding personal files and configurations unique to that user, while the root directory is the top level directory in the file system hierarchy which houses the necessary system files.

a.Change directory to the **tests** directory using absolute pathname

`cd /home/Altschool/tests`

![cd](https://cdn.hashnode.com/res/hashnode/image/upload/v1707517407571/91e8fa6d-9088-4042-a9ad-d177e689812f.png )

> `cd` means change directory. It is a command that is used to move to another directory. Like changing from the present directory to another existing directory of your choice
> 
> **Absolute pathname** specifies the location of a file or directory from the root directory of the file system. It provides the complete path starting from the root directory and includes all intermediate directories. For example, in a Unix-like file system, an absolute pathname might look like /home/Altschool/tests, where the first "/" after the "cd" command represents the root directory. Think of it like giving directions starting from the very bottom of the tree, the roots. So, if we want to find something, we start from the roots and follow the path all the way up to the branch where it's stored

---

b. Change directory to the **tests** directory using relative pathname

`cd ./tests`

![tests](https://cdn.hashnode.com/res/hashnode/image/upload/v1707517798506/4ed683ae-6092-49f6-978b-e16fd806ee65.png )

> When you wish to refer to files or directories in relation to where you currently are in the filesystem hierarchy, **relative pathnames** come in handy just like `cd ./tests`. They are frequently more practical and shorter than absolute pathnames. It describes the path from the current directory. For example, if the current directory is /home/Altschool/, a relative pathname to access the file tests located in the Altschool directory would be "cd tests" or "cd ./tests" where the first "." after the "cd" means you want to search in the present folder and the "/tests" is the folder you want to change to, particularly for moving across directories that share a structure. But if you change the current working directory, they could become unclear.
> 
> The same relative pathname may correspond to multiple files or directories depending on where you are in the filesystem because relative pathnames are interpreted based on the current working directory.

---

c. Use echo command to create a file named fileA with text content ‘Hello A’ in the misc directory. (remember we are doing everything along each step in the home directory of **Altschool** user)

`echo 'Hello A' > misc/fileA`

![echo](https://cdn.hashnode.com/res/hashnode/image/upload/v1707518171848/b15a3785-c203-44a9-b3b4-a2a41026fd2b.png )

> `echo` command is used for printing text or variables to the terminal or into a file in the terminal. One cool thing I love about the `echo` command is that you can print into a new file on one line of command, redirecting the output of a command into a new file using the "&gt;" symbol. The file does not necessarily have to be created before you can print in it. I hope that is clear. Check the attached image for context.
> 
> Also, since we are creating and using all commands in the home directory of Altschool, we will have to echo into `misc/fileA` following the path of misc.
> 
> Then use the `ls` command (I already explained it previously) with the `-al` flag to check for ALL directories, files, and everything in that directory. You can always have a directory inside a directory. A directory is synonymous to a folder.

---

d. Create an empty file named fileB in the misc directory. Populate the file with a dummy content afterwards

`touch misc/fileB` to create the fileB

`nano misc/fileB` to write in a dummy content in the fileB

`cat misc/fileB` to check the content in the fileB

![cat](https://cdn.hashnode.com/res/hashnode/image/upload/v1707518613397/b4fa555b-acc9-4b10-9759-89d1096f9af0.png )

> `touch` command is used to create files.
> 
> `nano` is a text editor that is commonly used for quick edits, viewing configuration files, or making simple changes to text files in Linux environments. It's especially popular on servers or systems without graphical user interfaces (GUIs) where command-line tools are preferred. One down side of this command is that your mouse won't function on the screen while in the text editor. The use of arrow keys and alphabet keys on the keyboard Allows you to do the job of writing and editing text on the screen.
> 
> `cat` is a "concatenate"command. It is a versatile and handy tool for quickly viewing the contents of files in the terminal after writing inside the file.

---

e. Copy contents of fileA into fileC

`cp misc/fileA misc/fileC`

![cp](https://cdn.hashnode.com/res/hashnode/image/upload/v1707519171800/194ac850-d228-4f0a-ae1e-82821da13d9f.png)

> `cp` command as it literally mean is to copy content from a file to another file while retaining contents and the file the initial copy was made from.

---

f. Move contents of fileB into fileD

`mv misc/fileB misc/fileD`

![mv](https://cdn.hashnode.com/res/hashnode/image/upload/v1707519446983/74e3afe2-1fd8-481b-aa19-1d97b2ff3619.png)

> `mv` can be used to move contents of a file to another, and also directories. You can also use it to rename files and directory.This flexibly allows renaming files and directories as well as conviently moving contents from a former file to a new one .This implies that the old file from which the contents were moved from will cease to exist.

g. Create a tar archive called misc.tar for the contents of misc directory

`tar -cvf misc.tar misc`

![tar](https://cdn.hashnode.com/res/hashnode/image/upload/v1707520172820/52067b2f-09ff-40c5-8156-f411145a9f8f.png)

> the `tar` command offers a flexible and powerful way to archive and manage files and directories in Linux systems.
> 
> Then the `-cvf` flag will be broken into bits so it will enable me explain them better. The `c` flag is used to create archive. The `v` flag stands for "verbose." When used, `tar` will display detailed information about the files and directories being archived.The `f` flag stands for "file." It is used to specify the name of the archive file.

---

h. Compress the tar archive to create a misc.tar.gz file

`gzip misc.tar`

![gzip](https://cdn.hashnode.com/res/hashnode/image/upload/v1707520615900/a604b814-fbdc-441d-a52d-4557a2a97d06.png)

> The `gzip` command is used for compressing files to save disk space or reduce transfer times when transferring files over a network.

---

i. Create a user and force the user to change his/her password upon login

`sudo chage -d 0 praise`

![sudo chage](https://cdn.hashnode.com/res/hashnode/image/upload/v1707520825018/bfbda5a8-6307-40c4-be29-8dd58a3faa5d.png)

> Remember I already explained what sudo is above right? So we would not touch it anymore.
> 
> When it comes to setting password expiration rules for user accounts on Linux systems, administrators have flexibility thanks to the `chage` command. Because administrators may tailor password aging policies to meet organizational needs, it helps enforce security best practices by guaranteeing that users update their passwords on a regular basis.
> 
> When a system administrator create a new user on the server of a company he/she creates the user with a password and the sends the details to that user to login ... To ensure the user's account is safe he/she(administrator) forces the user to change the password upon first login so that only the user has the new password
> 
> In the context of the `chage` command, the `-d` flag is used to set the date of the last password change for a user account. This flag allows the administrator to manually specify how many times the user should use the old password created by him/her(the administrator), and that is why we have `0` as it means the number of time a user can use the password before changing it. Apparantly, the user can only use the password the one time they used it in logging in.

---

j. Lock a users password

`sudo passwd -l praise`

![sudo passwd](https://cdn.hashnode.com/res/hashnode/image/upload/v1707521121058/c6077e1c-e080-49b6-ac39-fae375b9d145.png)

> The `passwd` command means password. and combined with the `-l` flag it is used to lock a user account. It prevents users from logging in. Locking user accounts is useful for temporarily preventing access to an account, such as during maintenance or investigation of security issues. It can also be used as a security measure if a user's access needs to be revoked temporarily or permanently.

---

k. Create a user with no login shell

`sudo useradd -s /sbin/nologin Vicky`

![sudo useradd](https://cdn.hashnode.com/res/hashnode/image/upload/v1707521497913/4a2d80d6-e9ec-4cc4-893b-b451f02544a6.png)

> The `-s /sbin/nologin` command is used to set the login shell for a user account to `/sbin/nologin`. A user account configured with /sbin/nologin as its login shell will prevent interactive logins through Telnet, SSH, or other means. Rather, upon attempting to log in, the user will be met with an error message stating that login is prohibited, usually accompanied with an administrator-provided message. By preventing interactive logins, it helps enhance the security of the system by limiting potential points of unauthorized access.
> 
> The `grep` command is used to search contents of a file... in the command `cat /etc/passed | grep username` the "|" is a pipe symbol used to redirect the output of a command into another command which is the `grep`

---

l. Disable password based authentication for ssh

`sudo vi /etc/ssh/sshd_config`

![sudo vi](https://cdn.hashnode.com/res/hashnode/image/upload/v1707521882802/3ab775da-6332-44bb-997e-ae8e7b447ccd.png )

> The command `vi /etc/ssh/sshd_config` is used to open the SSH daemon configuration file (`sshd_config`) in the `vi` text editor,just like the `nano` text editor we talked about earlier.
> 
> Here's a breakdown of what each part of the command does:
> 
> * `vi`: This is the command to invoke the `vi` text editor in the terminal. `vi` is a widely used text editor in Unix-like operating systems, including Linux.
>     
> * `/etc/ssh/sshd_config`: This is the path to the SSH daemon configuration file. In most Linux distributions, SSH (Secure Shell) configuration files are stored in the `/etc/ssh/` directory. The `sshd_config` file specifically contains configuration settings for the SSH daemon (`sshd`), which is the server-side component of the SSH protocol. This file controls various aspects of the SSH server's behavior, such as authentication methods, allowed users, permitted protocols, and more.
>     
> 
> Therefore, when you run `vi /etc/ssh/sshd_config`, you are opening the `sshd_config` file in the `vi` text editor, allowing you to view and edit the configuration settings for the SSH daemon.
> 
> From the screenshot in line 47 **PasswordAuthentication** is set to '**no'** which disables the password authentication for ssh.

---

m. Disable root login for ssh

`vi /etc/ssh/sshd_config`

![vi](https://cdn.hashnode.com/res/hashnode/image/upload/v1707522035649/e372fc66-8c1f-40a0-844f-c75e4fad1009.png )

> As a continuation from the disabled authentication, scroll back up on the vi editor to line 29 where you have PermitRootLogin and set it to 'no' and save it. You save by pressing the esc key then the double colon (:) followed by the "wq" to save it then you press ENTER to leave the test editor. It should look like this `:wq` . There you go!

## Conclusion:

In summary, as you navigate the terminal, embrace the learning process with patience and perseverance. Every error is a chance to deepen your understanding, and each solution adds to your expertise. Keep exploring, keep learning, and let your discoveries empower your Linux journey. Your thoughts, experiences, and feedback are valuable—feel free to share them with others in our vibrant community of learners. Together, we can inspire and support each other on this exciting adventure through the command line.
