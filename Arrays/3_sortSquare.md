题目：

977. Squares of a Sorted Array

Given an integer array `nums` sorted in **non-decreasing** order, return *an array of **the squares of each number** sorted in non-decreasing order*.

方法1： 双指针思路 two-pointers

1. 因为是升序排列，所以比较两端绝对值，把绝对值大的平方，放入新array里
2. 然后移动对应的指针

```java
class Solution {
    public int[] sortedSquare(int[] nums){
        int length = nums.length;
        int[] result = new int[length];
        int left = 0;
        int right = length - 1;
        
        for(int i = length - 1; i >= 0; i--){
            if(Math.abs(nums[left]) > Math.abs(nums[right])){
             	square = nums[left];
                left++;
            } else {
                square = nums[right];
                right--;
            }
            result[i] = square * square;
        }
        return result.
    }
}
```



方法2：Arrays的方法 （别忘了s）

```java
class Solution {
    public int[] sortedSquares(int[] nums) {
        for(int i = 0; i < nums.length; i++){
            nums[i] = nums[i] * nums[i];
        }
        Arrays.sort(nums);
        return nums;
    }
}
```



方法3：冒泡排序（效率很低）

```java
class Solution {
    public int[] sortedSquares(int[] nums) {
        for(int i = 0; i < nums.length; i++){
            nums[i] = nums[i] * nums[i];
        }
        for(int i = 0; i < nums.length - 1; i++){
            for(int j = 0; j < nums.length - 1 - i; j++){
                if(nums[j+1] < nums[j]){
                    int temp = nums[j];
                    nums[j] = nums[j+1];
                    nums[j+1] = temp;
                }
            }
        }
        return nums;
    }
}
```



