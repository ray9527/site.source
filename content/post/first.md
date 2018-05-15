---
title: "for循环的几种形式"
date: 2018-05-14T17:33:12+08:00
draft: false
---

比较了下普通for循环、iterator循环、增强for循环，主要看下增强for循环的原理：
<!--more-->
``` java
public static void main(String[] args) {
    List<Integer> list = new ArrayList<>();
    list.add(1);
    list.add(2);
    list.add(3);
    //普通for循环
    for (int i = 0;i < list.size(); i++) {
        System.out.println(list.get(i));
    }
    //iterator循环
    for (Iterator i = list.iterator(); i.hasNext();) {
        System.out.println(i.next());
    }
    //增强for循环
    for (Integer i : list) {
        System.out.println(i);
    }
}
```
编译后的代码：
``` java
public static void main(String[] args) {
        for(int i = 0; i < list.size(); ++i) {
            System.out.println(list.get(i));
        }

        Iterator var3 = list.iterator();

        while(var3.hasNext()) {
            System.out.println(var3.next());
        }

        var3 = list.iterator();

        while(var3.hasNext()) {
            Integer i1 = (Integer)var3.next();
            System.out.println(i1);
        }

    }
```
> 可以看到增强for循环底层还是根据iterator来实现的
