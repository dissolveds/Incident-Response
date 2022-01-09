## Amcache and Shimcache Files

Shimcache/Amcache records basic info about the last several (max 1024) executables that ran. Shimcache is the older implementation. 
Starting with Windows 8 and Server 2012, it was replaced by Amcache.   
The file location is under the Windows directory at: **C:\Windows\AppCompat\Programs\**    
**RecentFileCache.bcf** (Shimcache) and **Amcache.hve** (Amcache).  
The Amcache.hve file is a registry file that stores the information of executed applications.


## Forensic Value of Amcache Files

- Usually overlooked by attackers erasing their tracks
