Screenshots README



This file describes each screenshot included in the repository. Filenames and descriptions match the actual images captured on 2025-09-06.



1\) Screenshot 2025-09-06 164733.png

&nbsp;  Active Directory Users and Computers (ADUC) showing the TECHCORE.LOCAL domain and all department OUs (HR, Finance, IT, Marketing, R and D, Customer Support, etc.).



2\) Screenshot 2025-09-06 164829.png

&nbsp;  ADUC focused on the Customer Support OU displaying example users (Chloe Adams, Ethan Clark, Grace Lopez) and the Support-Staff security group.



3\) Screenshot 2025-09-06 165200.png

&nbsp;  Group Policy Management Console (GPMC) with the Corporate Wallpapers GPO selected. Scope tab shows the GPO linked to techcore.local with Security Filtering = Authenticated Users.



4\) Screenshot 2025-09-06 165716.png

&nbsp;  Corporate Wallpapers GPO setting path: User Configuration -> Administrative Templates -> Desktop -> Desktop Wallpaper. Policy is Enabled with Wallpaper Name set to \\\\DC1\\Wallpapers\\techcore\_wallpaper.bmp and Wallpaper Style = Fill.



5\) Screenshot 2025-09-06 170013.png

&nbsp;  Client command prompt showing gpupdate /force followed by gpresult /r. The Applied Group Policy Objects list includes CustomerSupport drive, Block Tools (Control Panel), and Corporate Wallpapers.



6\) Screenshot 2025-09-06 171350.png

&nbsp;  Client File Explorer (This PC) showing the mapped HR Drive (H:) under Network locations, mapped to \\\\DC1\\HRShare.



7\) Screenshot 2025-09-06 171933.png

&nbsp;  Event Viewer -> Windows Logs -> Security on the server, displaying auditing events such as Event ID 4634 (logoff) and related entries.



8\) Screenshot 2025-09-06 172113.png

&nbsp;  Client desktop with the TechCore corporate wallpaper applied via GPO.



