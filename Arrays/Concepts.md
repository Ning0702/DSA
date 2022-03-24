## What is an Array

1. An array is a collection of items. 

2. The items could be integers, strings, objects.

```java
//main
    DVD[] dvdCollections = new DVD[12];
    
class DVD {
    private String name;
    private int year;
    
    constructor
}
```

3. The items are stored in neighboring (contiguous) memory locations. Because they are stored together, checking through the entire collection of items is straightforward.

---------------------

Primitive operations:

1. write items in the array

   ```java
   //创建一个object，以便放入object 的 array中
   DVD firstDVD = new DVD("Gone in the wind", 1985);
   
   //放入index是7的位置
   dvdCollections[7] = firstDVD;
   ```

​		或者直接用 loop（for） 向 array 中写数据。而不能用增强for，因为需要具体的index确定保存位置。

2. read items from the array

   ```java
   System.out.println(dvdCollections[7]);
   ```

   如果该位置没有内容，就返回默认值，针对此类型是null。（int-0，double-0.0，boolean-false）

​		或者用loop （for，或增强for）从 array中读数据。

---------------------

Capacity & Length

1. Capacity 整个array的长度

   从0 到 array.length - 1是其index范围，防止ArrayIndexOutOfBoundsException

   capacity一旦确定，不能改变。

2. Length  实际存储了多少。可以用length作为记录大小的变量variable

   ```java
   int[] arr = new int[6];
   
   int length = 0;
   
   for(int i = 0; i < 3; i++){
       arr[i] = i * i;
       length++;
   }
   System.out.println(length);
   ```

   

## Basic properties of Arrays





## Implementing basic Array operations





## Simple programming techniques with Arrays