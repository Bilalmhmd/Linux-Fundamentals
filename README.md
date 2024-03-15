# Linux-Fundamentals
Tasks refers to the structure and organization of the Linux operating system.

## (1) Linux System Architecture
## Tasks

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
