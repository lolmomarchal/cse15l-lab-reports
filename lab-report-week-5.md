LAB REPORT 3
===========
*Lorenzo Olmo Marchal*

*CSE 15L B05*

*10/30/2022*


>Grep

The grep command is used for both searching, printing, and matching files with the given parameters you give it. It is useful when trying to find instances of certain patterns or keywords. 

***grep -c***

![image](https://user-images.githubusercontent.com/114376800/199086786-22a7b867-46c0-420b-903f-3feac5da8f45.png)

The grep -c command allows you to find the count of a certain pattern/string within your files. For example in the example above, it counted a total occurences of the word "risk" within this text file. This is useful when trying to find pssages with key words wihtout having to open them and read through them. 

***grep -l***

![image](https://user-images.githubusercontent.com/114376800/199087332-62d36a55-abdc-4949-a0fd-a0d32b36a9a4.png)

The grep -l command lists all the files that have a certain keypattern/word within them. This is more helpful when trying to find certain instances of a word throughout large directories such as technical or biomed. 

***grep -A***

![image](https://user-images.githubusercontent.com/114376800/199088288-a6ca15a5-53ad-4561-b09e-d747d708ad42.png)
![image](https://user-images.githubusercontent.com/114376800/199088326-4683bae2-e394-47a8-9a41-5d4ce54e4fad.png)

In the format grep -A(number of lines you want to print ofter keyword) (keyword) (files(s)), grep -A finds all instances of a keyword within a directory (if used with * for the file parameter) and prints out the instances as well as the specified amount of lines after them. This is helpful when trying to find certain words as well as the contexts they are used in within files and directories, especially large ones. 












