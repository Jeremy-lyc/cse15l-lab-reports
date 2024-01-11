<h1><italic>CSE 15L Lab 1 Report</italic></h1>

<h3>1. cd with no arguments</h3>

```
[user@sahara ~]$ cat
/lecture1
/lecture1
/lecture1/messages               
/lecture1/messages
hello
hello
```

- The working directory I'm working on is the `home` directory.
- When I'm going to run `cat` with **no argument**, it will run in interactive mode, and return everything I typed in. Also, to terminate the program, I need to press `ctrl + d`.
- I don't think it's an error, it's just how `cat` is working in the terminal.

---

<h3>2. cd with the command with a path to a directory as an argument</h3>

```
[user@sahara ~]$ cat lecture1
cat: lecture1: Is a directory
```

- The working directory I'm working on is the `home` directory, and the path I'm putting as the argument is `lecture1`.
- Because `cat` only reads the file, not the directory.
- It's an error because it throws `lecture: Is a directory` to me, and it's an error.

---
<h3>3. cd with the command with a path to a file as an argument.</h3>

```
[user@sahara ~]$ cat lecture1/Hello.java 
import java.io.IOException;
import java.nio.charset.StandardCharsets;
import java.nio.file.Files;
import java.nio.file.Path;

public class Hello {
  public static void main(String[] args) throws IOException {
    String content = Files.readString(Path.of(args[0]), StandardCharsets.UTF_8);    
    System.out.println(content);
  }
```

- The working directory I'm working on is the `home` directory, and I'm looking for the **Hello.java** file under the lecture1 folder.
- It returns me the code of this java file, and because the command `cat` is to read the file within the terminal.
- It's not an error.

---
