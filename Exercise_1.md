#  Exercise 1
## Commands: man,whatis ls,ls-la,ls -lah, ls -lai, cd, pwd , date  , cal (calender), cal 2021 , bc (basic calc),w,who


## commands manual
```
 man pwd
 ```
 
 ## List files
```
[root@dba048073888 log]# ls -la
total 16
drwxr-xr-x  4 root root 4096 Sep 15  2021 .
drwxr-xr-x 20 root root 4096 Sep 15  2021 ..
drwxr-xr-x  2 root root 4096 Sep 15  2021 anaconda
-rw-rw----  1 root utmp    0 Sep 15  2021 btmp
-rw-rw-r--  1 root utmp    0 Sep 15  2021 lastlog
drwx------  2 root root 4096 Sep 15  2021 private
-rw-rw-r--  1 root utmp    0 Sep 15  2021 wtmp

[root@dba048073888 log]#  ls -lah
total 16K
drwxr-xr-x  4 root root 4.0K Sep 15  2021 .
drwxr-xr-x 20 root root 4.0K Sep 15  2021 ..
drwxr-xr-x  2 root root 4.0K Sep 15  2021 anaconda
-rw-rw----  1 root utmp    0 Sep 15  2021 btmp
-rw-rw-r--  1 root utmp    0 Sep 15  2021 lastlog
drwx------  2 root root 4.0K Sep 15  2021 private
-rw-rw-r--  1 root utmp    0 Sep 15  2021 wtmp

## Check also the iNode number of each file
[root@dba048073888 log]#  ls -lai
total 16
266553 drwxr-xr-x  4 root root 4096 Sep 15  2021 .
266538 drwxr-xr-x 20 root root 4096 Sep 15  2021 ..
400301 drwxr-xr-x  2 root root 4096 Sep 15  2021 anaconda
266554 -rw-rw----  1 root utmp    0 Sep 15  2021 btmp
266555 -rw-rw-r--  1 root utmp    0 Sep 15  2021 lastlog
400315 drwx------  2 root root 4096 Sep 15  2021 private
266556 -rw-rw-r--  1 root utmp    0 Sep 15  2021 wtmp

 ```
 
 ## check out calander
 ```
 cal
    November 2022
Su Mo Tu We Th Fr Sa
       1  2  3  4  5
 6  7  8  9 10 11 12
13 14 15 16 17 18 19
20 21 22 23 24 25 26
27 28 29 30

cal 2022
                               2022

       January               February                 March
Su Mo Tu We Th Fr Sa   Su Mo Tu We Th Fr Sa   Su Mo Tu We Th Fr Sa
                   1          1  2  3  4  5          1  2  3  4  5
 2  3  4  5  6  7  8    6  7  8  9 10 11 12    6  7  8  9 10 11 12
 9 10 11 12 13 14 15   13 14 15 16 17 18 19   13 14 15 16 17 18 19
16 17 18 19 20 21 22   20 21 22 23 24 25 26   20 21 22 23 24 25 26
23 24 25 26 27 28 29   27 28                  27 28 29 30 31
30 31
 ```


## change directory
```
cd /var/log/
cd ..
cd ../..
cd
```

## print working directory (current location in file system
```
[root@dba048073888 log]# cd /var/log
[root@dba048073888 log]# pwd
/var/log
```

## Check out system date
```
[root@dba048073888 log]# date
Sat Nov  5 17:58:11 UTC 2022
```

 
## Check who connect to our server
```
w
19:59  up 2 days, 10:27, 4 users, load averages: 1.27 1.45 1.50
USER     TTY      FROM              LOGIN@  IDLE WHAT
web      console  -                Thu09   2days -
web      s000     -                17:32      24 /usr/local/bin/com.docker.cli exec -it 83af7b6c1bf4 /bin/bash
web      s001     -                18:16       - w
web      s002     -                19:41      16 -zsh M_S      ��    /bin/zsh

who
web              console      Nov  3 09:33
web              ttys000      Nov  5 17:32
web              ttys001      Nov  5 18:16
web              ttys002      Nov  5 19:41
```

## Using basic calculator

```
echo "20*3" | bc                                                                                                     ✔  21:11:01
60
```
