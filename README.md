# Linux-Fundamentals
Tasks refers to the structure and organization of the Linux operating system.

## (1) Linux System Architecture
```
1- What does kernel mean ?
2- What does Operating System mean ?
3- Is Linux a kernel OR operating system ?
4- What is an Architecture Layer Diagram ?
5- What is user space ?
6- What is kernel Space ?
7- Describe Main Layers for Linux kernel.
8- Identify the Purpose for each Layer.
9- Identify how each layer interacts with the lower one.
10- What is Glibc Library ?
11- What does command mean ?
12- Describe command in-terms of the following:  a. name b. Location c. version d. input  e. output
```

### 1- What does kernel mean ?
* a kernel is the most basic level or core of an operating system, responsible for resource allocation, file management, and security.


### 2- What does Operating System mean ?
* An Operating System (OS) is a program that manages all of the other application programs in a computer after being initially loaded into the computer by a boot program.
* It manages computer hardware and software resources, and provides common services for computer programs.
* The operating system acts as an intermediary between programs and the computer hardware.
* It provides a consistent and repeatable way for applications to interact with the hardware without the applications needing to know any details about the hardware.
* Users can interact directly with the operating system through a user interface, such as a command-line interface (CLI) or a graphical UI (GUI).


### 3- Is Linux a kernel OR operating system ?
* Technically, Linux is a kernel, which is the core part of an operating system.
* It’s the main component of a Linux operating system (OS) and is the core interface between a computer’s hardware and its processes.
* It communicates between the two, managing resources as efficiently as possible.
* However, the term “Linux” is often used to refer to a complete operating system that includes a shell (like bash) and command line and/or GUI tools to control the system.
* The technically correct term for this complete operating system is “Linux distribution” or simply "Linux distro".
* Examples of popular Linux distributions include Ubuntu, Red Hat, and Debian.


