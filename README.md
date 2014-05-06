adaway
======

Simple ad-blocking for GNU/Linux

## Installation

Copy adaway script to **/usr/local/sbin** directory and run the following commands:

* ` chown 0:0 /usr/local/sbin/adaway `
* ` chmod 750 /usr/local/sbin/adaway `

Please note: **/usr/local/sbin/** must be available in PATH. Otherwise copy script to **/usr/sbin** or **/sbin** directory 


## Ad Blocking

On first run this script will save _/etc/hosts_ as _/etc/hosts.local_ . This file later will be merged with ad-blocking rules as _/etc/hosts_ .

### Black and White lists

There are two files in /etc directory also made by this script on the first run:

* /etc/hosts.wlist
* /etc/hosts.blist
 
This files used for modifying /etc/hosts while merging ad-blocking rules

Each entry of black list will be added to /etc/hosts with 127.0.0.1 loopback address.

For example: to block banner from http://advert.example.com/banner.cgi=1, you must add only domain name `advert.example.com` - not IP address or full URL.


White list works in another way.

Each entry, containing any of the whitelisted domains will be removed from /etc/hosts

So, if you want to unblock ads from *.advert.example.com, it would be enough to write only advert.example.com or even example.com


### Backups

On each run before any other actions this script makes backup of current hosts file in `/var/backups/hosts.Y-m-d.gz` file.

-----

> **Use [Privoxy](http://www.privoxy.org/) instead of this script if you have /etc/hosts file of 2mb+**

----

#### Acknowledgment

This script was made to reflect the same result as [AdAway](http://www.adaway.org) app on my phone.
I would like to thank [Dominik Schürmann](https://github.com/dschuermann/) for his work.

