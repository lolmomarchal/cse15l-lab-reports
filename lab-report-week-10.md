LAB REPORT 5
===========
*Lorenzo Olmo Marchal*

*CSE 15L B05*

*11/28/2022*

>Grade.sh code

```
# Create your grading script here

set -e

rm -rf student-submission
git clone $1 student-submission
Directory=testingdir
if ! [[ -d "$DIRECTORY" ]]; then
  rm -rf testingdir

fi
# checking if files are inside
FILE=ListExamples.java
cd student-submission

if [[ ! -f "$FILE" ]];
then
  echo "Missing listExamples File, please submit again"
  exit 1
fi
cd ..

#making new directory and putti"ListExamples.java"ng list examples + tests inside

mkdir testingdir
cd student-submission
cp ListExamples.java ../testingdir
cd ..
rm -rf student-submission
cp TestListExamples.java testingdir
#going inside testing and then running junit

cd testingdir

set +e

CPATH=".:../lib/hamcrest-core-1.3.jar:../lib/junit-4.13.2.jar"
SCORE=0;
pwd
javac -cp $CPATH *.java

if [[ $? -eq 0 ]]
   then
       echo "Compiled, good job!"
        SCORE=1
       java -cp $CPATH org.junit.runner.JUnitCore TestListExamples 2> err.txt
        ERR=$(grep "FAILURES" err.txt)
       if [[ $ERR == "FAILURES!!!" ]]
       then
         cat err.txt
         echo "Your code failed at least one test, please resubmit"
        echo $SCORE
         else
           SCORE=2
         echo "Score" = $SCORE
        exit 0
      fi
   else
     java -cp $CPATH org.junit.runner.JUnitCore TestListExamples 2> out-err.txt
       echo "Compile failed, here are the errors found."
       cat out-err.txt
       echo "Score =" $SCORE
       exit 1
   fi
   echo $SCORE
```


>Screenshots of submissions 

***A.Compiler error***

![image](https://user-images.githubusercontent.com/114376800/204355666-fbf1e88f-731d-4e1c-a751-009b58853412.png)

***B.Wrong Filter Parameters***

![image](https://user-images.githubusercontent.com/114376800/204365706-fdb62fc5-b292-4583-bf18-5ae6d698d442.png)

***C.Wrong FileName***

![image](https://user-images.githubusercontent.com/114376800/204365837-e2ae1a5c-f976-4769-b369-efb1971e161e.png)


>Tracing Code

For this, I will be tracing the first example of submissions: the compiler error. 

**Lines 1-8**
The first line sets -e to make sure it stops if an error is found. It runs with 0 as it succeeds . It runs through the until line 5 where there is an if statement to see if the directory we are going to make , testingdir already exists. If it does, it is deleted. In this case, it does from a previous run so the code will pass through here with an $? of 0 for -d. 

*Do not run: N/A*

**Lines 8-15**
In line 8, the program creates a variable File with the value for ListExamples.java and line 9 cd into the student-submission directory. The if statement on line 10 checks if the file cannot be found. If it does, it does not run the inside of the if statement, which is the case for this repository so the statement is false. It then exits out of the student directory.

*Do not run: 10-14*

**Lines 16- 26**

In these lines, a new directory is being made and ListExamples and TestListExamples are being transferred over to it. The set -e is removed by line 24. Two variables, CPATH (with the path for Junit) and Score (to keep track of points) are initialized. 
Do not run: N/A

**Lines 27-51**

![image](https://user-images.githubusercontent.com/114376800/204366028-255d3ff2-94e3-4217-8191-3003895c3a34.png)


Line 27 is the call to javac. Because there is a compiling error, this is going to return with an exit code of 1. The standard error of this will be the error displayed in the screenshot above and the output will be 1.

Because the output for the last command is 1, the file skips the if condition in line 29 until the else in line 45. The content in this if is if the code compiles to look for the number of failed tests and update the score depending on the results (1 for compilation, 2 for all tests passed). 

Nevertheless, the script for this specific example continues on like 45 where javac is called once again to redirect the stderr into a file called out-err.txt and printed which would be the error, once again. The stdout of this will not be applicable as the files did not compile. In lines 47-49 the script echoes some feedback about the error including a message that the file did not compile, the stderr and the score (0 for lack of compilation). The program then exits with an exit code of 1. 


*Do not run: 29-44*








