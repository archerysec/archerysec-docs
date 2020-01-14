---
title: 
category: Getting Started
chapter: 2
order: 1
---

####  ** **DO NOT EXPOSE PUBLICLY, INTERNAL USE ONLY** **
<br/>
Before installing Archery, you need to make sure you have python3, pip3 and virtualenv pre installed in your system.

Time Zone: [https://en.wikipedia.org/wiki/List_of_tz_database_time_zones](https://en.wikipedia.org/wiki/List_of_tz_database_time_zones)

``` bash
export TIME_ZONE='Asia/Kolkata'

$ git clone https://github.com/archerysec/archerysec.git
$ cd archerysec
$ ./setup.sh
$ ./run.sh
```

### Restrict ArcherySec signup page on production.

- Edit file `webscanners/web_views.py`
- Search `def signup` function and comment `@public` decorator
- Edit file `archeryapi/views.py`
- Search def `class CreateUsers` and comment `@public` decorator
- Edit file `archerysecurity/settings/base.py`
- Search `STRONGHOLD_PUBLIC_URLS`
- Comment `r'^/api/createuser/$',`