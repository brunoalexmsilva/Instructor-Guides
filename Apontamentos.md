#
# **Chapter 2** - Accessing the command line

- **passwd**
    - change users password
- **whoami**
    - verify logged user
- **cat *filename***
    - shows full file content
- **less *filename***
    - shows file content from the beguining, use enter or space to scroll
- **more *filename***
    - shows file content from the beguining, use enter or space to scroll
- **head *filename***
    - by default shows 10 firts lines, however we can use the -n option to specify the number os lines
- **tail *filename***
    - by default shows 10 last lines, however we can use the -n option to specify the number os lines
- **wc *filename***
    - counts lines (-l), words (-w) and characters (-c) of a file
- **useradd**
    - add user
- **command option**
    - --option -> the option is a full word
    - -option -> th e option is interpreted character by character
- **\\**
    - Used to separate a command in multiple lines
- **history**
    - allow access to the list of previous used commands
        - !command -> executes previous "command" 
        - !23 -> executes command listes in position 23

 - ![Quadro1, command navigation shortcuts](/images/navigationshortcuts.png)  
 *Quadro1: Command Navigation ShortCuts*
 - **file *filename*** 
    - verify the type of file content (ascii, bynary, ...)
- **command Esc+.**
    - recalls the last used option  

#
#
# **Chapter 3** - Managing Files from the Command Line
- ![Quadro2, Linux File System](/images/importantfolders.png)  
*Quadro2: Linux File System*
- **ls**
    - list files and directories
        - -l -> long list format
        - -a -> all files including hiden ones
        - -R -> recorsive listing
        - -i -> inode number (file registration number)
- **pwd**
    - print working directory
- **cd *directoryname*** 
    - change directory
-  **touch *filename***
    -create an empty file
- **mkdir *directoryname***
    - creates a directory
    - -p creates the parent directories if not present
- **cp  *source destination***
    - copy a file from source to destination
    - -r -> copy a directory with its content
- **rm *filename***
    - delete a file
    - -r deletes a directory and its content
- **rmdir *directoryname*** 
    - deletes an empty directoy
- **ln  *filename linkfilename***
    - create an hard link for the file
        - both the file and the link point to the same inode, to delete the file we must delete all links and file
        - ls -l second column will let you know how many links exist to the inode including the original file name
        - ls -li will do the same and will let you know the inode number
    - -s will create a soft link
        - soft links are link a pointer to the original file, if we delete the original file the link will persist but it will point to a file that does not exist  
- **whereis *file***
    -  Locates the file
- ***command* -- *-argument***
    - Ignores -arguments as a command option and treats is as an argument
          
- ![Quadro3, File Paterns](/images/filepaterns.png)  
*Quadro3: File Paterns*
- **~**
    - home directory
- **{}**
    - extension capacities
    - examples
        - {m..p} will expand to m n o p
        - {Sunday,Monday,Tuesday,Wednesday}.log will expand to Sunday.log Monday.log Tuesday.log Wednesday.log
        - file{1..3}.txt will expand to file1.txt file2.txt file3.txt
        - file{a,b}{1,2}.txt will expand to filea1.txt filea2.txt fileb1.txt fileb2.txt
- **VARIABLE=*value***
    - create a variable and add it a value
    - to get the variable value use $(VARIABLE)
- **$(command)**
    - command substitution 
    - example:
        - echo Today is $(date +%A).
        - Today is Wednesday.
        - Backslash before the variabe or command (\$HOME) will protect the variable from expanding
        - The same happens if we use single qoutes echo ' variable $HOME'  

#
#
# **Chapter 4** - GETTING HELP IN RED HATENTERPRISE LINUX
## READING MANUAL PAGES
- There are different MAN Pages available for consulting devided in different sections.
- ![Quadro4, MAN Sections](/images/mansections.png)  
*Quadro4: MAN Pages sections*
- The most important ones are 1 (user commands), 5 (configuration files) and 8 (admin commands)
- To check the available manual section of a command use **man -k *command***
- To check a specific section use (for example section 5) **man 5 *command***
- To navigate the man pages use the following shortcuts:
- ![Quadro5, MAN Navigatoin](/images/mannavigation.png)  
*Quadro5: MAN Pages Navigation*
- MAN pages are devide into diffent area with the following headings:
- ![Quadro6, MAN Headings](/images/manheadings.png)  
*Quadro6: MAN Pages Heagings*  
## READING INFO DOCUMENTATION
- **pinfo**
    - access to the top of the pinfo tree
- **pinfo *command***
    - direct access to the command pinfo page  
- To navigate the pinfo pages use the following shortcuts:
- ![Quadro7, PINFO Navigatoin](/images/pinfonavigation.png)  
*Quadro7: PINFO Pages Navigation*  
- Examples:
    - **man -t command > *filetoprint.ps*** -t prepares de man pages for printing
    - **evince *filetoprint.ps** - opens file in preview mode  
#
#
#  **Chapter 5** - CREATING, VIEWING, AND EDITING TEXT FILES
## REDIRECTING OUTPUT TO A FILE OR PROGRAM
- STANDARD INPUT, STANDARD OUTPUT, AND STANDARD ERROR:
- ![Quadro8, STDin,out,error](/images/std.png)  
*Quadro8: STANDARD INPUT, STANDARD OUTPUT, AND STANDARD ERROR* 
- Output Redirections:
- ![Quadro9, STDRedirections](/images/stdRedirections.png)  
*Quadro9: Output Redirections*  
- ***command* < *file***
    - < can be use to replace the keyboard as the standard input
## CONSTRUCTING PIPELINES
- Pipelines:
- ![Quadro10, Pipelines](/images/pipelines.png)  
*Quadro10: Pipelines*
- ***command* | *command*** 
    - Example: ls | wc -l
- Tee:
- ![Quadro11, Tee](/images/tee.png)    
*Quadro10: Tee*
- ***command* | tee *command* | *command*** 
    - Example: ls -l | tee /tmp/saved-output | less  
## EDITING TEXT FILES FROM THE SHELL PROMPT  
- VIM Operating Modes:
- ![Quadro11, VimModes](/images/vimmodes.png)    
*Quadro1q: VIM Operating Modes*  
- VIM comands:
    - **Esc** - Enter Command Mode  
        - **:w** - write changes  
        - **:wq** - write changes and quit vim  
        - **:q!** - quit vim discarding changes  
        - **dd** - delete one line (3dd deletes 3 lines below)  
        - **yy** - copies the line (4yy copy 4 lines below)  
        - **p** - pastes the copied lines (5p pastes 5 times the copied lines)  
        - **u** - undo  
    - **v**, **V**, **CRTL+v** - Enter Visual Mode
        - **v** - character mode (select characters)
        - **V** - line mode (select lines)
        - **CTRL+v** - block mode (select colunms)
            - **y** - copy
            - **p** - paste
            - **d** - delete
            - **u** - undo
    - **i** - Enter Insert mode  
## CHANGING THE SHELL ENVIRONMENT
- Assigning Values to Variables
    -  VARIABLENAME=value
- Retrieving Values with Variable Expansion
    - $VARIABLENAME
    - Example:   
        - [user@host ~]$ echo Repeat $COUNTx  
        - Repeat  
        - [user@host ~]$ echo Repeat ${COUNT}x  
        - Repeat 40x  
- Configuring Bash with Shell Variables