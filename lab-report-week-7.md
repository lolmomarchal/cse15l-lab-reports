LAB REPORT 3
===========
*Lorenzo Olmo Marchal*

*CSE 15L B05*

*11/13/2022*

Part 1
------

>Task: In DocSearchServer.java, add a new line right before File[] paths = f.listFiles(); that prints out the toString of f and a message saying it’s a directory.

**instructions:***
```
vim DocSearchServer.java
/File[] <Enter>
 Press 'i' on keyboard -> enters insert mode
Go up a line (up key)
 paste line above
 System.out.println(f.toString + " is a directory");
<Esc>
:wq

```
1.**Enter vim mode**
 ![image](https://user-images.githubusercontent.com/114376800/201567862-c8a082a9-5d05-43e4-98ab-37372a4b9703.png)

2. **Finding the correct line**

![image](https://user-images.githubusercontent.com/114376800/201567999-f28c42ca-21ee-4d59-8fa9-31818be4ef5e.png)

3. **Entering insert mode**

![image](https://user-images.githubusercontent.com/114376800/201568059-4f66626a-af72-4c1e-a56e-413c054591e3.png)

4. **Going up to correct line and inputting correct code**

![image](https://user-images.githubusercontent.com/114376800/201568263-78ad9151-f733-4646-af5e-0cd31cbcaef8.png)

5. **Exiting vim mode**

![image](https://user-images.githubusercontent.com/114376800/201568286-9c953324-0935-4167-97e2-1f1876b0a3d8.png)

6. **Saving and exiting vim mode**

![image](https://user-images.githubusercontent.com/114376800/201568356-1661e999-fcc1-4860-966b-2bff2c3ec34f.png)


Part 2
-------

>Time through scp: 78 seconds

The most difficult part about using this method, is transversing through files. If you start in the directory where you are making changes you then have to scp (which I always spend a bit too much time on due to typos) and then  having to access the correct directory after ssh in order to run it. 

>Time through vim: 33 seconds

Using vim is much more efficient for this as you are already in the correct directory and only need to enter vim and iin less than 30 keystrokes make the changes you need. To run it, since you are already in the directory you simply need to javac and java the file.

Because of the reasons above, I would prefer to make changes in vim instead of making changes within the local computer when working on a program running on a remote computer. It is much more efficient and overall easier to do. 

Nevertheless, there might be certain things that *would* factor into my decision, mostly the amount of changes being made. If it is something as simple as the case above, vim is a much better option. However, it if it is somethign much more complex like making many hanges to a file, I would prefer to first finish it in my local computer- mostly so I can test is as I write and can look out of major errors such as missing a ";" that will be harder to find while only using vim. 
