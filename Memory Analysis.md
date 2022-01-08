## Sources of Memory Data

Live Machines:
- FTK Imager
- Redline
- Rekall
  > imagecopy "\path\to\file.img
- DumpIt.exe
- win32dd.exe / win64dd.exe

Offline:
- %SystemRoot%\Memory.dmp    Crash dumps, not raw, can be analyzed via WinDbg
- hiberfil.sys  Windows hibernation file, compressed memory image from the previous boot. hiber2bin/imagecopy to convert to raw
- .vmem file    VMware 
- .bin file     Hyper-V 
- .mem file     Parallels 
- .sav file     VirtualBox  
