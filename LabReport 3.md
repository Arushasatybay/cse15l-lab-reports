# Lab Report 3
## Part 1

### Failure Inducing Input:
```
import static org.junit.Assert.*;
import org.junit.*;

public class ArrayTests {
@Test
  public void testReversed2() {
    int[] input1 = { 3, 5, 7};
    assertArrayEquals(new int[]{7, 5, 3 }, ArrayExamples.reversed(input1));
  }
}
```

### An Input That Doesn't Induce a Failure:
```
import static org.junit.Assert.*;
import org.junit.*;

public class ArrayTests {
	@Test 
	public void testReverseInPlace() {
    int[] input1 = { 3 };
    ArrayExamples.reverseInPlace(input1);
    assertArrayEquals(new int[]{ 3 }, input1);
	}
}
```
### The symptom:
![Screenshot](https://github.com/Arushasatybay/cse15l-lab-reports/blob/main/Screenshot%202024-02-10%20at%206.06.43%20PM.png?raw=true)

### The bug:
```
public class ArrayExamples {

  // Changes the input array to be in reversed order
  static void reverseInPlace(int[] arr) {
    for(int i = 0; i < arr.length; i += 1) {
      arr[i] = arr[arr.length - i - 1];
    }
  }

  // Returns a *new* array with all the elements of the input array in reversed
  // order
  static int[] reversed(int[] arr) {
    int[] newArray = new int[arr.length];
    for(int i = 0; i < arr.length; i += 1) {
      arr[i] = newArray[arr.length - i - 1];
    }
    return arr;
  }
}
```

```
public class ArrayExamples {

  // Changes the input array to be in reversed order
  static void reverseInPlace(int[] arr) {
    for(int i = 0; i < arr.length; i += 1) {
      arr[i] = arr[arr.length - i - 1];
    }
  }

  // Returns a *new* array with all the elements of the input array in reversed
  // order
  static int[] reversed(int[] arr) {
    int[] newArray = new int[arr.length];
    for(int i = 0; i < arr.length; i += 1) {
      newArray[i] = arr[arr.length - i - 1];
    }
    return newArray;
  }
}
```
![PassedTests](https://github.com/Arushasatybay/cse15l-lab-reports/blob/main/Screenshot%202024-02-10%20at%206.15.20%20PM.png?raw=true)


