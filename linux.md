# ![Linux](https://img.shields.io/badge/Linux-Kernel-blue?style=for-the-badge) ![Interview](https://img.shields.io/badge/Interview-Questions-green?style=for-the-badge) ![Production Ready](https://img.shields.io/badge/Production-Ready-orange?style=for-the-badge)

# Linux Interview Questions & Answers

<details>
<summary>⚡ Basics</summary>
- **What is Linux?**  
  An open-source, Unix-like operating system kernel used widely in servers and cloud systems.

- **Difference between Linux and UNIX?**  
  Linux is open-source; UNIX is proprietary. Linux has multiple distributions.

- **What is a Kernel?**  
  Core part of the OS managing hardware, processes, and memory.

- **What are Shells in Linux?**  
  Command interpreters (e.g., Bash, Zsh) that allow user interaction with the OS.

- **What is a distribution?**  
  A Linux OS package including kernel, tools, and libraries (e.g., Ubuntu, CentOS).

- **Explain open-source vs free software.**  
  Open-source code can be modified; free software may or may not allow modification.
</details>

<details>
<summary>⚡ File System & Permissions</summary>
- **Linux file system hierarchy?**  
  Root `/`, `/home`, `/var`, `/etc`, `/usr`, `/tmp`, etc.

- **Explain file permissions.**  
  Read(r), Write(w), Execute(x) for User, Group, Others.

- **How to change permissions?**  
  `chmod [options] permissions file`

- **How to change ownership?**  
  `chown user:group file`

- **Difference between hard link and soft link?**  
  Hard link points to inode; soft link points to file path.

- **What is the difference between relative and absolute path?**  
  Relative path is from current directory; absolute path starts from `/`.
</details>

<details>
<summary>⚡ Users & Groups</summary>
- **How to add a new user?**  
  `useradd username` or `adduser username`

- **How to delete a user?**  
  `userdel username` (use `-r` to remove home dir)

- **How to modify user details?**  
  `usermod -aG group username`

- **How to list groups of a user?**  
  `groups username`

- **What is /etc/passwd and /etc/shadow?**  
  `/etc/passwd` stores user info; `/etc/shadow` stores encrypted passwords.
</details>

<details>
<summary>⚡ Processes & Jobs</summary>
- **How to list running processes?**  
  `ps aux` or `top`

- **How to kill a process?**  
  `kill PID` or `kill -9 PID` for force kill

- **Difference between foreground & background processes?**  
  Foreground runs attached to terminal; background runs detached using `&`.

- **What is a zombie process?**  
  Process finished execution but still has an entry in process table.

- **How to check process CPU/memory usage?**  
  `top` or `htop` or `ps aux --sort=-%mem`
</details>

<details>
<summary>⚡ Networking</summary>
- **How to check network interfaces?**  
  `ifconfig` or `ip addr`

- **How to check active connections?**  
  `netstat -tulnp` or `ss -tulnp`

- **How to ping a host?**  
  `ping hostname/IP`

- **How to trace route?**  
  `traceroute hostname`

- **How to check open ports?**  
  `lsof -i` or `netstat -tulnp`

- **How to test network bandwidth?**  
  `iperf` or `speedtest-cli`
</details>

<details>
<summary>⚡ Package Management</summary>
- **How to install packages in Debian/Ubuntu?**  
  `apt-get install package_name`

- **How to install packages in RHEL/CentOS?**  
  `yum install package_name` or `dnf install package_name`

- **How to update all packages?**  
  `apt-get update && apt-get upgrade` or `yum update`

- **How to remove a package?**  
  `apt-get remove package_name` or `yum remove package_name`
</details>

<details>
<summary>⚡ Shell & Scripting</summary>
- **How to run a script?**  
  `bash script.sh` or `./script.sh` (with execute permission)

- **How to pass arguments to a script?**  
  `$1, $2, ... $n` are positional parameters

- **What is a shebang?**  
  `#!/bin/bash` specifies the interpreter for the script

- **Difference between single and double quotes in shell?**  
  Single quotes prevent variable expansion; double quotes allow it

- **How to debug a script?**  
  `bash -x script.sh` shows commands execution step
</details>

<details>
<summary>⚡ Cron & Automation</summary>
- **What is cron?**  
  A scheduler to run tasks automatically at specific intervals.

- **Where is cron configuration stored?**  
  User: `crontab -e`, System: `/etc/crontab`

- **Cron format?**  
  `minute hour day month weekday command`

- **How to list all cron jobs?**  
  `crontab -l`

