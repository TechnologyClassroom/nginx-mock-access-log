# Web Server Mock Data

This is a repository that stores mock web server logs data such as those that
might be created by production instances of Apache2, NGINX, Caddy, and
Zentinel.

I am creating this for development and testing purposes for my
[LogReview](https://github.com/TechnologyClassroom/LogReview) and
[logreview-rs](https://github.com/TechnologyClassroom/logreview-rs)
repositories.

These will likely all be created with [jxkx1's
nginx-log-generator](https://github.com/jxkx1/nginx-log-generator) with some
minor tweaks. When helpful, I will share my updates upstream.

## Log description

* [test1.log] - Basic small log file with 100 lines in NGINX/Apache2 combined
  log format.
* [test2.log] - Medium log file with 437,500 lines with simulated C2 logs in
  NGINX/Apache2 combined log format.

## Variations

Apache2's `/etc/apache2/apache2.conf file` defines `combined` log format as this:

    LogFormat "%h %l %u %t \"%r\" %>s %O \"%{Referer}i\" \"%{User-Agent}i\"" combined

Most Apache2 and NGINX servers seem to use the combined log format.

### syslog-ng

Sometimes the log might be recorded to syslog-ng. To change a log to the
syslog-ng variation of apache2 combined log:

    sed -i 's/^/Apr 27 16:28:17 hostname1p apache\[4165\]: /g' test1.log

Note that the formatting might vary across some systems, but the columns
delimted by spaces are consistent.

### vhost_combined

Apache2's `/etc/apache2/apache2.conf file` defines `vhost_combined` log format
as this:

    LogFormat "%v:%p %h %l %u %t \"%r\" %>s %O \"%{Referer}i\" \"%{User-Agent}i\"" vhost_combined

Change a log to the apache2 vhosts_combined log format:

    sed -i 's/^/technologyclassroom.org:443 /g' test1.log

## Licensing

These are not real logs and the data is generic. I do not think this is
copyrightable so I put the CC0 license to signify that this is public domain.

If anything in the repository is copyrightable, consider it public domain, CC0,
Unlicense, MIT-0, 0BSD, or another highly-permissive compatible license.
