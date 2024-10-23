- [1.Introduction to Linux](#1Introduction-to-Linux)
  - What is Operating System
  - History of Linux | Unix
  - Importance of Linux
  - Linux Filesystem and directory Hierarchy
  - Linux Kernel, Boot Sequence, Kernel Space and User Space | How Linux works
  - Reset Root Password
- [2.Setting up the environment (installing both Ubuntu and Redhat)](#2setting-up-the-environment-installing-both-ubuntu-and-redhat)
  - Graphical vs Minimal Mode | Single User Mode vs Multi User Mode
  - Networking
  - Connect/Login to Linux system | Login Client
  - Introduction to Shell
  - Hostfile
  - Text Editor - vim | nano | vi | emacs
  - [Common commands to check system details after installing and accessing a server](#common-commands-to-check-system-details-after-installing-and-accessing-a-server)
- [3.Administering Users and Groups](#3Administering-Users-and-Groups)
  - Creating and Managing a user
  - adduser | useradd
  - Understanding passwd and shadow files
  - Understanding Linux Groups (groups, id)
  - Creating, changing, and removing user accounts (useradd, usermod, userdel)
  - Sudo Group,Permissions and sudousers file for a user
  - Group management (groupadd, groupdel, groupmod)
  - User account monitoring (whoami, who am i, who, id, w, uptime, last)   
- [4.Packages and Software Management]()
  - Package Management Distribution - pacman,zypper,rpm,yum,dpkg,apt and apt-get
  - DPKG (Debian and Ubuntu Based Distros) and APT (Advanced Package Tool)
  - Repository File | /etc/apt/sources.list
  - Installation new applications using `apt`
  - Install manually downloaded packages with example
  - Services like HTTP, SSH
  - Key Linux Package Management Commands
     - Ubuntu Based Systems
            - Searching through the repositories to find new apps
            - Installing packages that are not in the repository
            - Keeping programs updated
     - Fedora/RHEL 8 Based Systems
     - Suse Based Systems
     - Arch Based Systems
- [5.Network Management and Troubleshooting]()
  - Telnet
  - Ping(ICMP)
  - Traceroute
  - Static Route IP
  - Curl
  - Packet Analysis
  - Netstat
  - ifconfig
  - tcpdump
  - mtr
- [6.File and Directory Management](#6file-and-directory-management)
  - Basic File and Directory Operations
    - Creating, Deleting, Moving, and Copying Files/Directories
  - File/Directory Types
  - File/Directory Link Types - Hard Links vs. Soft Links (Symbolic Links)
  - Understanding Paths - `Absolute` vs. relative paths`
  - Understanding file timestamps: atime, mtime, ctime (stat, touch, date)
- [7.File Permission and Ownership]()
  - Understanding File and Directory Permissions
  - File/Directory Permission and Ownership
  - Default and Maximum File/Directory Permission
  - Advanced File Permission Concepts
    - File Permission with Umask
    - Advanced File Permission with Access Control Lists (ACL)
    - Special permissions - Setuid, Setgid, and Sticky Bit
- [8.inux Archiving/Compression, Backup/Sync and Recovery]()
  - Archiving & Compression
     - tar  | zip | gz | xz | bz2 | gzip | bzip2 | unzip | extract | decompress | gzip, gunzip, tar,
  - Backup & Sync
  - Backup/Recovery
- [9.Command Line | Awesome Linux commands]()
  - [Essential Basic and Advance Linux Commands](#Essential-Basic-and-Advance-Linux-Commands)
  - [Text Processing]
     - Text Manipulation Commands 
- [10.Process and Log Management]()
  - Terminal Multiplexer(nohup,tmux,PM2)
  - Working with Systemd
  - Kernel Update/Upgrade
  - Signal process
  - kill (Terminate)
  - Process Termination
  - top
  - htop
  - fuser
  - lsof
  - ps m
  - uptime
  - iostat
  - vmstat
  - watch
  - ps aux
  - ls /proc
  - cat /proc/12345/status
  - ps -ef
  - ip addr
  - nmon
  - 
- [11.Managing Disks and Partitioning]
  - Device - SSD | HDD | USB | Nvme
  - Filesystem Types - ext4, XFS | Block,File,Object
  - Partition Management
  - Logical Volume Managemnt(LVM)
  - Swap Partition
  - Mount and Unmount
  - lspci
  - sscsi 
- [12.Securing and Hardening]
   - Iptables | Netfilter | NFTables | FirewallD | UFW
   - Security
   - AppArmor
   - TCP Wrapper
   - SeLinux
   - Fail2ban
- [13.System Performance & Tuning Tools]()
- [14.Server Deployment]()
   - [Deploying LAMP/LEMP and Websites]
   - NTP Server and Client
   - NFS Server and Client
   - HTTP Server with Virtual Hosting
   - MariaDB Server
   - Nginx Web Server & Nginx Reverse Proxy
   - HaProxy LB
   - SSH Server with Key Based authentication
   - SSL & TLS - Let's Encrypt
- [15.System Monitoring & Cron Scheduling]()
- [16.Bash/Shell Scripting]()







## 🚀2.Setting up the environment (installing both Ubuntu and Redhat)
### Graphical vs Minimal Mode
### Networking
### Connect/Login to Linux system | Login Client
### Introduction to Shell
### Hostfile
### Common commands to check system details after installing and accessing a server.
- Check Hostname - `hostname` | `hostnamectl` | `hostnamectl set-hostname msi-linux.com`
- Check OS Version - `cat /etc/os-release`
- Check Kernel Version - `uname -r`
- Check System Architecture - `uname -m`
- Check System Uptime - uptime
- Check CPU Information - `lscpu`
- Check Memory Usage - `free -mh`
- Check Disk Usage - `df -hT`
- Check Network Interface - `ip a` | `ip addr show`
- Check IP Routing Table - `ip route show`
- Check Running Services - systemctl list-units --type=service
- Check Block Devices - `lsblk`
- Check Mounted File Systems - `mount | column -t`
- Check User Logged-In Information - `who`
- Check Hardware Information - `lshw -short`
- Check Running Processes - `ps aux`
- Check Available Updates - `apt update`
- Check System Time and Timezone - `timedatectl`
- Check Installed Packages - `dpkg -l`
- Check System Boot Time - `who -b`
### Package Management
### Package Management Distribution
### RPM and YUM, DPKG and APT
### APT Vs APT GET


## 🚀6.File and Directory Management
 - ### 🌟Basic File and Directory Operations
    - ### 🎉Creating, Deleting, Moving, and Copying Files/Directories
    - [ ] Commands
    - [ ] `ls` - list files and directories
      - [ ] `-a` for listing hidden files
      - [ ] `-l` for list formt
      - [ ] `-t` order by time
      - [ ] `-F` better distinguish between regular files and directories
    - [ ] `touch` - creating files (original intention is updating timestamp)
      - [ ] nice to know: `touch file{1..5}`
    - [ ] `rm` - remove files
      - [ ] `-r` for recursive
      - [ ] `-f` to force removal, no questions asked
    - [ ] `mkdir` - create directories
      - [ ] `-p` - for creating multiple nested directories
    - [ ] `rmdir` - remove directories
    - [ ] `echo` - display a line of text
    - [ ] `cat` - concatenate files (common usage: read a file)
    - [ ] `mv` - move files directories (also rename files and directories)
    - [ ] `cp` - copy a file
      - [ ] `-r` for recursive (copy a directory)

 - ### 🌟File/Directory Types
    - [ ] **Regular**\
   You can identify regular files using ls -l, where the file type is indicated by a dash **(-)** at the beginning of the permission string
       - [ ] `ls -l`
       - [ ] `-rw-r--r--  1 user user  1048576 Oct 21 14:34 example.txt`

    - [ ] Directory
    - [ ] Socket
    - [ ] Block
    - [ ] Link
   
 - File/Directory Link Types - Hard Links vs. Soft Links (Symbolic Links)
 - Understanding Paths - `Absolute` vs. relative paths`
 - Understanding file timestamps: atime, mtime, ctime (stat, touch, date)
- [7.File Permission and Ownership]()
  - Understanding File and Directory Permissions
  - File/Directory Permission and Ownership
  - Default and Maximum File/Directory Permission
  - Advanced File Permission Concepts
    - File Permission with Umask
    - Advanced File Permission with Access Control Lists (ACL)
    - Special permissions - Setuid, Setgid, and Sticky Bit




