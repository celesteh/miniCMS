# miniCMS
A tiny web insteface to HUGO. 
This is designed to work either on a normal website, or on a LAN that does not have access to the larger internet.

## Includes
* [FontAwesome] (http://fontawesome.io/) SIL and MIT licensed.

## Requirements
* [HUGO] (https://gohugo.io/)
* [SimpleMDE] (https://simplemde.com/) Which should be installed via bower, which is installed via npm
* PHP
* Any webserver. (Tested with [lighttpd](https://www.lighttpd.net/) on a RaspberryPi)

## How to install on a RaspberryPi

### Install and configure the webserver

* `sudo apt-get update`
* `sudo apt-get install lighttpd php5-cgi -y`
* `sudo lighty-enable-mod fastcgi`
* `sudo lighty-enable-mod fastcgi-php`
* `sudo mkdir /var/www/cgi-bin`
* edit `/etc/lighttpd/lighttpd.conf`
  * change the server modules section to:
`  server.modules = (`
`        "mod_access",`
`        "mod_alias",`
`        "mod_compress",`
`        "mod_redirect",`
`        "mod_rewrite",`
`        "mod_fastcgi",`
`        "mod_cgi",`
`)`

### Install SimpleMDE
* `sudo apt-get update`
* `sudo apt-get install npm`
* `sudo npm install -g bower`
* `cd /var/www/html/`  // Change THIS
* `bower install simplemde --save`

### Install HUGO
* `sudo apt-get hugo`