### 4- What is an Architecture Layer Diagram ?
![image](https://github.com/Bilalmhmd/Linux-Fundamentals/assets/70241688/c674c87e-722a-4351-ab4f-78f58c14fc31)

### 5- What is user space ?
* user space refers to the portion of memory containing unprivileged processes run by a user.
* It is strictly separated from kernel space, where privileged operating system kernel processes execute.
* Contains user-level applications, libraries, and programs.
* Unprivileged: These processes do not have complete access to the computer’s memory, disk storage, network hardware, or other resources.
* Sandboxed: User space processes run in their own virtual memory space and cannot directly access the memory of other processes.
* Examples: Regular applications, file manipulation software, input/output operations, etc.


### 6- What is kernel Space ?
* Reserved for privileged operating system functions.
* Only trusted code (the operating system kernel) has complete access to all components of the computer.
* Vulnerabilities in privilege separation can lead to security risks.
* Examples: System calls, device drivers, and core OS functionality.


### 7- Describe Main Layers for Linux kernel.
### 8- Identify the Purpose for each Layer.
* Process Scheduler:
  * The process scheduler ensures fair distribution of CPU time among all running processes.
  * It determines which process gets to execute next.
  * By efficiently managing CPU resources, it prevents starvation and ensures responsiveness.
  * Think of it as the traffic cop for processes, directing their execution.
  * !Virtual Resources for each Process.
* Memory Management Unit (MMU):
  * The MMU handles memory allocation and distribution.
  * It creates separate virtual address spaces for each process, isolating them from one another.
  * Manages page tables, swapping data between RAM and disk, and ensuring efficient memory usage.
  * !Virtual Memory.
* Virtual File System (VFS):
  * The VFS provides a unified interface for accessing different file systems (e.g., ext4, NTFS, NFS).
  * It abstracts the underlying file system details, allowing applications to work with files and directories uniformly.
  * Handles file I/O, permissions, and caching.
  * !File System Layers.

### 9- Identify how each layer interacts with the lower one.
* Process Scheduler:
  * Interaction with Memory Management Unit (MMU):
    * The process scheduler interacts with the MMU to allocate memory for process execution.
    * When a process is scheduled to run, the MMU ensures that its virtual address space is mapped to physical memory.
    * Context switches between processes involve updating the MMU’s page tables to switch memory mappings.
  * Interaction with Virtual File System (VFS):
    * The process scheduler interacts indirectly with the VFS.
    * When a process performs file I/O (e.g., reading or writing files), the scheduler ensures that the necessary file system calls are executed.
    * The VFS handles the actual file operations, translating them into low-level disk or network I/O.
* Memory Management Unit (MMU):
  * Interaction with Process Scheduler:
    * The MMU interacts with the process scheduler during context switches.
    * When a new process is scheduled to run, the MMU updates its memory mappings to reflect the new process’s address space.
    * During context switches, the MMU flushes cached data and loads the page tables for the next process.
  * Interaction with Virtual File System (VFS):
    * The MMU does not directly interact with the VFS.
    * However, when a process accesses files, the MMU ensures that the correct memory pages (containing file data) are loaded into RAM.
    * The VFS handles the higher-level file system operations.
* Virtual File System (VFS):
  * Interaction with Process Scheduler:
    * The VFS interacts indirectly with the process scheduler.
    * When a process performs file-related system calls (e.g., opening a file), the scheduler ensures that the appropriate VFS functions are invoked.
    * The VFS manages file descriptors and handles file access permissions.
  * Interaction with Memory Management Unit (MMU):
    * The VFS does not directly interact with the MMU.
    * However, when reading or writing files, the VFS ensures that the correct memory pages are accessed.
    * The MMU translates virtual addresses to physical addresses for file data retrieval.


### 10- What is Glibc Library ?
* glibc provides a collection of C library functions that offer low-level functionality to the operating system and other system software.
* It serves as a bridge between user-level applications and the Linux kernel.
* These functions include critical APIs such as ISO C11, POSIX.1-2008, BSD, and OS-specific APIs.
* Examples of functions provided by glibc include ```open``` , ```read```, ```write```, ```malloc```, ```printf```, ```getaddrinfo```, ```dlopen```, ```pthread_create```, ```crypt```, ```login```, and more.


### 11- What does command mean ?
*  a command refers to an instruction or action that you provide to the Linux shell (also known as the command-line interface or terminal). These commands allow you to interact with the operating system, perform tasks, and manage various aspects of your system.
*  Command Structure:
   * A command typically consists of:
     * The actual command name (e.g., ```ls```, ```cd```, ```mkdir```).
     * Optional arguments (additional information or options) that modify the behavior of the command.
   * For example:
     ```
     ls -l lists files and directories in long format.
     mkdir myfolder creates a new directory named “myfolder.”
     ```

### 12 - Describe command in-terms of the following: 
#### a. name b. Location c. version d. input  e. output

![image](https://github.com/Bilalmhmd/Linux-Fundamentals/assets/70241688/25c88876-1f99-474a-9002-8d2e17603bcf)

* a. Name:
  * A command is identified by its name, which represents a specific action or operation.
  * Examples of command names in Linux include ```ls```, ```mkdir```, ```cp```, ```ps```, and ```apt-get```.
    
* b. Location:
  * Commands are accessible from the command-line interface (CLI) or terminal.
  * They reside in specific directories known as command paths.
  * Common command locations:
    * ```/bin```: Contains essential system commands available to all users.
    * ```/usr/bin```: Holds additional user-level commands.
    * ```/sbin```: Stores system administration commands (usually for superusers).
    * ```/usr/sbin```: Contains additional system administration commands.
      
* c. Version:
  * Each command has a version associated with it.
  * Versions may differ based on the Linux distribution and the specific software package.
  * To check a command’s version, use the ``--version`` flag (e.g., ls ```--version```).
    
* d. Input:
  * Commands accept input in the form of arguments or options.
  * Arguments modify the behavior of the command (e.g., filenames, directories).
  * Options (flags) provide additional instructions (e.g., ```-l``` for long format in ``ls``).
    
* e. Output:
  * Commands produce output based on their functionality.
  * Output can be displayed directly in the terminal or redirected to files.
  * Examples:
    * ```ls``` lists files and directories.
    * ```mkdir``` creates a new directory.
    * ```ps``` displays information about running processes.


## (2) System Call Interface

```
1- Trace System call for [ ps & cd & ls ] commands.
```

### 1- Trace System call for [ ps & cd & ls ] commands.
```
strac -c ps
```
![strace_ps](https://github.com/Bilalmhmd/Linux-Fundamentals/assets/70241688/8106c076-11b8-4851-8fcc-d67cad16965e)

```
strac -c cd
  The error message you're encountering is because cd is a shell builtin command,
  not an executable file that can be traced using strace.
  strace is used to trace system calls and signals for a given executable or process.
  Since cd is a shell builtin, it doesn't exist as a separate executable file in the file system,
  hence strace can't find it.
```
![strace_cd](https://github.com/Bilalmhmd/Linux-Fundamentals/assets/70241688/cb7a8d7b-ebba-42a4-ae96-7a1553099bcd)

`NOTE:`
you can indirectly trace the system calls that occur when you execute `cd` by invoking `strace` within a subshell.
Here's how you can do it:
```
strace -c bash -c "cd /path/to/directory"
```
![strace_cd_new](https://github.com/Bilalmhmd/Linux-Fundamentals/assets/70241688/d56b4b0d-2405-4900-a549-e7dde4ae274e)

```
strac -c ls
```
![strace_ls](https://github.com/Bilalmhmd/Linux-Fundamentals/assets/70241688/4e1e7a26-f7dd-4459-813c-cf19d0972786)

### 2- a.extract files of interactions. b. Identify all the system calls that have been used. c.Measure system calls performance in terms of time.


## (3) Process Management Stack

```
1- What is a Process ?
2- What is a Process Owner ?
3- What are Parent & Child Processes ?
4- What are Process IDs ?
5- What is a Process Group ?
6- What are Process Types ?
7- what is The “Job” Concept ?
8- what is the Job Control ?
9- What are Jobs and Process Groups ?
10- what is Shell Session ?
11- what is Automatic Process ?
12- what are Cron Jobs ?
13- what is Daemon Process ?
```

### 1- What is a Process ?
- A Process is an instance of a running program.
- Linux is a multi-tasking OS, This means it can run multiple tasks simultaneously.
- The Linux Kernel distribute the processor time among the running processes.
- Even a single application, may have multiple threads (for doing multiple actions in parallel).
- In Linux, a thread is just another process (of special nature) so a multi-threaded application is an application that have multiple processes running in parallel.
- We can also have multiple instances of the same application running simultaneously in different processes.

### 2- What is a Process Owner ?
- Linux is a multi-user System, so multiple users can be using the system.
- Each user starting a process becomes its owner.
- Note that the process owner does not have to be the same as the owner 
  of the binary file for the process.
- Each process have an owner, some processes started by the system can 
  be owned by the root user.
- The process owner has privileges on his process. He can kill it, pause it, 
  resume it. 
- The ‘root’ user have super powers on all system processes.
- The process inherits its user privileges when trying to access resources 
(for example when a process tries to write in a file).

`Remember:` if the process file has the permission “s”, the process inherits its permissions from its 
file owner (and not the process owner).

### 3- What are Parent & Child Processes ?
- Processes are organized in parent-child relationships.
- Each process that creates another becomes the parent, and the new 
  process becomes the child process.
- First process to run is the `systemd` process that is started at system 
  boot… this is the grand parent of all processes in the whole system.
- If a process dies, then its orphan children are re-parented to the `systemd`
  process.


### 4- What are Process IDs ?
- Each Process has a unique number to identify it.
- It is called Process ID (PID).
- Each process will maintain its PID and the PID of its parent (PPID).
- The PID and PPID enable us to build the process hierarchy tree.
- The `systemd` process is the parent of all processes, which has `PID = 1  - PPID = 0`
- To show the Process tree hierarchy:
  
```
$ pstree (Show tree starting at systemd process)  
```
![pstree](https://github.com/Bilalmhmd/Linux-Fundamentals/assets/70241688/4e99325c-861f-443c-b507-14b9fac20ed6)

```
$ pstree -p (to show PIDs of all processes).
```
![pstree -p](https://github.com/Bilalmhmd/Linux-Fundamentals/assets/70241688/73f6de36-7165-4fe3-9b25-0590475ec435)

```
$ pstree 1000 (Show tree starting at process with PID = 1000).
- I didn't have a process with PID = 1000. , SO i will try anthor PID = 2347. 
```
![pstree 2347](https://github.com/Bilalmhmd/Linux-Fundamentals/assets/70241688/9a65e895-f65a-498f-91f9-aae83c48f366)


### 5- What is a Process Group ?
- Process Group is a family of processes (A process, its children,grand-children, …etc).
- When a process is created it becomes a member of the process group of its parent.
- Some processes may be started in its new group, and it will 
  detach from its parent group, and become a Process Group Leader.
- All descendants will follow the new group.
- Each process maintain the ID of its process group (PGID)
  - For a normal process, its PGID is the same as its parent PGID.
  - For a Process Group Leader, its PGID is the same as its own PID.
 
```
 - This draw will explain the relation between process and others with groups.
```
![image](https://github.com/Bilalmhmd/Linux-Fundamentals/assets/70241688/65deb34b-e5ae-4470-b9a8-365ae2dbe1ef)


### 6- What are Process Types ?
- Processes can be classified into one of the following:
  - Interactive Processes.
  - Automatic Processes (Batch Processes).
  - Daemon Processes.


`Interactive Process: ` 

- The process is started by a user within a terminal
- It is controlled via that terminal
- It is attached to its terminal, and will be killed if its terminal is closed.
- It is called interactive, cause it communicates with the user through the terminal.
- Can run in the foreground or the background.
- `Examples: `
  
  ```
  $ ls
  $ cat *.log | grep “error” | sort 
  $ echo “Good Morning” > my-file
  ```
 ![types](https://github.com/Bilalmhmd/Linux-Fundamentals/assets/70241688/b3cadae3-8353-419b-b762-8e2ab71e56eb)


### 7- what is The “Job” Concept ?
- When a command is issued, the execution of this command is called a Job.
- The Job can be,
  - A single process
  ```
  $ gedit
  $ cat my-file
  ```
  - Multiple connected processes
  ```
  $ ls | sort
  ```
  - A script that runs multiple processes (within a sub-shell)
  ```
  $ ./my-script
  ```
  - Jobs can be manipulated in the shell via “Job Control”

  - Jobs can run in the,
    - Foreground
      - All input and Output of the terminal is exclusively for this job.
      - User can not use the terminal for any other activity or start other jobs.
      - Only One Job can be a foreground job.
      - Initially the shell is in the foreground until a job is launched.
    - Background
      - Job Input/Output does not utilize the terminal.
      - However, it is `still attached to the terminal.`
      - Possibility of multiple Jobs in the background for the same terminal.
      - Sometimes it is useful when,
        ```
        - The process in the job has a Graphical User Interface and does not need the 
          terminal for its Input/Output.
        - The process takes a long time in processing, and user needs to use the terminal 
          for other purposes.
        - User needs to launch another job on the same terminal.
        ```

### 8- what is the Job Control ?
- Start a job in the foreground
```
$ gedit
```
![gedit](https://github.com/Bilalmhmd/Linux-Fundamentals/assets/70241688/05fac491-fa91-4eb3-8f09-513d1b28acc3)

- Start a job in the background
```
$ gedit &
```
![gedit ](https://github.com/Bilalmhmd/Linux-Fundamentals/assets/70241688/b7939df5-a265-4416-bee8-5f696d3a2fe1)

- Stop the foreground Job
```
$ gedit
Ctrl-z
```
![stop](https://github.com/Bilalmhmd/Linux-Fundamentals/assets/70241688/0973eeca-0375-444a-8fc8-b72111befc21)

- Resume the Paused Job in the foreground
```
$ gedit
Ctrl-z
$ fg
```
![resume](https://github.com/Bilalmhmd/Linux-Fundamentals/assets/70241688/3c3cd173-b6d8-435e-a27a-e5f33ca8be7e)

- Interrupt a foreground Job
```
$ gedit
Ctrl-c
```
![interrupt](https://github.com/Bilalmhmd/Linux-Fundamentals/assets/70241688/b26617e2-da92-4b58-bff3-b13fd9843649)

- Switch the foreground Job to the background
```
$ gedit
Ctrl-z
$ bg
```
![switch to bg](https://github.com/Bilalmhmd/Linux-Fundamentals/assets/70241688/f4177c1e-2552-4254-9a30-8422fd435aab)

- List Jobs within the current shell session
```
$ jobs
This will show which job runs in the FG, and which run in BG
```
![jobs](https://github.com/Bilalmhmd/Linux-Fundamentals/assets/70241688/7b1815a6-21ba-4aab-95d7-725a5b309161)

- Switch a background job into the foreground 
```
$ jobs
$ fg %n (where n is the process number in the list )
```
![switch to fg](https://github.com/Bilalmhmd/Linux-Fundamentals/assets/70241688/f10cdca7-0375-408e-b05a-bc18dc57037f)

• Kill a background Job (all processes in this Job)
```
$ jobs
$ kill %n
```
![kill](https://github.com/Bilalmhmd/Linux-Fundamentals/assets/70241688/8bb7ed6c-599a-4973-a4b0-e5ec37eb316b)


### 9- What are Jobs and Process Groups ?
- For each new Job, a new Process Group is created for processes inside this job.
- This means that each job has its own process group. 
- If the Job is about running a script, then the sub-shell that runs the script becomes the Process Group Leader.
- When you perform Job control commands (send it to background, stop it, bring it back to foreground. … ) , it applies 
  on whole process group for this Job and not on single process.
  
### 10- what is Shell Session ?
- Each shell has its own session.
- All processes running inside this session, will carry the same SID (which is the PID or the shell owning the session).
- The shell is named the session leader.
- A shell session contains one or more Jobs (the ones launched under it).
- Jobs inside a session, one of this happens,
  - All Jobs run in the background, and the shell runs in the foreground.
  - A single Job runs in the foreground, while the shell and all other Jobs run in the background.


### 11- what is Automatic Process ?
- Also called a batch process.
- This is a process that is not started directly by the user, instead, the user `schedule it for a later start`.
- When started, It is not started inside a terminal, and `not attached to a terminal` (user does not even needs to be logged in when it starts).
- It is queued in a spooler area, to be executed on a FIFO manner.
- It is scheduled in one of the following ways,
  ```
  - Scheduled to run at a certain date and time (using the at command).
  - Scheduled to run when system load is low (using the batch command).
  - Scheduled to run periodically with certain periodicity or interval.
  ```
  #### 1- Scheduling Automatic Tasks (at Command).
  ```
  -$ at [options] <time> < <script file>
  -$ at -f <script file> <time>
  ```
  <font color="red">Schedules jobs described in the file to run at the specified time.</font>
  • Example:
  ```
     $ at 01:35 < job-to-run
     $ at 9am February 2 < job-to-run
     $ at tuesday +2 hours < job-to-run
     $ at -f job-to-run noon
  ```
  |  Command     | Description               |
  | -----------  | ------------------------- |
  |   $ at -l    |                           |
  |   $ atq      |    List scheduled jobs    |
  |   $ at -r 3  |                           |
  |   $ atq      |   Delete scheduled job #3 |

  #### 2- Run at Low Load times (batch Command)
  ```
  $ batch < <File containing Jobs>
  ```
  
  <p style="color:blue">Run the script whenever the system load allows.</p>
  
  • Example:
  ```
  $ batch < job-to-run
  ```

  #### 3- Cron Jobs
  - Cron Jobs are those which are scheduled to run periodically (the word cron comes from Greek word for time).
  - Jobs are organized in commands or shell scripts
  - They are scheduled by the user to run at, 
    - Fixed times
    - Fixed dates
    - Intervals
  - Used often to automate repeated tasks (such as maintenance or administration tasks).
  - Cron Jobs are organized in a set of configuration files that specify the Job to be run, and the required periodicity.
  - These are called `crontab files.`
  - Types of crontab files
    - User crontab files (per user file).
    - System crontab files (for root user).
    - Other special files (will be discussed later).

  #### 4- crontab Files Format
  - The crontab files have the following format.
  - It contains a line per scheduled job.
  - Each line has three sections,
    - Time Schedule Section
      - This section describes when this Job is to be executed.
    - User Section
      - This section only applicable for some crontab files.
    - Job Description Section
      - Command to execute.
    
![image](https://github.com/Bilalmhmd/Linux-Fundamentals/assets/70241688/d3972aba-8cc1-468f-93af-574ceebe7e8d)


  #### 5- More Examples


  | Time (Min) | Time (Hr) | Day of Month | Month | Day of Week | Description |
  |------------|-----------|--------------|-------|-------------|-------------|
  | 30         | 0         | 1            | 1,6,12| *           | At 12:30 AM On First of Jan, June, Dec |
  | 0          | 20        | *            | 10    | 1-5         | At 8:00 PM on Every (Mon-Fri) in Oct |
  | 0          | 0         | 1,10,15      | *     | *           | At Midnight on 1,10,15 on Every Month |
  | 5,10       | 0         | 10           | *     | 1           | At 12:05 and 12:10 AM on Every Monday and 10th of every Month |
  | 30         | 18        | *            | *     | *           | At 6:30 PM Every day |
  | */5        | *         | *            | *     | *           | Every 5 Minutes |
  | 1,31       | 04,05     | 1-15         | 1,6   | *           | At 4:01, 4:31, 5:01, 5:31 on the first 15 days of Jan and June |

 #### 6- Special Strings
 
 | String | Description |
 |-------------|-------------|
 | @reboot     | Run once at Startup |
 | @yearly     | Run once a year “0 0 1 1 *” |
 | @annually   | Same as @yearly |
 | @monthly    | Run once a month “0 0 1 * *” |
 | @weekly     | Run once a week “0 0 * * 0” |
 | @daily      | Run once a day “0 0 * * *” |
 | @midnight   | Same as @daily |
 | @hourly     | Run once an hour “0 * * * *” |
