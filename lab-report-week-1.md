WEEK 1 LAB REPORT 
============
*Lorenzo Olmo Marchal*

*CSE 15L B05*

*9/30/2022*

> Step 1: Installing VSCODE

To first install VSCode you must go to this [link](https://code.visualstudio.com/)

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

**cat** is another essential command that allows you to print out what a file contains:

![image](https://user-images.githubusercontent.com/114376800/193379881-3aa5c384-1a80-41c1-880c-b36e1f699677.png)


There are other commands you can try as pictured below:

![image](https://user-images.githubusercontent.com/114376800/193379843-1ecef9d1-3791-44ab-86a3-d1c00a0af74e.png)

Each of these can allow you navigate through files.

> Step 4: Moving Files with scp

For this next step, you will need to log out of remote host. You can do so by typing out exit in the command line. 

![image](https://user-images.githubusercontent.com/114376800/193379953-6747ddda-6b7f-4daf-a336-d239e0bf6e43.png)

Once you have done so, you are going to make a new java file within VS Code and insert this piece of code: 

```class WhereAmI {
  public static void main(String[] args) {
    System.out.println(System.getProperty("os.name"));
    System.out.println(System.getProperty("user.name"));
    System.out.println(System.getProperty("user.home"));
    System.out.println(System.getProperty("user.dir"));
  }
}
 ```
 Then, you should run these two commands: 
 
 ![image](https://user-images.githubusercontent.com/114376800/193380036-15bd7537-79b3-4423-9992-0c82557b57dc.png)
 
 - The first one, **javac**, is the java compiler which compiles your code so you can run it with the **java** command. Always run javac after making anytype of change to your code. 

To copy and send the WhereAmI.java file to our remote host, we will be using the **scp** command. This stands for secure copy protocol!

![image](https://user-images.githubusercontent.com/114376800/193380127-d718b765-5e1c-41a1-b9f8-a7139efb318e.png)

Make sure that when using scp you clarify *what* and *where* you are sending. 

After doing so, log into your account again using SSH. Then use ls to make sure the file was transferred:

![image](https://user-images.githubusercontent.com/114376800/193381223-7fe01ecb-5f9e-4287-9950-3ecb89013762.png)

You can run this file the same way we did in local with javac & java.

> Step 5: Setting an SSH Key

An SSH Key is an individual identification "key" that allows you to connext to remote hosts without having to type in a password for every ssh or scp command you might do without being logged in- which in the long run saves a lot of time. 

To create one you must type in this command (make sure to be logged out from the remote host): 

![image](https://user-images.githubusercontent.com/114376800/193383801-35975b8e-490a-46ca-814f-dacbee90e3c0.png)

As you see we have 2 separate keys the private vs public key. For this we will only be using the **public** one. Like we did before, we will use **scp** to sned the ssh key files to our remote host. After doing so, you should be able to log in or send files to the remote host *without* needing a password. 

![image](https://user-images.githubusercontent.com/114376800/193383893-ff5ae121-a9ad-4bf3-91c5-b6dbd46b553a.png)


> Step 6:









 
 















