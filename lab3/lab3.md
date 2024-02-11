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
  
