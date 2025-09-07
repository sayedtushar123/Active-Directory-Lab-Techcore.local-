# Active Directory Lab Project

This project is a hands-on Active Directory lab I built using Windows Server 2019 as a Domain Controller (DC1) and Windows 10/11 client machines inside VirtualBox. The goal was to recreate a real-world corporate IT environment where users, groups, policies, and resources are managed centrally.

The domain is set up as TECHCORE.LOCAL with multiple departments, each organized into their own Organizational Units (OUs). I created and tested Group Policy Objects (GPOs) to enforce security, apply restrictions, deploy software, and provide a consistent user environment. I also configured file shares, mapped drives, managed DNS, and enabled auditing to simulate enterprise IT operations.

## What I Implemented

- Domain Setup
  - Windows Server 2019 Domain Controller (DC1)
  - Domain: TECHCORE.LOCAL
  - Windows 10/11 clients joined to the domain in VirtualBox

- Organizational Units
  - HR, Finance, IT, Marketing, R&D, Customer Support
  - Users and groups managed by department

- Group Policies
  - Password policy and account lockout settings
  - Disabled guest account
  - Blocked Control Panel for non-IT users
  - Applied corporate wallpaper for branding
  - Security auditing for logon events and file access
  - Software deployment for HR department using MSI via GPO
  - Windows Update management to control update settings

- File Server
  - Departmental shared folders with NTFS permissions
  - Drive mapping via GPO for each department

- Troubleshooting & Hardening
  - Fixed DNS issues (multi-homed VirtualBox adapters, NAT vs Host-only)
  - Resolved Group Policy update and wallpaper application failures
  - Used tools like gpupdate, gpresult, dcdiag, nltest, and Event Viewer
  - Addressed domain login errors (domain unavailable, time sync issues)
  - Scoped GPOs so IT/admin accounts were not restricted

## Skills Gained

- Active Directory domain and OU administration
- Group Policy creation, scoping, and troubleshooting
- File server setup with permissions and mapped drives
- Software deployment through Group Policy
- DNS configuration and AD troubleshooting
- Security hardening and auditing policies
- Windows Update management via GPO
- Building and maintaining a virtual lab in VirtualBox

---

This lab gave me practical experience in how companies manage users, devices, and policies with Active Directory. It also helped me practice troubleshooting real-world problems like DNS misconfiguration, Group Policy failures, login issues, and wallpaper branding — challenges IT admins deal with daily in enterprise environments.
