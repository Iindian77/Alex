#  Exercise 7
## Commands: cut,paste,tr (traslate) , vi , vim

### cut

The cut command is used to extract sections from a file by selecting specific columns or fields.

Example:

$ cat file.txt
1,apple,red
2,banana,yellow
3,orange,orange

$ cut -d ',' -f 2 file.txt
apple
banana
orange


### paste

The paste command is used to merge lines from two or more files side by side.

Example:
```
$ cat file1.txt
apple
banana
orange

$ cat file2.txt
red
yellow
orange

$ paste file1.txt file2.txt
apple   red
banana  yellow
orange  orange
```


### tr (translate)

The tr command is used to translate or delete characters in a file or input stream.

Example:

$ cat file.txt
HELLO WORLD

$ tr '[:upper:]' '[:lower:]' < file.txt
hello world


### vi

vi is a text editor used in Unix and Unix-like operating systems. It is a modal editor that allows users to switch between different modes for inserting, editing, and navigating text.

Example:
```
$ vi file.txt
This command will open the file.txt in vi editor.
```

### vim

vim is an improved version of the vi editor, with additional features and enhancements. It is a widely used text editor in Unix and Unix-like operating systems.

Example:

```
$ vim file.txt
This command will open the file.txt in vim editor.
```