#  Exercise 10
## Commands: files permissions , file owner , passwd , chmod,chown,who , su,useradd,userdel , usermod


### File permissions

File permissions specify who can read, write, and execute a file on a Unix-like system. The ls -l command can be used to view the permissions of a file.

Example:
```
$ ls -l file.txt
-rw-r--r-- 1 username groupname 0 Jan  1 00:00 file.txt
The above output shows that the file is readable and writable by the owner (username), and only readable by members of the group (groupname) and all other users.
```
### File owner

The file owner specifies the user who owns a file. The ls -l command can also be used to view the owner of a file.

Example:
```
$ ls -l file.txt
-rw-r--r-- 1 username groupname 0 Jan  1 00:00 file.txt
The above output shows that the owner of file.txt is username.
```
### passwd

The passwd command is used to change a user's password.

Example:
```
$ passwd
Changing password for user username.
New password:
Retype new password:
```

### chmod

The chmod command is used to change the permissions of a file.

Example:
```
$ chmod 700 file.txt
The above command sets the permissions of file.txt so that only the owner can read, write, and execute the file.
```
### chown

The chown command is used to change the owner and/or group of a file.

Example:
```
$ chown newowner:newgroup file.txt
The above command changes the owner of file.txt to newowner and the group to newgroup.
```
### who

The who command shows who is currently logged in to the system.

Example:
```
$ who
username  tty1         2022-01-01 00:00
```
### su
The su command is used to switch to another user account.

Example:
```
$ su otheruser
Password:
The above command switches the current user to otheruser.
```

### useradd

The useradd command is used to add a new user account.

Example:
```
$ useradd newuser
The above command creates a new user account named newuser.
```

### userdel
The userdel command is used to delete a user account.

Example:
```
$ userdel olduser
The above command deletes the user account olduser.
```

### usermod

The usermod command is used to modify a user account.

Example:

```
$ usermod -a -G newgroup username
The above command adds the user username to the newgroup group.

```