- **How to run a cron job every day at 5 AM?**  
  `0 5 * * * command`
</details>

<details>
<summary>⚡ System Monitoring</summary>
- **How to check CPU usage?**  
  `top`, `htop`, `mpstat`

- **How to check memory usage?**  
  `free -m` or `vmstat`

- **How to monitor disk usage?**  
  `df -h` for partitions, `du -sh folder` for folder size

- **How to monitor running processes?**  
  `ps aux` or `top`

- **How to check logs in real-time?**  
  `tail -f /var/log/syslog`
</details>

<details>
<summary>⚡ Logging</summary>
- **Where are system logs stored?**  
  `/var/log/` (e.g., `syslog`, `messages`, `auth.log`)

- **How to rotate logs?**  
  `logrotate` automatically rotates and compresses logs

- **How to check authentication logs?**  
  `cat /var/log/auth.log`
</details>

<details>
<summary>⚡ Security & Firewall</summary>
- **How to check active firewall rules?**  
  `iptables -L` or `firewalld --list-all`

- **How to block a port?**  
  `iptables -A INPUT -p tcp --dport 8080 -j DROP`

- **How to check failed login attempts?**  
  `grep "Failed password" /var/log/auth.log`

- **What is SELinux?**  
  Security module enforcing access control policies
</details>

<details>
<summary>⚡ Disk & Storage Management</summary>
- **How to list disks and partitions?**  
  `lsblk` or `fdisk -l`

- **How to check free disk space?**  
  `df -h`

- **How to check folder size?**  
  `du -sh folder`

- **How to mount a disk?**  
  `mount /dev/sdb1 /mnt`

- **How to create filesystem?**  
  `mkfs.ext4 /dev/sdb1`
</details>

<details>
<summary>⚡ Backup & Recovery</summary>
- **How to backup a folder?**  
  `tar -czvf backup.tar.gz /path/to/folder`

- **How to restore a backup?**  
  `tar -xzvf backup.tar.gz -C /restore/path`

- **How to create incremental backup?**  
  Use `rsync -av --link-dest` for incremental backups
</details>

<details>
<summary>⚡ Production-Level Scenarios</summary>
- **High CPU usage?**  
  Use `top`/`htop` to identify process and `kill` or optimize it.

- **High memory usage?**  
  Check `free -m` and `ps aux --sort=-%mem`, restart service if needed.

- **Disk full issue?**  
  Use `df -h` & `du -sh`, remove temp/logs, or expand partition.

- **Network down / latency?**  
  Check `ping`, `traceroute`, firewall rules, restart network service.

- **Service not starting?**  
  Check logs in `/var/log`, permissions, dependencies, restart service.

- **Zombie processes?**  
  Identify parent PID and kill parent or `kill -9` zombie if necessary.
</details>

<details>
<summary>⚡ Best Practices</summary>
- Regularly update and patch OS (`apt-get update && upgrade`).  
- Monitor logs and set alerts for critical services.  
- Use strong passwords and SSH key authentication.  
- Limit root access and use `sudo` for administrative tasks.  
- Automate backups and test recovery procedures.  
- Monitor system resources and plan capacity proactively.  
- Use version control for scripts and configuration files.
</details>

<details>
<summary>⚡ Commands Cheat Sheet</summary>
- **File & Directory:** `ls`, `cd`, `pwd`, `cp`, `mv`, `rm`, `mkdir`, `rmdir`  
- **Permissions:** `chmod`, `chown`, `chgrp`, `umask`  
- **Processes:** `ps aux`, `top`, `htop`, `kill`, `jobs`, `fg`, `bg`  
- **Networking:** `ping`, `ifconfig`, `ip addr`, `netstat`, `ss`, `traceroute`, `curl`, `wget`  
- **Disk & Storage:** `df -h`, `du -sh`, `lsblk`, `fdisk -l`, `mount`, `umount`, `mkfs`  
- **Users & Groups:** `useradd`, `usermod`, `passwd`, `groups`, `id`, `who`  
- **System Monitoring:** `free -m`, `vmstat`, `uptime`, `iostat`, `sar`, `dmesg`  
- **Package Management:** `apt-get`, `yum`, `dnf`  
- **Scripting:** `bash script.sh`, `$1, $2`, `echo`, `read`, `cron`, `crontab`  
- **Logs:** `tail -f /var/log/syslog`, `grep`, `logrotate`  
- **Firewall & Security:** `iptables`, `firewalld`, `ufw`, `selinux`
</details>
