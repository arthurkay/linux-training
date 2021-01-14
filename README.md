# Linux Training

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