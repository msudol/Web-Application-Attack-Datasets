# Web-Application-Attack-Datasets

Combined datasets of ECML/PKDD 2007 and CSIC 2010

## Info

Web application attack datasets for machine learning are actually fairly sparse, one would assume that large, modern collections of parsed valid and anomalous traffic to website and web applications from http logs would be everywhere, but it's not the case.  My assumption is most people and companies that endeavor to collect this information decide to keep it under wraps to source their own engines and sell a product. 

Through my research I've been able to find a couple older datasets, the ECML/PKDD 2007 Challenge and the CSIC 2010 Dataset. More details on these can be found in the OriginalDataSets folder.

## Data Conversion

The data provided needs to be of value to machine learning applications, in this case Weka. So the datasets need to be converted to .arff format.  Additionally, parts of the data would need to be parsed out, and example tuple from the original dataset for CSIC anonalous traffic looks like this.

```
POST http://localhost:8080/tienda1/publico/anadir.jsp HTTP/1.1
User-Agent: Mozilla/5.0 (compatible; Konqueror/3.5; Linux) KHTML/3.5.8 (like Gecko)
Pragma: no-cache
Cache-control: no-cache
Accept: text/xml,application/xml,application/xhtml+xml,text/html;q=0.9,text/plain;q=0.8,image/png,*/*;q=0.5
Accept-Encoding: x-gzip, x-deflate, gzip, deflate
Accept-Charset: utf-8, utf-8;q=0.5, *;q=0.5
Accept-Language: en
Host: localhost:8080
Cookie: JSESSIONID=AE29AEEBDE479D5E1A18B4108C8E3CE0
Content-Type: application/x-www-form-urlencoded
Connection: close
Content-Length: 146

id=2&nombre=Jam%F3n+Ib%E9rico&precio=85&cantidad=%27%3B+DROP+TABLE+usuarios%3B+SELECT+*+FROM+datos+WHERE+nombre+LIKE+%27%25&B1=A%F1adir+al+carrito

```

Data from ECML has a defined class, but is even more complex

```
End - Id: 11407
Start - Id: 5438
class: Valid
PUT /gtm1ca4udeicv6tia.cfm? HTTP/1.1
Content-Length: 90
Content-Language: oe1,b,T1r
Content-Encoding: gzip
Content-Location: http://Odpuslu.com/iptp/44kr.nsf
Content-MD5: OXNlc0huc3NoaG10dGlidA==
Content-Type: application/x-www-form-urlencoded
Expires: Mon, 25 May 09 09:19:27 UTC
Last-Modified: Thu, 10 Aug 06 19:22:54 UTC
Host: www.ZtaSt.ch:80
Connection: keep-alive
Accept: application/*, application/postscript, text/*
Accept-Charset: *;q=0.8
Accept-Encoding: 
Accept-Language: Rt-Cgeree
Cache-Control: only-if-cached
Client-ip: 9.201.23.222
Cookie: ci1rr0nsd=65;1ttictrkduPi8o=Jtsongjfweas;eIeCPA4v7lFB=i=a;zperl31Um8=27892;uona5nriGooie=%linktemocha<e<cmhtacces<nne wxh];hbPdy4on=evala7
Cookie2: $Version="054"
Date: Mon, 23 Jul 07 12:46:28 UTC
ETag: "GdhQ7zVO5_wsjp1g"
Expect: tbt2=enhoqa
From: duemse@aiti.it
If-Modified-Since: Wed, 23 Sep 09 22:31:51 UTC
If-Unmodified-Since: Sun, 07 Oct 07 06:40:21 GMT
If-Match: "ercKWFyC73sZFhQ"
If-None-Match: "g4CRY-w_DxM-StbbM"
If-Range: Mon, 07 Dec 09 15:41:40 UTC
Max-Forwards: 721
MIME-Version: 8.8
Pragma: rehr='redi'
Proxy-Authorization: Basic SWF6OWNyOmNlZk50
Authorization: Digest nonce
Range: 84-,-306723
Referer: http://btyeqane.net/ehhnetse/pyn3nr/mAucetn/vtf2.tiff
TE: trailers,trailers
Trailer: User-Agent
User-Agent: Mozilla/9.6 (compatible; MSIE 3.6; Linux i586; istyf; tieture9)
UA-CPU: MIPS
UA-Disp: 329,3885,32
UA-OS: Win95
UA-Color: color16
UA-Pixels: 375x4615
Via: HTTP/5.7 www.ZEio6.png
Transfer-Encoding: compress
Upgrade: RahN/5.1, tLrem/6.4, ett/3.2, iub/6.4, gni/3.3
Warning: 648 www.miheezn.jpeg "dtnwn8Ibraihenesvqow" "Wed, 13 Jul 05 15:04:04 GMT"
X-Forwarded-For: 180.40.114.160
X-Serial-Number: 20359821901
----: --------------------------------------
~~~~~: ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

7aafaahs0l1ed3s=oudHcrssimsIH&5cGcmdGmqperlAV3=otincludeunion9rr&eih=cFW&FmYpopt96DWedN=35

```

One advantage of this data is that it contains both GET requests with the query data, as well as POST requests with the request data.

There are however several disadvantages to this data. The CSIC dataset is entirely generated from a lab environment, so HOST information is all the same. CSIC also does not have date and time information, so the correlation between attempts over time can't be assessed for brute force or DOS attempts.

