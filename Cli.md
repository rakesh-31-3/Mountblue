---Basic File and Directory Management:--
1.man(Manual Pages): it display's the manual page of for a command,providing the detailed explaination of the usage.
Example:
man ls -> Gives the detailed explanation for the ls

2.cd(Change directory): used to change the directory path.
Example: 1. cd [path] 2. cd .. moves to the parent directory 3. cd ~ moves to the Home directory 4. cd - switch back to the last visited directory

3.mkdir(Make directory): used to create a directory.
Example: 1. mkdir filename 2. mkdir -p parent_filename/child_filename create a parent directory if does not exist.

4.mv(move or Rename Files): used to move or Rename files/directory's
Example: 1. mv [source] [destination] 2. mv oldName newName

5.cp(Copy Files): used to copy the files.
Example:
1.cp [source] [destination] 2. cp -r folder1/ folder2/

6.ls(List directory Contents):
Example: ls [option] [directory]
1.Flags: 1. -l --> long listed formate 2. -a --> show hidden files 3. -h --> human redable file sizes 4. -R --> list sub directory's recursively

7.pwd(print working directory): Outputs the absolute path of the current working directory.
Example:
pwd

8.rm(Remove files/directory's): used to remove files/direcory's
Example: 1. rm [files/directory]
Flags:
1.-r Remove directories recursively. 2. -f force deletion

9.chmod(Change file permission): used to change the file permission's
Example: 1. chmod [permissions] [files]
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
sudo chown [ownerName] fileName 1. sudo chown praveen test.txt
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
sudo apt remove [package Name]

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
tail -n 10 filename.txt --> displays the last 10 lines of the file

17.rsync(Remote Synchronization):syncronize the file systems
it's like copy the files
rsync -av folder folder
git
18.grep(Global regularExpression print): used to search the text
Example: grep [pattern] [filename]
Flags:
-i case-insensitive search
-r recursive search
-n show line numbers

19.find: used to find the files
Example: find . -name/-size filename/size

1.  find . -name 'test.txt'
2.  find . -size +1M

20.sort: used to sort the files data.
Example: sort [filename]
sort -r filename -> sort in reverse order
1.sort test.txt
2.sort -r test.txt

21.date: used to display the date
Exaple : date

22.tree (Directory tree): used to display the directory tree
Example: tree [directoryName]

23.wc(word count): used to count the words,lines,charachters
Example: wc filename
Flags:
-l -> count lines
-w -> word count
-c -> char count

24.ps(process status): used to display process status
Example: ps -ef
ps aux
ps -e

25.top(real time process Monitoring):
Example : top

26. df(disk space usage): used to display the disk space usage
    Example: df -h
    -h -> means human redable sizes

27. uname(System information): used to display the system information.
    Example: uname
    uname -a -> -a will give more detailed information

28.free (Memory Usage): displays the memory usage
Example: free
free -h -> -h means human readble sizes

29.lspci(List pci devices):
Example: lspci
What is your audio driver?:
lspci | grep -i audio

30.kill(Terminate Process):
Example: kill [pid] -> pid means process id
flags:
-9 -> force kill

31.ping(Test Network Connection):
Example: ping google.com

32.ifconfig(Network interface configuration):
Example: ifconfig

33.ssh(secure shell):
Example: ssh user@hostname

34.xargs(Build Argument list):
Building and executing commands from standard input: xargs is particularly useful when you need to perform an operation on a list of items that is too long to fit on a single command line.
Processing output from other commands: xargs can take the output from other commands, such as find, grep, or ls, and use it as input to build and execute new commands.
Handling large numbers of files or directories: When working with a large number of files or directories, xargs can help by breaking the input into smaller chunks and executing the command on each chunk.
Performing parallel processing: xargs can be used with the -P option to execute multiple commands in parallel, which can significantly speed up processing time.
Handling input with special characters: xargs can handle input with special characters, such as spaces or newlines, by using the -0 option to treat input items as separated by null characters.

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

41.lsof(List Open Files): It is a command-line utility used in Unix-like operating systems, including Linux, to report a list of all open files and the processes that opened them. This includes,
1.Regular files
2.Directories
3.Network connections (sockets)
4.Pipes
5.Devices
6.File names and paths
7.Process IDs (PIDs) and names
8.File types (e.g., regular file, directory, socket)
Example:
lsof -i :5432

----------Processes, ports-------------
1.List your browser's process ids (pid) and parent process ids(ppid):
-> ps -ef | grep -i 'brave'
2.Stop the browser application from the command line:
-> pkill browserName
or
-> first start a browser by writing browsername
-> find the pid by running -> ps -e | grep -i firefox
-> \* if we write ps -e it only gives process id's(pid) but if we write ps -ef it will give pid and ppid and uid as well and if we write ps aux it will give pid,mem,cpu as well.
-> Then you will get pid of the browser like this .. -> 5552 ? 00:00:07 firefox
-> then write --> kill -9 5552
3.Check disk status:
-> df -h 4. Getting the most senior parent process:
-> ppid means parent process id and pid means process id
-> so,most senior process does'nt have any parent processs id's becouse it is the most senior, so we need to find pid which have ppid have 0
-> command: ps -ef | awk '$3 == 0 {print}'
-> $3 means 3 colunm which is ppid
5.learn what is the difference between absolute and relative paths:
1.Absolute: An absolute path is a complete path to a file or directory from the root directory.
->It starts with the root directory symbol (/) and specifies the entire path, including the file name.
->Absolute paths are always the same, regardless of the current working directory.
->Example: /home/waqas/documents/example.txt
2.Relative: A relative path, on the other hand, is a path that is relative to the current working directory.
->It does not start with the root directory symbol (/) and specifies the path relative to the current directory.
->Relative paths can be different depending on the current working directory.
->Example: documents/example.txt
6.Find out what are terminal control codes such as Ctrl + D, Ctrl + C, Ctrl + Z etc and use them:
1.Ctrl + D: Sends the EOF (End of File) signal, signaling the end of input to a program.
->Often used to terminate input to commands like cat or to log out of a terminal session.
2.Ctrl + C: Sends the SIGINT signal, which interrupts a running process (e.g., stopping a program like ping).
3.Ctrl + Z: Sends the SIGTSTP signal to suspend (pause) a running process. The process can be resumed later with the fg or bg commands.
7.Go to home folder. Use find command to find all occurrences of "java" text anywhere in any filename or directory name in your system:
command: sudo find / -iname '\*java'
