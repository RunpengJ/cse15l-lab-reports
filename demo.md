## UCSD CSE15L F22 Skill Demonstration 1

https://ucsd-cse15l-f22.github.io/week/week3/#setup 
Task Description:

1. Clone this repository (we recommend using the command line in VScode!): https://github.com/ucsd-cse15l-f22/skill-demo1

   - git clone https://github.com/ucsd-cse15l-f22/skill-demo1 demo1

2. Build and run the tests locally, using javac and java (note that bash will not work locally on the Windows machines)

    - javac -cp ".;lib/hamcrest-core-1.3.jar;lib/junit-4.13.2.jar" *.java

    - java -cp ".;lib/junit-4.13.2.jar;lib/hamcrest-core-1.3.jar" org.junit.runner.JUnitCore TestDocSearch


3. Fix the broken test (the test is wrong, not the implementation) and rerun locally
    - Change 10 total to 1391 total


4. Build and run the server locally, using javac and java (note that bash will not work locally on the Windows machines)

    - Mac Bash start.sh 4567
    - javac Server.java DocSearchServer.java 
    - java DocSearchServer 4567

5. In a browser, visit the paths / and /search?q=... where ... is a search term of your choice that finds at least 2 files on localhost to demonstrate that it works

    - /
    - /search?q=chapter

6. Get the code for the server onto ieng6 and build and run it there (your choice of how) as the provided account. A ssh key will be configured for the account you are provided for the exam.

    - scp TestDocSearch.java cs15lfa22jo@ieng6.ucsd.edu:~/
    - ssh cs15lfa22jo@ieng6.ucsd.edu
    - WaTaTaPuNeKuC8HiHaSi[aMaFoNoYe
    - git clone https://github.com/ucsd-cse15l-f22/skill-demo1 de1
    - mv TestDocSearch.java de1/
    - cd de1
    - bash start.sh 4567

7. Open the path / and /search?q=... where ... is a search term of your choice that finds at least 2 files on the ieng6 server to demonstrate that it works
    - http://ieng6-20#.ucsd.edu:4567
    - /
    - /search?q=chapter

8. Change the program so that it searches for substrings within the path based on the query, rather than within the file’s contents. For example, a query like /search?q=rr74 would find the file technical/biomed/rr74.txt
    - Change Line 47: f.getName()
    
9. Build and run the server locally and demonstrate the new behavior
    - javac Server.java DocSearchServer.java 
    - java DocSearchServer 4567

10. Copy the change to the remote ieng6, then build and demonstrate the new behavior there
    - scp DocSearchServer.java cs15lfa22jo@ieng6.ucsd.edu:~/de
    - ssh 
    - Bash start.sh
    - /search?q=chapter

Course website: https://ucsd-cse15l-f22.github.io/

Repository link for skill-demo1: https://github.com/ucsd-cse15l-f22/skill-demo1
Link to my repo: https://github.com/RunpengJ/cse15l-lab-reports 


