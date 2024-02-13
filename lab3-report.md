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

**1. `grep -n`: displays the matched lines and the line numbers that the pattern appears on**

Example 1:
```
emma2@Wolfies-laptop MINGW64 ~/OneDrive/Documents/GitHub/docsearch (main)
$ grep -n "biological" technical/biomed/*.txt
technical/biomed/1471-2091-2-11.txt:350:     and differentially elaborate distinct biological activities
technical/biomed/1471-2091-2-12.txt:315:     biological role that this receptor class plays for Bt
technical/biomed/1471-2105-3-17.txt:814:     (biological) and treatment variabilities.
technical/biomed/1471-2105-3-17.txt:909:     DM integrated the mathematical and biological
technical/biomed/1471-2105-3-18.txt:2217:     biologically useful. It is meant only as a testbed for the
```
Example 2:
```
emma2@Wolfies-laptop MINGW64 ~/OneDrive/Documents/GitHub/docsearch (main)
$ grep -n "California" technical/911report/*.txt
technical/911report/chapter-13.4.txt:2005:     reasons for sending Hazmi and Mihdhar to California do not seem especially
technical/911report/chapter-13.4.txt:2017:     addresses-one in the United States ("possibly in California") and one in South  
technical/911report/chapter-13.4.txt:2037:     California." Intelligence report, interrogation of KSM, June 15, 2004.
technical/911report/chapter-13.4.txt:2184:     acclimate the hijackers to the United States, particularly San Diego, California." 
```
In both of these examples, the output provided is just a sample output and not the full list. When `grep -n` is used in the terminal, it takes the input pattern and prints out a list of where that pattern appears in the given files and what line they are on in the file. This command could be useful if you are looking for similar words in a bunch of files or if you are looking for a phrase/word in a specific file.

**2. `grep -c`: prints a count of the lines that match the pattern for each file**

Example 1:
```
emma2@Wolfies-laptop MINGW64 ~/OneDrive/Documents/GitHub/docsearch (main)
$ grep -c "older adults" technical/biomed/*.txt
technical/biomed/1468-6708-3-1.txt:14
technical/biomed/1468-6708-3-10.txt:0
technical/biomed/1468-6708-3-3.txt:0
```
Example 2:
```
emma2@Wolfies-laptop MINGW64 ~/OneDrive/Documents/GitHub/docsearch (main)
$ grep -c "North Tower" technical/911report/*.txt
technical/911report/chapter-1.txt:2
technical/911report/chapter-10.txt:0
technical/911report/chapter-11.txt:0
technical/911report/chapter-12.txt:0
technical/911report/chapter-13.5.txt:15
technical/911report/chapter-2.txt:0
technical/911report/chapter-9.txt:98
```
In both examples the provided output is not the full printed-out output. When `grep -c` is used in the terminal, it takes the input pattern and prints out a list of how many times that pattern appears in each file that is specified in the command line. This command could be useful to search files and see which file could be most useful when looking at a specific topic or to count how many times the pattern shows up in a group of files. 

**3. `grep -l`: Displays list of a filenames only that contain the pattern**

Example 1:
```
emma2@Wolfies-laptop MINGW64 ~/OneDrive/Documents/GitHub/docsearch (main)
$ grep -l "medical reports" technical/*/*.txt
technical/biomed/1471-2350-3-1.txt
```
Example 2:
```
emma2@Wolfies-laptop MINGW64 ~/OneDrive/Documents/GitHub/docsearch (main)
$ grep -l "biological" technical/*/*.txt > all-biolog-files.txt

emma2@Wolfies-laptop MINGW64 ~/OneDrive/Documents/GitHub/docsearch (main)
$ wc all-biolog-files.txt 
  320   320 11951 all-biolog-files.txt
```
When `grep -l` is used in the terminal, it takes the input pattern and prints out a list of all the files that contain the pattern. This command could be useful to find files about specific topics in a large directory of files or to go further and count how many files contain the pattern.

**4. `grep -i`: print lines with matching criteria while ignoring upper and lowercasing**

Example 1:
```
emma2@Wolfies-laptop MINGW64 ~/OneDrive/Documents/GitHub/docsearch (main)
$ grep -i "molecule" technical/biomed/*.txt
technical/biomed/1471-2091-2-10.txt:     The CD98 (4F2, FRP-1) molecule, a cell surface
technical/biomed/1471-2091-2-10.txt:     The CD98 molecule is also widely expressed on rapidly
technical/biomed/1471-2091-2-10.txt:     functionally interact remains unclear. The CD98 molecule
technical/biomed/1471-2091-2-10.txt:     particular β1 integrins and other cell surface molecules
technical/biomed/1471-2091-2-10.txt:     Several important signaling molecules, including activated
technical/biomed/1471-2091-2-10.txt:     with mAb against various cell surface molecules. From
technical/biomed/1471-2091-2-10.txt:     not other cell surface molecules, including the LDL
technical/biomed/1471-2091-2-10.txt:     comparable to re-precipitated CD81 (lane b), a molecule
technical/biomed/1471-2091-2-11.txt:     glycine-conjugated bile acids as a class of molecules
technical/biomed/1471-2091-2-12.txt:     molecule with short sequence homology to
```
Example 2:
```
emma2@Wolfies-laptop MINGW64 ~/OneDrive/Documents/GitHub/docsearch (main)
$ grep -i "molecule" technical/biomed/*.txt > total-apperance.txt

emma2@Wolfies-laptop MINGW64 ~/OneDrive/Documents/GitHub/docsearch (main)
$ wc total-apperance.txt 
  912  8222 89990 total-apperance.txt
```
When `grep -i` is used in the terminal, it takes the input pattern and regardless of capitalization, it prints all the files with a short sentence of where the word appears. This can be useful if you don't know if the word you are looking for is capitalized or not and it could also be useful if you are trying to find how many times the word appears but the word is sometimes capitalized.

[Source 1](https://www.geeksforgeeks.org/grep-command-in-unixlinux/)
[Source](https://docs.rackspace.com/docs/use-the-linux-grep-command)
