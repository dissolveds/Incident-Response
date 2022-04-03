## Methods
There are several way you could get information on sites the user visited, which search queries performed and downloaded files:

- Export process memory and process it with **Strings** utility  
````
volatility.exe -f <path_to_memomry_dump> --profile <os_profile> memdump -p <browser_pid> -D <path_for_browser_dump_file>
strings64.exe <path_for_browser_dump_file> > <broswer_strings.txt>
````
- Export process memory and process it with **bulk_extractor**  
````
volatility.exe -f <path_to_memomry_dump> --profile <os_profile> memdump -p <browser_pid> -D <path_for_browser_dump_file>
bulk_extractor -o <output_file_path> -x all -e email <path_for_browser_dump_file>
````

"-x" - disable all scanners  
"-e" - enable an email scanner, which searches for emails and URLs

- Search for URLs using regular expressions or **YARA** rules
````
volatility.exe -f <path_to_memomry_dump> --profile <os_profile> yarascan -Y "/(https?:\/\/)?([\w\.-]+)([\/\w \.-]*)/" -p <browser_pid>
````

## Tools

- Volatility  
- [bulk_extractor](https://downloads.digitalcorpora.org/downloads/bulk_extractor)  
- YARA Rules

## Reference
- Practical Memory Forensics: Jumpstart effective forensic analysis of volatile memory, by Svetlana Ostrovskaya and Oleg Skulkin 
