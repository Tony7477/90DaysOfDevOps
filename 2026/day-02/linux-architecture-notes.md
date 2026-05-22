# Core components of linux

1. kernal : core component of linux , where it acts as bridge between software applications and hardware . it is responsible for majority of operations memory management, process scheduling ,hardware communication , system security.

2. init/systemd /systemctl:  systemd is the service manager and systemctl is the command line tool to talk to systemd.

3. user-space (in linux userspace is isolated from kernal space this is mainly done to avoid kernal level panics which can cause to system crash by creating a sandbox like environment to userspace).

## Process states :

Running (R) : the processes which are still executing.


Sleeping(interruptible (S) / uninterruptible (D)) : interrupted (The process will wake up on signal ), uninterrupted until I/o operation gets completed it will not respond.


Zombie (Z)  : if child process which completed still shows in process table , as parent process didn't acknowledge.


Stopped (T): the process has been suspended  and if its its need to be continued,  `SIGCONT`


## daily usage 5 commands

For creation and renaming files : `touch` and `mv` are used respectively.

For handling the directories  creating, removing , moving : `cd` ,`mkdir` , `rmdir` , `mv` respectively.

For retrieving the previous cmds you have used : `history` and `ctrl + r` 

For knowing what the exact command does : `man`  

For knowing present directory, copying , listing all files and directories : `pwd` , `cp` , `ls` respectively

For removing the file use : `rm`


what is devops?

devops is a combination of cultural philosophies, tools, practices in software development practices that acts as a catalyst so  the organization 
can deliver the product at faster pace.by ensuring improving delivery , Automation , code /application quality , continuous monitering and observability, continous testing.

Building, testing and deploying are the 3 things that are devops eccentric role and focus of interest should be here and do automation.

## Looking at system resources

`free -h`

Critical terms to know before using this cmd :

total : All the RAM the computer or VM has.
used : memory that programs are actually occupying
free : memory that is free and unused.
shared (space managed by kernal): memory shared between different programs (tmpfs)
buff/cache (freeable space and managed by kernal): 
available : The most important number it is an estimate of how much RAM a new program could start using without forcing anything to move to slow swap.

inside swap :
total : how much swap space you have .
used : how much swap is currently used.
free : unused swap space.

`df -h`

tells about diskspace on all mounted file systems











