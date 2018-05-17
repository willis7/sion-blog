+++
title = 'log tips and tricks'
date = "2018-05-17T00:01:00+01:00"
tags = ["logs", "grep", "less"]
categories = ['devops']
+++

As engineers we're constantly trawling through logs. Here's some tips for making that task a little easier.

## Searching logs
For larger logs we may want to scroll by page:

`cat mylog.log | less`

We can then use PgUp or PgDn or the mac equivalent.

## Regex search in less
`/<regex>`

## Find error with grep
`$ grep -I error /var/log/messages`
or find firewall related stuff

`sudo tail -f /var/log/messages |grep FIREWALL`

## Some common NGINX searches

```
$ grep "/login.php??" /var/log/nginx/access.log
$ grep "...etc/passwd" /var/log/nginx/access.log
$ egrep -i "denied|error|warn" /var/log/nginx/error.log

$ sudo grep 404 /var/log/nginx/access.log
$ sudo grep "GET /images/cityscience.jpg" /var/log/nginx/access.log
$ sudo grep -i "get /images/cityscience.jpg" /var/log/nginx/access.log

$ sudo tail -n 100 /var/log/nginx.log | grep 404
```