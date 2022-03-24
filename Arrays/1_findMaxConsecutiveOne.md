题目：

Given a binary array `nums`, return *the maximum number of consecutive* `1`*'s in the array*.

解释：

binary array不是二维数组（two-dimensional array)，而是只保存二进制数的数组

思路：

1. 要有不断loop，要有变量count来计每一段的数
2. 因为有比较最大的count，要有max来记录比较count之间的最大值
3. for循环，可以在 == 1时，不断比较和更新max（方法1，但是比较耗内存），也可以在!=1时更新以下max，同时在最后返回时二次比较，以防止数组结尾为1，max没有及时被更新（方法二，多一个步骤）
4. Math.max(num1, num2) 用起来

方法1：

```java
class Solution {
    public int findMaxConsecutiveOnes(int[] nums) {
        int count = 0;
        int max = 0;
        for(int i = 0; i < nums.length; i++){
            if(nums[i] == 1) {
                max = Math.max(++count, max);
            } else {
                //check whether max saves the maximum numbers
                count = 0;
            }
        }
        //并非单纯传max回去，而是传再次比较的结果回去
        return max;
    }
}
```



方法2：

```java
class Solution {
    public int findMaxConsecutiveOnes(int[] nums) {
        int count = 0;
        int max = 0;
        for(int i = 0; i < nums.length; i++){
            if(nums[i] == 1) {
                count++;
            } else {
                //check whether max saves the maximum numbers
               max = Math.max(count, max);
                count = 0;
            }
        }
        //并非单纯传max回去，而是传再次比较的结果回去，这样就保证在结束为1时，max得到更新
        return Math.max(count, max);
    }
}
```

