#  Exercise 6
## Commands: wc,grep,Regular expression,sed, awk


### Regular expression

```
Review Regular Expressions
In this part, you use the grep command to review how you can use regular expressions for filtering.
Note: Your output may differ than the output shown below as the state of the VM is based on the most recent iteration that you downloaded as well as any changes you may have made. However, you should get some output from the passwd file but your highlighted output will differ.
a.	Use the grep command to filter the contents of the passwd file to display the line from the passwd file containing centos. Notice that the two instances of centos are highlighted. Also notice that the grep command is case-sensitive. The instance of centos is not highlighted.
centos@centos-lab:~$ grep centos /etc/passwd
centos:x:900:900:centos,,,:/home/centos:/bin/bash
centos@centos-lab:~$


b.	Use the grep command to show how many times root appears in the passwd file. Notice that all three instances of root are highlighted.
centos@centos-lab:~$ grep root /etc/passwd
root:x:0:0:root:/root:/bin/bash
centos@centos-lab:~$



c.	Use the grep command with the anchor character ^ to find the word, but only at the beginning of the line. Notice that only the word at the beginning of the line is highlighted.
centos@centos-lab:~$ grep '^root' /etc/passwd
root:x:0:0:root:/root:/bin/bash
centos@centos-lab:~$



d.	Use the grep command with the anchor character $ to find a word at the end of a line.
centos@centos-lab:~$ grep 'false$' /etc/passwd
tss:x:106:114:TPM software stack,,,:/var/lib/tpm:/bin/false
lightdm:x:107:117:Light Display Manager:/var/lib/lightdm:/bin/false
hplip:x:115:7:HPLIP system user,,,:/run/hplip:/bin/false
centos@centos-lab:~$



e.	Use the grep command with the anchor character . to match specific length words with different letters in them. Notice that not only is daem highlighted, but also dnsm is highlighted.
centos@centos-lab:~$ grep 'd..m' /etc/passwd
daemon:x:1:1:daemon:/usr/sbin:/usr/sbin/nologin
dnsmasq:x:109:65534:dnsmasq,,,:/var/lib/misc:/usr/sbin/nologin
avahi-autoipd:x:110:121:Avahi autoip daemon,,,:/var/lib/avahi-autoipd:/usr/sbin/nologin
usbmux:x:111:46:usbmux daemon,,,:/var/lib/usbmux:/usr/sbin/nologin
avahi:x:113:122:Avahi mDNS daemon,,,:/var/run/avahi-daemon:/usr/sbin/nologin
colord:x:116:125:colord colour management daemon,,,:/var/lib/colord:/usr/sbin/nologin
pulse:x:117:126:PulseAudio daemon,,,:/var/run/pulse:/usr/sbin/nologin
centos@centos-lab:~$



f.	Use the grep command to find lines where only the numbers 8 or 9 are present. Notice that only the lines containing an 8, a 9, or both are returned.
centos@centos-lab:~$ grep '[8-9]' /etc/passwd
mail:x:8:8:mail:/var/mail:/usr/sbin/nologin
news:x:9:9:news:/var/spool/news:/usr/sbin/nologin
list:x:38:38:Mailing List Manager:/var/list:/usr/sbin/nologin
irc:x:39:39:ircd:/var/run/ircd:/usr/sbin/nologin
uuidd:x:103:109::/run/uuidd:/usr/sbin/nologin
centos:x:900:900:centos,,,:/home/centos:/bin/bash
systemd-network:x:999:999:systemd Network Management:/:/usr/sbin/nologin
systemd-resolve:x:998:998:systemd Resolver:/:/usr/sbin/nologin
systemd-timesync:x:997:997:systemd Time Synchronization:/:/usr/sbin/nologin
systemd-coredump:x:996:996:systemd Core Dumper:/:/usr/sbin/nologin
rtkit:x:108:119:RealtimeKit,,,:/proc:/usr/sbin/nologin
dnsmasq:x:109:65534:dnsmasq,,,:/var/lib/misc:/usr/sbin/nologin
centos@centos-lab:~$




g.	Use the grep command to find literal characters. Notice that only the lines containing a comma are returned.
centos@centos-lab:~$ grep '[,]' /etc/passwd
centos:x:900:900:centos,,,:/home/centos:/bin/bash
tss:x:106:114:TPM software stack,,,:/var/lib/tpm:/bin/false
rtkit:x:108:119:RealtimeKit,,,:/proc:/usr/sbin/nologin
dnsmasq:x:109:65534:dnsmasq,,,:/var/lib/misc:/usr/sbin/nologin
avahi-autoipd:x:110:121:Avahi autoip daemon,,,:/var/lib/avahi-autoipd:/usr/sbin/nologin
usbmux:x:111:46:usbmux daemon,,,:/var/lib/usbmux:/usr/sbin/nologin
kernoops:x:112:65534:Kernel Oops Tracking Daemon,,,:/:/usr/sbin/nologin
avahi:x:113:122:Avahi mDNS daemon,,,:/var/run/avahi-daemon:/usr/sbin/nologin
hplip:x:115:7:HPLIP system user,,,:/run/hplip:/bin/false
colord:x:116:125:colord colour management daemon,,,:/var/lib/colord:/usr/sbin/nologin
pulse:x:117:126:PulseAudio daemon,,,:/var/run/pulse:/usr/sbin/nologin
centos@centos-lab:~$



h.	Use the grep command to find occurrences of zero or more of the pattern preceding it. Notice that only the lines with either new and ne are returned.
centos@centos-lab:~$ grep 'new*' /etc/passwd
news:x:9:9:news:/var/spool/news:/usr/sbin/nologin
nobody:x:65534:65534:nobody:/nonexistent:/usr/sbin/nologin
messagebus:x:100:103::/nonexistent:/usr/sbin/nologin
_apt:x:102:65534::/nonexistent:/usr/sbin/nologin
tcpdump:x:104:110::/nonexistent:/usr/sbin/nologin
systemd-network:x:999:999:systemd Network Management:/:/usr/sbin/nologin
kernoops:x:112:65534:Kernel Oops Tracking Daemon,,,:/:/usr/sbin/nologin
saned:x:114:124::/var/lib/saned:/usr/sbin/nologin
centos@centos-lab:~$
-------------------------

```



