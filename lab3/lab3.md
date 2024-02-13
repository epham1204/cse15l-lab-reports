# __Lab 3__
## __Part 1__
I will be using week 4's lab, `ArrayExamples` and `ArrayTests`, specifically, the `testReversed` bug

* __Failure-inducing input__
* JUnit test
  ```
  @Test
  public void testReversed() {
        int[] input1 = {1, 2, 3};
        assertArrayEquals(new int[]{3, 2, 1}, ArrayExamples.reversed(input1));
  }
  arrays first differed at element [0]; expected:[3] but was:[0]
  at ArrayTests.testReversed(ArrayTests.java:8)
  ```
 
* Associated code
  ```
  static int[] reversed(int[] arr) {
        int[] newArray = new int[arr.length];
        for(int i = 0; i < arr.length; i += 1) {
            arr[i] = newArray[arr.length - i - 1];
        }
        return arr;
  }
  ```
* __Passing input__
* JUnit test
  ```
  @Test
  public void testReversed() {
        int[] input1 = {1, 2, 3};
        assertArrayEquals(new int[]{3, 2, 1}, ArrayExamples.reversed(input1));
  }
  ```
* Associated code
  ```
  static int[] reversed(int[] arr) {
        int[] newArray = new int[arr.length];
        for(int i = 0; i < arr.length; i += 1) {
            newArray[i] = arr[arr.length - i - 1];
        }
        return newArray;
  }
  ```
* __Symptom__
* __Failing__
  ![Image](testFail.png)
* __Passing__
  ![Image](testPass.png)
  
* __Bug__
* Before
  ```
  for(int i = 0; i < arr.length; i += 1) {
      arr[i] = newArray[arr.length - i - 1];
  }
  return arr;
  ```
* After
* ```
  for(int i = 0; i < arr.length; i += 1) {
      newArray[i] = arr[arr.length - i - 1];
  }
  return newArray;
  ```
* This fix addresses the issue of the failing test because the failing test
* has two major errors in the code. First, it returns the original array
* instead of a new array with the reversed values. Second, it changes
* the values of the original array rather than changing the values of the
* new array

## __Part 2__
__`less`__
1. `-N`\
__Example 1__\
_Command_
![Image](lessNumCommand.png)
_Output_
![Image](lessNum.png)
* This command prints out the file but adds numbering to each line.
* This is useful because you can search the text via line number now.\
__Example 2__\
_Command_
![Image](lessNumCommandTwo.png)
_Output_
![Image](lessNumTwo.png)
* Same as the other example, the command adds line numbering.
* It is useful because you can `ctrl+f` and search line numbers.\
__Source__\
* I found this option through the use of the `man less` command
* in VSCode.
2. `-K`\
__Example 1__\
_Command_
![Image](lessQuitCommand.png)
_Output_
![Image](lessQuit.png)
* This command lets you use an interruptable(`Ctrl+C`) to exit out of `less`.
* This is useful because the only way to exit `less` is with `q` but
* now you have a second option to leave `less`.  \
__Example 2__\
_Command_
![Image](lessQuitCommandTwo.png)
_Output_
![Image](lessQuitTwo.png)
* Same as the other example, this command lets you use `Ctrl+C` to exit
* out of `less`.
* This is useful because you can use the normal interruptable `Ctrl+C`
* with another command.
__Source__\
* I found this option through the use of the `man less` command
* in VSCode.
