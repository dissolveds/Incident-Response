## Chrome

The Chrome browser profile contains files that save the user's info during a browser session.  

**Profile Path**	
```
C:\user\<username>\AppData\Local\Google\Chrome\User Data\Default\
```
Same information can be found by navigating to ```chrome://version ```

**Browser History**

This file is stored as an SQLite database and contains the browsing information for all logged-in users, such as download chains, search terms, visited links, Downloads, etc.
```
C:\Users\<username>\AppData\Local\Google\Chrome\User Data\Default\History
```
DB browser can be used to view the content of this db.
Forensically interestings tables:

- URLs: url, title, visit count, typed count, last visit time, hidden
- Visits: unique to the Chromium browser only, multiple records of the same URL each time it's visited. Used in conjuction with VISIT_SOURCE table.
- Downloads: guid, current path, target path, start time, received bytes, total bytes, referer, tab_url, tab_referer_url, mime type
