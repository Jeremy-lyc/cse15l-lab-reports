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

- This is happening because the code is assigning the last element in the list to the very first element, and the second last element to the second element. However, if you iterate over the whole list, the second half of the list will be assigned the same value as itself as the value of the first half of the list already is being changed. In this fixed code, I used a local variable `tempValue` to store the integer that exists in the first half of the list and assign it to the second half of the list after the first half of the list's element is changed. Also, this for loop only iterates through half of the list.

---

<h3>Part 2 - Researching Commands</h3>
