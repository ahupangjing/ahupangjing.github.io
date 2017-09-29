---
layout:     post
title:      "Python基本语法"
subtitle:   " \"Hello Python\""
date:       2017-09-29 18:20:00
author:     "PJ"
header-img: "img/post-bg-2015.jpg"
catalog: true
tags:
    - python
---
## python
大学时候学的C语言，选修了java，自学了C#,一直到现在主要使用java（Server）以及C#（Client）的开发，经常听说python有多好的言语，所以就在下班之余学习了一下
，本文主要记录学习以便于复习之用，书籍--《python编程：从编程到实战》，网上找的电子书,当然如果你找不到也可以邮箱联系我。

## 语法部分

#### 从列表中删除元素
del是删除并且不能再使用
pop是删除之后可以再次使用
remove是在不了解索引的情况下，可以实现直接删除值

#### 排序
sort排序，永久性的排序（降序），sort(reverse=True)（升序，注意，True的首字母必须大写）
sorted排序，是临时排序，并不影响原始的显示结果

#### 列表
列表可以看作C语言中的数组，做列表的操作与对数组的操作完全一致

##### 列表解析
> `numbers=[value**3 for value in range(1,11)]`<br>
> `print(numbers)`
##### 非列表解析
>`numbers1=[]`<br>
>`for num in range(1,11):`<br>
	>`numbers1.append(num**3)`	
	
结果都是求取1-10的三次方，列表解析没有冒号存在

##### 复制列表

>`>>> squares_b=squares  #这种直接赋值只是将squares_b指向square的内存地址。并没有真正分配内存空间，所以在修改任何一个会导致另一个的改变`<br>
>`>>> print(squares_b)`<br>
>`[1, 4, 9, 16, 25, 36, 49, 64, 81]`<br>
>`>>> print(squares)`<br>
>`[1, 4, 9, 16, 25, 36, 49, 64, 81]`<br>
>`>>> squares_b.append('a')`<br>
>`>>> print(squares)`<br>
>`[1, 4, 9, 16, 25, 36, 49, 64, 81, 'a']`<br>
>`>>> print(squares_b)`<br>
>`[1, 4, 9, 16, 25, 36, 49, 64, 81, 'a'] #所以导致表象上看修改他们之中的任何一个，另外一个也会被改变`<br>


>`>>> sq=squares[:]  #这种方式是复制的同时并且分配内存地址`<br>
>`>>> print(sq)`<br>
>`[1, 4, 9, 16, 25, 36, 49, 64, 81, 'a']`<br>
>`>>> sq.append(2)`<br>
>`>>> print(sq)`<br>
>`[1, 4, 9, 16, 25, 36, 49, 64, 81, 'a', 2] #向sq中添加元素并不会影响squares内值的改变`<br>
>`>>> print(squares)`<br>
>`[1, 4, 9, 16, 25, 36, 49, 64, 81, 'a']`<br>


#### 元组（tuple）(元组的值不能修改，想要改变元组的值只能给元组变量重新赋值)

元组的定义:> `num=(100,200,300,400,500)`<br>
> `>>> print(num)`<br>
> `(100, 200, 300, 400, 500, 600)`<br>
> `>>> print(num[4])`<br>
> `500`<br>
> `>>> num[0]=1`<br>

> Traceback (most recent call last):
>  File "<pyshell#204>", line 1, in <module>
>  num[0]=1
TypeError: 'tuple' object does not support item assignment
> `>>> for value in num:
	print(value)`
	
给元组变量赋值
> `>>> num=('aa','bb','cc','dd')'<br>
> '>>> print(num)'<br>
> '('aa', 'bb', 'cc', 'dd')`<br>

由于元组使用的是小括号，在数学中，有时候需要使用小括号来指定计算顺序，例如(2+3)/5，这时候优先计算2+3，然后再除以5。在python中，小括号同样指定计算顺序，在定义只有一个元素的元组时就会产生歧义。因此，使用以下方法定义一个只含有一个元素的元组。

> `>>> a = (1,) #定义元组a `<br>
> `>>> b = ('Tom',) #定义元组b `<br>
> `>>> c = (1) #定义c `<br>
> `>>> d = ('Tom') #定义d `<br>
> `>>> print(type(a)) #打印a的类型 <class 'tuple'> `<br>
> `>>> print(type(b)) #打印b的类型 <class 'tuple'> `<br>
> `>>> print(type(c)) #打印c的类型 <class 'int'>`<br> 
> `>>> print(type(d)) #打印d的类型 <class 'str'>`<br>


