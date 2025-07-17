# 🐧 Top 50 Linux Interview Commands with Explanations

## 🔧 Basic File and Directory Commands

1. **`ls`** – Lists files and directories  
   Example: `ls -l`

2. **`cd`** – Changes directory  
   Example: `cd /var/log`

3. **`pwd`** – Prints current working directory

4. **`mkdir`** – Creates a directory  
   Example: `mkdir myfolder`

5. **`rm`** – Removes files or directories  
   Example: `rm -r myfolder`

6. **`cp`** – Copies files or directories  
   Example: `cp file1 file2`

7. **`mv`** – Moves or renames files  
   Example: `mv oldname newname`

8. **`touch`** – Creates an empty file  
   Example: `touch file.txt`

9. **`cat`** – Displays file content  
   Example: `cat file.txt`

10. **`more`, `less`** – Views content page-by-page  
    Example: `less file.txt`

---

## 📁 File Permissions and Ownership

11. **`chmod`** – Changes file permissions  
    Example: `chmod 755 script.sh`

12. **`chown`** – Changes file ownership  
    Example: `chown user:group file.txt`

13. **`umask`** – Sets default permission for new files

14. **`stat`** – Displays detailed file info

---

## 🔍 Search and Filters

15. **`find`** – Finds files and directories  
    Example: `find / -name "*.log"`

16. **`grep`** – Searches within files  
    Example: `grep "error" logfile.txt`

17. **`locate`** – Quickly searches indexed files  
    Example: `locate file.txt`

18. **`which` / `whereis`** – Finds executable path  
    Example: `which python`

---

## 🧪 File Processing & Text Handling

19. **`awk`** – Pattern scanning and processing  
    Example: `awk '{print $1}' file.txt`

20. **`sed`** – Stream editor  
    Example: `sed 's/old/new/g' file.txt`

21. **`cut`** – Cuts sections from lines  
    Example: `cut -d ':' -f1 /etc/passwd`

22. **`sort`** – Sorts lines  
    Example: `sort file.txt`

23. **`uniq`** – Removes duplicates  
    Example: `sort file.txt | uniq`

24. **`head`, `tail`** – Displays beginning or end of files  
    Example: `tail -n 100 logfile.txt`

---

## 📦 Archiving & Compression

25. **`tar`** – Archives files  
    Example: `tar -cvf archive.tar myfolder`

26. **`gzip` / `gunzip`** – Compress or decompress files

27. **`zip` / `unzip`** – Works with `.zip` files

---

## ⚙️ System Monitoring & Processes

28. **`ps`** – Shows active processes  
    Example: `ps aux`

29. **`top` / `htop`** – Real-time process monitoring

30. **`kill` / `killall`** – Sends signal to process  
    Example: `kill -9 PID`

31. **`nice` / `renice`** – Adjusts process priority

32. **`df`** – Disk space usage  
    Example: `df -h`

33. **`du`** – Disk usage of directories  
    Example: `du -sh *`

34. **`free`** – Shows memory usage  
    Example: `free -m`

35. **`uptime`** – Shows system uptime

36. **`vmstat`** – Performance stats

37. **`iostat`** – CPU and I/O usage

---

## 🌐 Networking Commands

38. **`ping`** – Tests connectivity  
    Example: `ping google.com`

39. **`netstat`** – Network connections (deprecated)

40. **`ss`** – Socket statistics  
    Example: `ss -tuln`

41. **`curl`** – Transfers data to/from server  
    Example: `curl http://example.com`

42. **`wget`** – Downloads files  
    Example: `wget https://example.com/file.tar.gz`

43. **`ifconfig` / `ip a`** – Shows network interfaces

44. **`traceroute`** – Traces route to host

45. **`nslookup` / `dig`** – DNS queries

---

## 🧰 User Management

46. **`whoami`** – Shows current user

47. **`id`** – User and group IDs

48. **`adduser` / `useradd`** – Adds a new user

49. **`passwd`** – Changes user password

50. **`sudo`** – Run command with superuser rights  
    Example: `sudo apt update`
