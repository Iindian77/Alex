#  Exercise 3
## Commands: pipeing, redirect,more,less,head,tail, command subsitution, read

## piping - command chaining
```
// create 100 files
[root@localhost pipeing]# touch Exercise_{1..100}.sh

//use | (pipe)
[root@localhost pipeing]# ls -lah | grep 2.*
-rw-r--r--.  1 root root    0 Dec  9 14:30 Exercise_12.sh
-rw-r--r--.  1 root root    0 Dec  9 14:30 Exercise_2.sh
-rw-r--r--.  1 root root    0 Dec  9 14:30 Exercise_20.sh


[root@localhost pipeing]# ls -lah | grep IP_10.10.4 | wc -l
11

root@55396d782e99:/# touch Exercise_{1..100}_$(date +"%Y%m%d").sh


 ```
 
 ## redirect
 The  "<" or ">" or ">>" or ">>>" symbol is used for input / output redirection. 

```
//output redirect - this will override the exsiting contetnt of the file
[root@localhost pipeing]# cat /var/log/httpd/access_log | grep png > /temp/access-log.txt

// output redirect and append to a file
[root@localhost pipeing]# cat /var/log/httpd/access_log | grep png >> /temp/access-log.txt


// input redirect
cat << EOF
first line
second line
EOF

cat << EOF
This is line 1.
This is line 2.
EOF

<: This symbol is used to redirect the input of a command from a file. For example, sort < file.txt will read the contents of the file.txt file and sort them.


<<: This symbol is used to redirect input from the shell, typically used to provide input to a command. For example, wc -l << EOF will run the wc -l command and use the text entered below it as its input until the EOF marker is reached.

<<<: This symbol is similar to <<, but it's used to provide a string as input to a command. For example, grep 'example' <<< 'this is an example text' will search for the word 'example' in the string 'this is an example text'.


//Redirection Operator: &>>
The operator "&>>" will append the standard output and the standard error to the specified file.

[root@localhost pipeing]# cat /var/log/httpd/access_log | kgrep png &>> /tmp/access-log.txt
[root@localhost pipeing]# cat /tmp/access-log.txt
-bash: kgrep: command not found



```

 ## more

```

```

## less

```

```

## head

```

```

## tail

```
//tail

//tail -f

tail -F

tail -100F

```


## command subsitution
```
//this allows us take the output of one command and store into variable
[root@localhost pipeing]# file=`ls`
[root@localhost pipeing]# echo $file
IP_10.10.1.1 IP_10.10.10.1 IP_10.10.11.1 IP_10.10.12.1 IP_10.10.13.1 IP_10.10.14.1 IP_10.10.15.1 IP_10.10.16.1 IP_10.10.17.1 IP_10.10.18.1 IP_10.10.19.1 IP_10.10.2.1 IP_10.10.20.1 IP_10.10.21.1 IP_10.10.22.1 IP_10.10.23.1 IP_10.10.24.1 IP_10.10.25.1 IP_10.10.26.1 IP_10.10.27.1 IP_10.10.28.1 IP_10.10.29.1 IP_10.10.3.1 IP_10.10.30.1 IP_10.10.31.1 IP_10.10.32.1 IP_10.10.33.1 IP_10.10.34.1 IP_10.10.35.1 IP_10.10.36.1 IP_10.10.37.1 IP_10.10.38.1 IP_10.10.39.1 IP_10.10.4.1 IP_10.10.40.1 IP_10.10.41.1 IP_10.10.42.1 IP_10.10.43.1 IP_10.10.44.1 IP_10.10.45.1 IP_10.10.46.1 IP_10.10.47.1 IP_10.10.48.1 IP_10.10.49.1 IP_10.10.5.1 IP_10.10.50.1 IP_10.10.6.1 IP_10.10.7.1 IP_10.10.8.1 IP_10.10.9.1 test1.txt



[root@localhost pipeing]# uptime=`uptime`
[root@localhost pipeing]# echo $uptime
15:15:56 up 13 days, 14:52, 2 users, load average: 0.00, 0.01, 0.05


[root@localhost pipeing]# currentRam=`free -m  | grep Mem | awk '{print $4}'`
[root@localhost pipeing]# echo $currentRam
156


// another option 
[root@localhost pipeing]# currentRam=$(free -m  | grep Mem | awk '{print $4}')
[root@localhost pipeing]# echo $currentRam
156
```

## read command
```
[root@localhost pipeing]# cat test1.txt
#!/bin/bash
echo "Please enter your email address: "
read email
echo "Your email is: $email"

read -p 'Please enter your usernames: ' user
echo "Your user is: $user"

read -sp 'Please enter your password: ' pass
echo "Your pass is: $pass"

[root@localhost pipeing]# ./test1.txt
Please enter your email address:
matar1@gmail.com
Your email is: matar1@gmail.com
Please enter your usernames: matar1
Your user is: matar1
Please enter your password: Your pass is: blabla

```

