## Prefetch Files

When a user launches an application from a particular location for the very first time, 
Windows creates a Prefetch file (**.pf**) for that application under **%SystemRoot%\Prefetch** (C:\Windows\Prefetch).
These files are then used by the OS to pre-load the stored information from disk into memory in advance to speed up subsequent boots or application startup.
With Windows Vista, this idea was extended to SuperFetch, which tracks user behavior and attempts to predict when applications will be launched and cache the data necessary to load each application in advance.
The Application Prefetch file is named using the **name of the executable**, followed by a **dash**, and then an **eight character hash of the location** from which that application was run (eg. CALC.EXE-77FDF17F.pf)
If an application is run from two different locations on the drive, there will be two different prefetch files in the Prefetch folder. 

#### Maximum Number of Prefetch files:

Windows XP to Windows 7: 128  
Windows 8 to Windows 10: 1024

#### Registry Keys

 **HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\Session Manager\Memory Management\PrefetchParameters**
 
Under this key, the EnablePrefetcher value can either be:

0 – Disabled  
1 – Application Prefetching Enabled  
2 – Boot Prefetching Enabled  
3 – Application and Boot Prefetching Enabled  


## Forensic Value of Prefetch Files

 Prefetch files contain the following information:
 
 - The name of executable
 - The executable’s path
 - Unicode list of DLLs used by that executable
 - The number of times the executable has been run
 - The creation timestamp of .pf file (in some cases, this may indicate the first run time of an executable in a system)
 - The last run time of the executable (last modification timestamp of .pf file)
 - For Windows 8 onwards, the 7 previous last run timestamps if executed more than once
 - The files and directories that were used by the executable
 - Volume related information, like volume path and volume serial number

![image](https://user-images.githubusercontent.com/18302548/148655719-86a7c59b-9c27-4242-8331-bf96d1b076f8.png)

 #### Forensic use-cases
 
 - Prefetch files can prove that a suspect ran a cleanup program to cover up any traces of wrongdoing
 - If a program has since been deleted, a Prefetch file may still exist to provide evidence of previous existence and execution.
 - By analyzing the Prefetch files, forensic investigators can determine the exact path of a malware and when it was first/last run.
 - Same names but unusual executable locations or file sizes

#### Notes
Based on [Krzystof Gajewski blog post](https://cyberdefnerd.com/2022/01/16/can-windows-update-fool-you-during-the-investigation/) Windows Update may delete delete PREFETCH files.


## Tools

- [PECmd by Eric Zimmerman](https://ericzimmerman.github.io)  
  Examples:  
  - PECmd.exe -f "C:\Temp\CALC.EXE-3FBEF7FD.pf"  
  - PECmd.exe -d "C:\Temp" -k "system32, fonts"  
  - PECmd.exe -d "C:\Windows\Prefetch" --csv "C:\Users\Admin\Downloads\PECmd\"
- [WinPrefetchView by Nirsoft (GUI)](http://www.nirsoft.net/utils/win_prefetch_view.html)
