## Bandwidth Monitoring Script: A script to monitor network bandwidth usage.
Samantha, another network engineer, is tasked with monitoring network bandwidth usage to ensure optimal performance. With multiple network interfaces on the servers she manages, Samantha needs a way to continuously monitor traffic. She writes a script that uses ifstat to check the bandwidth usage on a specific interface, allowing her to quickly detect any unusual spikes or drops in network activity.



2. Bandwidth Monitoring Script
This script monitors network bandwidth usage using the ifstat command.

```
#!/bin/bash

# Check if ifstat is installed
if ! command -v ifstat &> /dev/null; then
  echo "ifstat command is required but not installed. Please install ifstat."
  exit 1
fi

# Monitor bandwidth usage on interface eth0 every second
echo "Monitoring bandwidth usage on interface eth0..."
ifstat -i eth0 1 10

```