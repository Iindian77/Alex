#  Exercise 8
## Commands:  sort,uniq,join,vmstat,tar
### sort

The sort command is used to sort the lines of a text file in either ascending or descending order based on a specific field.

Example:
```
$ cat file.txt
b
a
c

$ sort file.txt
a
b
c
```


### uniq

The uniq command is used to remove duplicate lines from a sorted file or input stream.

Example:
```
$ cat file.txt
apple
banana
orange
orange
orange
peach

$ sort file.txt | uniq
apple
banana
orange
peach
```


### join

The join command is used to combine lines from two or more files based on a common field.

Example:
```
$ cat file1.txt
1 apple
2 banana
3 orange

$ cat file2.txt
1 red
2 yellow
3 orange

$ join -1 1 -2 1 file1.txt file2.txt
1 apple red
2 banana yellow
3 orange orange
```

### vmstat

The vmstat command is used to display system statistics like CPU usage, memory usage, disk activity, and more.

Example:

```
$ vmstat 1 5
procs -----------memory---------- ---swap-- -----io---- -system-- ------cpu-----
 r  b   swpd   free   buff  cache   si   so    bi    bo   in   cs us sy id wa st
 1  0      0 1665128  76176 282200    0    0     8    28   44   67  1  0 99  0  0
 0  0      0 1664732  76180 282200    0    0     0     0 1105 1749  2  1 97  0  0
 0  0      0 1664056  76180 282208    0    0     0     0 1133 1802  2  1 98  0  0
 0  0      0 1663104  76180 282208    0    0     0     0 1129 1758  2  1 98  0  0
 0  0      0 1662832  76180 282208    0    0     0     0 1151 1810  2  1 97  0  0
This command will display system statistics every second, for a total of 5 times.
```

### tar

The tar command is used to create or extract archives (collections of files and directories) in Unix and Unix-like operating systems.

Example:
```
$ tar -cvzf archive.tar.gz file1.txt file2.txt
This command will create a compressed archive archive.tar.gz that contains file1.txt and file2.txt.

```