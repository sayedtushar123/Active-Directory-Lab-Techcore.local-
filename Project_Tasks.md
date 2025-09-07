Project\_Tasks.md — TechCore Active Directory Lab (TECHCORE.LOCAL)

This file is a step-by-step record of my Active Directory lab project. The lab was built on Windows Server 2019 (DC1) and Windows 10/11 clients running inside VirtualBox.



1. Lab Setup

* Installed Windows Server 2019 and named it DC1
* Installed Windows 10/11 client machines in VirtualBox
* Configured two network adapters on clients: Host-Only for domain traffic (DNS pointing to DC1 at 192.168.56.10) and NAT for internet access
* Promoted DC1 to Domain Controller and created a new forest called TECHCORE.LOCAL
* Verified that Active Directory and DNS roles were working correctly



2. Organizational Units and Accounts

* Created department OUs: HR, Finance, IT, Marketing, R\&D, and Customer Support
* Created security groups such as HR-Staff, Finance-Staff, etc
* Added 3 user in each department and computers to their corresponding OUs
* Ensured IT and admin accounts were excluded from restrictive policies



3. Central Store and ADMX Templates

* Configured the Central Store in SYSVOL for Group Policy definitions
* Added the Windows 11 (24H2) ADMX and ADML templates
* Confirmed Group Policy Management Console used the Central Store



4. File Server and Permissions

* Created departmental folders on DC1 under C:\\Departments
* Set NTFS permissions so that Domain Admins and SYSTEM have full control, and each department group has modify access to its folder
* Shared the folders (for example \\DC1\\HRShare)
* Verified share and NTFS permissions enforced least privilege



5. Group Policy Objects

* Configured password policy and account lockout settings
* Disabled the guest account
* Block USB for non IT users.
* Blocked Control Panel and Settings for non-IT users
* Applied corporate wallpaper through a shared folder (\\DC1\\Wallpapers\\techcore\_wallpaper.bmp)
* Configured auditing for logon/logoff and file access
* Created drive mappings by OU (HR gets H: mapped to \\DC1\\HRShare, Finance gets F: mapped to \\DC1\\FinanceShare, etc)
* Deployed software to the HR department using an MSI package via GPO
* Configured Windows Update management to prevent auto restart while users are logged in and to stop users from changing update settings



6. DNS and Networking Fixes

* Ensured clients used only DC1 (192.168.56.10) as DNS
* Removed DNS settings from the NAT adapter
* Set Host-Only adapter to higher priority than NAT
* Disabled multi-homed DNS registration to prevent conflicts
* Flushed DNS and tested using nltest and gpupdate to confirm reliable GPO application
* Resynced time on clients to fix Kerberos issues



7. Troubleshooting and Tools

* Used gpupdate /force to refresh policies
* Used gpresult to confirm applied policies
* Ran dcdiag and dfsrmig to confirm domain and SYSVOL health
* Used nltest to check domain controller discovery
* Checked Group Policy and auditing logs in Event Viewer
* Fixed login errors by rejoining clients to the domain or correcting DNS and time settings
* Verified file shares, mapped drives, and MSI deployment on clients



8. Lessons Learned

* Clients must always use the domain controller for DNS or Group Policy will fail
* VirtualBox multi-adapter networking can break GPOs and wallpaper policies if DNS priority is wrong
* GPO order only matters when multiple GPOs set the same option
* Wallpaper is cosmetic, but password policy, account lockout, and auditing are essential
* Blocking PowerShell globally can cause side effects, so real environments use AppLocker or SRP
* Auditing provides useful visibility into user actions
* Windows Update GPOs must be tested carefully as they can affect the user experience



9. Evidence

* OU structure in Active Directory Users and Computers
* GPO settings in Group Policy Management Console
* gpresult reports on clients
* File share permissions and mapped drives
* MSI software installed in HR clients
* Wallpaper applied on clients when DNS was stable
* Event Viewer logs showing auditing events
* 

10\. tatus Summary

* Domain setup: Complete
* OUs, users, groups: Complete
* Security policies: Complete
* User restrictions: Complete
* Corporate wallpaper: Configured, with VirtualBox reliability caveat
* File shares and drive mapping: Complete
* Auditing: Complete
* Software deployment for HR: Complete
* Windows Update management: Complete
* Troubleshooting: Documented and resolved
