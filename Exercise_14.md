#  Exercise 14
## Commands: LAB create 10 directories and readme file in each

```
#!/bin/bash

# create directories
for i in {1..10}
do
  mkdir "Lesson_$i"
done

# create readme files
for dir in Lesson_*/
do
  echo "This is the readme file for $dir" > "$dir/README.md"
done

```