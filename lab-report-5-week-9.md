# Lab Report 5 Week 9

## Grade Script

```
# Create your grading script here
CPATH=".:../lib/hamcrest-core-1.3.jar:../lib/junit-4.13.2.jar"
set -e

rm -rf student-submission
git clone $1 student-submission

cp TestListExamples.java student-submission
cd student-submission

if [[ -f ListExamples.java ]] 
then

  echo "ListExamples.java is a file"

else

  echo "****** Report ******"
  echo "No Credits!"
  echo "ListExamples.java not found or is not a file."
  exit 1

fi

set +e
javac -cp $CPATH *.java 2> compileerr.txt

if [[ $? -eq 0 ]]
then 

  java -cp $CPATH org.junit.runner.JUnitCore TestListExamples > out.txt
  
  if [[ $? -eq 0 ]]
  then 

    echo "****** Report ******"
    echo "Credited!"
    grep "OK" out.txt
    exit 0

  fi

  echo "****** Report ******"
  echo "No Credits!"
  grep -i "error" out.txt
  grep "Tests run:" out.txt
  exit 1
  
fi

echo "****** Compile error ******"
grep "error" compileerr.txt
exit 1
```

## Examples

1. ![correted](/Image/report5part1.1.png)

2. ![compileerror](/Image/report5part1.2.png)

3. ![filenamewrong](/Image/report5part1.3.png)

## Trace the Script

- I am going to trace the script with Example 1

```bash
# Create your grading script here
CPATH=".:../lib/hamcrest-core-1.3.jar:../lib/junit-4.13.2.jar" 
set -e # we make it exit immediately if a command exits with a non-zero status, return code was 0

rm -rf student-submission # remove the previous student submission, return code was 0
git clone $1 student-submission # copy the student's repository to be graded, return code was 0

cp TestListExamples.java student-submission # copy the TestListExamples.java to the student's repository to grade the submitted files, return code was 0
cd student-submission # change the directory into the student's submission, return code was 0

if [[ -f ListExamples.java ]] # the condition was true, because the file to be checked is in the student's repository
then

  echo "ListExamples.java is a file" # as the condition was true, the code output the string, return code was 0

else
  # the next 4 lines didn't get run because the condition was true
  echo "****** Report ******" 
  echo "No Credits!"
  echo "ListExamples.java not found or is not a file."
  exit 1

fi

set +e # we did this as we didn't want it exit immediately if a command exits with a non-zero status, return code was 0
javac -cp $CPATH *.java 2> compileerr.txt # try to compile the student's java files, return code was 0

if [[ $? -eq 0 ]] # the condition was true because the return code was 0 based on the last command
then 

  java -cp $CPATH org.junit.runner.JUnitCore TestListExamples > out.txt # run the compiled java files, the standard output for this run was that tests were successfully run, return code was 0
  
  if [[ $? -eq 0 ]] # the condition was true as the return code from the last command was 0
  then 
    # the following 4 lines get run
    echo "****** Report ******" , # output the string, return code was 0
    echo "Credited!" # output the string, return code was 0
    grep "OK" out.txt # output lines that contain "OK" in the out.txt file, return code was 0
    exit 0 # EXIT the grade script here with a value of 0

  fi
  # the following 5 lines didn't get run because of an early exit
  echo "****** Report ******" 
  echo "No Credits!"
  grep -i "error" out.txt
  grep "Tests run:" out.txt
  exit 1
  
fi
# the following 3 lines didn't get run because of an early exit
echo "****** Compile error ******"
grep "error" compileerr.txt
exit 1
```

