# Lab Report 5 - Putting it All Together (Week 9)

**Part 1 – Debugging Scenario**


Design a debugging scenario, and write your report as a conversation on EdStem. It should have:

1. The original post from a student with a screenshot showing a symptom and a description of a guess at the bug/some sense of what the failure-inducing input is. (Don’t actually make the post! Just write the content that would go in such a
 post)

### Original Post on EdStem

**Title:**  Issue with Java Program Output - Need Help Debugging

**Content:** 

> Hi everyone,
> 
> I am currently working on the Java program `MyProgram.java`. I also ran this Java file by using a bash script called `run.sh`. This Java program will read a text file, and print each line numbered. However, as there is an odd output. The programming omits every second line on the display.
> 
> Here's a screenshot of my terminal after running `./run.sh`:
> 
> ![Terminal Output](labreport5(1).png)
> 
> It seems like the bug might be related to how the program reads the file or processes the lines. I'm a bit stuck on what could be causing this. Any suggestions on how to debug this would be really helpful!

2. A response from a TA asking a leading question or suggesting a command to try (To be clear, you are mimicking a TA here.)
   
**Response from TA:**

> Hi there,
> 
> Your description of the problem makes me suspect a problem with loop or file reading logic in `MyProgram.java`. Could you do me a favour and run `cat -n yourInputFile.txt` in your terminal and then post its output here? The command shall produce your input with line numbers for us to check against your program’s output.
> 

3. Another screenshot/terminal output showing what information the student got from trying that, and a clear description of what the bug is.
**Follow-Up Post from Student:**

> Thanks for the suggestion! Here's the output from running `cat -n inputFile.txt`:
> 
> ![Terminal Output - Cat Command](screenshot2.png)
> 
> I compared this with my program's output and noticed that indeed my program is skipping lines. Here's the bug: in my file reading loop, I was calling `reader.readLine()` twice per iteration, which caused every other line to be skipped.

   
4. At the end, all the information needed about the setup including:
* The file & directory structure needed
* The contents of each file before fixing the bug
* The full command line (or lines) you ran to trigger the bug
* A description of what to edit to fix the bug


> **Setup Information:**
> - **File & Directory Structure:**
>   - labreport5
>     - MyProgram.java
>     - run.sh
>     - inputFile.txt
> - **Contents of MyProgram.java (before fixing):**
>   ```java
>   import java.io.*;
>   public class MyProgram {
>       public static void main(String[] args) throws IOException {
>           BufferedReader reader = new BufferedReader(new FileReader("inputFile.txt"));
>           String line;
>           int lineNum = 1;
>           while ((line = reader.readLine()) != null) {
>               System.out.println(lineNum + ": " + line);
>               line = reader.readLine(); 
>               lineNum++;
>           }
>           reader.close();
>       }
>   }
>   ```
> - **Contents of run.sh:**
>   ```bash
>   #!/bin/bash
>   javac MyProgram.java
>   java MyProgram
>   ```
>
> -**Contents of inputFile.txt:**
> ```
> Hello
>world
>This
>is
>the
>last
>lab
>report
> ```
> 
> - **Command Line to Trigger the Bug:**
>   ```
>   ./run.sh
>   ```
> - **Fix:**
>   To fix the bug, remove the second call to `reader.readLine()` inside the while loop in `MyProgram.java`.
