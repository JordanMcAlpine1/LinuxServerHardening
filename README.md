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

### Main Objective: Collect system information and backup the OS.

## Tasks

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
   - **Actions**:
     - Remove their user accounts.
     - Delete their home directories and files.

2. **Lock User Accounts on Temporary Leave**
   - **Actions**:
     - Lock the accounts to prevent login.

3. **Unlock Employed Users**
   - **Actions**:
     - Unlock their accounts if they are locked.

4. **Manage Group Memberships**
   - **Actions**:
     - Move all employees previously in the `marketing` group to a new group named `research`. Create the `research` group if it does not exist.
     - Remove the `marketing` group entirely, as the department has been closed.


![Screenshot 2024-12-02 at 9 00 29 PM](https://github.com/user-attachments/assets/a1701677-a6e1-4a01-be1a-2d6b0bb47b63)

![Screenshot 2024-12-02 at 9 05 29 PM](https://github.com/user-attachments/assets/fe3beb28-a843-4e75-8008-a494a18a6127)

![Screenshot 2024-12-02 at 10 09 27 PM](https://github.com/user-attachments/assets/cc62bbd3-8f8c-480b-ba71-dbbac3137531)

![Screenshot 2024-12-02 at 10 22 40 PM](https://github.com/user-attachments/assets/d415db70-8afd-4b02-82c6-18c0a7ad482b)



---

## Password Policy Update

### Main Objective: Update the password requirements for all users to enhance security.

### Requirements

- Minimum 8 characters.
- At least one special character.
- Allow only 2 retries for incorrect passwords.
- At least one uppercase character.


![Screenshot 2024-12-03 at 11 56 11 AM](https://github.com/user-attachments/assets/0a7c8f89-1208-40e2-b4a7-a0e9a631ae8b)



---

## Sudo Privilege Configuration

### Main Objective: Configure sudo privileges for employees as per the following requirements:

### Requirements

1. **Full Sudo Privileges**
   - Only **Sherlock** should have full sudo privileges.
   - Remove full sudo privileges from all other users.

2. **Restricted Sudo Privileges**
   - **Watson** and **Mycroft** should only have sudo access to run the script located at:
     ```plaintext
     /var/log/logcleanup.sh
     ```

3. **Research Group Privileges**
   - All employees belonging to the `research` group should only have sudo access to run the following script:
     ```plaintext
     /tmp/scripts/research_script.sh
     ```


![Screenshot 2024-12-03 at 6 32 26 PM](https://github.com/user-attachments/assets/92029e7a-350a-49ba-908b-1550408c40db)

![Screenshot 2024-12-03 at 6 40 56 PM](https://github.com/user-attachments/assets/3851b865-8249-45e4-80d9-6f73ac2af5de)



---

## File Permissions and Security Audit

### Main Objective: Secure file permissions and clean up sensitive files from the system.

## Tasks

1. **Remove World Permissions in any user's home directory**

2. **Update Permissions for Specific Scripts**
- **Engineering Scripts**:
  - Files containing the word `engineering` in the filename should only be accessible (view, edit, or execute) by members of the `engineering` group.
  - Commands:
    ```bash
    find / -iname '*engineering*' -exec chown :engineering {} \;
    find / -iname '*engineering*' -exec chmod 770 {} \;
    ```

- **Research Scripts**:
  - Files containing the word `research` in the filename should only be accessible (view, edit, or execute) by members of the `research` group.
  - Commands:
    ```bash
    find / -iname '*research*' -exec chown :research {} \;
    find / -iname '*research*' -exec chmod 770 {} \;
    ```

- **Finance Scripts**:
  - Files containing the word `finance` in the filename should only be accessible (view, edit, or execute) by members of the `finance` group.
  - Commands:
    ```bash
    find / -iname '*finance*' -exec chown :finance {} \;
    find / -iname '*finance*' -exec chmod 770 {} \;
    ```

### 3. Remove Files Containing Hidden Passwords
- **Objective**: Search for files where employees may have stored passwords (e.g., files with names such as `password`, `.password`, or containing the word `password`) and delete them.
- **Actions**:
  1. Search for files containing the word `password` (case-insensitive):
     ```bash
     find / -iname '*password*'
     ```
  2. Review the files to confirm they contain sensitive information and delete them:
     ```bash
     rm <file>
     ```

