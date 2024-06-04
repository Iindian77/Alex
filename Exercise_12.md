#  Exercise 12
## Commands: bash top 10

### Using double brackets for more powerful conditional expressions:
```
if [[ $var == "string" && $var2 -eq 3 ]]; then
  # code here
fi
```


### Using brace expansion to generate sequences:
```
echo {1..10}
# Output: 1 2 3 4 5 6 7 8 9 10
```
### Using process substitution to treat the output of a command as a file:
```
diff <(command1) <(command2)
```


### Using command substitution to capture the output of a command:
```
result=$(command)
```


### Using the "shopt" built-in command to set shell options:
```
shopt -s extglob # enables extended globbing
```


### Using the "case" statement for more flexible conditional branching:
```
case "$variable" in
  pattern1) command1;;
  pattern2) command2;;
  *) default_command;;
esac
```


### Using arrays for storing and manipulating lists of values:
```
my_array=("value1" "value2" "value3")
echo "${my_array[@]}" # prints all values
```

### Using command-line arguments to make scripts more flexible:
```
#!/bin/bash
# $1 and $2 are the first and second arguments, respectively
echo "Hello, $1 and $2!"
```


### Using functions to reuse code:
```
my_function() {
  # code here
}

my_function # call the function
```



### Using "trap" to clean up resources when a script is interrupted:
```
#!/bin/bash
function cleanup {
  # code here to clean up resources
}
trap cleanup EXIT # call cleanup function when script exits
```