# 🚀 90 Days of DevOps: Mastering Linux Commands with Real-Life Examples 🖥️⚡

![image](https://github.com/user-attachments/assets/f8225c77-ce1f-4f5c-a9b4-092c37bf2867)


If you’re starting your DevOps journey, mastering Linux commands is crucial. Think of Linux as the engine under the hood of most DevOps tools—whether it’s Docker, Kubernetes, Jenkins, or cloud servers, they often run on Linux.

In this guide, I’ll cover basic Linux commands with real-life examples, simple explanations, and use cases to make your DevOps learning smoother. 💡

## 🔐 1. User Privileges and Access Control

### `sudo su -` — Switch to Superuser (Root)

**Purpose:** Gain administrative privileges to run sensitive commands.

**Real-Life Example:** Imagine you need to install new software on your computer. You can’t do it as a normal user, so you switch to the “admin” mode.

```bash
sudo su -
```

- `sudo`: Execute commands as another user (usually root).
- `su`: Switch user (default is root).
- `-`: Loads root’s environment variables.

**Tip:** Always use `sudo` instead of logging in as root to avoid accidental system-wide changes.

## 📂 2. Navigating Directories

Just like you browse folders on Windows or macOS, Linux uses commands to move around directories.

- **`pwd` — Print Working Directory**
  ```bash
  pwd
  ```
  **Example Output:**
  ```bash
  /home/user/documents
  ```
  Shows your current directory.

- **`cd` — Change Directory**
  ```bash
  cd /path/to/folder
  ```
  **Example:**
  ```bash
  cd /var/log
  ```
  Navigates to the “log” folder.

- **`ls` — List Files and Folders**
  ```bash
  ls
  ```
  **Options:**
  - `-l`: Long format listing (details like permissions, size).
    ```bash
    ls -l
    ```
  - `-a`: Show hidden files (those starting with .).
    ```bash
    ls -a
    ```

- **`tree` — Display Directory Structure**
  ```bash
  tree
  ```
  **Example Output:**
  ```
  .
  ├── file1.txt
  └── folder/
      └── file2.txt
  ```

## 📝 3. File Management

Managing files is a core skill. Here’s how to create, copy, move, and delete files in Linux.

- **`touch` — Create a New File**
  ```bash
  touch myfile.txt
  ```

- **`cp` — Copy Files and Folders**
  ```bash
  cp source.txt destination.txt
  ```

  **Copy entire folder:**
  ```bash
  cp -r folder1/ folder2/
  ```

- **`mv` — Move or Rename Files**
  ```bash
  mv oldname.txt newname.txt
  ```

  **Move file to another directory:**
  ```bash
  mv myfile.txt /home/user/documents/
  ```

- **`rm` — Remove Files and Folders**
  ```bash
  rm myfile.txt
  ```

  **Delete folder recursively:**
  ```bash
  rm -rf myfolder/
  ```

  ⚠️ **Caution:** `rm -rf` is irreversible. Be careful!

- **`find` — Search for Files**
  ```bash
  find / -name "file.txt"
  ```

- **`grep` — Search Inside Files**
  ```bash
  grep "search_term" file.txt
  ```

  **Example:** Find all lines containing “error” in logs.
  ```bash
  grep "error" /var/log/syslog
  ```

## 📄 4. Text Editors

### vi/vim Editor — Powerful but Complex

- **Open file:**
  ```bash
  vi filename
  ```
- **Enter Insert Mode:** Press `i`
- **Save and Exit:**
  ```bash
  :wq
  ```
- **Exit without Saving:**
  ```bash
  :q!
  ```

### nano Editor — Beginner-Friendly

- **Open file:**
  ```bash
  nano filename
  ```
- **Save:** `Ctrl + O`
- **Exit:** `Ctrl + X`

**Real-Life Example:** Editing configuration files like `nginx.conf` or `docker-compose.yml`.

## ⚙️ 5. System Monitoring and Performance

Monitor your system’s health and resources.

### CPU Information
- **`lscpu` — Shows CPU details.**
  ```bash
  lscpu
  ```
  **Example Output:**
  ```bash
  Architecture:        x86_64
  CPU(s):              8
  Vendor ID:           GenuineIntel
  ```

### Memory Usage
- **`free -h` — Check RAM usage.**
  ```bash
  free -h
  ```
  **Example Output:**
  ```bash
                total        used        free
  Mem:           16Gi        5Gi         11Gi
  Swap:           2Gi        0Gi          2Gi
  ```

### Disk Usage
- **`df -h` — Check disk space.**
  ```bash
  df -h
  ```
  **Example Output:**
  ```bash
  Filesystem      Size  Used Avail Use% Mounted on
  /dev/sda1        50G   20G   28G  42% /
  ```

- **`du -sh /path` — Check folder size.**
  ```bash
  du -sh /var/log
  ```

### Processes and Resources
- **`top` — Live resource usage.**
- **`htop` — Enhanced process viewer (install it using `sudo apt install htop`).**
- **`ps aux` — List all running processes.**
  ```bash
  ps aux | grep nginx
  ```

## 🔗 6. Network Management

### Check Network Interfaces
- **`ifconfig` or `ip addr`**
  ```bash
  ip addr
  ```

### Test Connectivity
- **`ping`**
  ```bash
  ping google.com
  ```

### Check Open Ports
- **`netstat -tuln`**
  ```bash
  netstat -tuln
  ```

## 📦 7. Package Management

### Debian-based (Ubuntu)
- **Update Repositories:**
  ```bash
  sudo apt update
  ```

- **Upgrade Packages:**
  ```bash
  sudo apt upgrade
  ```

- **Install Software:**
  ```bash
  sudo apt install nginx
  ```

### Red Hat-based (CentOS, Fedora)
- **Install Software:**
  ```bash
  sudo yum install nginx
  ```

## 🛡️ 8. Permissions and Ownership

Linux uses permissions to control access to files.

- **`chmod` — Change Permissions**
  ```bash
  chmod 755 script.sh
  ```
  - `7` (rwx): read, write, execute
  - `5` (r-x): read, execute

- **`chown` — Change Ownership**
  ```bash
  chown user:group file.txt
  ```

**Real-Life Example:**
If you’re setting up a web server, the `www-data` user might need permissions to access web files.

## 🔄 9. Automation with Shell Scripts

Create simple automation scripts.

**Example:** Backup a directory
```bash
#!/bin/bash
tar -czvf backup.tar.gz /path/to/folder
echo "Backup completed successfully!"
```

- **Make it executable:**
  ```bash
  chmod +x backup.sh
  ./backup.sh
  ```

## 🛡️ 10. Security Essentials

- **Firewall (UFW):**
  ```bash
  sudo ufw enable
  sudo ufw allow 22/tcp
  sudo ufw status
  ```

- **SSH into Remote Servers:**
  ```bash
  ssh user@server_ip
  ```

## 💡 Pro Tips for DevOps:

- **Use `cron` for scheduled tasks:**
  ```bash
  crontab -e
  # Run backup every day at 2 AM
  0 2 * * * /path/to/backup.sh
  ```

- **Use `tmux` or `screen` for persistent terminal sessions.**
- **Learn `sed` and `awk` for powerful text processing.**

# 🚀 Ready for DevOps?

If you’re following the **#90DaysOfDevOps** challenge, **bookmark** this post and **share** it with fellow learners. 💡✨

💬 **Question:** *What’s your most-used Linux command?* Drop it in the comments! 👇

#DevOps #Linux #SysAdmin #Cloud #90DaysOfDevOps #Automation #SRE #Networking #Tech

