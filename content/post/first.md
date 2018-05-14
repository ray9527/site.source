---
title: "for循环的几种形式"
date: 2018-05-14T17:33:12+08:00
draft: false
---


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