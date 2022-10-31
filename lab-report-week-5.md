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

