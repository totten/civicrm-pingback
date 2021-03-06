civicrm-pingback
================

This repository contains the files used for the https://latest.civicrm.org website. This is used by CiviCRM core to check if any updates are needed.

As part of this update check (ie. pingback), a number of anonymous information is collected on the CiviCRM instance (see https://github.com/civicrm/civicrm-core/blob/master/CRM/Utils/VersionCheck.php). This information is stored in the stats database, and used notably for the CiviCRM statistics (see https://stats.civicrm.org). 

Requirements:
- a recent version of PHP with the mysqli extension enabled
- a copy of the GeoLite2 Country database, available at http://dev.maxmind.com/geoip/geoip2/geolite2/, stored at: /usr/share/GeoIP/GeoLite2-Country.mmdb
- a script to regularely update the GeoIP database - such as https://github.com/maxmind/geoipupdate or a much simpler shell script

### CLI: Listing releases

```
./bin/pb release:list
```

### CLI: Adding a new release

```
### Add a new security release
./bin/pb release:add 4.7.99 --date=2017-01-01 --security=true

## Add a new non-security release
./bin/pb release:add 4.7.99 --date=2017-01-01 --security=false

## Add a new release. (Default: Non-security, today's date)
./bin/pb release:add 4.7.99
```
