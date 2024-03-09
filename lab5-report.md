# Lab Report 5 - Putting it All Together

## Part 1 – Debugging Scenario

Design a debugging scenario, and write your report as a conversation on EdStem. It should have:

###1. The original post from a student with a screenshot showing a symptom and a description of a guess at the bug/some
   sense of what the failure-inducing input is. (Don't actually make the post! Just write the content that would go in such a post)

   Hello! I am writing the grade script for the list examples and I am getting some errors I don't really know how to go about fixing.
   When I run one of the repos that has failures, I get the correct output: ![Image](working bash script.png)

   However when I then run the repo that is successful, as in has no errors I do not get the correct output: ![Image](failing grade script.png)

   From looking at the JUnit output text file I feel like that is why this is not working however, I do not know how to go about fixing it.
   ![Image](working code output.png) ![Image](failing code output.png)

   From the first image, I can see how the script is getting the numbers to produce the grade correctly, however with the passing repo, it does not
   show failures and tests ran so there aren't two numbers to grab and show the score. I have an idea to write some code that finds if the output
   says "OK" in it somewhere because I believe that is produced every time successful code is run, however, I do not really know how to go about
   this without causing the current code to break and stop producing the correct output for the repo that has failures. Thank you for any advice!
   
3. A response from a TA asking a leading question or suggesting a command to try (To be clear, you are mimicking a TA here.)

4. Another screenshot/terminal output showing what information the student got from trying that, and a clear description of what the bug is.

5. At the end, all the information needed about the setup including:
The file & directory structure needed:
The contents of each file before fixing the bug:
The full command line (or lines) you ran to trigger the bug:
A description of what to edit to fix the bug:

You should actually set up and run the scenario from your screenshots. 
It should involve at least a Java file and a bash script. Describing the bug 
should involve reading some output at the terminal resulting from running one 
or more commands. Design an error that produces more interesting output than a 
single message about a syntax or unbound identifier error – showcase some interesting wrong behavior! 
Feel free to set this up by cloning and breaking some existing code like the grading script or code from class, or by designing something of your own from scratch, etc.
