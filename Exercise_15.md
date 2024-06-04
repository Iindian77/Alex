#  Exercise 15
## Commands: BASH

## script to check if process is running andstart if not
```
#! /bin/bash
ls /var/run httpd/httpd.pid   #"/var/run" directory is often used by system daemons to store runtime information such as process IDs (PIDs)
if [ $? -eg 0 ]    #checks the exit status of the previously executed command
then 
echo "Httpd process is running.
else 
echo "Httpd process is NOT Running.
echo "Starting the process.
systemctl start httpd 
if [ $? -eq 0 ] 
then 
echo "Process started successfully.
else
echo "Process Starting Failed, contact the admin."
fi
fi
 ```