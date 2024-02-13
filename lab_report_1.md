<h1><italic>CSE 15L Lab 1 Report</italic></h1>

<h3>1. cd with no arguments</h3>

```
[user@sahara ~/lecture1/messages]$ cd
[user@sahara ~]$ 
```

- The working directory I'm working on is the `home/lecture1/messages` directory.
- It will return to the `home` directory because when you use `cd` with no arguments, it will return to the base directory.
- It's not an error.

---

<h3>2. cd with the command with a path to a directory as an argument</h3>

```
[user@sahara ~]$ cd lecture1/messages
[user@sahara ~/lecture1/messages]$
```

- The working directory I'm working on is the `home` directory.
- It will bring me to the `messages` directory under the `lecture1` directory, which is under the `home` directory.
- It's not an error

---

<h3>3. cd with the command with a path to a file as an argument</h3>

```
[user@sahara ~/lecture1/messages]$ cd en-us.txt
bash: cd: en-us.txt: Not a directory
```

- The working directory I'm working on is the `home/lecture1/messages` directory.
- It will return this error because `en-us.txt` is a file, not a directory, and the `cd` command only takes a directory command.
- It's an error because the argument I give is a file, not a directory.

---

<h3>4. ls with no arguments </h3>

```
[user@sahara ~]$ ls
lecture1
```

- The working directory I'm working on is the `home` directory.
- It will list out what is under the home directory, which is the `lecture1` directory because the `ls` command with no argument will list out the stuff under the current directory.
- It's not an error.

---

<h3>5. ls with the command with a path to a directory as an argument</h3>

```
[user@sahara ~]$ ls lecture1
Hello.class  Hello.java  messages  README
```

- The working directory I'm working on is the `home` directory, and I'm putting `lecture1` as the command.
- It will return what is under the `home/lecture1` directory, and list everything under it all out.
- It's not an error.

---

<h3>6. ls with the command with a path to a file as an argument</h3>

```
[user@sahara ~/lecture1]$ ls Hello.java
Hello.java
```

- The working directory I'm working on is the `home/lecture1` directory.
- It will return me the file name, because `Hello.java` is a file, not the directory.
- It's not an error, it's just how `ls` works with the file name argument, and it does not return any warning.

----

<h3>7. cd with no arguments</h3>

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

<h3>8. cd with the command with a path to a directory as an argument</h3>

```
[user@sahara ~]$ cat lecture1
cat: lecture1: Is a directory
```

- The working directory I'm working on is the `home` directory, and the path I'm putting as the argument is `lecture1`.
- Because `cat` only reads the file, not the directory.
- It's an error because it throws `lecture: Is a directory` to me, and it's an error.

---
<h3>9. cd with the command with a path to a file as an argument</h3>

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
