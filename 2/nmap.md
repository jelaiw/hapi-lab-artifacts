```sh
$ nmap 10.128.0.3
Starting Nmap 7.94 ( https://nmap.org ) at 2023-09-04 16:54 UTC
Nmap scan report for vulnweb.us-central1-c.c.hapi-lab.internal (10.128.0.3)
Host is up (0.00025s latency).
Not shown: 998 closed tcp ports (conn-refused)
PORT   STATE SERVICE
22/tcp open  ssh
80/tcp open  http

Nmap done: 1 IP address (1 host up) scanned in 0.17 seconds
```

```sh
$ nmap -sC -sV -oA nmap 10.128.0.3
Starting Nmap 7.94 ( https://nmap.org ) at 2023-09-04 16:57 UTC
Nmap scan report for vulnweb.us-central1-c.c.hapi-lab.internal (10.128.0.3)
Host is up (0.00024s latency).
Not shown: 998 closed tcp ports (conn-refused)
PORT   STATE SERVICE VERSION
22/tcp open  ssh     OpenSSH 8.4p1 Debian 5+deb11u1 (protocol 2.0)
| ssh-hostkey: 
|   3072 f6:7c:70:e4:c6:c7:d9:db:2a:ee:4d:9c:dc:47:2b:22 (RSA)
|   256 db:1f:db:14:06:57:3e:f6:e2:78:8e:1d:80:35:f4:bd (ECDSA)
|_  256 78:d5:25:0e:36:aa:6b:8a:06:dc:06:2f:e8:35:25:64 (ED25519)
80/tcp open  http
|_http-cors: HEAD GET POST PUT DELETE PATCH
| http-robots.txt: 1 disallowed entry 
|_/ftp
|_http-title: OWASP Juice Shop
| fingerprint-strings: 
|   FourOhFourRequest, GetRequest: 
|     HTTP/1.1 200 OK
|     Access-Control-Allow-Origin: *
|     X-Content-Type-Options: nosniff
|     X-Frame-Options: SAMEORIGIN
|     Feature-Policy: payment 'self'
|     X-Recruiting: /#/jobs
|     Accept-Ranges: bytes
|     Cache-Control: public, max-age=0
|     Last-Modified: Mon, 04 Sep 2023 16:38:42 GMT
|     ETag: W/"7c3-18a610f8837"
|     Content-Type: text/html; charset=UTF-8
|     Content-Length: 1987
|     Vary: Accept-Encoding
|     Date: Mon, 04 Sep 2023 16:58:00 GMT
|     Connection: close
|     <!--
|     Copyright (c) 2014-2023 Bjoern Kimminich & the OWASP Juice Shop contributors.
|     SPDX-License-Identifier: MIT
|     --><!DOCTYPE html><html lang="en"><head>
|     <meta charset="utf-8">
|     <title>OWASP Juice Shop</title>
|     <meta name="description" content="Probably the most modern and sophisticated insecure web application">
|     <meta name="viewport" content="width=device-width, initial-scale=1">
|     <link id="favicon" rel="icon" type="image/x-icon" href="asset
|   HTTPOptions, RTSPRequest: 
|     HTTP/1.1 204 No Content
|     Access-Control-Allow-Origin: *
|     Access-Control-Allow-Methods: GET,HEAD,PUT,PATCH,POST,DELETE
|     Vary: Access-Control-Request-Headers
|     Content-Length: 0
|     Date: Mon, 04 Sep 2023 16:58:00 GMT
|     Connection: close
|   X11Probe: 
|     HTTP/1.1 400 Bad Request
|_    Connection: close
1 service unrecognized despite returning data. If you know the service/version, please submit the following fingerprint at https://nmap.org/cgi-bin/submit.cgi?new-service :
SF-Port80-TCP:V=7.94%I=7%D=9/4%Time=64F60C97%P=x86_64-pc-linux-gnu%r(GetRe
SF:quest,979,"HTTP/1\.1\x20200\x20OK\r\nAccess-Control-Allow-Origin:\x20\*
SF:\r\nX-Content-Type-Options:\x20nosniff\r\nX-Frame-Options:\x20SAMEORIGI
SF:N\r\nFeature-Policy:\x20payment\x20'self'\r\nX-Recruiting:\x20/#/jobs\r
SF:\nAccept-Ranges:\x20bytes\r\nCache-Control:\x20public,\x20max-age=0\r\n
SF:Last-Modified:\x20Mon,\x2004\x20Sep\x202023\x2016:38:42\x20GMT\r\nETag:
SF:\x20W/\"7c3-18a610f8837\"\r\nContent-Type:\x20text/html;\x20charset=UTF
SF:-8\r\nContent-Length:\x201987\r\nVary:\x20Accept-Encoding\r\nDate:\x20M
SF:on,\x2004\x20Sep\x202023\x2016:58:00\x20GMT\r\nConnection:\x20close\r\n
SF:\r\n<!--\n\x20\x20~\x20Copyright\x20\(c\)\x202014-2023\x20Bjoern\x20Kim
SF:minich\x20&\x20the\x20OWASP\x20Juice\x20Shop\x20contributors\.\n\x20\x2
SF:0~\x20SPDX-License-Identifier:\x20MIT\n\x20\x20--><!DOCTYPE\x20html><ht
SF:ml\x20lang=\"en\"><head>\n\x20\x20<meta\x20charset=\"utf-8\">\n\x20\x20
SF:<title>OWASP\x20Juice\x20Shop</title>\n\x20\x20<meta\x20name=\"descript
SF:ion\"\x20content=\"Probably\x20the\x20most\x20modern\x20and\x20sophisti
SF:cated\x20insecure\x20web\x20application\">\n\x20\x20<meta\x20name=\"vie
SF:wport\"\x20content=\"width=device-width,\x20initial-scale=1\">\n\x20\x2
SF:0<link\x20id=\"favicon\"\x20rel=\"icon\"\x20type=\"image/x-icon\"\x20hr
SF:ef=\"asset")%r(HTTPOptions,EA,"HTTP/1\.1\x20204\x20No\x20Content\r\nAcc
SF:ess-Control-Allow-Origin:\x20\*\r\nAccess-Control-Allow-Methods:\x20GET
SF:,HEAD,PUT,PATCH,POST,DELETE\r\nVary:\x20Access-Control-Request-Headers\
SF:r\nContent-Length:\x200\r\nDate:\x20Mon,\x2004\x20Sep\x202023\x2016:58:
SF:00\x20GMT\r\nConnection:\x20close\r\n\r\n")%r(RTSPRequest,EA,"HTTP/1\.1
SF:\x20204\x20No\x20Content\r\nAccess-Control-Allow-Origin:\x20\*\r\nAcces
SF:s-Control-Allow-Methods:\x20GET,HEAD,PUT,PATCH,POST,DELETE\r\nVary:\x20
SF:Access-Control-Request-Headers\r\nContent-Length:\x200\r\nDate:\x20Mon,
SF:\x2004\x20Sep\x202023\x2016:58:00\x20GMT\r\nConnection:\x20close\r\n\r\
SF:n")%r(X11Probe,2F,"HTTP/1\.1\x20400\x20Bad\x20Request\r\nConnection:\x2
SF:0close\r\n\r\n")%r(FourOhFourRequest,979,"HTTP/1\.1\x20200\x20OK\r\nAcc
SF:ess-Control-Allow-Origin:\x20\*\r\nX-Content-Type-Options:\x20nosniff\r
SF:\nX-Frame-Options:\x20SAMEORIGIN\r\nFeature-Policy:\x20payment\x20'self
SF:'\r\nX-Recruiting:\x20/#/jobs\r\nAccept-Ranges:\x20bytes\r\nCache-Contr
SF:ol:\x20public,\x20max-age=0\r\nLast-Modified:\x20Mon,\x2004\x20Sep\x202
SF:023\x2016:38:42\x20GMT\r\nETag:\x20W/\"7c3-18a610f8837\"\r\nContent-Typ
SF:e:\x20text/html;\x20charset=UTF-8\r\nContent-Length:\x201987\r\nVary:\x
SF:20Accept-Encoding\r\nDate:\x20Mon,\x2004\x20Sep\x202023\x2016:58:00\x20
SF:GMT\r\nConnection:\x20close\r\n\r\n<!--\n\x20\x20~\x20Copyright\x20\(c\
SF:)\x202014-2023\x20Bjoern\x20Kimminich\x20&\x20the\x20OWASP\x20Juice\x20
SF:Shop\x20contributors\.\n\x20\x20~\x20SPDX-License-Identifier:\x20MIT\n\
SF:x20\x20--><!DOCTYPE\x20html><html\x20lang=\"en\"><head>\n\x20\x20<meta\
SF:x20charset=\"utf-8\">\n\x20\x20<title>OWASP\x20Juice\x20Shop</title>\n\
SF:x20\x20<meta\x20name=\"description\"\x20content=\"Probably\x20the\x20mo
SF:st\x20modern\x20and\x20sophisticated\x20insecure\x20web\x20application\
SF:">\n\x20\x20<meta\x20name=\"viewport\"\x20content=\"width=device-width,
SF:\x20initial-scale=1\">\n\x20\x20<link\x20id=\"favicon\"\x20rel=\"icon\"
SF:\x20type=\"image/x-icon\"\x20href=\"asset");
Service Info: OS: Linux; CPE: cpe:/o:linux:linux_kernel

Service detection performed. Please report any incorrect results at https://nmap.org/submit/ .
Nmap done: 1 IP address (1 host up) scanned in 13.46 seconds
                    
```
