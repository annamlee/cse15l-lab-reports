# Lab Report 2 - Servers and Bugs
Here is a report covering the labs from week 2 and week 3!

## Part 1
Here is a web server called `StringServer`. This server keeps track of a single string that gets added to by incoming requests. The input comes from the user-inputted URL. 
The requests look like `/add-message?s=<string>`. Whatever string is inputted after the `=` will be concatenated to the existing strings, along with a new line (`\n`). The web page should display the entire history of strings inputted, each on a new line.

Here is the code for `StringServer`:
![image](StringServer.png)

Here is an example of successfully concatenating a string using `StringServer`.
![image](cat-string.png)
In order for the String `"how are you"` to be concatenated to the existing string of `"hello"` and be displayed on the webpage, the method `handleRequest(URI url)` is called. Relevant arguments for this method include the URI object, which is `http://localhost:4000/add-message?s=how are you` in this case. This goes through the method and gets split up into relevant Strings. In lines 13-21 of `StringServer`, the url gets split up and the value of the string gets concatenated to the existing string in line 17. In this scenario, `how are you\n` gets concatenated to `hello`. This causes the value of `msg`, the variable storing all the string requests, to update to store `hello\n how are you\n`. Therefore, when `msg` is returned at the end of the method, the webpage displays both the current stsing request and any previoius requests.

Here is an example of unsuccessfully concatenating a string on `StringServer`, resulting in a 404 error.
![Image](404-not-found.png)

In this screenshot, the method `handleRequest(URI url)` is called. Relevant arguments for this method include the URI object, which is `http://localhost:4000:add-messge?s=123` in this case. This goes through the method and gets split up into relevant strings. In lines 13-21 of `StringServer`, the url gets split up and into relevant values. On line 14, the code checks if `add-message` is in the url. Because of the typo in the url, `add-message` is not in the url, and the else block finishes. It reaches the end of the method and `404 Not Found!` gets returned at line 22. Because the url did not contain `add-message`, the value of `msg` does not change from this request. The value of `msg` only changes if the url is in the format `/add-message?s=<string>`.

## Part 2
Here is the method `reverseInPlace(int[] arr)` in `ArrayExamples.java`.
![Image](buggy-reverse-in-place.png)

A failure-inducing input for this method is `int[] input2 = {1,2,3}`.
Here is the JUnit test for this failure-inducing input:
```
@Test
public void testReverseInPlace2(){
  int[] input2 = {1,2,3};
  ArrayExamples.reverseInPlace(input2);
  assertArrayEquals(new int[]{3,2,1}, input2);
}
```

An input that does not induce a failure is `int[] input = {5}`. 
Here is the JUnit test for this input:
```
@Test
public void testReverseInPlace(){
  int[] input1 = {5};
  ArrayExamples.reverseInPlace(input1);
  assertArrayEquals(new int[]{5}, input1);
}
```

Running the JUnit tests convey that the symptom of the failure-inducing input is `{3,2,3}`. The JUnit test displays an error message for running `testReverseInPlace2()`, stating that the expected array and the actual array were different. Because this was the only test that failed, it means that `testReverseInPlace()` passed and the expected array matched with the actual outputted array.
![Image](reverse-array-failed-test.png)

Here is the loop in `reverseInPlace(int[] arr)` that was causing the bug:
```
for(int i = 0; i < arr.length; i += 1){
  arr[i] = arr[arr.length-i-1];
}
```

Here is the modified for loop which fixes the bug:
```
for(int i = 0; i < arr.length/2; i += 1) {
  int temp = arr[i];
  arr[i] = arr[arr.length-i-1];
  arr[arr.length-i-1] = temp;
}
```

This change to the code addresses the issue because it only iterates through half of the array and swaps two indices per iteration. The first iteration swaps the first and last elements, the second iteration swaps the second and second to last element, etc. The original loop iterated through the entire array changing one element at a time, however, this caused an error because by the time the loop reached the second half of the array, the original elements in the previous indices are gone, having already been reassigned to the reversed values. This code edit avoids this issue by swapping two elements in one iteration.

## Part 3
During lab in week 2, I learned that ports for web serversers could get overloaded when too many people try to connect to the same one. Because there were so many people trying to use the port 4000, some people could not connect and had to instead choose another number between 1024 and 49151.
