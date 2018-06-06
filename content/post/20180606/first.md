---
title: "集合转数组 toArray 方法注意点"
date: 2018-06-06T15:42:50+08:00
draft: false
---
集合转数组 toArray 方法注意点：

<!--more-->

```java
private static void toArrayTest() {
        List<Integer> list = new ArrayList<>(Arrays.asList(1,2,3,4,5));
        /*
            使用带参的toArray方法的几个注意点
            1.如果 array.length = list.size()，则将传入的数组作为容器存放集合数据
            2.如果 array.length > list.size()，将传入的数组作为容器存放集合数据，同时会将 array[list.size()] 置为null
            3.如果 array.length < list.size()，则重新生成一个数组返回，原数组元素均为null
         */
        Integer[] x = new Integer[3];
        Integer[] y = new Integer[5];
        Integer[] z = new Integer[7];
        list.toArray(x);
        list.toArray(y);
        list.toArray(z);
        System.out.println(Arrays.toString(x)); // [null, null, null]
        System.out.println(Arrays.toString(y)); // [1, 2, 3, 4, 5]
        System.out.println(Arrays.toString(z)); // [1, 2, 3, 4, 5, null, null]
    }
```