### wc

The wc command is used to count the number of lines, words, and characters in a file or set of files.

Example:
```
$ wc file.txt
  10  25 150 file.txt
```

### grep

The grep command is used to search for patterns in text files or output. It can be used to search for specific words or patterns in a file or output.

Example:
```
$ grep 'error' file.txt
ERROR: Failed to open file.
```


Regular expression

Regular expressions (regex) are patterns used to match and manipulate text. They can be used with various command-line tools like grep, sed, and awk.

Example:
```
$ sed 's/hello/world/g' file.txt
world, world
goodbye, world
```

### sed

The sed command is used to perform text transformations on an input stream (a file or output). It can be used to substitute text, delete lines, insert text, and more.

Example:

```
$ sed 's/hello/world/g' file.txt
world, world
goodbye, world
```

### Replacing Text in a File:
Input text (file.txt):
Hello, world!


sed command:
```
sed 's/world/Universe/' file.txt
Output:


Hello, Universe!
```
Explanation: The sed command substitutes (s/) the word "world" with "Universe" in the input text.



### Deleting Lines that Match a Pattern:
Input text (file.txt):
Hello, world!
Goodbye, world!

```
sed command:
sed '/world/d' file.txt
Output:
Goodbye, world!
```
Explanation: The sed command deletes (d) the lines that contain the pattern "world" in the input text.



Appending Text to the End of Each Line:
Input text (file.txt):

Hello
Goodbye
```
sed command:
sed 's/$/, world!/' file.txt
Output:
Hello, world!
Goodbye, world!
```
Explanation: The sed command appends (using $) the text ", world!" to the end of each line in the input text.


Extracting Specific Columns:
Input text (file.txt):
John Doe,35,Male
Jane Smith,28,Female
```
sed command:
sed 's/\([^,]*\),\([^,]*\),\([^,]*\)/\1 \3/' file.txt
Output:
John Doe Male
Jane Smith Female

```
Explanation: The sed command captures specific columns using regular expressions and replaces the line with the captured columns separated by a space.



----------------------------------------------------------------------------------



### awk

The awk command is a powerful text processing tool that can be used to manipulate and process data in text files. It can be used to search for patterns, manipulate fields, and perform calculations.

Example:

```
$ awk '{print $1}' file.txt
hello,
goodbye,

Print the first column of a file:
awk '{ print $1 }' file.txt

Print the second column of a file where the first column equals a certain value:
awk '$1 == "value" { print $2 }' file.txt

Print the sum of the second column of a file:
awk '{ sum += $2 } END { print sum }' file.txt

Print the number of lines in a file:
awk 'END { print NR }' file.txt


Replace all occurrences of a certain string with another string in a file:
awk '{ gsub("old", "new") } 1' file.txt
```
