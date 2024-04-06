# cd, ls, and cat, and using the workspace you created in this lab:


## cd

**Share an example of using the command with no arguments.**

input

ran at : /Users/scott/Downloads/cse15/lecture1

```
cd
```

output

not an error, output is blank, changes the working directory to my /Users/scott/

**Share an example of using the command with a path to a directory as an argument.**
   
input

ran at: /Users/scott/Downloads/cse15/lecture1

```
cd lecture1
```

output

```
scott@scott lecture1 %
```

not an error, changed working directory to lecture1

**Share an example of using the command with a path to a file as an argument.**

input
```
cd Hello.java
```

output

```
cd: not a directory: Hello.java
```

Error, cd is used to move directories and Hello.java is not a directory

# ls

**Share an example of using the command with no arguments.**

input

ran at: /Users/scott/Downloads/cse15/lecture1

```
ls
```

output

```
Hello.class     Hello.java      README          messages
```

not an error, listed all files within directory

**Share an example of using the command with a path to a directory as an argument.**
   
input

ran at: /Users/scott/Downloads/cse15/

```
ls lecture1
```

output

```
Hello.class     Hello.java      README          messages
```

not an error, listed all files within given directory

**Share an example of using the command with a path to a file as an argument.**
   
input

ran at: /Users/scott/Downloads/cse15/lecture1

```
ls Hello.java
```

output

```
Hello.java
```

not an error, the only file within Hello.java is itself

# cat

**Share an example of using the command with no arguments.**
   
input

ran at /Users/scott/Downloads/cse15/lecture1

```
cat
```

output

error, empty output, no arguments given

**Share an example of using the command with a path to a directory as an argument.**

input

ran at: /Users/scott/Downloads/cse15/

```
cat lecture1
```

output

```
cat: lecture1: Is a directory
```

error, cat is supposed to give contents of a file, not directory

**Share an example of using the command with a path to a file as an argument.**

input

ran at: /Users/scott/Downloads/cse15/lecture1

```
cat Hello.java
```

output

```
import java.io.IOException;
import java.nio.charset.StandardCharsets;
import java.nio.file.Files;
import java.nio.file.Path;

public class Hello {
  public static void main(String[] args) throws IOException {
    String content = Files.readString(Path.of(args[0]), StandardCharsets.UTF_8);    
    System.out.println(content);
  }
}%
```

not an error, told us what was inside of Hello.java
