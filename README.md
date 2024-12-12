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
     - HostName: Executing the `hostname` command.
     - OS Version: Executing `cat /etc/os-release`.
     - Memory Information: Executing `free -h` for human-readable memory details.
     - Uptime Information: Executing the `uptime` command.

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


![Screenshot 2024-12-02 at 8 22 33 PM](https://github.com/user-attachments/assets/cc081a90-269f-4792-bae4-76f4ffc10c3d)

![Screenshot 2024-12-03 at 7 14 39 PM](https://github.com/user-attachments/assets/13b5207b-baf3-4ecf-b5b8-948ba632a3cc)

![Screenshot 2024-12-02 at 8 41 41 PM](https://github.com/user-attachments/assets/0014cb83-1e1e-42e3-9d7a-5e94c76eb009)



---

## Employee Audit and Access Management

### Main Objective: Audit employees to ensure that users and groups have the minimum required access to perform their work.

### Staff List and Position Updates

Below is the current list of employees and their employment status

| Employee Name | Employment Status     |
|---------------|-----------------------|
| sherlock      | Employed              |
| watson        | Employed              |
| mycroft       | Employed              |
| moriarty      | On temporary leave    |
| lestrade      | Terminated            |
| irene         | Terminated            |
| mrs_hudson    | On temporary leave    |
| mary          | Terminated            |
| gregson       | Terminated            |
| toby          | Employed              |
| adler         | Employed              |

## Tasks

1. **Remove Terminated Staff**
- **Objective**: Delete all user accounts of staff listed as "Terminated."
- **Actions**:
  - Remove their user accounts.
  - Delete their home directories and files.

### 2. Lock User Accounts on Temporary Leave
- **Objective**: Restrict access for employees on "temporary leave."
- **Actions**:
  - Lock the accounts to prevent login.

### 3. Unlock Employed Users
- **Objective**: Ensure all users listed as "Employed" have active accounts.
- **Actions**:
  - Unlock their accounts if they are locked.

### 4. Manage Group Memberships
- **Objective**: Update group memberships for employees as per organizational changes.
- **Actions**:
  - Move all employees previously in the `marketing` group to a new group named `research`. Create the `research` group if it does not exist.
  - Remove the `marketing` group entirely, as the department has been closed.


## Command Overview

### Remove Terminated Staff
- Delete user accounts and home directories:
  ```bash
  sudo userdel -r <username>
