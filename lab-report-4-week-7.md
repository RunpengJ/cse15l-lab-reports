# Lab Report 4 Week 7

## Part I

- Task: In DocSearchServer.java, change the name of the start parameter of getFiles, and all of its uses, to instead be called base.

### Solution 

- Sequence of total key pressed: /start\<Enter>cebase\<Esc>n.n.:wq

Description 

** I type <span style="color:blue">:set number</span> to illustrate the line number

0. Initial state
    - ![initial](/Image/report4part1.1.png)

1. /start\<Enter> 
    - Find the first occurence of "start", and the cursor jumps to the first letter of the "start"
    - ![start1](/Image/report4part1.2.png)

2. ce
    - Delete the word "start", and switch into the insert mode
    - ![c](/Image/report4part1.3.png)
    - ![ce](/Image/report4part1.4.png)

3. base\<Esc>
    - Type the word "base", and press \<Esc> to back to the normal mode
    - ![basenormal](/Image/report4part1.5.png)

4. n . (dot)
    - Press n to go to the next occurence of the searched word, then press . (dot) to repeat the last modification
    - ![pressn](/Image/report4part1.6.png)
    - ![pressdot](/Image/report4part1.7.png)

5. n . (dot)
    - Repeat Step 4; Press n to go to the next occurence of the searched word, then press . (dot) to repeat the last modification
    - ![pressn2](/Image/report4part1.8.png)
    - ![pressdot2](/Image/report4part1.9.png)

6. :w\<Enter>
    - Press : to enter commands, enter w\<Enter> to save the changes
    - ![save](/Image/report4part1.10.png)


## Part II

- The first style took me about 23 seconds, and the second style took me about 13 about seconds. One difficulty I met is typing the scp command, as I need to know where in the remote account I want to put my file.

- Which of these two styles would you prefer using if you had to work on a program that you were running remotely, and why?
  - I prefer the second style. Because the scp command requires the path to where I want to place my file, which sometimes takes me time to find out. 

- What about the project or task might factor into your decision one way or another? (If nothing would affect your decision, say so and why!)
  - If the project is complicated and requires a lot of work, and I would prefer the second style, as my local computer might not be able to handle such complicated project. Otherwise, I may prefer the first style. 