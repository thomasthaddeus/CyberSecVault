# Google Dorking

[Google Dorking](#google-dorking)

- [Google Dorking](#google-dorking)
  - [Security Related Dorks](#security-related-dorks)
  - [Internal Server related Dorks](#internal-server-related-dorks)
  - [Server Configuration Related Dorks](#server-configuration-related-dorks)
  - [Very Specific Server file Dorks (hit and miss!)](#very-specific-server-file-dorks-hit-and-miss)
  - [Generic File Searching Dorks](#generic-file-searching-dorks)
  - [OnlyFans Google Dorks](#onlyfans-google-dorks)
  - [Tinder Google Dorks](#tinder-google-dorks)

---

**References**: [The Ultimate Google Dorking Cheat Sheet – 2023](https://usersearch.org/updates/2023/02/05/the-ultimate-google-dorking-cheatsheet-2023/)

## Security Related Dorks

| #  | Google Dork Query                            | Explanation: "Searches for"                                               |
|----|----------------------------------------------|---------------------------------------------------------------------------|
| 1  | `filetype:pdf password`                      | PDF files containing the word "password".                                 |
| 2  | `intitle:index.of password.txt`              | websites with "index.of" in the title and the word "password.txt".        |
| 3  | `intext:"username" filetype:xls`             | Excel files containing the word "username".                               |
| 4  | `intext:"email" filetype:pdf`                | PDF files containing the word "email".                                    |
| 5  | `inurl:admin login`                          | webpages with "admin" and "login" in the URL.                             |
| 6  | `intitle:"Login page" "Username" "Password"` | pages with the title "Login page", "Username", and "Password".            |
| 7  | `inurl:login intext:"password"`              | pages with "login" in the URL and the word "password" in the text.        |
| 8  | `inurl:.php?id=`                             | pages containing ".php?id=" in the URL.                                   |
| 9  | `intitle:"SQL query failed" intext:"mysql"`  | pages with the title "SQL query failed" and the word "mysql" in the text. |
| 10 | `site:.edu filetype:pdf`                     | PDF files on ".edu" websites.                                             |
| 11 | `intext:"Private Key" filetype:pem`          | files with "Private Key" in the text and the file type "pem".             |
| 12 | `intitle:"Index of /" +passwd`               | websites with "Index of /" in the title and the word "passwd".            |
| 13 | `intitle:"Index of /" +secret`               | websites with "Index of /" in the title and the word "secret".            |
| 14 | `intext:"Confidential" filetype:ppt`         | PowerPoint files with the word "Confidential" in the text.                |
| 15 | `intext:"Database Error" intitle:"Warning"`  | pages with the text "Database Error" and the title "Warning".             |
| 16 | `intext:"PHP Script" "Debug"`                | pages with the text "PHP Script" and the word "Debug".                    |
| 17 | `intext:"to=python" filetype:py`             | Python files with the text "to=python".                                   |
| 18 | `intext:"API Key" filetype:yml`              | YAML files with the text "API Key".                                       |
| 19 | `intext:"API Key" filetype:env`              | environment files with the text "API Key".                                |
| 20 | `intext:"Private Key" filetype:key`          | files with the text "Private Key" and the file type "key".                |
| 21 | `intext:"System Information" filetype:log`   | log files with the text "System Information".                             |
| 22 | `intitle:"Index of /" +backup`               | websites with "Index of /" in the title and the word "backup".            |

## Internal Server related Dorks

Generic google dork queries in a cheatsheet format to search for security-related files on Google.

| #  | Google Dork Query                                | Explanation                                                                   |
|----|--------------------------------------------------|-------------------------------------------------------------------------------|
| 23 | `intext:"username"` `intitle:"config"`           | Searches for pages with the text "username" and the title "config".           |
| 24 | `intext:"Password"` `intitle:"Settings"`         | Searches for pages with the text "Password" and the title "Settings".         |
| 25 | `intext:"password"` `intitle:"configuration"`    | Searches for pages with the text "password" and the title "configuration".    |
| 26 | `intext:"secret"` `intitle:"config"`             | Searches for pages with the text "secret" and the title "config".             |
| 27 | `intext:"API Key"` `intitle:"documentation"`     | Searches for pages with the text "API Key" and the title "documentation".     |
| 28 | `intext:"server_name"` `filetype:nginx`          | Searches for Nginx configuration files with the text "server_name".           |
| 29 | `intext:"database_password"` `filetype:env`      | Searches for environment files with the text "database_password".             |
| 30 | `intext:"API Key"` `intitle:"Readme"`            | Searches for pages with the text "API Key" and the title "Readme".            |
| 31 | `intext:"ssh"` `intitle:"authorized_keys"`       | Searches for pages with the text "ssh" and the title "authorized_keys".       |
| 32 | `intext:"AWS Key"` `intitle:"Credentials"`       | Searches for pages with the text "AWS Key" and the title "Credentials".       |
| 33 | `intext:"AWS Access Key"` `intitle:"Settings"`   | Searches for pages with the text "AWS Access Key" and the title "Settings".   |
| 34 | `intext:"api_key"` `intitle:"Settings"`          | Searches for pages with the text "api_key" and the title "Settings".          |
| 35 | `intext:"access_token"` `intitle:"config"`       | Searches for pages with the text "access_token" and the title "config".       |
| 36 | `intext:"client_secret"` `intitle:"config"`      | Searches for pages with the text "client_secret" and the title "config".      |
| 37 | `intext:"private_key"` `intitle:"documentation"` | Searches for pages with the text "private_key" and the title "documentation". |
| 38 | `intext:"master_key"` `intitle:"documentation"`  | Searches for pages with the text "master_key" and the title "documentation".  |
| 39 | `intext:"db_password"` `intitle:"config"`        | Searches for pages with the text "db_password" and the title "config".        |

## Server Configuration Related Dorks

Internal server related Google Dorks to find exposed config files used to set up servers.

| #  | Google Dork Query                            | Explanation                                                               |
|----|----------------------------------------------|---------------------------------------------------------------------------|
| 40 | `intext:"ftp_password"` `intitle:"config"`   | Searches for pages with the text "ftp_password" and the title "config".   |
| 41 | `intext:"root_password"` `intitle:"config"`  | Searches for pages with the text "root_password" and the title "config".  |
| 42 | `intext:"sql_password"` `intitle:"config"`   | Searches for pages with the text "sql_password" and the title "config".   |
| 43 | `intext:"jwt_secret"` `intitle:"config"`     | Searches for pages with the text "jwt_secret" and the title "config".     |
| 44 | `intext:"secret_key"` `intitle:"config"`     | Searches for pages with the text "secret_key" and the title "config".     |
| 45 | `intext:"encryption_key"` `intitle:"config"` | Searches for pages with the text "encryption_key" and the title "config". |
| 46 | `intext:"key"` `intitle:"ssh_config"`        | Searches for pages with the text "key" and the title "ssh_config".        |
| 47 | `intext:"password"` `filetype:env`           | Searches for environment files with the text "password".                  |
| 48 | `intext:"api_key"` `filetype:env`            | Searches for environment files with the text "api_key".                   |
| 49 | `intext:"secret_key"` `filetype:env`         | Searches for environment files with the text "secret_key".                |
| 50 | `intext:"password"` `filetype:yaml`          | Searches for YAML configuration files with the text "password".           |
| 51 | `intext:"api_key"` `filetype:yaml`           | Searches for YAML configuration files with the text "api_key".            |
| 52 | `intext:"secret_key"` `filetype:yaml`        | Searches for YAML configuration files with the text "secret_key".         |
| 53 | `intext:"password"` `filetype:json`          | Searches for JSON configuration files with the text "password".           |
| 54 | `intext:"api_key"` `filetype:json`           | Searches for JSON configuration files with the text "api_key".            |
| 55 | `intext:"secret_key"` `filetype:json`        | Searches for JSON configuration files with the text "secret_key".         |
| 56 | `intext:"password"` `filetype:xml`           | Searches for XML configuration files with the text "password".            |
| 57 | `intext:"api_key"` `filetype:xml`            | Searches for XML configuration files with the text "api_key".             |
| 58 | `intext:"secret_key"` `filetype:xml`         | Searches for XML configuration files with the text "secret_key".          |
| 59 | `intext:"ssh"` `intitle:"id_rsa"`            | Searches for pages with the text "ssh" and the title "id_rsa".            |
| 60 | `intext:"ssh"` `intitle:"id_dsa"`            | Searches for pages with the text "ssh" and the title "id_dsa".            |
| 61 | `intext:"private_key"` `intitle:"ssh"`       | Searches for pages with the text "private_key" and the title "ssh"        |

## Very Specific Server file Dorks (hit and miss!)

Server Configuration Related Dorks. Less commonly found, but when found…can be pretty juicy!

| #  | Google Dork Query                                                                                        | Explanation                                                                                                        |
|----|----------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------|
| 62 | `intitle:"Index of /" +"parent directory" +description +size +last modified +"Apache" +"Windows"`        | Same as above, but for Windows-based servers.                                                                      |
| 63 | `intitle:"Index of /" +"parent directory" +description +size +last modified +"Microsoft-IIS" +"Unix"`    | Same as above, but for Microsoft IIS servers on Unix-based systems.                                                |
| 64 | `intitle:"Index of /" +"parent directory" +description +size +last modified +"Microsoft-IIS" +"Windows"` | Same as above, but for Microsoft IIS servers on Windows-based systems.                                             |
| 65 | `intitle:"Index of /" +"parent directory" +description +size +last modified +"Nginx" +"Unix"`            | Same as above, but for Nginx servers on Unix-based systems.                                                        |
| 66 | `intitle:"Index of /" +"parent directory" +description +size +last modified +"Nginx" +"Windows"`         | Same as above, but for Nginx servers on Windows-based systems.                                                     |
| 67 | `inurl:backup`                                                                                           | Searches for pages containing the word "backup", often revealing sensitive backup files and directories.           |
| 68 | `inurl:backup` `filetype:sql`                                                                            | Searches for SQL backup files.                                                                                     |
| 69 | `inurl:backup` `filetype:bak`                                                                            | Searches for files with the .bak extension, often revealing backup files.                                          |
| 70 | `inurl:backup` `filetype:tar`                                                                            | Searches for tar archive files, often containing backup data.                                                      |
| 71 | `inurl:backup` `filetype:gz`                                                                             | Searches for gzip-compressed files, often containing backup data.                                                  |
| 72 | `inurl:config.php`                                                                                       | Searches for pages containing the phrase "config.php", often revealing sensitive configuration files.              |
| 73 | `inurl:wp-config.php`                                                                                    | Searches for pages containing the phrase "wp-config.php", often revealing sensitive WordPress configuration files. |
| 74 | `inurl:database.php`                                                                                     | Searches for pages containing the phrase "database.php", often revealing sensitive database configuration files.   |
| 75 | `inurl:error_log`                                                                                        | Searches for pages containing the phrase "error_log", often revealing sensitive error logs.                        |
| 76 | `inurl:access_log`                                                                                       | Searches for pages containing the phrase "access_log", often revealing sensitive access logs.                      |
| 77 | `inurl:phpinfo.php`                                                                                      | Searches for pages containing the phrase "phpinfo.php", often revealing sensitive PHP information.                 |
| 78 | `inurl:server-status`                                                                                    | Searches for pages containing the phrase "server-status", often revealing sensitive server information.            |
| 79 | `inurl:phpmyadmin`                                                                                       | Searches for pages containing the phrase "phpmyadmin",often revealing sensitive PHPMyAdmin information.            |

## Generic File Searching Dorks

Very Specific Server file Dorks (hit and miss!). You’ll not often see results for these, but where they do occur, it can be a goldmine! \
These just search for specific file types. You can modify these to search for any kind of file you are interested in.

|`filetype:pem`|Searches for PEM certificate files.|
|`filetype:cer`|Searches for certificate files with the .cer extension.|
|`filetype:key`|Searches for encryption key files.|
|`filetype:ppk`|Searches for PuTTY private key files.|
|`filetype:pfx`|Searches for PKCS #12 certificate files.|
|`filetype:asc`|Searches for ASCII armored PGP or GPG files.|
|`filetype:crt`|Searches for certificate files with the .crt extension.|
|`filetype:csr`|Searches for certificate signing request files.|
|`filetype:der`|Searches for binary DER certificate files.|

## OnlyFans Google Dorks

OnlyFans has more registered users than the number of people in the USA!
If you are interested in furthering your knowledge sets in finding users on Google Dorks, we have a good amount of information on it in our article.

OnlyFans Google Dork queries to find information about the website.

| #  | Google Dork                                         | Explanation                                                                             |
|----|-----------------------------------------------------|-----------------------------------------------------------------------------------------|
| 1  | `site:onlyfans.com` `inurl:"/files"`                | Searches for directories containing the word "files" on OnlyFans.com.                   |
| 2  | `site:onlyfans.com` `"Index of /"`                  | Searches for directories with an index of files on OnlyFans.com.                        |
| 3  | `site:onlyfans.com` `intitle:"Uploaded Files"`      | Searches for pages with the title "Uploaded Files" on OnlyFans.com.                     |
| 4  | `site:onlyfans.com` `filetype:pdf`                  | Searches for PDF files on OnlyFans.com.                                                 |
| 5  | `site:onlyfans.com` `filetype:docx`                 | Searches for Microsoft Word files on OnlyFans.com.                                      |
| 6  | `site:onlyfans.com` `filetype:ppt`                  | Searches for Microsoft PowerPoint files on OnlyFans.com.                                |
| 7  | `site:onlyfans.com` `intitle:"login"`               | Searches for pages with the title "login" on OnlyFans.com.                              |
| 8  | `site:onlyfans.com` `intitle:"sign in"`             | Searches for pages with the title "sign in" on OnlyFans.com.                            |
| 9  | `site:onlyfans.com` `inurl:"/admin"`                | Searches for directories containing the word "admin" on OnlyFans.com.                   |
| 10 | `site:onlyfans.com` `"Powered by OnlyFans"`         | Searches for pages containing the phrase "Powered by OnlyFans" on OnlyFans.com.         |
| 11 | `site:onlyfans.com` `"Contact Us"`                  | Searches for pages containing the phrase "Contact Us" on OnlyFans.com.                  |
| 12 | `site:onlyfans.com` `"About Us"`                    | Searches for pages containing the phrase "About Us" on OnlyFans.com.                    |
| 13 | `site:onlyfans.com` `inurl:"/privacy"`              | Searches for pages containing the word "privacy" on OnlyFans.com.                       |
| 14 | `site:onlyfans.com` `inurl:"/terms"`                | Searches for pages containing the word "terms" on OnlyFans.com.                         |
| 15 | `site:onlyfans.com` `inurl:"/faq"`                  | Searches for pages containing the word "faq" on OnlyFans.com.                           |
| 16 | `site:onlyfans.com` `inurl:"/help"`                 | Searches for pages containing the word "help" on OnlyFans.com.                          |
| 17 | `site:onlyfans.com` `inurl:"/support"`              | Searches for pages containing the word "support" on OnlyFans.com.                       |
| 18 | `site:onlyfans.com` `intitle:"Blog"`                | Searches for pages with the title "Blog" on OnlyFans.com.                               |
| 19 | `site:onlyfans.com` `"Latest News"`                 | Searches for pages containing the phrase "Latest News" on OnlyFans.com.                 |
| 20 | `site:onlyfans.com` `"Press Releases"`              | Searches for pages containing the phrase "Press Releases" on OnlyFans.com.              |
| 21 | `site:onlyfans.com` `"Company Information"`         | Searches for pages containing the phrase "Company Information" on OnlyFans.com.         |
| 23 | `site:onlyfans.com` `inurl:"/careers"`              | Searches for pages containing the word "careers" on OnlyFans.com.                       |
| 24 | `site:onlyfans.com` `intitle:"Jobs"`                | Searches for pages with the title "Jobs" on OnlyFans.com.                               |
| 25 | `site:onlyfans.com` `inurl:"/career"`               | Searches for pages containing the word "career" on OnlyFans.com.                        |
| 26 | `site:onlyfans.com` `inurl:"/hiring"`               | Searches for pages containing the word "hiring" on OnlyFans.com.                        |
| 27 | `site:onlyfans.com` `intitle:"Careers at OnlyFans"` | Searches for pages with the title "Careers at OnlyFans" on OnlyFans.com.                |
| 28 | `site:onlyfans.com` `intitle:"Join Our Team"`       | Searches for pages with the title "Join Our Team" on OnlyFans.com.                      |
| 29 | `site:onlyfans.com` `intitle:"Open Positions"`      | Searches for pages with the title "Open Positions" on OnlyFans.com.                     |
| 30 | `site:onlyfans.com` `"Join the OnlyFans Community"` | Searches for pages containing the phrase "Join the OnlyFans Community" on OnlyFans.com. |
| 31 | `site:onlyfans.com` `"Community Guidelines"`        | Searches for pages containing the phrase "Community Guidelines" on OnlyFans.com.        |
| 32 | `site:onlyfans.com` `intitle:"Forum"`               | Searches for pages with the title "Forum" on OnlyFans.com.                              |
| 33 | `site:onlyfans.com` `intitle:"Community"`           | Searches for pages with the title "Community" on OnlyFans.com.                          |
| 34 | `site:onlyfans.com` `inurl:"/forum"`                | Searches for pages containing the word "forum" on OnlyFans.com.                         |
| 35 | `site:onlyfans.com` `inurl:"/community"`            | Searches for pages containing the word "community" on OnlyFans.com.                     |
| 36 | `site:onlyfans.com` `"Get in Touch"`                | Searches for pages containing the phrase "Get in Touch" on OnlyFans.com.                |
| 37 | `site:onlyfans.com` `intitle:"Contact"`             | Searches for pages with the title "Contact" on OnlyFans.com.                            |
| 38 | `site:onlyfans.com` `intitle:"Reach Out"`           | Searches for pages with the title "Reach Out" on OnlyFans.com.                          |
| 39 | `site:onlyfans.com` `intitle:"Get Help"`            | Searches for pages with the title "Get Help" on OnlyFans.com.                           |
| 40 | `site:onlyfans.com` `"Support Center"`              | Searches for pages containing the phrase "Support Center" on OnlyFans.com.              |
| 41 | `site:onlyfans.com` `inurl:"/support-center"`       | Searches for pages containing the word "support-center" on OnlyFans.com.                |
| 42 | `site:onlyfans.com` `intitle:"Support"`             | Searches for pages with the title "Support" on OnlyFans.com.                            |

## Tinder Google Dorks

Some top Google Dork queries for Tinder.

| #  | Google Dork Query                                        | Description                                                                                   |
|----|----------------------------------------------------------|-----------------------------------------------------------------------------------------------|
| 1  | `site:tinder.com` `inurl:login`                          | Searches for pages with "login" in the URL on the tinder.com domain                           |
| 2  | `site:tinder.com` `intitle:"tinder login"`               | Searches for pages with "tinder login" in the title on the tinder.com domain                  |
| 3  | `site:tinder.com` `"Tinder, Inc."`                       | Searches for pages mentioning "Tinder, Inc." on the tinder.com domain                         |
| 4  | `site:tinder.com` `intext:"password"`                    | Searches for pages containing the word "password" on the tinder.com domain                    |
| 5  | `site:tinder.com` `filetype:php inurl:login`             | Searches for .php files containing "login" in the URL on the tinder.com domain                |
| 6  | `site:tinder.com` `intext:"Tinder API"`                  | Searches for pages containing the text "Tinder API" on the tinder.com domain                  |
| 7  | `site:tinder.com` `intext:"private data"`                | Searches for pages containing the text "private data" on the tinder.com domain                |
| 8  | `site:tinder.com` `"secure server"`                      | Searches for pages containing the text "secure server" on the tinder.com domain               |
| 9  | `site:tinder.com` `intext:"user name"`                   | Searches for pages containing the text "user name" on the tinder.com domain                   |
| 10 | `site:tinder.com` `"access denied"`                      | Searches for pages containing the text "access denied" on the tinder.com domain               |
| 11 | `site:tinder.com` `intitle:"tinder sign up"`             | Searches for pages with "tinder sign up" in the title on the tinder.com domain                |
| 12 | `site:tinder.com` `inurl:register`                       | Searches for pages with "register" in the URL on the tinder.com domain                        |
| 13 | `site:tinder.com` `filetype:xml`                         | Searches for .xml files on the tinder.com domain                                              |
| 14 | `site:tinder.com` `intext:"tinder database"`             | Searches for pages containing the text "tinder database" on the tinder.com domain             |
| 15 | `site:tinder.com` `intext:"tinder API"`                  | Searches for pages containing the text "tinder API" on the tinder.com domain                  |
| 16 | `site:tinder.com` `intext:"tinder secret key"`           | Searches for pages containing the text "tinder secret key" on the tinder.com domain           |
| 17 | `site:tinder.com` `inurl:terms`                          | Searches for pages with "terms" in the URL on the tinder.com domain                           |
| 18 | `site:tinder.com` `intitle:"tinder privacy policy"`      | Searches for pages with "tinder privacy policy" in the title on the tinder.com domain         |
| 19 | `site:tinder.com` `intext:"tinder personal information"` | Searches for pages containing the text "tinder personal information" on the tinder.com domain |
| 20 | `site:tinder.com` `intext:"tinder user data"`            | Searches for pages containing the text "tinder user data" on the tinder.com domain            |
