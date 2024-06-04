#  Exercise 4
## Commands: which,whereis,locate + updatedb,find, telnet, ssh, nc


## commands manual


### which

The which command is used to locate the executable file associated with a given command or program name. It searches through the directories listed in the $PATH environment variable to find the location of the specified command.

Example:
```
$ which python
/usr/bin/python
```

### whereis

The whereis command is used to locate the binary, source, and manual page files for a command or program.

Example:
```
$ whereis python
python: /usr/bin/python /usr/lib/python2.7 /usr/lib/python3.8 /usr/share/man/man1/python.1.gz
```

### locate + updatedb

The locate command is used to find files and directories on a system by name. It uses a pre-built database of filenames and their locations, which is updated periodically by the updatedb command.

Example:
```
$ locate myfile.txt
/home/user/myfile.txt
Note: Before using locate, you may need to run sudo updatedb to update the database.
```

### find

The find command is used to search for files and directories in a specified location. It allows you to search for files by name, size, modification time, and other criteria.

Example:
```
$ find /home/user -name "*.txt"
/home/user/myfile.txt
/home/user/otherfile.txt
```

### telnet

The telnet command is used to connect to a remote server using the Telnet protocol. It can be used to establish a terminal session on a remote system.

Example:
```
$ telnet example.com 80
Trying 93.184.216.34...
Connected to example.com.
Escape character is '^]'.
```

ssh

The ssh command is used to connect to a remote server using the SSH protocol. It can be used to establish a secure terminal session on a remote system.

Example:
```
$ ssh user@example.com
Password:
Last login: Fri Apr  2 09:30:11 2023 from 10.0.0.2
```

nc

The nc command (short for netcat) is a networking utility used for reading and writing data across network connections. It can be used to transfer files, send and receive messages, and more.

Example:
```
$ echo "Hello, world!" | nc example.com 8080
Note: This example sends the message "Hello, world!" to the server at example.com on port 8080. The server may or may not respond, depending on its configuration.
```
