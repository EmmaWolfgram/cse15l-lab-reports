# Lab 3 Report - Bugs and Commands (Week 5)

## Part 1 - Bugs

Chosen bug: static int[] reversed(int[] arr)

**1. A failure-inducing input for the buggy program, as a JUnit test and any associated code**
```
@Test
public void testReversedFailOnGoodImple() {
  int[] intput1 = {1, 2, 3};
  assertArrayEquals(new int[]{3, 2, 1}, ArrayExamples.reversed(input1));
```

**2. An input that doesn't induce a failure, as a JUnit test and any associated code**
```
@Test
public void testReversedPassOnBadImple() {
  int[] input1 = {0, 0, 0};
  assertArrayEquals(new int[]{0, 0, 0}, ArrayExamples.reversed(input1));
```

**3. The symptom, as the output of running the tests**
![Image](failOnGood.png)
![Image](passOnBad.png)

**4. The bug, as the before-and-after code change required to fix it**

Before
```
static int[] reversed(int[] arr) {
  int[] newArray = new int[arr.length];
  for(int i = 0; i < arr.length; i += 1) {
    arr[i] = newArray[arr.length - i - 1];
  }
  return arr;
}
```
After
```
static int[] reversed(int[] arr) {
  int[] newArray = new int[arr.length];
  for(int i = 0; i < arr.length; i += 1) {
    newArray[i] = arr[arr.length - i - 1];
  }
  return newArray;
}
```
**Why does this fix the issue?** In this code, the broken line appears inside the for loop. This method is supposed to copy over elements from one array into a new array but in reverse order. In the broken code, when the elements are copied over, it is putting elements from the new array into the old array. When the new array is created, all the values are defaulted to zero, so when the method runs, all the values in the array are switched to values from the new array which are all zeros. The code after fixes this issue by copying the old array values into the new array in reverse order.

## Part 2 - Researching Commands

**GREP**

1. grep -n: displays the matched lines and the line numbers that the pattern appears on
Example 1
```
emma2@Wolfies-laptop MINGW64 ~/OneDrive/Documents/GitHub/docsearch (main)
$ grep -n "biological" technical/biomed/*.txt
technical/biomed/1471-2091-2-11.txt:350:     and differentially elaborate distinct biological activities
technical/biomed/1471-2091-2-12.txt:315:     biological role that this receptor class plays for Bt
technical/biomed/1471-2105-3-17.txt:814:     (biological) and treatment variabilities.
technical/biomed/1471-2105-3-17.txt:909:     DM integrated the mathematical and biological
technical/biomed/1471-2105-3-18.txt:2217:     biologically useful. It is meant only as a testbed for the
```
Example 2
```
emma2@Wolfies-laptop MINGW64 ~/OneDrive/Documents/GitHub/docsearch (main)
$ grep -n "California" technical/911report/*.txt
technical/911report/chapter-13.4.txt:2005:     reasons for sending Hazmi and Mihdhar to California do not seem especially
technical/911report/chapter-13.4.txt:2017:     addresses-one in the United States ("possibly in California") and one in South  
technical/911report/chapter-13.4.txt:2037:     California." Intelligence report, interrogation of KSM, June 15, 2004.
technical/911report/chapter-13.4.txt:2184:     acclimate the hijackers to the United States, particularly San Diego, California." 
```
In both of these examples, the output provided is just a sample output and not the full list. When `grep -n` is used in the terminal, it take the input of the pattern and prints out a list of where that pattern appears in the given files and what line they are on in the file. This command could be useful if you are looking for similar words in a bunch of files or if you are looking for a phrase/word in a specific file.
3. grep -c  (This prints only a count of the lines that match a pattern)
4. grep -l  (Displays list of a filenames only.)
5. grep -v  (This prints out all the lines that do not matches the pattern)
all on https://www.geeksforgeeks.org/grep-command-in-unixlinux/

For example, we saw the -name option for find in class. For each of those options, give 2 examples of using it on files and 
directories from ./technical. Show each example as a code block that shows the command and its output, and write a sentence 
or two about what it’s doing and why it’s useful.
