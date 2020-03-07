# Remove Duplicates from sorted array

Given a sorted array nums, remove the duplicates in-place such that each element appear only once and return the new length.

**Note : Do not allocate extra space for another array, you must do this by modifying the input array in-place with O(1) extra memory.**

```
Example 1:

Given nums = [1,1,2],

Your function should return length = 2, with the first two elements of nums being 1 and 2 respectively.

It doesn't matter what you leave beyond the returned length.

Example 2:

Given nums = [0,0,1,1,1,2,2,3,3,4],

Your function should return length = 5, with the first five elements of nums 
being modified to 0, 1, 2, 3, and 4 respectively.

It doesn't matter what values are set beyond the returned length.
```

### Implementation 1 : 

```java
import java.util.Arrays;
import java.util.HashSet;
import java.util.Set;

public class App {

	public static void main(String[] args) {
		int[] nums = {1, 1, 2};
		removeDuplicates(nums);
		System.out.println(Arrays.toString(nums));
	}
	
	public static int removeDuplicates(int[] nums) {
          Set<Integer> set = new HashSet<>();
          int index = 0;
          for(int i : nums){
            if(!set.contains(i)){
                set.add(i);
	        nums[index++] = i;	
             } 
          }
         return index;
       }

}
```
The above implementation have Runtime Complexity of O(n) but it uses extra space O(d), where d is the number of distinct elements in the input array.

```
Runtime Complexity = O(n)
Space Complexity   = O(d)
```

### Implementation 2 :

```java
import java.util.Arrays;

public class App {

	public static void main(String[] args) {
		int[] nums = {1, 1, 2};
		removeDuplicates(nums);
		System.out.println(Arrays.toString(nums));
	}
	
	public static int removeDuplicates(int[] nums) {
	   int index = 1;
	   for(int i = 1; i < nums.length; i++){
		if(nums[i] != nums[i-1])
		   nums[index++] = nums[i];
	   }
           return index;  
       }
}
```
The above implementation have Runtime complexity of O(n) and space complexity of O(1)

```
Runtime Complexity = O(n)
Space Complexity   = O(1)
```
