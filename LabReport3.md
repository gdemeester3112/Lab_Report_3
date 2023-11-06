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
