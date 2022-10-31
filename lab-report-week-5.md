LAB REPORT 3
===========
*Lorenzo Olmo Marchal*

*CSE 15L B05*

*10/30/2022*

>Less

 In general the less command shows all the files within a directory/the contents of the file one "page" at a time. It allows to scroll through the contents as you would a page. In general it makes it easier to load large files/diretories such as ./technical and biomed as it increases the loading speed. 

***less -N***

![image](https://user-images.githubusercontent.com/114376800/198950238-aec17f9f-46bf-4efc-a2c4-4c764144d6c0.png)

The -N command allows you see the number of lines in each file. This is helpful as it allows you the see the amount of lines per file as you are scrolling through a large directory as ./techncial or a smaller subfolder like biomed. In a situation where you want to scroll page per page while trying to find a file with a certain amount of lines or even peruse to see what file (the ones with fewer/most lines)you wan to choose friends. 


***less -G***

![image](https://user-images.githubusercontent.com/114376800/198962131-9a7870d1-3942-4ff3-88a1-06aa44931802.png)

The -G command allows you to be able to go to the last line of the file. This is helpful when going through large files where you want to go directly to the last line to scroll from the end to the beginning of the file page to page.  

***less -p[pattern]***
![image](https://user-images.githubusercontent.com/114376800/198964991-f01362b0-328f-4afc-873c-fadd9aee6dd5.png)

![image](https://user-images.githubusercontent.com/114376800/198964953-02390802-a4a8-4ef9-97c5-9107f54b75e4.png)
 
 This finds the occurences of a pattern/string in a file and highlights them for you to scroll through. In a large file, this allows you to scroll through while having the pattern you require
/are looking.

>Find 

The find command in general allows you to find certain files depending on conditions you set such as date, size, etc..

***find -size***

![image](https://user-images.githubusercontent.com/114376800/198976438-3aa2be22-74a0-4d29-86bb-8045d592dc40.png)

The size command allows you find files that are within a certain that are equal or larger than the parameter you give. In the case of the example above, the size being used is files equal or greater than 1024 bytes. This is incredibly useful when trying to find certain files based on their size to either remove (to free up space) or just eventually sort them. 

***find -perm***

![image](https://user-images.githubusercontent.com/114376800/199082713-9895f57e-88b0-447f-a969-1dd311e44725.png)
![image](https://user-images.githubusercontent.com/114376800/199082848-fd89b5d9-9809-41cc-a811-06f94d13e38f.png)

The find -perm command allows you to find certain files depending on the requirements you give it. In this case, it is finding all of the files that are executable. This is helpful when you have many files, like in this repository, and want to find files you can run. 


***find -exec ***

![image](https://user-images.githubusercontent.com/114376800/199083925-458c191e-6191-4113-8e3e-77b983e9144b.png)

The find -exec command allows you to specificall execute additional operations (such as wc) on specific files found with the parameters. It allows for more efficiency as well as general practicality when navigating through files and executing extra commands while using find. 


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












