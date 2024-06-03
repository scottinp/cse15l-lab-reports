# Part 1

## Student Piazza Post

*Title* : Sum not appearing in text file

> I want to write a java file and bash script to find the sum of arguments and put it into a txt file, but when I run my bash script to add numbers, nothing appears. Here is my bash script and java file.

run.sh
```
javac -g *.java

ARGS="$@"

java Add $ARGS > sum.txt

echo "Sum of $ARGS is stored in sum.txt"
```

# Part 2
