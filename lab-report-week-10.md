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
