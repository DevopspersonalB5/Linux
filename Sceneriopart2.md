## 🔐 File Permissions and Ownership

### 1. A script fails with "Permission denied." How do you fix it?

**Answer:** Use `ls -l script.sh` to check permissions. Add execute rights:

```bash
chmod +x script.sh
````

**Explanation:** Without execute permissions, a shell script won’t run.

---

### 2. Give full permissions to the owner, and only read to others.

```bash
chmod 744 file.txt
```

**Explanation:** `7 = rwx` for owner, `4 = r` for group and others.

---

### 3. Change ownership of all files in `/data` to user `devops`.

```bash
chown -R devops:devops /data
```

**Explanation:** `-R` applies changes recursively.

---

### 4. How do you remove write permission for group from a file?

```bash
chmod g-w filename
```

**Explanation:** `g-w` removes write for the group.

---

### 5. Check which users can write to a file.

```bash
ls -l file.txt
```

**Explanation:** Based on the output (e.g., `-rw-r--r--`), only the owner can write.

---

## 🔍 Search and Filters

### 6. Find all `.log` files larger than 100MB.

```bash
find / -type f -name "*.log" -size +100M
```

**Explanation:** Useful for locating large log files for cleanup.

---

### 7. Find files modified in the last 7 days.

```bash
find /path -type f -mtime -7
```

**Explanation:** Helps identify recently changed files.

---

### 8. Search for "ERROR" in all `.log` files.

```bash
grep -R "ERROR" *.log
```

**Explanation:** Recursively searches through all `.log` files.

---

### 9. Find empty files in `/tmp`.

```bash
find /tmp -type f -empty
```

**Explanation:** Useful for cleaning up useless files.

---

### 10. Exclude commented lines while searching for "backup".

```bash
grep -v '^#' script.sh | grep "backup"
```

**Explanation:** Removes lines starting with `#` before searching.

---

## 📄 File Processing & Text Handling

### 11. Extract first column from CSV.

```bash
cut -d',' -f1 file.csv
```

**Explanation:** `cut` extracts specified fields from delimited files.

---

### 12. Replace "dev" with "prod" in config files.

```bash
sed -i 's/dev/prod/g' *.conf
```

**Explanation:** Performs inline replacement across multiple files.

---

### 13. Remove duplicate lines in a file.

```bash
sort file.txt | uniq
```

**Explanation:** `sort` is needed before `uniq` to group duplicates together.

---

### 14. Sort logs by timestamp.

```bash
sort access.log
```

**Explanation:** Assumes logs are in a format that `sort` can interpret chronologically.

---

### 15. Count how many times an IP appears in access.log.

```bash
grep "192.168.1.1" access.log | wc -l
```

**Explanation:** `wc -l` counts the number of matching lines.

---

## 📦 Archiving & Compression

### 16. Create tarball excluding `.conf` files.

```bash
tar --exclude='*.conf' -czvf backup.tar.gz /etc
```

**Explanation:** `--exclude` omits matching files.

---

### 17. Extract `.tar.gz` to specific path.

```bash
tar -xzvf archive.tar.gz -C /opt/restore/
```

**Explanation:** `-C` specifies the extraction path.

---

### 18. List contents of archive without extracting.

```bash
tar -tzf archive.tar.gz
```

**Explanation:** Shows what's inside the archive.

---

### 19. Compress all `.log` files.

```bash
gzip *.log
```

**Explanation:** Compresses files individually.

---

### 20. Inspect `.zip` without extraction.

```bash
unzip -l archive.zip
```

**Explanation:** Lists files inside the ZIP archive.

---

## 📈 System Monitoring & Processes

### 21. Check memory and CPU of a process.

```bash
top
```

**Explanation:** Real-time system performance monitoring.

---

### 22. Top 5 memory-heavy processes.

```bash
ps aux --sort=-%mem | head -n 6
```

**Explanation:** Sorts by memory usage.

---

### 23. Monitor disk I/O per process.

```bash
iotop
```

**Explanation:** Displays real-time disk I/O (requires root).

---

### 24. Bring background job to foreground and kill it.

```bash
fg %1  # bring to foreground  
Ctrl+C or kill <PID>
```

**Explanation:** Useful when background processes hang.

---

### 25. Find zombie processes.

```bash
ps aux | awk '$8=="Z"'
```

**Explanation:** Zombies have a process state `Z`.

---

## 🔄 Bonus Scenarios

### 26. Backup `.conf` files modified today.

```bash
find /etc -name "*.conf" -mtime 0 -exec cp {} /backup \;
```

**Explanation:** `-mtime 0` finds files changed today.

---

### 27. Monitor log in real-time for "CRITICAL".

```bash
tail -f app.log | grep --line-buffered "CRITICAL"
```

**Explanation:** Live monitoring of logs with alert terms.

---

### 28. Kill all processes of a user.

```bash
pkill -u devops
```

**Explanation:** Terminates all user-owned processes.

---

### 29. List open ports and related processes.

```bash
ss -tulnp
```

**Explanation:** Shows listening ports and PIDs.

---

### 30. Find top 10 largest files in `/var`.

```bash
find /var -type f -exec du -h {} + | sort -rh | head -n 10
```

**Explanation:** Helps identify space hogs.
