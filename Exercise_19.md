## Network Configuration Backup Script: A script to backup router configurations.
Mark, a network administrator, manages several routers across the corporate network. Regular backups of router configurations are essential to prevent data loss and ensure quick recovery in case of failures. Mark writes a script to automate the backup process by logging into each router and saving the configuration files. This ensures that he always has the latest configurations stored safely.

3. Network Configuration Backup Script
This script logs into a list of routers via SSH and backs up their configurations.


```
#!/bin/bash

# Define a list of router IP addresses
routers=("172.20.10.2" "172.20.10.2")

# Define SSH user
user="matar"

# Define backup directory
backup_dir="/tmp/backup"

# Create backup directory if it doesn't exist
mkdir -p $backup_dir

# Loop through each router in the list
for router in "${routers[@]}"; do
  # Use SSH to execute the 'show running-config' command on the router
  ssh -o KexAlgorithms=+diffie-hellman-group14-sha1  -o HostKeyAlgorithms=+ssh-rsa -o PubkeyAcceptedAlgorithms=+ssh-rsa $user@$router "show running-config" > $backup_dir/$router-config-$(date +%F).txt
  
  # Check the exit status of the SSH command
  if [ $? -eq 0 ]; then
    # If SSH command was successful, print a success message
    echo "Configuration backup for $router completed successfully."
  else
    # If SSH command failed, print a failure message
    echo "Configuration backup for $router failed."
  fi
done


```


```
ssh matar@172.20.10.2 -o KexAlgorithms=+diffie-hellman-group14-sha1  -o HostKeyAlgorithms=+ssh-rsa -o PubkeyAcceptedAlgorithms=+ssh-rsa

```