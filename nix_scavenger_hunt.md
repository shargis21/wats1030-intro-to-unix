# *nix Scavenger Hunt

Complete the following challenges using the command-line interface on your favorite
Unix or Linux operating system. You are welcome and encouraged to consult any
additional documentation online or in books.

Please add your answers/responses/text pastes to the document after each prompt.

Note: For some of the challenges you will need to reference files included with
this repository, so you will need to fork the repo into your own Github account
and then clone it to your development environment.

## The Challenges

### Navigating the Filesystem

* Get an idea of where you are in the operating system. Use the `pwd` command to find your "path to working directory"--your current location in the filesystem of your devbox. 
*Paste the output of the `pwd` command here:*
/home/cabox/workspace

* Discover more about this filesystem. Use `ls` (the "list" command)to see what is in this directory.
*What directories and files do you see when you run `ls`?*
LICENSE    challenge_files        nix_scavenger_hunt_stretch.md                    
README.md  nix_scavenger_hunt.md

* You can use *options* to modify how a command runs. Try using `ls -alh` to see the contents of your current directory.
*How are the results different when you use the `-alh` options?*
total 36K                                                                                             
drwxrwxr-x  4 cabox cabox 4.0K Jan 12 16:12 .                                                         
drwxr-xr-x 11 cabox cabox 4.0K Jan 12 16:12 ..                                                        
drwxrwxr-x  8 cabox cabox 4.0K Jan 12 16:12 .git                                                      
-rw-rw-r--  1 cabox cabox 1.1K Jan 12 16:12 LICENSE                                                   
-rw-rw-r--  1 cabox cabox 2.7K Jan 12 16:12 README.md                                                 
drwxrwxr-x  7 cabox cabox 4.0K Jan 12 16:12 challenge_files                                           
-rw-rw-r--  1 cabox cabox 5.5K Jan 12 16:12 nix_scavenger_hunt.md                                     
-rw-rw-r--  1 cabox cabox  317 Jan 12 16:12 nix_scavenger_hunt_stretch.md 
*Not sure what the jumble of letters and one number at the beginning means yet, but this definitely gives more information about the contents of the directory like the date an time accessed as well as the file size.*

* The `man` ("manual") command tells you more about how any given command works. (*WARNING:* CodeAnywhere does not support the man command. You can click the following link to complete this task:). Run `man` to see instructions about how to use `man`. Then use `man` to learn what the `a`, `l`, and `h` options mean when used with the `ls` command. *Write down what those options do?*
ls -a: lists all files including hidden file starting with ','
ls -l: list with long format - show permissions
ls -h: list directory information

* Commands can also take *arguments*, which are usually the names of files or locations that you want the command to work with. Try running `ls /` to see what files are in the *root* directory of the filesystem. *What files and directories do you see listed?*
bin   dev  fastboot  lib    media  opt   root  sbin  sys  usr                                         
boot  etc  home      lib64  mnt    proc  run   srv   tmp  var 

* A Unix filesystem has a few special shortcuts to refer to specific locations. `/` indicates the *root* of the filesystem, meaning the top-most directory in the filesystem hierarchy. Use the `cd` ("change directory") command to move to the root directory. (Hint: Use `man` to look up the `cd` command if you have any issues) *Then run `pwd` and paste the output here:*
It just keeps telling me 'Permission denied' when I try to move to the root directory. I can move to all the other directories, media, var, home, etc. but when I do teh same command (cd /root) it says 'Permission denied'--update: Shawn told me I wasn't supposed to have permission so this is correct.


* Another special shortcut in Unix is the `~` location. This indicates the *user root* directory, meaning the top-most directory in the hierarchy that comes below your user account. Use `cd` to move to `~`. *Run `pwd` and paste the response here:* /home/cabox  

* Change directory into the `challenge_files` directory. Use `ls` to find only the files with a `.demo` pattern. *How many files do you find?* 3

* Use the `cd` command to move "up" one directory. *Where are you in the filesystem now?* /home/cabox  

* Press the up arrow on your keyboard. *What just happened?* pwd, the last command i typed

* Press the up arrow a few more times. *What do you see?*

* Run the `history` command. *What do you see?* cool! scrolling through the last commands I typed. That's handy!

### Observing the System

* Discover what account you are logged into using the `whoami` command. *What username are you currently using?* cabox

* Discover who else is on your system with the `who` command. *Are any other users using your system? If so, list them here:* cabox    pts/0        Jan 12 16:58 (54.186.244.104) 

* How long has your system been running? Use `uptime` to see, and *paste the result here:*
 17:03:09 up 51 min,  1 user,  load average: 0.03, 0.01, 0.00 

* Run `ps aux` and review the results. (Hint: Use `man` to learn more about the `ps` command and options.) *How do you interpret what you see here?*
It is showing me all processes with my user ID. It displays the process ID, terminal associated with the process, the cumulated CPU time-in, and the executable name. Apparently because I just used ps aux and not ps -aux, its showing me BSD options, which I"m not exactly sure what that means yet. I think the 'a' is a command the 'ux' means user X. I think actually because its BSD-style, the man says its also showing process state, and showing command args instead of the executable name.

