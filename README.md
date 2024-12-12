# Linux Server Hardening

## Description  

This project focuses on improving the security, performance, and manageability of a Linux system by implementing various system hardening measures and best practices. The tasks are designed to address potential vulnerabilities, streamline system operations, and ensure compliance with security standards.

## Operating System  

- **Linux**  

## Skills Gained and Excercised

- **User and Access Management**
- **Service Auditing and Optimization**
- **System Updates and Package Management**
- **File System Security**
- **Log Management and Troubleshooting**
- **SSH Configuration and Secure Remote Access**

---

## Pre-Hardening Steps

### Main Objective: Collect system information and backup the OS.

### Tasks

1. **Collect System Information**
   - Retrieve the following information and document it in a summary report:
     - HostName
     - OS Version
     - Memory Information
     - Uptime Information

2. **Create a Backup of the OS, Excluding the Following Directories:**
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

### Tasks

1. **Remove Terminated Staff**
   - **Actions**:
     - Remove their user accounts.
     - Delete their home directories and files.

2. **Lock User Accounts on Temporary Leave**

3. **Unlock Employed Users**

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

### Requirements:

- Minimum 8 characters.
- At least one special character.
- Allow only 2 retries for incorrect passwords.
- At least one uppercase character.


![Screenshot 2024-12-03 at 11 56 11 AM](https://github.com/user-attachments/assets/0a7c8f89-1208-40e2-b4a7-a0e9a631ae8b)



---

## Sudo Privilege Configuration

### Main Objective: Configure sudo privileges for employees as per the following requirements:

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

### Tasks

1. **Remove World Permissions in Any User's Home Directory**

2. **Update Permissions for Specific Scripts**
   - **Engineering Scripts**:
     - Files containing the word `engineering` in the filename should only be accessible (view, edit, or execute) by members of the `engineering` group.

   - **Research Scripts**:
     - Files containing the word `research` in the filename should only be accessible (view, edit, or execute) by members of the `research` group.

   - **Finance Scripts**:
     - Files containing the word `finance` in the filename should only be accessible (view, edit, or execute) by members of the `finance` group.

3. **Remove Files Containing Hidden Passwords**
  

![Screenshot 2024-12-03 at 7 09 12 PM](https://github.com/user-attachments/assets/c66cf2bd-d7a2-4342-a25b-0ec0ea82e9ba)

![Screenshot 2024-12-03 at 6 50 41 PM](https://github.com/user-attachments/assets/82229499-a4ad-4f9f-a31a-d477ed862729)

![Screenshot 2024-12-03 at 6 57 29 PM](https://github.com/user-attachments/assets/da2046cf-4027-47a6-9e4e-29183704563e)

![Screenshot 2024-12-03 at 7 03 10 PM](https://github.com/user-attachments/assets/344516c3-7da2-42e4-939e-5d05bfbb1ab6)



---

## Secure SSH Configuration

### Main Objective: Configure the SSH service to enhance security and restart the service to apply updates.

### Tasks

1. **Configure SSH to Disable Empty Passwords**

2. **Disable Root SSH Login**

3. **Restrict SSH to Port 22 Only**

4. **Enable SSH Protocol 2**

5. **Restart the SSH Service to Apply New Configuration Settings**


![Screenshot 2024-12-04 at 7 56 15 PM](https://github.com/user-attachments/assets/d5530051-2701-4825-9ab0-6f48fc39250b)

![Screenshot 2024-12-04 at 7 57 28 PM](https://github.com/user-attachments/assets/5578390a-a98d-4e76-9f5c-36cc6421cf5a)

![Screenshot 2024-12-04 at 8 00 01 PM](https://github.com/user-attachments/assets/debd20c1-3d9a-45e9-a757-cc419b043982)

![Screenshot 2024-12-04 at 8 01 31 PM](https://github.com/user-attachments/assets/e26975c1-b451-456e-9559-4ece6bd0dc58)

![Screenshot 2024-12-04 at 8 51 01 PM](https://github.com/user-attachments/assets/55a6c46a-8f7c-44ab-b291-19341822038a)



---

## Package Management and Security Hardening

### Main Objective: Update the package manager, identify and address potential security issues, and install essential security tools.

### Tasks

1. **Update and Upgrade Packages to the Latest Package Versions**

2. **Create a List of Installed Packages for Review**

3. **Identify and Remove Potentially Vulnerable Packages**

4. **Remove Unnecessary Dependencies**

5. **Install Essential Security Tools**
     - **Install the following packages:**
        - **UFW (Uncomplicated Firewall)**: Simplifies firewall management.
        - **Lynis**: Performs security audits.
        - **Tripwire**: Detects and reports file system changes.

#### Notes
   ##### Removed Packages and Security Vulnerabilities Explanation:
   - **Telnet**: Transmits data, including passwords, in plaintext, making it vulnerable to interception.
   - **RSH (Remote Shell)**: Lacks encryption and authentication, making it susceptible to spoofing and eavesdropping.


![Screenshot 2024-12-04 at 8 58 25 PM](https://github.com/user-attachments/assets/9b2c68ce-2b21-4fe6-bc82-030438490423)

![Screenshot 2024-12-04 at 9 05 07 PM](https://github.com/user-attachments/assets/2c71ef61-32d2-4239-b41e-379a03ba2248)

![Screenshot 2024-12-04 at 9 58 38 PM](https://github.com/user-attachments/assets/c8516b2c-5cbc-4e93-86e4-b8901986f1f6)

![Screenshot 2024-12-04 at 10 01 48 PM](https://github.com/user-attachments/assets/ba530537-6188-49d5-8b8a-58d576377585)

![Screenshot 2024-12-04 at 10 05 25 PM](https://github.com/user-attachments/assets/7cceebb3-0ece-4e76-890e-cc7be4e7ee48)

![Screenshot 2024-12-04 at 10 15 55 PM](https://github.com/user-attachments/assets/f56963c4-f184-429f-bd03-fbe780615b3b)

![Screenshot 2024-12-04 at 10 18 26 PM](https://github.com/user-attachments/assets/172381a2-ac77-48e7-8cb3-a533ffd800fa)



---

## Service Management and Security Audit

### Main Objective: Identify, manage, and secure system services by stopping, disabling, and removing unnecessary or potentially insecure services.

### Tasks

1. **List and Document All Services on the System**

2. **Identify Specific Services**
   - **Actions:**
      - Check if any of the following services are running:  `mysql` `samba`
      - Search for the specified services in the `service_list.txt` file

3. **Stop, Disable, and Remove Identified Services from the System**


![Screenshot 2024-12-05 at 4 28 03 PM](https://github.com/user-attachments/assets/f1d76d76-c37c-4c23-95ad-85bc702eca87)

![Screenshot 2024-12-05 at 4 36 07 PM](https://github.com/user-attachments/assets/6722bdec-b100-43e2-b76f-7ea52d454ccb)

![Screenshot 2024-12-05 at 4 37 48 PM](https://github.com/user-attachments/assets/5e978a08-49ce-4839-b129-ce3bb7ee97af)

![Screenshot 2024-12-05 at 4 38 54 PM](https://github.com/user-attachments/assets/fc57ae19-7407-43f6-8477-d68241e3050e)

![Screenshot 2024-12-05 at 4 42 50 PM](https://github.com/user-attachments/assets/69d155be-b683-4603-83c6-ec6b05c8e676)



---

## Log Management and Configuration

### Main Objective: Configure journald for persistent log storage, limit log size, and set up log rotation to manage disk space efficiently.

### Tasks

1. **Configure `journald.conf` for Persistent Log Storage and Limited Size**
   - **Actions**:
      - Ensure logs are saved locally and disk usage is limited
         - Set **storage=persistent**
         - Set **systemMaxUse=300M**
  

2. **Configure Log Rotation**
   - **Actions**:
      - Prevent logs from using excessive disk space by rotating logs daily and retaining them for **7 days**.


![Screenshot 2024-12-05 at 4 45 34 PM](https://github.com/user-attachments/assets/d619cec1-a034-4563-ae96-b20869aa8bb0)

![Screenshot 2024-12-05 at 4 49 40 PM](https://github.com/user-attachments/assets/ca553773-e4fa-4d31-bc4f-c20a71a9201f)

![Screenshot 2024-12-05 at 4 52 24 PM](https://github.com/user-attachments/assets/9eecc0b0-df72-4e7c-b23a-20625a1b42f2)



---

## Hardening Scripts for Automation

### Main Objective: Create `bash` scripts to perform the aforementioned security hardening procedures.

### hardening_script1

![Screenshot 2024-12-06 at 3 37 28 PM](https://github.com/user-attachments/assets/cbe033a7-f592-489d-8fba-2c763e392c81)

![Screenshot 2024-12-06 at 3 38 25 PM](https://github.com/user-attachments/assets/1435dbd1-aafc-46fc-ae6b-00174148f845)

![Screenshot 2024-12-06 at 3 38 58 PM](https://github.com/user-attachments/assets/9f5d4d8a-3ef6-4114-83b3-31193ff8d797)


### hardening_script1 Test

![Screenshot 2024-12-05 at 10 27 24 PM](https://github.com/user-attachments/assets/d500fcd1-d05f-4617-ae51-d69778df843c)


### hardening_script2

![Screenshot 2024-12-06 at 3 07 23 PM](https://github.com/user-attachments/assets/088bc89a-4889-4020-9cb8-974ed7a3f60b)


### hardening_script2 Test

![Screenshot 2024-12-06 at 3 09 28 PM](https://github.com/user-attachments/assets/12f1db76-a296-45be-a716-86ba862ef186)



---

## Schedule Hardening Scripts

### Main Objective: Schedule `bash` scripts using `cron`.

### Tasks

1. **Schedule hardening_script1 to run once a month on the first of the month**

2. **Schedule hardening_script2 to run once a week every monday**

![Screenshot 2024-12-06 at 3 17 29 PM](https://github.com/user-attachments/assets/ceabb7c4-87cf-410e-bcf0-a14612638827)

![Screenshot 2024-12-06 at 3 18 20 PM](https://github.com/user-attachments/assets/2e069b9e-4de4-48db-b67d-fcf35c8e43f6)
