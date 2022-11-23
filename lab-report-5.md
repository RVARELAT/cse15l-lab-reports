# Week 9 Lab Report

```
CPATH=".:../lib/hamcrest-core-1.3.jar:../lib/junit-4.13.2.jar"

rm -rf student-submission

# make student submission directory (credit to lab group partner Jan Kwong who had this great idea of creating a student submission directory to work with)
mkdir student-submission

git clone $1 student-submission

cp TestListExamples.java student-submission
cd student-submission


# space before [[ ]] to avoid error
if [[ -f "ListExamples.java" ]]
    then 
        echo "File Found: +1 point"
    else
        echo "Wrong file submitted: Grade 0 (Submit right file or check file name)"
        exit 0
fi 

javac -cp $CPATH *.java


if [[ $? -eq 0 ]]
    then 
        echo "Compile Succesful: +1 point"
    else 
        echo "Compilation Failed: 1/5 Grade" 
        exit 0
fi 

#credit to lab partner Jan Kwong who I borrowed the idea of using $CPATH to make sure we dont get the error of "error: package org.junit does not exist")
java -cp $CPATH org.junit.runner.JUnitCore TestListExamples > file2.txt

if [[ $? -eq 0 ]]
    then
        cat file2.txt
        echo "Passed Tests: 5/5 A+ Grade :)"
        exit
    else 
        cat file2.txt
        echo "Tests have failed: 2/5 Grade"
        exit
fi
```

## Screenshot for the output of which has the methods correct
![first image](ex2.png)
- This student submission recieves full credit :).

## Screenshot for the output which has which has a syntax error of a missing semicolon
![second image](ex3.png)
- This student submission gets credit for submitting the right file but since they failed the compilation, I only give them one point :(.

## Screenshot for the output which has a great implementation saved in a file with the wrong name.
![third image](ex5.png)
- This student submission recieves no credit but I do make sure to leave a message saying to make sure they submit the right file/file name.