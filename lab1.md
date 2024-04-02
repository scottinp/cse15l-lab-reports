cd, ls, and cat, and using the workspace you created in this lab:


# cd

Share an example of using the command with no arguments.
**input**
```
cd
```

**output**
output is blank, changes working directory to my user

Share an example of using the command with a path to a directory as an argument.
**input**
```
cd lecture1
```

**output**
```
scott@scott lecture1 %
```
changed working directory to lecture1

Share an example of using the command with a path to a file as an argument.
**input**
```
cd Hello.java
```

**output**
```
cd: not a directory: Hello.java
```

# ls
Share an example of using the command with no arguments.
**input**
```
ls
```

**output**
```
Hello.class     Hello.java      README          messages
```

Share an example of using the command with a path to a directory as an argument.
**input**
```
ls lecture1
```
(ran while outside of lecture1 folder)

**output**
```
Hello.class     Hello.java      README          messages
```

Share an example of using the command with a path to a file as an argument.
**input**
```
ls Hello.java
```

**output**
```
Hello.java
```

# cat
Share an example of using the command with no arguments.
**input**
```
cat
```

**output**
empty output

Share an example of using the command with a path to a directory as an argument.
**input**
```
cat lecture1
```

**output**
```
cat: lecture1: Is a directory
```
Share an example of using the command with a path to a file as an argument.
**input**
```
cat Hello.java
```

**output**
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
