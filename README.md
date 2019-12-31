# Remove Duplicates from sorted array

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
	            nums[index] = i;
	            index++; 	
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

