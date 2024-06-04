#  Exercise 5
## Commands:  traceroute, ping, mtr, ip addr , curl, wget

### traceroute

The traceroute command is used to trace the route that packets take between a local host and a remote destination. It shows the IP addresses and round-trip times for each hop along the way.

Example:
```
$ traceroute example.com
traceroute to example.com (93.184.216.34), 30 hops max, 60 byte packets
 1  192.168.1.1 (192.168.1.1)  1.024 ms  1.405 ms  1.687 ms
 2  10.5.5.1 (10.5.5.1)  5.325 ms  5.401 ms  5.527 ms
 3  207.225.29.81 (207.225.29.81)  6.794 ms  6.909 ms  7.081 ms
 4  207.225.27.53 (207.225.27.53)  6.307 ms  6.405 ms  6.508 ms
 5  67.231.222.14 (67.231.222.14)  6.557 ms  6.683 ms  6.801 ms
 ...
```

### ping

The ping command is used to test the reachability of a remote host by sending ICMP echo request packets and waiting for ICMP echo reply packets.

Example:
```
$ ping example.com
PING example.com (93.184.216.34) 56(84) bytes of data.
64 bytes from 93.184.216.34 (93.184.216.34): icmp_seq=1 ttl=57 time=8.43 ms
64 bytes from 93.184.216.34 (93.184.216.34): icmp_seq=2 ttl=57 time=8.66 ms
64 bytes from 93.184.216.34 (93.184.216.34): icmp_seq=3 ttl=57 time=8.52 ms
 ...
```

### mtr

The mtr command (short for My traceroute) combines the functionality of ping and traceroute into a single tool. It continuously pings a remote host and displays the network path and round-trip times for each hop.

Example:
```
$ mtr example.com
                                    Packets               Pings
 Host                             Loss%   Snt   Last   Avg  Best  Wrst StDev
 1. 192.168.1.1                    0.0%    61    1.0   1.4   0.9  11.4   1.4
 2. 10.5.5.1                       0.0%    61    6.0   5.4   4.6  21.8   3.3
 3. 207.225.29.81                  0.0%    61    6.8   6.7   6.1   7.5   0.2
 4. 207.225.27.53                  0.0%    61    6.2   6.3   5.9   6.9   0.3
 5. 67.231.222.14                  0.0%    61    6.7   6.8   6.2 
```

### ip addr

The ip addr command is used to show the IP addresses assigned to the network interfaces on a host.

Example:
```
$ ip addr
1: lo: <LOOPBACK,UP,LOWER_UP> mtu 65536 qdisc noqueue state UNKNOWN group default qlen 1000
   inet 127.0.0.1/8 scope host lo
      valid_lft forever preferred_lft forever
2: eno1: <BROADCAST,MULTICAST,UP,LOWER_UP> mtu 1500 qdisc mq state UP group default qlen 1000
   inet 192.168.1.100/24 brd 192.168.1.255 scope global dynamic eno1
      valid_lft 82984sec preferred_lft 82984sec
...

```

### curl

The curl command is used to transfer data from or to a server using one of the supported protocols (HTTP, FTP, etc.). It can be used to download or upload files, or to interact with web services.

Example:
```
$ curl https://example.com
<!doctype html>
<html>
<head>
    <title>Example Domain</title>
...
```


### wget

The wget command is used to retrieve files from the web using HTTP, HTTPS, or FTP protocols. It can be used to download entire websites, recursive downloads, or single files.

Example:
```
$ wget https://example.com
--2023-04-02 11:37:23--  https://example.com/
Resolving example.com... 93.184.216.34, 2606:2800:220:1:248:1893:25c8:1946
Connecting to example.com|93.184.216.34|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 1270 (1.2K) [text/html]
Saving to: ‘index.html’

index.html          100%[===================>]   1.24K  --.-KB/s    in 0s

2023-04-02 11:37:23 (15.5 MB/s) - ‘index.html’ saved [1270/1270]
```