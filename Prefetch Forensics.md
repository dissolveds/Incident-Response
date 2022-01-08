## Prefetch Files

When a user launches an application from a particular location for the very first time, 
Windows creates a Prefetch file (**.pf**) for that application under **%SystemRoot%\Prefetch** (C:\Windows\Prefetch).
These files are then used by the OS to pre-load the stored information from disk into memory in advance to speed up subsequent boots or application startup.
With Windows Vista, this idea was extended to SuperFetch, which tracks user behavior and attempts to predict when applications will be launched and cache the data necessary to load each application in advance.
The Application Prefetch file is named using the **name of the executable**, followed by a **dash**, and then an **eight character hash of the location** from which that application was run (eg. CALC.EXE-77FDF17F.pf)


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


