<p align="center">
  <img src="https://i.imgur.com/pU5A58S.png" alt="Microsoft Active Directory Logo" />
</p>

# Active Directory User Account Management on Azure

This repository provides practical examples and walkthroughs for managing user accounts in an Active Directory environment hosted on Azure Virtual Machines. It covers common tasks such as account lockout policy setup, simulating lockouts, account enabling/disabling, and auditing through event logs.

---

## Technologies and Environments

- **Microsoft Azure** (Virtual Machines & Networking)  
- **Remote Desktop Protocol (RDP)**  
- **Active Directory Domain Services (AD DS)**  
- **PowerShell & Event Viewer**  

---

## Operating Systems Used

- Windows Server 2022 (Domain Controller)  
- Windows 10 (Client)  

---

## Features and Use Cases

### 1. Account Lockout Policy Configuration  
- Setting up account lockout thresholds using Group Policy.  
- Testing account lockouts through repeated invalid login attempts.  
- Procedures to unlock accounts and reset passwords.

### 2. Managing Account Status  
- Steps to disable and re-enable user accounts.  
- Demonstrating the effects of disabled accounts on login attempts.

### 3. Event Log Monitoring  
- Tracking security events on the Domain Controller and client machines.  
- Identifying failed login attempts and account lockout events via logs.

---

## Getting Started

1. Log in to your Domain Controller VM (`dc-1`) with administrative credentials.  
2. Confirm you have at least one test user account created in Active Directory.

---

## Step-by-Step Instructions

### Configure Account Lockout Policy

- Open **Group Policy Management Console (GPMC)** on the DC.  
- Navigate to the appropriate Group Policy Object and edit:  
  - Set the policy to lock accounts after 5 failed login attempts.  
- Save changes and enforce the policy.  
- Test by attempting to log in with an incorrect password multiple times to trigger the lockout.

### Observe Lockout Behavior and Recovery

- Confirm the account is locked after threshold exceeded.  
- Unlock the account and reset its password as needed for continued testing.

### Enable/Disable User Accounts

- Disable a specific user account from Active Directory Users and Computers (ADUC).  
- Attempt login with the disabled account and note the error message.  
- Re-enable the account and verify successful login afterward.

### Audit with Event Logs

- Use **Event Viewer** on the Domain Controller to review security logs related to login activity.  
- Check the client machine’s event logs to correlate login failures and lockouts.

---

## Recommended Screenshots

**For Account Lockout Policy Configuration & Testing:**  
- Screenshots showing GPMC policy settings.  
- Screens capturing the login attempts and lockout notifications.

<img width="448" alt="Screenshot 2025-01-23 at 6 43 36 PM" src="https://github.com/user-attachments/assets/0d424068-0be0-4580-be80-cc4abc554b0e" />
<img width="395" alt="Screenshot 2025-01-23 at 6 45 12 PM" src="https://github.com/user-attachments/assets/f105c6d8-ae9c-4703-82d6-1704a238d0be" />
<img width="791" alt="Screenshot 2025-01-23 at 6 45 33 PM" src="https://github.com/user-attachments/assets/32bc91e8-8b5f-4fbb-98a2-6ef4ea6ad1b1" />

**For Lockout Behavior & Recovery:**  
- Screens of unlocking the account in ADUC.  
- Password reset interface or confirmation.

<img width="527" alt="Screenshot 2025-01-23 at 6 47 37 PM" src="https://github.com/user-attachments/assets/1ab65701-9f50-43eb-b3fd-555272c876d7" />
<img width="419" alt="Screenshot 2025-01-23 at 6 48 22 PM" src="https://github.com/user-attachments/assets/5e8c41e6-70cd-475a-86f4-ff9ad1967d42" />
<img width="931" alt="Screenshot 2025-01-23 at 6 48 37 PM" src="https://github.com/user-attachments/assets/8ced3e12-bd2c-4a9f-ab8f-54e3f632ea6f" />

**For Enabling/Disabling Accounts:**  
- User account disabled in ADUC.  
- Login failure message with a disabled account.  
- Successful login after re-enabling.

<img width="503" alt="Screenshot 2025-01-23 at 6 51 51 PM" src="https://github.com/user-attachments/assets/45750d32-a894-49a1-945e-b9a65adeff5e" />
<img width="543" alt="Screenshot 2025-01-23 at 6 52 54 PM" src="https://github.com/user-attachments/assets/49d4c42e-20c9-4d65-bf21-5663d64f6da7" />

**For Log Monitoring:**  
- Event Viewer logs on Domain Controller showing failed login events.  
- Client machine event log entries related to account lockouts.

<img width="432" alt="Screenshot 2025-01-23 at 7 42 02 PM" src="https://github.com/user-attachments/assets/963d4b20-c8b6-45da-9095-8abe250660c2" />
<img width="1402" alt="Screenshot 2025-01-23 at 7 42 24 PM" src="https://github.com/user-attachments/assets/bca6d2a0-a992-4414-8e3d-54c34ecea5f2" />


---

## Purpose

This project aims to equip IT administrators and professionals with hands-on scenarios for effective Active Directory user account management. By demonstrating real-world workflows and troubleshooting steps, it serves as a practical resource to enhance skills in securing and maintaining AD user environments within Azure.

---

