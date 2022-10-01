WEEK 1 LAB REPORT 
============
*Lorenzo Olmo Marchal*

*CSE 15L B05*

*9/30/2022*

> Step 1: Installing VSCODE

To first install VSCode you must go to this ![link](https://code.visualstudio.com/).

![image](https://user-images.githubusercontent.com/114376800/193378834-f03b0e83-109e-4403-bda8-84e487bb9f96.png)

There you will see the option to download it for your speciffic operating system as pictured above. For the purpose
of this tutorial, the instructions will dictate how to install it on **windows**.  
After the file finishes downloading, open up VScode. When it opens you should see something like this:

![image](https://user-images.githubusercontent.com/114376800/193378965-dc8f1e3c-456c-48b1-812e-ccfd7d765627.png)

Now, click the option for **terminal** and select **new terminal**

![image](https://user-images.githubusercontent.com/114376800/193379041-78e71dca-4d4f-4ad9-889e-3a31130e5703.png)

> Step 2: Remotely Connecting

________________________________________________________________________________

In order to connect remotely, you need 2 major requirements
- Vs Code
- SSH

To check if SSH has been downloaded unto your computer open up windows powershell
![image](https://user-images.githubusercontent.com/114376800/193379157-f4b42727-7db7-4cf0-a63c-de2d15f09ae2.png)

and run as an admistrator. To do this you will need to run these two commands:

![image](https://user-images.githubusercontent.com/114376800/193379215-e466460e-1fef-46e0-b885-9f45992fe4b1.png) 

After doing so, you should follow the instructions in this [guide](https://learn.microsoft.com/en-us/windows-server/administration/openssh/openssh_install_firstuse?tabs=gui)
to install the **Open SSH Client**. 
______________________________________________________________________________

After Installing the SSH Open Client, we are going to switch over to the terminal we created in VS Code. There, we will connect to the remote host
by using the account designated to us( in my case this is cs15lfa22ke@ieng6.ucsd.edu). After entering the ssh cs15lfa22zz@ieng6.ucsd.edu command
you will be prompted to input your password.

![image](https://user-images.githubusercontent.com/114376800/193379549-5e5b02bf-0ed0-4019-a4c2-ce4d21e08147.png)

Here, we are using the SSH command to connect. In the bottom half of this image, you will see that we have sucessfully connected 
to the remote host by the 'cluster status'. 

> Step 3: Trying Some Commands

Now that we are connected to the remote host, lets try out some commands. The first one you should attempt to us is **ls** and you can simply
type it into the terminal. This command will let you know what directories are within the remote host. Knowing this, we can then use the command **cd** to access these directories.

![image](https://user-images.githubusercontent.com/114376800/193379734-757c7a3e-0671-4408-9a6d-a6218850d6c7.png)

Try to create a directory by using the command **mkdir** (hint! It stands for make directory)

![image](https://user-images.githubusercontent.com/114376800/193379778-1c0544a6-5c79-4d0b-a0fe-89cac98c5d25.png)












