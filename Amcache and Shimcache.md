## Amcache and Shimcache Files

Shimcache/Amcache records basic info about the last several (max 1024) executables that ran. Shimcache is the older implementation. 
Starting with Windows 8 and Server 2012, it was replaced by Amcache.   
The file location is under the Windows directory at: **"C:\Windows\AppCompat\Programs\"**    
**RecentFileCache.bcf** (Shimcache) and **Amcache.hve** (Amcache). 
The Shimcache only contains the information prior to the system’s last startup, as
current entries are stored only in memory.  
The Amcache.hve file is a registry file that stores the information of executed applications.

#### Registry Keys

HKLM\SYSTEM\CurrentControlSet\Control\SessionManager\AppCompatCache\AppCompatCache

## Forensic Value of Amcache Files    
The cache stores various file metadata depending on the operating system, such as:
- File Full Path
- File Size
- Volume GUID
- Shimcache Last Updated time
- Process Execution Flag
- Last modified date
- SHA1 hash

**Key things to remember:**  
- Recent entries are on the top.
- Entries are written on shutdown
- Cannot determine the last time of execution via Shimcache
- The appearance of a binary in the File key in AmCache.hve is not sufficient to prove binary execution but does prove the presence of the file on the system

![image](https://user-images.githubusercontent.com/18302548/148705036-572d96e1-a64e-490f-86b7-6c5b987204a9.png)


#### Forensic use-cases
- Usually overlooked by attackers erasing their tracks
- Can be used to track executed binaries, installed and deleted programs


## Tools

- [RecentFileCacheParser and AmcacheParser](https://ericzimmerman.github.io/#!index.md) by Eric Zimmerman
- RegRipper 

### Reference
[Analysis of the Amcache by Blanche Lagny](https://www.ssi.gouv.fr/uploads/2019/01/anssi-coriin_2019-analysis_amcache.pdf)
