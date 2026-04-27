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

## Licensing

These are not real logs and the data is generic. I do not think this is
copyrightable so I put the CC0 license to signify that this is public domain.
