---Basic File and Directory Management:--
1.man(Manual Pages): it display's the manual page of for a command,providing the detailed explaination of the usage.
  Example:
        man ls -> Gives the detailed explanation for the ls

2.cd(Change directory): used to change the directory path.
  Example:
       1. cd [path]
       2. cd ..  moves to the parent directory
       3. cd ~  moves to the Home directory
       4. cd - switch back to the last visited directory

3.mkdir(Make directory): used to create a directory.
   Example:
        1. mkdir filename 
        2. mkdir -p parent_filename/child_filename  create a parent directory if does not exist.

4.mv(move or Rename Files): used to move or Rename files/directory's
    Example: 
        1. mv [source] [destination]
        2. mv oldName newName

5.cp(Copy Files): used to copy the files.
    Example:
       1.cp [source] [destination]
       2. cp -r folder1/ folder2/  

6.ls(List directory Contents):
    Example: ls [option] [directory]
       1.Flags:
         1. -l --> long listed formate
         2. -a --> show hidden files
         3. -h --> human redable file sizes
         4. -R --> list sub directory's recursively

7.pwd(print working directory): Outputs the absolute path of the current working directory.
    Example:
       pwd  

8.rm(Remove files/directory's): used to remove files/direcory's
   Example:
       1. rm [files/directory]
    Flags:
     1.-r Remove directories recursively.
     2. -f force deletion

9.chmod(Change file permission): used to change the file permission's
   Example:
      1. chmod [permissions] [files]
    -> Permissions are set using the numbers
     we have -> rwe
     r-(read) = 4
     w -(write) = 2
     e -(execute) = 1
    
     1. chmod 755 [filename]
    755 --> u g o
    u-> owner
    g-group
    o-other users
    in the above example  owner have read,write,execute, permissions,group have read,execute and others have read,execute permissions.

10.chown(change OwnerShip): used to change the ownerShip.
   Example: 
      sudo chown [ownerName] fileName
        1. sudo chown praveen test.txt
      sudo chown user:groupFileName test.txt
        1.sudo chown preveen:preveen test.txt
    -To create a new user---
     -> sudo useradd -m username
      -> sudo useradd -m nani
    -to Delete a user
     -> sudo userdel -r username
      -> sudo userdel -r nani

11.sudo(super user do): Run as a super user
   Example:
     sudo [command]
     sudo apt update

12.apt(Package Manager): package manager is used to manage the packages
   Example:
    sudo apt install [package Name]
    sudo apt upgrade [package Name]

13.touch(Create Empty Files): used to create a empty files
   Example: touch filename

14.cat(Concatenate and display files):
   Example: cat filename

15.less and more(View Large files): used to dispaly large files in a manageble way
   less: Navigate through the file.
    Example: less filename
   more: used to display the large file into page by page
    Example: more filename

16.tail(display at the end of the file): 
   Example: tail [filename]
   Flags:
     -n: specifies the number of lines
    tail -n 10 filename.txt  --> displays the last 10 lines of the file

17.rsync(Remote Synchronization):

18.grep(Global regularExpression print): used to search the text
   Example: grep [pattern] [filename]
   Flags:
     -i case-insensitive search
      -r recursive search
      -n show line numbers

19.find: used to find the files 
  Example: find . -name/-size filename/size
   1. find . -name 'test.txt'
   2. find . -size +1M

20.sort: used to sort the files data.
  Example: sort [filename]
           sort -r filename   -> sort in reverse order
    1.sort test.txt
    2.sort -r test.txt

21.date: used to display the date
  Exaple : date

22.tree (Directory tree): used to display the directory tree
  Example: tree [directoryName]

23.wc(word count): used to count the words,lines,charachters
  Example: wc filename
  Flags:
    -l  -> count lines
    -w -> word count
    -c -> char count 

24.ps(process status): used to display process status
  Example: ps -ef
           ps aux

25.top(real time process Monitoring):
  Example : top

26. df(disk space usage): used to display the disk space usage
  Example: df -h
   -h -> means human redable sizes

27. uname(System information): used to display the system information.
  Example: uname 
          uname -a  -> -a will give more detailed information

28.free (Memory Usage): displays the memory usage
   Example: free 
            free -h -> -h means human readble sizes

29.lspci(List pci devices):
  Example: lspci

30.kill(Terminate Process):
  Example: kill [pid]  -> pid means process id
  flags:
    -9 -> force kill

31.ping(Test Network Connection):
   Example: ping google.com

32.ifconfig(Network interface configuration):
   Example: ifconfig 

33.ssh(secure shell):
  Example: ssh user@hostname

34.xargs(Build Argument list):

35.printenv(print Environemnt Variables):
    Example: printenv

36.nano(Text Editor):
  Example: nano [filename]

37.awk(Text processing):
  Example: awk '{print $1}' filename

38.sed(Steam Editor): it process the text file. it works line by line
   -> It is used to edit streams (files) using regular expressions.
   -> But this editing is not permanent. It remains only in display, but in actual, file content remains the same.
  Example: sed -n '100,200p' filename

39. | (pipe): used to combine multiple commands, pipe convert the output of the one command as th input for thr anthor command
   Example : grep filename | wc -w

40. netstat(network Statastics): used to display the information about the network connections
   Example: netstat
   flags:
   -t -> show tcp connections
   -l -> displays listening ports
   -u -> displays udp ports
   -n -> Displays addresses and port numbers in numeric form,

----------Processes, ports-------------
1.List your browser's process ids (pid) and parent process ids(ppid)?
 -> ps -ef | grep -i 'brave'
2.Stop the browser application from the command line?
 ->

41.lsof(List Open Files): It is a command-line utility used in Unix-like operating systems, including Linux, to report a list of all open files and the     processes that opened them. This includes,
  1.Regular files
  2.Directories
  3.Network connections (sockets)
  4.Pipes
  5.Devices
  6.File names and paths
  7.Process IDs (PIDs) and names
  8.File types (e.g., regular file, directory, socket)
 