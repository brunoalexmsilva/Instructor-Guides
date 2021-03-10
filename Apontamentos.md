#
# Accessing the command line

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
# Managing Files from the Command Line
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
- 