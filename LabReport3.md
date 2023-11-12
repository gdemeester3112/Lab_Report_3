# This is my code for a failure-inducing input for the buggy program, as a JUnit test and any associated code

## This is the code:

```
  static void reverseInPlace(int[] arr) {
    for(int i = 0; i < arr.length; i += 1) {
      arr[i] = arr[arr.length - i - 1];
    }
```
## And the failure-inducing JUnit test

```
@Test 
	public void testFiveInPlace() {
    int[] input1 = {1,2,3,4,5};
    ArrayExamples.reverseInPlace(input1);
    assertArrayEquals(new int[]{5,4,3,2,1}, input1);
	}
```

# This is my code for an input that doesn’t induce a failure, as a JUnit test and any associated code 

## This is the code

```
  static void reverseInPlace(int[] arr) {
    for(int i = 0; i < arr.length; i += 1) {
      arr[i] = arr[arr.length - i - 1];
    }
  }
```

## And the test that doesnt fail:

```
  @Test 
	public void testOneInPlace() {
    int[] input1 = {1};
    ArrayExamples.reverseInPlace(input1);
    assertArrayEquals(new int[]{1}, input1);
	}
```

# These are the two resutls I got:

## Fail inducing test:

![Image](Fail test.png)

# No Fail inducing test:

![Image](No fail test.png)

# This is the code before:

```
  static void reverseInPlace(int[] arr) {
    for(int i = 0; i < arr.length; i += 1) {
      arr[i] = arr[arr.length - i - 1];
    }
  }
```

# This is the code after:

```
  static void reverseInPlace(int[] arr) {
    for(int i = 0; i < arr.length / 2; i += 1) {
      int temp = arr[i];
      arr[i] = arr[arr.length - i - 1];
      arr[arr.length i - 1] = temp;
    }
  }

```

> This code fixes the reverseInPlace because it swaps the elemts at position i and arr.length - i - 1 and stores it in a temporary variable. This ensures that every element is only moved once so it is reversed. The code beofre makes it so that once you swap past the middle the array will start swapping elements back that have already been modified so for example if i is the last element in the array, the first element which has the value of the last element will be assigned to the last element aswell.

# These are my examples of using 


