题目：

Given an array `nums` of integers, return how many of them contain an **even number** of digits.

分析：

1. 对每一个元素，用while循环，将每一位上的数字都除以10。只要结果还>10，就一直循环。
2. 将计算的位数数字 %2，判断是even 还是 odd
3. 记得每次取一个元素，都要把count变量归零

方法：

```java
class Solution {
    public int findNumbers(int[] nums) {
        int evens = 0;
        int number = 0;
        
        for(int i = 0; i < nums.length; i++){
            //注意一定要每次清零，不然就会一直累计计算
            int count = 0;
            number = nums[i];
            
            //学习此条件的设定
            while(number != 0){
                //只要除以10就行，取余反倒无法规避个位是0的情况
                number = number / 10;
                 count++;
            }
            if(count % 2 == 0){
                evens++;
            }
        }
        return evens;
    }
}
```



