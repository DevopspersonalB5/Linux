# 🐧 Top 20 Linux Scenario-Based Interview Questions for DevOps Engineers

---

## 1. How would you troubleshoot high CPU usage on a Linux server?

Use tools like `top`, `htop`, `ps`, and `vmstat` to identify the process using the most CPU.

```bash
ps -eo pid,ppid,cmd,%mem,%cpu --sort=-%cpu | head
````

---

## 2. A disk is full on a production server. What steps will you take?

* Check usage: `df -h`
* Find large files: `du -sh /*`, `find / -type f -size +100M`
* Clean logs, rotate logs, or move data to other volumes.

---

## 3. How do you find which process is using a particular port?

Use:

```bash
lsof -i :<port>
ss -tuln | grep <port>
```

---

## 4. Your application is unable to connect to the database server. How would you debug this?

* Check network connectivity: `ping`, `telnet`, `nc`
* Review firewall settings: `iptables`, `ufw`
* Inspect DB logs and credentials.

---

## 5. How do you set environment variables permanently for all users?

* Add to `/etc/environment` or `/etc/profile` for system-wide
* Add to `~/.bashrc` for a specific user.

---

## 6. How do you monitor log files in real-time?

```bash
tail -f /var/log/syslog
less +F /var/log/syslog
```

Also consider centralized logging tools like ELK, Fluentd, or CloudWatch.

---

## 7. How would you check if a cron job ran as expected?

* Check cron logs:

  * `/var/log/syslog` (Debian)
  * `/var/log/cron` (RHEL)
* Ensure script is executable and paths are correct.

---

## 8. Your web server is returning 403 errors. How do you debug this?

* Check file and directory permissions
* Verify SELinux: `getenforce`, `setenforce`
* Inspect Apache/Nginx logs

---

## 9. How do you find and kill a zombie process?

Use:

```bash
ps aux | grep 'Z'
```

Zombie processes can't be killed directly—kill their parent process.

---

## 10. How do you check and increase open file limits in Linux?

* Check: `ulimit -n`
* Temporarily: `ulimit -n 65535`
* Permanently: Edit `/etc/security/limits.conf`

---

## 11. How do you create a systemd service for a custom script?

Create `/etc/systemd/system/myapp.service`:

```ini
[Unit]
Description=My App Service

[Service]
ExecStart=/path/to/script.sh
Restart=always

[Install]
WantedBy=multi-user.target
```

Enable it with:

```bash
systemctl enable --now myapp
```

---

## 12. How do you secure SSH on a Linux server?

* Change default port in `/etc/ssh/sshd_config`
* Disable root login
* Enable key-based auth
* Limit users with `AllowUsers`

---

## 13. How do you debug a system boot failure?

* Boot into recovery via GRUB
* Check logs with `journalctl -xb`
* Use `fsck` to scan disk issues
* Use `dmesg` for kernel messages

---

## 14. How would you automate user creation and password setup?

```bash
useradd john && echo "john:password" | chpasswd
```

Use with Ansible, shell scripts, or cloud-init.

---

## 15. How do you monitor memory usage and identify memory leaks?

* Use: `top`, `free -m`, `vmstat`, `smem`
* For memory leaks: `valgrind`, `memwatch`, or application-specific tools

---

## 16. How would you mount a new volume and ensure it persists?

```bash
mount /dev/xvdf /mnt/data
```

Add to `/etc/fstab`:

```fstab
/dev/xvdf /mnt/data ext4 defaults 0 0
```

---

## 17. Your application’s log file is growing too large. What do you do?

* Use `logrotate` for log rotation and compression.
* Config example in `/etc/logrotate.d/myapp`

---

## 18. How do you limit CPU or memory usage of a process?

* Use `nice`, `cpulimit`, or `cgroups`
* Docker: `--cpus` and `--memory` flags

---

## 19. How do you analyze a core dump from a crashed application?

```bash
ulimit -c unlimited
gdb /path/to/app core
```

---

## 20. How do you ensure a service auto-restarts on failure?

In systemd service file:

```ini
[Service]
Restart=on-failure
RestartSec=5
```

Apply changes:

```bash
systemctl daemon-reexec
```
