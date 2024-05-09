# Part 1: Reversed Bug

## A failure-inducing input for the buggy program, as a JUnit test and any associated code


Failure inducing input
```
@Test 
  public void reversedTest() {
    int[] input1 = {1, 2, 3, 4, 5};
    assertArrayEquals(new int[]{5, 4, 3, 2, 1}, ArrayExamples.reversed(input1));
  }
```

## An input that doesn't induce a failure, as a JUnit test and any associated code

```
@Test 
  public void reversedTest2() {
    int[] input1 = {1, 2, 3, 4, 5};
    assertArrayEquals(new int[]{1, 2, 3, 4, 5}, ArrayExamples.reversed(input1));
  }
```

## The symptom, as the output of running the two tests above

![Image](reversedTest.png)

![Image](reversedTest2.png)

## The bug, as the before-and-after code change required to fix it

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
      newArray[arr.length - i - 1] = arr[i];
    }
    return newArray;
  }
```

## Briefly describe (2-3 sentences) why the fix addresses the issue

The after code fixes the two errors. First, the bad code was setting elements from the new array which don't even exist yet into the old array. Second, it was returning the old array. The new code correctly sets elements into the new array and returns the new array.

# Part 2 : less

I asked chatgpt for ways to use less, the prompt I gave it is at the bottom of the page.

## 1. grep pattern filename
input 1
```
grep Aziz 911report/chapter-1.txt
```
output 1
```
    For those heading to an airport, weather conditions could not have been better for a safe and pleasant journey. Among the travelers were Mohamed Atta and Abdul Aziz al Omari, who arrived at the airport in Portland, Maine.
```

input 2
```
grep 9:03 911report/chapter-9.txt
```
output 2
```
                    2 World Trade Center (the South Tower) at 9:03 until the collapse of the South
                    of the North Tower at 10:28 From 8:46 until 9:03 A.M.
            In the 17-minute period between 8:46 and 9:03 A.M. on September 11, New York City and
            From 9:03 until 9:59 A.M.
            At 9:03:11, the hijacked United Airlines Flight 175 hit 2 WTC (the South Tower) from
                companies, as units that had been in or en route to the North Tower lobby at 9:03
                that had been dispatched to the North Tower prior to 9:03 reported immediately to
            Throughout this period (9:03 to 9:59), a group of NYPD and Port Authority police

```

## 2. grep -c pattern file

input 1
```
grep -c flight 911report/chapter-1.txt
```
output 1
```
74
```

input 2
```
grep -c New 911report/chapter-1.txt
```
output 2
```
50
```

## 3. grep -c -r pattern directory

input 1
```
grep -c -r flight 911report/
```
output 1
```
911report/chapter-1.txt:74
911report/chapter-10.txt:10
911report/chapter-11.txt:7
911report/chapter-12.txt:5
911report/chapter-13.1.txt:0
911report/chapter-13.2.txt:39
911report/chapter-13.3.txt:9
911report/chapter-13.4.txt:28
911report/chapter-13.5.txt:50
911report/chapter-2.txt:1
911report/chapter-3.txt:14
911report/chapter-5.txt:27
911report/chapter-6.txt:15
911report/chapter-7.txt:59
911report/chapter-8.txt:8
911report/chapter-9.txt:3
911report/preface.txt:0
```

input 2
```
grep -c -r WTC 911report/
```
output 2
```
911report/chapter-1.txt:0
911report/chapter-10.txt:0
911report/chapter-11.txt:0
911report/chapter-12.txt:0
911report/chapter-13.1.txt:0
911report/chapter-13.2.txt:1
911report/chapter-13.3.txt:1
911report/chapter-13.4.txt:0
911report/chapter-13.5.txt:56
911report/chapter-2.txt:0
911report/chapter-3.txt:0
911report/chapter-5.txt:0
911report/chapter-6.txt:0
911report/chapter-7.txt:0
911report/chapter-8.txt:0
911report/chapter-9.txt:80
911report/preface.txt:0
```

## 4. grep -v -c pattern file

input 1
```
grep -v -c flight 911report/chapter-1.txt
```
output 1
```
657
```

input 2
```
grep -v -c medicine biomed/1468-6708-3-1.txt
```
output 2
```
432
```

## Sources (ChatGPT)

Prompt given
```
what are some different ways to use the command 'grep'?
```

Output given
```
grep is a powerful command-line tool used for searching text patterns in files. Here are some different ways to use the grep command:

Basic Search: grep pattern file
This searches for the specified pattern in the given file.
Case Insensitive Search: grep -i pattern file
Performs a case-insensitive search.
Recursive Search: grep -r pattern directory
Searches for the pattern recursively in all files under the specified directory.
Search for Whole Words: grep -w pattern file
Searches for the whole word pattern in the file.
Counting Matches: grep -c pattern file
Counts the number of lines that contain the pattern in the file.
Display Matching Line Numbers: grep -n pattern file
Displays the line numbers of matching lines in the file.
Invert Match: grep -v pattern file
Displays lines that do not contain the pattern.
Search Multiple Files: grep pattern file1 file2 file3
Searches for the pattern in multiple files.
Display Matching Portion: grep -o pattern file
Displays only the matching portion of the lines.
Using Regular Expressions: grep -E 'regex' file
Uses extended regular expressions for pattern matching.
Ignoring Binary Files: grep -I pattern file
Ignores binary files.
Displaying Lines Before and After Match: grep -B 3 -A 2 pattern file
Displays 3 lines before and 2 lines after each matching line.
These are just a few examples of how you can use grep. It's a versatile tool with many options for searching and manipulating text files.
```

2nd prompt
```
what is -r
```

2nd output
```
The -r option in the grep command stands for "recursive." When used, grep will search recursively through directories and subdirectories for the specified pattern in files. This means that it will not only search in the specified directory but also in all directories and subdirectories within that directory.

For example, if you want to search for the pattern "hello" in all files under the current directory and its subdirectories, you can use grep -r "hello" . (the dot represents the current directory).
```

