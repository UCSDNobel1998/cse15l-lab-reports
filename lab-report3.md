# Lab Report 3 - Bugs and Commands (Week 5)


## Part 1 - Bugs


**Choose one of the bugs from week 4’s lab:**


I chose the bug of the averageWithoutLowest method from the ArrayExamples.java.


**Provide:**


* **A failure-inducing input for the buggy program, as a JUnit test and any associated code (write it as a code block in Markdown):**
  

The associated code in the ArrayTests.java:

```
 @Test
  public void averageWithoutLowest() {
    double [] input1 = {-1.0, -2.0, -3.0, -3.0};
    double expected = -1.5;
    assertEquals(expected, ArrayExamples.averageWithoutLowest(input1), 0.01);
  }
```
---

* **An input that doesn’t induce a failure, as a JUnit test and any associated code (write it as a code block in Markdown):**
The associated code in the ArrayTests.java:

```
@Test
  public void averageWithoutLowest2() {
    double [] input1 = {1.0, 2.0, 4.0};
    double expected = 1.5;
    assertEquals(expected, ArrayExamples.averageWithoutLowest(input1), 0.01);
  }
```
---

* **The symptom, as the output of running the tests:(provide it as a screenshot of running JUnit with at least the two inputs above):**

 ![Image](JunitTestRunning.png)

 ---

* **The bug, as the before-and-after code change required to fix it (as two code blocks in Markdown):**
Before the change:

```
  // Averages the numbers in the array (takes the mean), but leaves out the
  // lowest number when calculating. Returns 0 if there are no elements or just
  // 1 element in the array
  static double averageWithoutLowest(double[] arr) {
    if(arr.length < 2) { return 0.0; }
    double lowest = arr[0];
    for(double num: arr) {
      if(num < lowest) { lowest = num; }
    }
    double sum = 0;
    for(double num: arr) {
      if(num != lowest) { sum += num; }
    }
    return sum / (arr.length - 1);
  }
```

---
After the change:

```
static double averageWithoutLowest(double[] arr) {
    if(arr.length < 2) { return 0.0; }
    double lowest = arr[0];
    int countLowest = 0;

    for(double num: arr) {
      if(num < lowest) {lowest = num;}
    }

    for(double num: arr) {
      if(num == lowest) {countLowest++;}
    }
 
    double sum = 0;

    for(double num: arr) {
      if(num != lowest) { sum += num; }
    }
    
    return sum / (arr.length - countLowest);
  }

```
---

**Briefly describe why the fix addresses the issue.**

In the previous code, it was assumed that there was only one lowest number in the array. After finding the lowest number in the array, I used a for loop to count its occurrences. It allows me to 
calculate the actual average without the lowest numbers of the array. During the calculation, I excluded all the lowest numbers. Therefore, this fix can address the issue.

---

## Part 2 - Researching Commands

**Consider the commands less, find, and grep. Choose one of them. Online, find 4 interesting command-line options or alternate ways to use the command you chose.**

I choose find. 








