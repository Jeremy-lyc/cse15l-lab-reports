# CSE 15L Lab Report 3

<h3>Part 1 — Bugs</h3>

- A failure-inducing input for the buggy program, as a JUnit test and any associated code

    ```
    public void testReverseInPlace() {
        int[] input1 = { 3, 2, 1 };
        ArrayExamples.reverseInPlace(input1);
        assertArrayEquals(new int[]{ 1, 2, 3 }, input1);
    }
    ```

- An input that doesn't induce a failure, as a JUnit test and any associated code

    ```
    public void testReverseInPlace() {
        int[] input1 = { 1 };
        ArrayExamples.reverseInPlace(input1);
        assertArrayEquals(new int[]{ 1 }, input1);
    }
    ```

- The symptom, as the output of running the tests

  ![Image](/Pictures/CSE_15L_Lab_4_Code_Bug.png)

- The bug, as the before-and-after code change required to fix it

  ![Image](/Pictures/CSE_15L_Lab_4_Code_Before_Fixed.png)

  ![Image](/Pictures/CSE_15L_Lab_4_Code_After_Fixed.png)

- This happens because the code assigns the last element in the list to the very first element, and the second last element to the second element. However, if you iterate over the whole list, the second half of the list will be assigned the same value as itself as the value of the first half of the list is already being changed. In this fixed code, I used a local variable `tempValue` to store the integer in the first half of the list and assign it to the second half of the list after the list's element is changed. Also, this for loop only iterates through half of the list.

---

<h3>Part 2 - Researching Commands</h3>

- Find files that are larger than 200kb (1)

    ```
    [user@sahara ~/docsearch]$ find ./technical -type f -size +200k
    ./technical/911report/chapter-13.4.txt
    ./technical/911report/chapter-3.txt
    ./technical/911report/chapter-13.5.txt
    ```

    This is useful when we want to look up some files that are specific to our expectation of their size.

- Find directories that are smaller than 200kb (1)

    ```
    [user@sahara ~/docsearch]$ find ./technical -type d -size -200k
    ./technical
    ./technical/911report
    ./technical/biomed
    ```
    
    This is useful because sometimes we want to find some large directories in our system and try to delete them if we haven't used them for a long time.

- Find files that are not `.txt` files (1)

    ```
    [user@sahara ~/docsearch]$ find ./technical -type f -not -name "*.txt"
    
    ```
    Nothing happened here because all the files under the `/technical` directory are `.txt` files. But this is useful when we have multiple file extensions here.

- Find directories that are not `/biomed` (1)

    ```
    [user@sahara ~/docsearch]$ find ./technical -type d -not -name "biomed"
    ./technical
    ./technical/911report
    ```
    This method is useful because sometimes we can easily find files or directories that we want if we have a consistent naming style in all of our files.

- Find files that are edited one minute ago (2) (3)

    ```
    [user@sahara ~/docsearch]$ find ./technical -type f -mmin -1
    ./technical/biomed/1468-6708-3-1.txt
    ```

    This is useful because sometimes we forget the name or lose track of files that we just edited.

- Find directories that are edited one minute ago (2) (3)

    ```
    [user@sahara ~/docsearch]$ find ./technical -type d -mmin -1
    ./technical/biomed
    ```

   This is useful because you might want to look up some directories that we just created or renamed.

- Find files whose path is a maximum of 1 from current working directories (4)

    ```
    [user@sahara ~/docsearch]$ find ./technical -maxdepth 1 -type f
    ```

    This is useful because we do not want all files from every directory under this current directory.

- Find directories whose path is a maximum of 1 from current working directories (4)

    ```
    [user@sahara ~/docsearch]$ find ./technical -maxdepth 1 -type d
    ./technical
    ./technical/911report
    ./technical/biomed
    ```

    This is useful because the find command usually finds everything under this directory, and we could limit its depth to find things if it's too large
---

<h3>Citation:</h3>

- https://snapshooter.com/learn/linux/find --- (1)
- https://stackoverflow.com/questions/32922557/find-files-modified-over-1-hour-ago-but-less-than-3-days --- (2)
- https://tecadmin.net/linux-find-command-with-examples/ --- (3)
- https://www.computerhope.com/unix/ufind.htm --- (4)
