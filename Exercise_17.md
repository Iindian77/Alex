# Story: Network Engineering Script Requests
### As a network engineer, you often need to automate various tasks to streamline your workflow. Here are five useful scripts that can help you with common network engineering tasks:

## Ping Test Script: A script to ping multiple hosts and report their status.
1. Ping Test Script
This script pings a list of hosts and reports whether each host is reachable.

```
#!/bin/bash

# Define a list of hosts to ping
hosts=("192.168.1.1" "192.168.1.2" "google.com")

# Loop through each host in the list
for host in "${hosts[@]}"; do
  # Ping the host with a timeout of 1 second and count of 1 ping
  ping -c 1 -W 1 $host > /dev/null 2>&1
  
  # Check the exit status of the ping command
  if [ $? -eq 0 ]; then
    # If ping was successful, print that the host is reachable
    echo "$host is reachable."
  else
    # If ping failed, print that the host is not reachable
    echo "$host is not reachable."
  fi
done


```

