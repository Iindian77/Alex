## Log File Analysis Script: A script to analyze log files for errors and warnings.
Lisa, a system administrator, needs to regularly check system log files for errors and warnings to ensure everything is running smoothly. Manually scanning through logs is tedious and prone to human error. To streamline this task, Lisa writes a script that searches log files for specific patterns, such as "ERROR" and "WARNING," making it easy to identify and address potential issues.


4. Log File Analysis Script
This script analyzes a log file for errors and warnings.

```
#!/bin/bash

# Define the log file to analyze
log_file="/var/log/syslog"

# Define patterns to search for
patterns=("ERROR" "WARNING")

# Loop through each pattern and search the log file
for pattern in "${patterns[@]}"; do
  echo "Searching for $pattern in $log_file..."
  
  # Use grep to search for the pattern in the log file
  grep -i $pattern $log_file
  
  # Check the exit status of the grep command
  if [ $? -eq 0 ]; then
    # If grep found matches, print a success message
    echo "Found $pattern in $log_file."
  else
    # If grep did not find matches, print a message
    echo "No $pattern found in $log_file."
  fi
done


```



```
May 24 14:01:00 server1 systemd[1]: Starting Daily apt download activities...
May 24 14:01:01 server1 systemd[1]: apt-daily.timer: Adding 7h 9min 20.491762s random time.
May 24 14:01:01 server1 systemd[1]: Started Daily apt download activities.
May 24 14:05:17 server1 kernel: [123456.789012] CPU0: Core temperature above threshold, cpu clock throttled (total events = 1)
May 24 14:05:17 server1 kernel: [123456.789015] CPU1: Package temperature above threshold, cpu clock throttled (total events = 1)
May 24 14:05:17 server1 kernel: [123456.789017] mce: [Hardware Error]: Machine check events logged
May 24 14:05:17 server1 kernel: [123456.789019] mce: [Hardware Error]: CPU 0: Machine Check: 0 Bank 4: f200000000000800
May 24 14:10:11 server1 kernel: [123789.123456] audit: type=1400 audit(1621878211.123:84): apparmor="ALLOWED" operation="open" profile="docker-default" name="/etc/hostname" pid=15345 comm="cat" requested_mask="r" denied_mask="r" fsuid=0 ouid=0
May 24 14:20:00 server1 systemd[1]: Starting Cleanup of Temporary Directories...
May 24 14:20:00 server1 systemd[1]: Started Cleanup of Temporary Directories.
May 24 14:30:45 server1 kernel: [124567.890123] EXT4-fs (sda1): mounted filesystem with ordered data mode. Opts: (null)
May 24 14:40:33 server1 kernel: [125678.123456] [UFW BLOCK] IN=eth0 OUT= MAC=00:11:22:33:44:55:66:77:88:99:aa:bb:cc:dd SRC=192.168.0.1 DST=192.168.0.2 LEN=52 TOS=0x00 PREC=0x00 TTL=64 ID=54321 DF PROTO=TCP SPT=12345 DPT=80 WINDOW=0 RES=0x00 RST URGP=0
May 24 14:50:12 server1 systemd[1]: Starting Daily Cleanup of Temporary Directories...
May 24 14:50:12 server1 systemd[1]: Started Daily Cleanup of Temporary Directories.
May 24 15:00:01 server1 kernel: [126789.123456] WARNING: at /build/linux-hwe-fqeqXG/linux-hwe-4.15.0/net/netfilter/nf_conntrack_core.c:1234
May 24 15:05:55 server1 kernel: [127456.789012] CPU0: Core temperature above threshold, cpu clock throttled (total events = 2)
May 24 15:05:55 server1 kernel: [127456.789015] CPU1: Package temperature above threshold, cpu clock throttled (total events = 2)
May 24 15:05:55 server1 kernel: [127456.789017] mce: [Hardware Error]: Machine check events logged
May 24 15:15:34 server1 kernel: [128789.123456] audit: type=1400 audit(1621880134.123:85): apparmor="DENIED" operation="open" profile="docker-default" name="/etc/shadow" pid=15346 comm="cat" requested_mask="r" denied_mask="r" fsuid=0 ouid=0
May 24 15:25:20 server1 systemd[1]: Stopping User Manager for UID 1000...

```