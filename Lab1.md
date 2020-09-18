# Lab Task

(All this information is on the ee160 webstie)

## Making teams
1. Make teams of 3. Team of 2 will be allowed if there is not enough people.

## Logging to Wiliki
Windows Users use PuTTY

Mac Users use Terminal

If on MAC
```
ssh username@wiliki.eng.hawaii.edu
```

If on Windows - PuTTY
```
Host Name: wiliki.eng.hawaii.edu
Port: 22
Connection Type: SSH

Click "Open"
Enter ONLY username (without @hawaii.edu or @wiliki.eng.hawaii.edu)
Enter password
```

##  "Setting Up Your Environment"
Now create a directory, type the following:
```
mkdir EE160
```
PS: You can replace EE160 for the name of the new folder


## Unix Commands

### Tips
Write the following for more information of the command:

```
man name_of_Command
```

### Navigating in Unix
- pwd
    - print name of current/working directory

- cd
    - change directory (Move to a different folder)

- ls
    - list directory contents

- cat
    - concatenate files and print on the standard output
    - cat test test1 test2 > test3
        - This will create a file called test3 and all output will be redirected in a newly created file

### Managing files
- mkdir
    - make directory
- cp 
    - copy files and directory
- mv 
    - move (rename files)
- rm
    - rempve files

## VIM (Text editor)
Type the following in wiliki to find a manual for vi

```
vimtutor
```

### TLDR
- Press I: Insert Mode to start typing
- Press ESC: Command Mode to enter commands
    - :w  ->  save
    - :wq ->  save and quit
    - :q  ->  quit
    - :q! ->  force quit without saving
    

## ELM
```
Type: elm
To send: m
After finishing typing: CTRL - X
Sends a real email

use q to quit

Or y
```

```
elm -s subject_name [Name_Of_Email, you can just type UH Username]
```
