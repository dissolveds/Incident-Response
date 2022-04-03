## Sources of Memory Data

- **%SystemRoot%\Memory.dmp**  Crash dumps, not raw, can be analyzed via WinDbg
- **hiberfil.sys**  Windows hibernation file, compressed memory image from the previous boot. hiber2bin/imagecopy to convert to raw
- **pagefile.sys**  Not a complete copy of RAM,  parts of memory paged out to disk
- **.vmem** file    VMware raw memory
- **.vmss** file    VMware suspended state
- **.vmsn** file    VMware snapshot
- **.bin** file     Hyper-V memory chunks
- **.vsv** file     Hyper-V metadata
- **.mem** file     Parallels 
- **.sav** file     VirtualBox partial memory image

## Tools

- FTK Imager
- Redline
- Rekall  
  imagecopy \path\to\file.img
- DumpIt.exe
- WinPmem
- Belkasoft Live Ram Capturer
- Magnet Ram Capture
- win32dd.exe / win64dd.exe
