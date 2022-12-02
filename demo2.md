# Skill Demo 2

1. fork


2. log in to ssh

3. javac Server.java GradeServer.java
   java GradeServer 4000

4. use "http://ieng6-20X:4000/"
   change url to "http://ieng6-20X:4000/grade?repo=https://github.com/ucsd-cse15l-f22/list-methods-signature"

5. add code

    ```bash
    if [[ $? -ne 0 ]]
    then
    echo "Failed to compile, 0/4"
    exit 1
    fi
    ```

6. rerun the "http://ieng6-20X:4000/grade?repo=https://github.com/ucsd-cse15l-f22/list-methods-signature"