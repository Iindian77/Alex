#  Exercise 11
## Commands:  shebang, global variables - create temp var, create permanent vars, use theme

The "shebang" in Bash refers to the first line of a Bash script that starts with #! (also called a hashbang). This line specifies the interpreter that should be used to execute the script.
This tells the system to use the Bash interpreter located at /bin/bash to execute the script.

```
#!/bin/bash
```
It's also worth noting that the shebang line is not limited to Bash; it can be used to specify the interpreter for any scripting language. For example, a Python script that should be executed with Python 3 could have the following shebang line:
```
#!/usr/bin/python3
```


### Creating and Using Variables

### Creating Temporary Variables
Temporary variables can be created and used within the same shell session. To create a temporary variable, simply assign a value to it using the following syntax:

variable_name=value
For example, to create a temporary variable called myvar and assign the value "hello", use the following command:
```
myvar=hello
To access the value of the variable, precede its name with the dollar sign $:

echo $myvar
This will output hello.
```


### Creating Permanent Variables
Permanent variables can be defined in a startup file like .bashrc or .bash_profile and can be used across different shell sessions. To create a permanent variable, add the following line to the startup file:
```
export variable_name=value
```
For example, to create a permanent variable called myvar and assign the value "hello" in the .bashrc file, use the following command:
```
echo 'export myvar=hello' >> ~/.bashrc
This will append the export command to the .bashrc file. 
```
To activate the changes, run the following command:
```
source ~/.bashrc
Now the myvar variable is available for use in all subsequent shell sessions.
```

### Using Variables
Once a variable is defined, its value can be accessed using the $ sign followed by the variable name. Here are a couple of examples of using variables:
```
myvar=hello
echo $myvar
This will output hello.

greeting="Hello, World!"
echo $greeting
This wi`ll output Hello, World!.
```
