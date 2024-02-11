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

