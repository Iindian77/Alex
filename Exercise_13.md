#  Exercise 13
## Commands: Lab - Linux Review - BASH scripting



General guidelines: 
This lab requier you to create file contain ip,name 
for each ip in the file you will need to make ssh and retrive the hostname

----------------------------------------------------------------------------------------------------------------------------------------
### prerequsit:
intstall sshpass
```
yum install -y sshpass
```

Create file contain list of devices:
Example for the list:
```
cat /home/matarb/nameOfYourFile.txt
127.0.0.1,blabal1
127.0.0.1,blabla2
127.0.0.1,blabla3
```

Write a bash script connect each device using ssh and return the device hostname

```
#!/bin/bash

# Set the filename of the input file
input_file="ip_hostnames.txt"

# Set the filename of the temporary file to store the results
temp_file="results.txt"

# Clear the temporary file
> "$temp_file"

# Loop through each line in the input file
while IFS="," read -r ip hostname || [[ -n "$ip" ]]; do
    # SSH login using sshpass and ssh
    output=$(sshpass -p "your_password" ssh -o "ConnectTimeout=7" -o "UserKnownHostsFile=/dev/null" -o "StrictHostKeyChecking=no" "root@$ip" 2>/dev/null << EOF
        hostname
        who
EOF
    )

    # Append the hostname and logged-in user to the temporary file
    echo "IP: $ip" >> "$temp_file"
    echo "Hostname: $hostname" >> "$temp_file"
    echo "$output" >> "$temp_file"
    echo >> "$temp_file"

done < "$input_file"

# Print the contents of the temporary file
cat "$temp_file"

# Remove the temporary file
rm "$temp_file"

```


