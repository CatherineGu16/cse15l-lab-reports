# **Lab Report 1: Remote Access**

## Installing VSCode
To install VSCode, go to the [VSCode website](https://code.visualstudio.com/) and click the download button for Windows. Follow the download instructions and after opening the VSCode, you should see a screen like this:
<br /><br />
![Image](photos/VSCodeStart.PNG)

---
## Remotely Connecting
After installing the OpenSSH program and finding your [course account](https://sdacs.ucsd.edu/~icc/index.php) for the course, open VSCode and click Terminal, then New Terminal from the top menu bar. This will open up a powershell terminal at the bottom of the screen. 
<br /> <br />
In the terminal, type `ssh cs15lwi22ars@ieng6.ucsd.edu` to begin the connection to the ucsd server (Make sure to replace the last three letters before the @ with your course-specific account letters).
<br /> <br />
The terminal will then prompt you for the password for your account. When entering your password, you may notice that nothing appears after `Password:` as you type. THIS IS NORMAL! Once the password is typed in, press enter and you should be logged into the ssh and connected to the server.
<br /> <br />
Your terminal should look like this: <br /> <br />
![Image: ssh login terminal](photos/sshTerminal.PNG)

---
## Trying Some Commands
You can use many commands in the terminal including, but not limited to the following: <br />
- `cd` : changes working directory
- `cd ..` : change directory back to the parent directory of the current directory
- `pwd` : print working directory
- `ls` : lists all files and directories under current directory
- `mkdir` : make new directory

<br />
Here is an example of using some of the commands in the terminal: 
<br /> <br />

![ImageTerminal](photos/TerminalBasicCommands.PNG)
<br />

---
## Moving Files with scp
In order to move files into ssh, we need to utilize the command `scp`. Make sure you are not logged into your ssh and create a java file locally(The file used is `WhereAmI.java`). 
<br /> <br />
In the terminal, type in the command `scp WhereAmI.java cs15lwi2ars@ieng6.ucsd.edu:~/`. 
<br /> <br />
Fill in the password for your ssh like before and the `WhereAmI.java` file should be copied into the remote computer. After running this command the terminal should look like this: 
<br /> <br />
![Image](photos/scpCommand.PNG)

---
## Setting an SSH Key
An ssh key allows for you to login to your ssh without having to input your password every single time. To do this for a Windows machine, enter `ssh-keygen -t ed25519` into the terminal. Press enter to accept the default file to store your key and press enter again to skip making a passphrase for the key.
<br />  <br />
Once you have successfully created the passkey, entering `ssh cs15wi22ars@ieng6.ucsd.edu` will automatically log you into your account. This is what the terminal will display:
<br /> <br />
![Image](photos/sshkeyConfirmed.PNG)


---
## Optimizing Remote Running
Testing code can be very time consuming, but there are ways to save some of that time by optimizing remote running. One way is to use `;` to run multiple commans in a single line. For example, you can combine compiling and running of a class in ssh in one step by typing `ssh cs15lwi22ars@ieng6.ucsd.edu "javac WhereaAmI.java; java WhereAmI` Below is what running this line would display:
<br /> <br />
![Image](photos/OptimizingRunning.PNG)

---