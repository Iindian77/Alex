#  Exercise 9
## Commands: uname, df,du,top , ps , free, ifconfig , lscpu,netstat,/proc/cpuinfo

### uname

The uname command is used to print system information about the operating system and its kernel.

Example:
```
$ uname -a
Linux mycomputer 5.13.0-19-generic #19-Ubuntu SMP Fri Oct 15 20:09:12 UTC 2021 x86_64 x86_64 x86_64 GNU/Linux
```

### df
The df command is used to display information about the disk space usage on file systems.

Example:
```
$ df -h
Filesystem      Size  Used Avail Use% Mounted on
/dev/sda1        20G  8.9G  9.7G  48% /
/dev/sda2        20G  4.0G   15G  22% /home
```


### du

The du command is used to estimate file space usage.

Example:
```
$ du -sh /home/user
4.0G  /home/user
```


### top

The top command is used to display real-time information about the system's resource usage.

Example:
```
$ top
This command will display a continuously updating list of the system's resource usage statistics, such as CPU usage and memory usage.
top - 19:40:04 up  7:11,  4 users,  load average: 0.00, 0.01, 0.05
Tasks: 104 total,   1 running, 103 sleeping,   0 stopped,   0 zombie
%Cpu(s):  0.0 us,  0.3 sy,  0.0 ni, 99.7 id,  0.0 wa,  0.0 hi,  0.0 si,  0.0 st
KiB Mem :   995676 total,   146452 free,   239020 used,   610204 buff/cache
KiB Swap:  2097148 total,  2097148 free,        0 used.   581472 avail Mem

   PID USER      PR  NI    VIRT    RES    SHR S %CPU %MEM     TIME+ COMMAND
 26980 root      20   0  161968   2176   1532 R  0.3  0.2   0:00.03 top
     1 root      20   0  128136   6748   4168 S  0.0  0.7   0:05.07 systemd
     2 root      20   0       0      0      0 S  0.0  0.0   0:00.00 kthreadd
     4 root       0 -20       0      0      0 S  0.0  0.0   0:00.00 kworker/0:0H
     5 root      20   0       0      0      0 S  0.0  0.0   0:01.19 kworker/u256:0
     6 root      20   0       0      0      0 S  0.0  0.0   0:00.65 ksoftirqd/0
     7 root      rt   0       0      0      0 S  0.0  0.0   0:00.00 migration/0
     8 root      20   0       0      0      0 S  0.0  0.0   0:00.00 rcu_bh
     9 root      20   0       0      0      0 S  0.0  0.0   0:01.03 rcu_sched
    10 root       0 -20       0      0      0 S  0.0  0.0   0:00.00 lru-add-drain
    11 root      rt   0       0      0      0 S  0.0  0.0   0:00.41 watchdog/0

```

### create synthetic load on the cpu
Example:
```
sudo yum install stress
stress --cpu 4 --timeout 60s &

```


### ps
The ps command is used to display information about the currently running processes.

Example:
```
$ ps -ef
UID        PID  PPID  C STIME TTY          TIME CMD
root         1     0  0 Nov08 ?        00:00:01 /sbin/init
root         2     0  0 Nov08 ?        00:00:00 [kthreadd]
root         3     2  0 Nov08 ?        00:00:00 [rcu_gp]
...
```

### free

The free command is used to display information about the system's memory usage.

Example:
```
$ free -h
              total        used        free      shared  buff/cache   available
Mem:            31G        6.1G         15G        3.3M         10G         24G
Swap:            0B          0B          0B
```



### ifconfig

The ifconfig command is used to display network interface information.

Example:
```
$ ifconfig
eth0: flags=4163<UP,BROADCAST,RUNNING,MULTICAST>  mtu 1500
        inet 192.168.1.100  netmask 255.255.255.0  broadcast 192.168.1.255
        inet6 fe80::a00:27ff:fef4:8c2d  prefixlen 64  scopeid 0x20<link>
        ether 08:00:27:f4:8c:2d  txqueuelen 1000  (Ethernet)
        RX packets 194688  bytes 241808180 (230.4 MiB)
        RX errors 0  dropped 0  overruns 0  frame 0
        TX packets 233123  bytes 33853823 (32.3 MiB)
        TX errors 0  dropped 0 overruns 0  carrier 0  collisions 0
```


### lscpu

The lscpu command is used to display information about the system's CPU architecture.

Example:
```
$ lscpu
Architecture:          x86_64
CPU op-mode(s):       

```


### netstat

The netstat command is used to display information about the network connections on a system.

Example:
```
$ netstat -tulpn
Active Internet connections (only servers)
Proto Recv-Q Send-Q Local Address           Foreign Address         State       PID/Program name
tcp        0      0 0.0.0.0:22              0.0.0.0:*               LISTEN      1053/sshd       
tcp6       0      0 :::22                   :::*                    LISTEN      1053/sshd       
udp        0      0 0.0.0.0:68              0.0.0.0:*                           968/dhclient    
udp6       0      0 :::58092                :::*                                968/dhclient    
```

### cat /proc/cpuinfo

The /proc/cpuinfo file provides detailed information about the system's CPU.

Example:
```
$ cat /proc/cpuinfo
processor       : 0
vendor_id       : GenuineIntel
cpu family      : 6
model           : 58
model name      : Intel(R) Core(TM) i5-3570K CPU @ 3.40GHz
...

```

### vmstat

vmstat is used to monitor and report virtual memory, CPU, and I/O statistics of a Linux system.

Example:
```
sudo yum install procps-ng
[root@srv1 ~]# vmstat 1 5
procs -----------memory---------- ---swap-- -----io---- -system-- ------cpu-----
 r  b   swpd   free   buff  cache   si   so    bi    bo   in   cs us sy id wa st
 2  0      0 675616   2108 112556    0    0    47     6   45  121  0  0 99  0  0
 0  0      0 675616   2108 112556    0    0     0     0   24   31  0  0 100  0  0
 0  0      0 675616   2108 112556    0    0     0     0   15   14  0  0 100  0  0
 0  0      0 675616   2108 112556    0    0     0     0   17   21  0  0 100  0  0
 0  0      0 676524   2108 112556    0    0     0     4   64   51  0  1 99  0  0
```


### iotop
iotop is used to monitor and analyze I/O usage by processes in real-time, helping identify disk I/O bottlenecks and resource-intensive processes.

Example:
```
sudo yum install iotop

iotop
Total DISK READ :	0.00 B/s | Total DISK WRITE :       0.00 B/s
Actual DISK READ:	0.00 B/s | Actual DISK WRITE:       0.00 B/s

```
