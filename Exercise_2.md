#  Exercise 2
## Commands: mkdir,rm,mv,cp,cat,echo,touch,bc,tr


## mkdir - Create a directory:
```
mkdir my_directory
This command creates a directory named "my_directory".

mkdir -p path/to/new_directory
Option 2: Creating Multiple Directories with Parents


```

## rm - Remove files or directories:
```
rm file.txt
This command removes the file named "file.txt".

rm -r directory_name
to remove directory


rm -rf directory_name
to remove directory or file and force (dont ask anything just delete)
```

## mv - Move or rename files or directories:
```
mv file.txt new_location/
This command moves the file named "file.txt" to the directory "new_location/".
```

## cp - Copy files or directories:
```
cp file.txt copy_of_file.txt
This command creates a copy of "file.txt" named "copy_of_file.txt".

cp -r source_directory destination_directory
copies the source_directory and all its contents recursively.

```

## echo - Display a line of text:
```
echo "Hello, World!"
This command prints "Hello, World!" to the terminal.
```

## touch - Create an empty file or update file timestamps:
```
touch new_file.txt
This command creates an empty file named "new_file.txt" or updates the timestamp if the file already exists.
```


## Using the tr command

```
This command translates all lowercase characters in the input string to uppercase.
echo "hello world" | tr '[:lower:]' '[:upper:]'

This command deletes all digits from the input string, leaving only alphabetic characters.
echo "hello123world456" | tr -d '[:digit:]'

This command replaces newline characters with spaces, effectively merging multiple lines into a single line.
echo -e "line1\nline2\nline3" | tr '\n' ' '

This command squeezes multiple spaces into a single tab character, effectively converting consecutive spaces into tabs.
echo "hello   world" | tr -s ' ' '\t'


This command first translates all lowercase characters to uppercase and then translates spaces to underscores, effectively converting the input string into a format suitable for filenames (uppercase letters with underscores instead of spaces).
echo "hello world" | tr '[:lower:]' '[:upper:]' | tr ' ' '_'

```

