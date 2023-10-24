# Apache File Locations

Apache HTTP Server, commonly referred to as Apache, is open-source, cross-platform web server software. It's highly customizable, and files' locations can vary based on individual configurations and the specific operating system used. However, in a standard Apache installation, important configuration, log, and web files are often found in these locations:

1. **Configuration Files:**

- On Debian-based systems (like Ubuntu), you would find them in: `/etc/apache2/`
- On Red Hat-based systems (like CentOS), you would find them in: `/etc/httpd/`
- On a generic Unix-based system, you might find them in: `/usr/local/apache2/conf/`

The main configuration file is typically called `httpd.conf` or `apache2.conf`. In newer installations, you might also find additional configurations under `sites-enabled/`, `mods-enabled/`, `conf-enabled/` directories.

2. **Log Files:**

- On Debian-based systems: `/var/log/apache2/`
- On Red Hat-based systems: `/var/log/httpd/`
- On a generic Unix-based system: `/usr/local/apache2/logs/`

The error log is usually called `error_log`, and the access log `access_log`.

3. **Website Files:**

- On Debian-based systems: `/var/www/`
- On Red Hat-based systems: `/var/www/html/`
- On a generic Unix-based system: `/usr/local/apache2/htdocs/`

Remember that these locations can vary greatly depending on system administrator's preferences and the specifics of the system setup. These are just some common default locations.

To find the exact locations, you can look at the Apache configuration file(s). Look for `DocumentRoot` for the website files location, `ErrorLog` for the error log file location, and `CustomLog` for the access log file location.

---

## Apache Default Locations

GoBuster is a directory brute-forcing tool, meaning it attempts to discover directories and files on a web server by systematically guessing names. The results from a GoBuster scan will highly depend on the wordlist used, the specific configuration of the server, and the contents hosted there.

Here are some common directories and files that might show up in a scan of a typical Apache server, again emphasizing this is highly dependent on the server configuration and content:

1. `/` - root directory of the website
2. `/index.html` or `/index.php` - main webpage
3. `/admin` - if an admin panel is exposed (although this is a security risk and not recommended)
4. `/login` or `/login.php` - login page
5. `/images/` - directory where images are stored
6. `/css/` - directory where CSS style sheets are stored
7. `/js/` - directory where JavaScript files are stored
8. `/cgi-bin/` - directory that may contain scripts
9. `/uploads/` or `/files/` - directories where user uploaded files might be stored
10. `/robots.txt` - file that gives instructions to web crawlers
11. `/sitemap.xml` - file that helps search engines index the site
12. `/.htaccess` - Apache directory-level configuration file
13. `/server-status` and `/server-info` - if mod_status and mod_info modules are enabled and exposed (not recommended, as it's a potential security risk)
