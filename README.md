# Linux Training

# Table of Contents

[File organisation in a Linux System](#linux-file-system)

[Listing Finding Contents](#listing-finding-contents)

[Package Manager](#package-manager)

[More on Package Managers](#more-on-package-managers)


## Linux File System

> File organisation in a Linux System

 Directory | Description
 ----------|------------------------------------------------------------------------------------------
 / (root filesystem) |	The root filesystem is the top-level directory of the filesystem. It must contain all of the files required to boot the Linux system before other filesystems are mounted. It must include all of the required executables and libraries required to boot the remaining filesystems. After the system is booted, all other filesystems are mounted on standard, well-defined mount points as subdirectories of the root filesystem.
 /bin |	The /bin directory contains user executable files.
 /boot |	Contains the static bootloader and kernel executable and configuration files required to boot a Linux computer.
 /dev |	This directory contains the device files for every hardware device attached to the system. These are not device drivers, rather they are files that represent each device on the computer and facilitate access to those devices.
 /etc |	Contains the local system configuration files for the host computer.
 /home | Home directory storage for user files. Each user has a subdirectory in /home.
 /lib |	Contains shared library files that are required to boot the system.
 /media  |	A place to mount external removable media devices such as USB thumb drives that may be connected to the host.
 /mnt |	A temporary mountpoint for regular filesystems (as in not removable media) that can be used while the administrator is repairing or working on a filesystem.
 /opt |	Optional files such as vendor supplied application programs should be located here.
 /root | This is not the root (/) filesystem. It is the home directory for the root user.
 /sbin | System binary files. These are executables used for system administration.
 /tmp |	Temporary directory. Used by the operating system and many programs to store temporary files. Users may also store files here temporarily. Note that files stored here may be deleted at any time without prior notice.
 /usr |	These are shareable, read-only files, including executable binaries and libraries, man files, and other types of documentation.
 /var |	Variable data files are stored here. This can include things like log files, MySQL, and other database files, web server data files, email inboxes, and much more.

 ## Linux Introduction

 Linux is an Open Source kernel, upon which a lot of distributions have been built. Two of the most commons families include Red Hat Enterprise (RHEL) and Debain based Operating systems. Below is a few of the linux distributions from each family.

 RHEL | DEBIAN
 ------|---------------------------
 Red Hat Enterorise Linux | Debain
 CentOS | Ubuntu
 Fedora | Linux Mint
 Oracle | Deepin

 ## Listing Finding contents

 The main command used to list directory contents is `ls`. The comand can also be used to pipe its output as input to the `grep` command to fine tune one's searches.

 >e.g To list case insensitive files containing the phrase `text`
  
  ```bash
  ls -a | grep -i 'text'
  ```

 >e.g To list case sensitive files containing the phrase `text`, drop the `-i` flag 

```bash
ls -a | grep 'text'
```

>e.g To list files that end in `.txt`, add a `$` sign at the end of the regular expression

```bash
ls -a | grep -i '.txt'$
```

>e.g To list filess that start with `index` use the caret symbole before the regular expressions.

```bash
ls -a | grep -i ^'index'
```

Aside from using ls and piping its output to stdout, one can also use the `find` command to locate files.
>Note: `find` unlike `ls` does not take a regular expressions, instead it takes a complete file/directory name. Aside from the directory name, once can also specify wether to look for a file or directory by parsing the `f` flag for file and `d` flag for directory.

e.g


```bash
find ./ -name index.html -type f
```
 ## Package Manager

A package manager or package-management system is a collection of software tools that automates the process of installing, upgrading, configuring, and removing computer programs for a computer's operating system in a consistent manner.

`~ Wikipedia`

While debian based systems use `apt` as the package manager, RHEL based systems use `yum` wihis  is now deprecated in RHEL 8 and replaced with `dnf`.

e.g To install nginx on these systems, one would type:


### Debain based system

apt install nginx

apt-get install nginx


### RHEL based system

dnf install nginx

yum install nginx (deprecated)

## More On Package Managers

> Usage: <...> means a required parameter
>  [...] optional parameter

Command (Debian) | Command (RHEL) | Explanation
-----------------|-----------------|------------------
apt install \<program\> | yum install \<program\>  <br /> or <br /> dnf install \<program\> | Install a program called `program`
apt update | yum update <br /> or <br /> dnf update | Used to download latest package information from configured sources. For RHEL configured sources set options for individual repositories by editing the \[repository\] sections in /etc/yum.conf and .repo files in the /etc/yum.repos.d/ directory. For Debian based systems, this is done from /etc/apt/sources.list or files in the directory /etc/apt/sources.list.d
sudo add-apt-repository 'deb [arch=amd64] https://repo.mongodb.org/apt/ubuntu bionic/mongodb-org/4.0 multiverse' | rpm -ivh https://centos.pkgs.org/7/mongodb-4.2-x86_64/mongodb-org-4.2.11-1.el7.x86_64.rpm | An example of getting the repository for mongo db
apt list \<program\> | yum list \<program\> <br /> dnf list \<program\> | Display installed and available packages
apt-cache search \<program\> | yum search \<program\> <br /> dnf search \<program\> | List packages by keywords found in summary fields
apt-cache show \<program\> | yum info \<program\> <br /> dnf info \<program\> | Get detailed information of the specififed package
apt remove \<program\> | yum remove \<program\> <br /> dnf remove \<program\> | Remove the specified program from system 