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

* In the first code, we were assigning values of newArray to arr. However, every element of the newArray at that point is initialized to 0, so arr is not being reversed but rather assigned to new elements, which are 0. By assigning values of arr to newArray, and then returning the new reversed array, we are fixing the bug.


## Part 2 Researching Grep Command
1. **grep -i** on a directory:
   ```
   (base) MacBook-Pro-46:docsearch-1 aruzhansatybay$ grep -i "water" ./technical/
   grep: ./technical/: Is a directory
   ```
   * This command searches for a specific pattern, in this case: "water", case-insensitively. However, it cannot be used on directories so this output is given.

   **grep -i** on a file:
   ```
   (base) MacBook-Pro-46:docsearch-1 aruzhansatybay$ grep -i "older" ./technical/biomed/1468-6708-3-1.txt
        Older adults are frequently counseled to lose weight,
        non-smoking older adults have investigated the association
        in certain small subsets. A review of 13 studies of older
        Many healthy older adults report gradual weight gain
        number of studies of older persons is fairly small, and
        In older adults, risk factors may have a greater effect
        years of being healthy, in a cohort of older adults for
        modification interventions in older adults.
          65 and older at baseline [ 11 ] . Subjects were recruited
          older men and 30-35 for older women. In Figure 1, the
          categories could be combined for older adults. Since
          older women could be efficient if YHL (but not YOL) was
          interventions for older adults who were merely overweight
          evaluations should be considered critically when older
          33 34 ] . For older adults, the risks associated with
          outcome for a trial of weight loss in older adults
          found for underweight older adults. Clinical trials whose
          average older adult; however, adjustment for detailed
        older adults, especially for women. Future efforts to
        no excess risk for older adults who would be classified as
        obese or underweight older adults, and discouraging trials
        that address older adults who are merely overweight.
   ```
   * This command, when applied to a file, scans for a pattern, in this case, the word "older," and outputs only the lines that contain the target word regardless of the case. This case-insensitive search is highly efficient for word searches. `grep -i`  searches not only for words but patterns which enables a more complex search.
     


