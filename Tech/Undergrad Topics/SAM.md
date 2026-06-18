What is WAMP?

IIS - Internet Information Services 

Apache HTTP Server (httpd)

logs\apache_error.log
logs\access.log

Listen — defines which port Apache listens on (default: 80)

Options Indexes — enables directory listing (REMOVE in production for security)

Options -Indexes — DISABLES directory listing (security best practice)

AllowOverride All — allows .htaccess files to override server config

Require all granted — allows access from all IPs

Require local — restricts access to localhost only

httpd-vhosts.conf
File location: apache/conf/extra/httpd-vhosts.conf

2Must be included in httpd.conf: Include conf/extra/httpd-vhosts.conf

3VirtualHost *:80 — catches all traffic on port 80

4ServerName — the domain or IP for this virtual host

5ServerAlias — alternative domain names for the same host

6DocumentRoot — the folder Apache serves for this virtual host

7Options -Indexes +FollowSymLinks — secure directory options

8AllowOverride All — enables .htaccess for this virtual host

.htaccess File
Located in the website root folder (e.g., C:\wamp64\www\mysite\.htaccess)

2WordPress auto-generates .htaccess when you save Permalink settings

3WordPress .htaccess enables mod_rewrite for clean URLs

4Restrict access: 'Deny from all' blocks a folder from web access

5Redirect URLs: Redirect 301 /old-page /new-page

6Protect wp-config.php: <Files wp-config.php> deny from all </Files>

7AllowOverride All must be set in VirtualHost for .htaccess to work

CONFIG
DATABASE
REPO

Conflict Resolution
