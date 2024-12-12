# Linux Server Hardening

## Description  

(Place descritption here)  

## Operating System  

- **Linux**  

## Skills Gained and Excercised

- **Hands-On Linux Experience**
- **Tool Mastery**
- **Security Awareness**
- **Critical Thinking**

---

## Pre-Hardening Steps

### System Information Collection and OS Backup

1. **Collect System Information**
   - Retrieve the following information and document it in a summary report:
     - HostName: Use the `hostname` command.
     - OS Version: Use `cat /etc/os-release`.
     - Memory Information: Use `free -h` for human-readable memory details.
     - Uptime Information: Use the `uptime` command.

2. **Create a Backup of the OS**
   - Use the `tar` command to back up the OS to `/baker_street_backup.tar.gz`, excluding the following directories:
     - `/baker_street_backup.tar.gz` (to avoid recursive inclusion)
     - `/proc`
     - `/tmp`
     - `/mnt`
     - `/sys`
     - `/dev`
     - `/run`

3. **Verify Output**
   - Confirm the summary report is generated with the collected system details.
   - Check that the backup file, `/baker_street_backup.tar.gz`, is created successfully.

### Commands Overview

### Collect Information
- **HostName**: `hostname`
- **OS Version**: `cat /etc/os-release`
- **Memory Information**: `free -h`
- **Uptime Information**: `uptime`

### Backup Command
To create the backup:
```bash
sudo tar -cvpzf /baker_street_backup.tar.gz --exclude=/baker_street_backup.tar.gz --exclude=/proc --exclude=/tmp --exclude=/mnt --exclude=/sys --exclude=/dev --exclude=/run
