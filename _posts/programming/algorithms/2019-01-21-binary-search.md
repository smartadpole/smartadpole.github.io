---
layout: article
title:  "「算法」 二分查找"
date:   2019-01-21 18:37:40 +0800
key: binary-search-20190121
aside:
  toc: true
category: [Algorithms, AlgSearch]
---

>要求：待搜索序列有序；  
优势：将原本的线性时间提升到了对数时间范围；  


## 一、 算法讲解
将查找的键和数组（默认升序排列）的中间键作比较，如果被查找的键小于中间键，就在左子数组继续查找；如果大于中间键，就在右子数组中查找，否则中间键就是要找的元素；  
binary_search， lower_bound， equal_range  

[c 示例](#binary_search_code_c)，[python 示例](#binary_search_code_python)  

## 二、 变种
二分查找变种较多，不过它们的“套路”是一样的：  

```c
while (left <= right)
{
    int mid = (left + right) / 2;
    if (array[mid] ? key)
    {
        //... right = mid - 1;
    }
    else
    {
        // ... left = mid + 1;
    }
}
return xxx;
```

1. 首先判断出是返回 left，还是返回 right  
我们知道最后跳出循环的结果是 right = left - 1；最后 right 和 left 一定是卡在"边界值"的左右两边，如果是比较值为 key，查找小于等于（或者是小于）key 的元素，则边界值就是等于 key 的所有元素的最左边那个，其实应该返回 left；`感觉说得不对`{:.warning}  
2. 判断出比较符号  
如果是查找小于等于 key 的元素，则知道应该使用判断符号 >=，因为是要返回 left，所以如果 array[mid] 等于或者大于 key，就应该使用 >= `感觉说得不对`{:.warning}  

- 查找第一个与 key 相等的元素：[c 示例](#binary_search_first_equal_code_c)，  
- 查找最后一个与 key 相等的元素：[c 示例](#binary_search_last_equal_code_c)，  
- 查找最后一个等于或者小于 key 的元素：[c 示例](#binary_search_last_lower_equal_code_c)，  
- 查找最后一个小于 key 的元素：[c 示例](#binary_search_last_lower_code_c)，  
- 查找第一个等于或者大于 key 的元素：[c 示例](#binary_search_first_equal_upper_code_c)，  
- 查找第一个大于 key 的元素：[c 示例](#binary_search_first_upper_code_c)，  

## 三、 关键点
1. 二分的关键就是st和ed两个指针如何移动；需要记住的是，st只会往大的方向移动，ed只会往小方向移动；  
2. mid= st + (ed-st)/2 而不用 mid = (st + ed) / 2 是因为后面的情况当st+ed很大时可能会产生溢出；
3. 注意避免死循环(一般就考虑最后两个数的极端情况)：  
- 当mid = st + (ed-st)/2 时，mid偏向左边（一般求小于等于target的数），所以st必须移动st = mid+1，否则就可能会死循环；  
- 当mid = st + (ed-st)/2 + 1，mid偏向右边（一般是求大于等于target的数），所以ed必须移动ed = mid -1，否则可能死循环
4. 一般来说，如果是求恰好找到的，可以多加一个等于的时候退出  
5. 有时候，我们不好判断到底判断条件里<还是<=的时候，可以把条件限定在2个数A，B（一般来说，此时的mid = A）和target：  
- A（mid） < target，我们需要st还是ed移动  
- A（mid） = target，我们需要st还是ed移动  

二分查找法的写法并不唯一，主要可以变动地方有四处：  
- right 的初始化，可以写成 nums.size() 或者 nums.size() - 1；  
- left 和 right 的关系，可以写成 left < right 或者 left <= right；  
- 更新 right 的赋值，可以写成 right = mid 或者 right = mid - 1；  
- 最后返回值，可以返回 left，right，或 right - 1；  

但是这些不同的写法并不能随机的组合；若right初始化为了nums.size()，那么就必须用left < right，而最后的right的赋值，用哪个都可以，博主偷懒就不写-1了；但是如果我们 right 初始化为 nums.size() - 1，那么就必须用 left <= right，并且right的赋值要写成 right = mid - 1，不然就会出错；所以博主的建议是选择一套自己喜欢的写法，并且记住，实在不行就带简单的例子来一步一步执行，确定正确的写法也行；  

## 四、 实践

-------------------  
 End
{:.warning}  



## 附录
### A 示例
<span id="binary_search_code_c">**1. 二分查找 C 示例**</span>   

```c
/**
 * 二分查找，找到该值在数组中的下标，否则为-1
 */

 //二分查找的递归版本
int binary_search_recursion(const int array[], int low, int high, int key)  
{  
    int mid = (high + low)/2;  
    if(low > high)  
        return -1;  
    else{  
        if(array[mid] == key)  
            return mid;  
        else if(array[mid] > key)  
            return binary_search_recursion(array, low, mid-1, key);  
        else  
            return binary_search_recursion(array, mid+1, high, key);  
    }  
}  

//二分查找的循环版本
static int binarySerach(int[] array, int key) {
    int left = 0;
    int right = array.length - 1;

    while (left <= right)
    {
        int mid = (left + right) / 2;
        if (array[mid] == key)
        {
            return mid;
        }
        else if (array[mid] < key)
        {
            left = mid + 1;
        }
        else
        {
            right = mid - 1;
        }
    }

    return -1;
}
```


<span id="binary_search_first_equal_code_c">**2. 查找第一个与 key 相等的元素 C 示例**</span>   

```c
// 查找第一个相等的元素
static int findFirstEqual(int[] array, int key)
{
    int left = 0;
    int right = array.length - 1;

    while (left <= right)
    {
        int mid = (left + right) / 2;
        if (array[mid] >= key)
        {
            right = mid - 1;
        }
        else
        {
            left = mid + 1;
        }
    }
    if (left < array.length && array[left] == key)
    {
        return left;
    }

    return -1;
}
```

<span id="binary_search_last_equal_code_c">**3. 查找最后一个与 key 相等的元素 C 示例**</span>   

```c
// 查找最后一个相等的元素
static int findLastEqual(int[] array, int key)
{
    int left = 0;
    int right = array.length - 1;

    while (left <= right)
    {
        int mid = (left + right) / 2;
        if (array[mid] <= key)
        {
            left = mid + 1;
        }
        else
        {
            right = mid - 1;
        }
    }
    if (right >= 0 && array[right] == key)
    {
        return right;
    }

    return -1;
}
```
<span id="binary_search_last_lower_equal_code_c">**4. 查找最后一个等于或者小于 key 的元素 C 示例**</span>   

```c
// 查找最后一个等于或者小于key的元素
static int findLastEqualSmaller(int[] array, int key)
{
    int left = 0;
    int right = array.length - 1;

    while (left <= right)
    {
        int mid = (left + right) / 2;
        if (array[mid] > key)
        {
            right = mid - 1;
        }
        else
        {
            left = mid + 1;
        }
    }
    return right;
}
```
<span id="binary_search_last_lower_code_c">**5. 查找最后一个小于 key 的元素 C 示例**</span>   

```c
static int findLastSmaller(int[] array, int key) {

    int left = 0;
    int right = array.length - 1;

    while (left <= right)
    {
        int mid = (left + right) / 2;
        if (array[mid] >= key)
        {
            right = mid - 1;
        }
        else
        {
            left = mid + 1;
        }
    }
    return right;
}
```
<span id="binary_search_first_equal_upper_code_c">**6. 查找第一个等于或者大于 key 的元素 C 示例**</span>   

```c
// 查找第一个等于或者大于key的元素
static int findFirstEqualLarger(int[] array, int key)
{
    int left = 0;
    int right = array.length - 1;

    while (left <= right)
    {
        int mid = (left + right) / 2;
        if (array[mid] >= key)
        {
            right = mid - 1;
        }
        else
        {
            left = mid + 1;
        }
    }
    return left;
}
```
<span id="binary_search_first_upper_code_c">**7. 查找第一个大于 key 的元素 C 示例**</span>   

```c
// 查找第一个大于key的元素
static int findFirstLarger(int[] array, int key)
{
    int left = 0;
    int right = array.length - 1;

    while (left <= right)
    {
        int mid = (left + right) / 2;
        if (array[mid] > key)
        {
            right = mid - 1;
        }
        else
        {
            left = mid + 1;
        }
    }
    return left;
}
```

<span id="binary_search_code_python">**8. 二分查找 python 示例**</span>  

```c

```

### B 参考文献  
[^1]: Bruce Eckel, Chuck Allison 著. 刘宗田, et al. 译.  C++ 编程思想[M]. 北京:机械工业出版社, 2016.  