* Run `top` and review the results. (Hint: You may need to use `ctrl-c` to get out of this app.) *How do you interpret what you see here?* 
The top program provides a dynamic real-time view of a running system. It can display system summary information as well as a list of tasks currently being managed by the Linux kernel. Yes I copy and pasted that from the man. what i'm seeing seems right. the only programs I have running are the root, the cabox, and I assume the www-data are the websites I have open and running.

### Finding and Viewing Files

* Make sure you are in the `challenge_files` directory. Use the `*` wildcard to find all the files that have the word "credit" in the filename. *How many files did you find?* 2, credit_cards.txt  credit_cards2.txt  

* Use the `more` command to view one of the `credit_cards` files you just discovered. (Hint: Type `q` to quit viewing the file. Press the `spacebar` to page down. Use your keyboard arrows to move up/down.) *What is the date in the file you have viewed?* Last updated 01-15-2015

* Use the `find` command to search for files more effectively. Search the sub-directories under `challenge_files` to find the location of the file named `modi_laboriosam.txt`. *Where is that file located?* /home/cabox/workspace/challenge_files/tmp/modi_laboriosam.txt 

* Use the `grep` command to search for text within a file. Use `grep` on all the `.user` files in `challenge_files` to find which files contain "WA" (the abbreviation for Washington state). *How many files did you find?*
2,
Lissie-Strosin.user                                                                
Britt-Erdman.user 

* Use the `-r` option of `grep` to *recursively* find the text "Waldo" hidden in a file somewhere under the `challenge_files` directory. *Paste the result showing the file and line where the word "Waldo" shows up.*
serial-numbers/eaque_molestiae.txt:Ut est maiores quia autem. Nisi modi Waldo sed c
orporis sit explicabo ut est. Et est placeat ea sunt sunt consectetur sunt incidunt
. Explicabo vel esse blanditiis dolorem culpa non quia. 

### Pipes and Connecting Commands

* Sometimes it's useful to output the results of a command to a text file for further analysis, reference, or processing. Try running `ls > files.txt`. Notice that the file `files.txt` was created. View that file using `more`. *What do you see in the `files.txt` file?* All of the .user and .demo files are there listed out. It just listed out all of the files that were in the challenge_files. 

* Notice that if you run `ls -alh` in the `challenge_files` directory, the files scroll by very quickly. Sometimes it would be better to get the results in a paginated format. Try running `ls -alh | more`. *Describe what you see when you run `ls -alh | more`.* 
When I first ran just 'ls-alh' all the files just showed up at once, but when I ran it with more, it gave me the option to scroll through them page by page, which is nice. If I hit enter, it moves down one file, if I hit the spacebar it moves down a whole page. 

* Earlier, when you viewed the list of active processes on your devbox using `ps aux`, the list was probably really long. You can make this list more manageable by using the pipe (`|`) to filter the results of `ps` using `grep`. Run `ps aux | grep <your_username>` to see what processes are running for your specific user. *Paste the list of processes that reference your username here:*
root       783  0.0  0.6  63876  3328 ?        Ss   01:21   0:00 sshd: cabox [
priv]                                                                         
cabox      785  0.0  0.2  64140  1536 ?        S    01:21   0:00 sshd: cabox@n
otty                                                                          
cabox      786  0.0  0.1  12780   988 ?        Ss   01:21   0:00 /usr/lib/open
ssh/sftp-server                                                               
root       998  0.0  0.6  63876  3476 ?        Ss   01:33   0:00 sshd: cabox [
priv]                                                                         
root      1000  0.0  0.6  63876  3480 ?        Ss   01:33   0:00 sshd: cabox [
priv]                                                                         
cabox     1002  0.0  0.2  63876  1464 ?        S    01:33   0:00 sshd: cabox@p
ts/0                                                                          
cabox     1003  0.0  0.2  63876  1468 ?        S    01:33   0:00 sshd: cabox@p
ts/1                                                                          
cabox     1004  0.0  0.8  20632  4556 pts/0    Ss+  01:33   0:00 -bash        
cabox     1051  0.0  0.8  20632  4556 pts/1    Ss+  01:33   0:00 -bash        
root      1398  0.0  0.6  63876  3480 ?        Ss   01:33   0:00 sshd: cabox [
priv]                                                                         
cabox     1400  0.0  0.2  64008  1492 ?        S    01:33   0:00 sshd: cabox@p
ts/2                                                                          
cabox     1401  0.0  0.8  20632  4572 pts/2    Ss   01:34   0:00 -bash        
cabox     1607  0.0  0.2  15520  1144 pts/2    R+   01:42   0:00 ps aux       
cabox     1608  0.0  0.1   8816   760 pts/2    S+   01:42   0:00 grep --color=
auto cabox  
