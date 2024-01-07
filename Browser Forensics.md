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

**Cached History**

The cached data include images, JavaScript files, form data, etc., and could be stored in multiple formats. Chrome stores cached data in three types of files: index, data_X, and f_XXXX, aunder the following path:

```
C:\Users\<username>\AppData\Local\Google\Chrome\User Data\Default\Cache\Cache_Data
```
The data_X file will store cached content of content small size; if it exceeds a certain size, the content is stored in the f_XXXX files instead.

**Cookies**

Cookies in chrome are stored in a database file called Cookies.sqlite.
```
C:\Users\<username>\AppData\Local\Google\Chrome\User Data\Default\Network\Cookies
```

**Bookmarks**

Bookmarks are stored in JSON format and can be found in the following locations:
```
C:\Users\<username>\AppData\Local\Google\Chrome\User Data\Default\Bookmarks
```
```
C:\Users\username>\AppData\Local\Google\Chrome\User Data\ChromeDefaultData\Bookmarks
```

**Chrome Sync Accounts/Data**

```
C:\Users\<username>\AppData\Local\Google\Chrome\User Data\Default\Sync Data\LevelDB\SyncData.sqlite

```

**Chrome Logins**

Chrome login data (saved credentials) is located as a sqlite database in the directory:
```
C:\Users\<username>\AppData\Local\Google\Chrome\User Data\Default\Login Data
```
Forensically interestings tables:
logins - origin URL, username value, date created and date_password_modified

Note: the password will be empty because they are stored in encrypted form and will therefore display as a BLOB value.
