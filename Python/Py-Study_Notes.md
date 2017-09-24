Python Study notes
==================
优雅、明确、简单

[廖雪峰的官方网站-Python入门教程][1]

## Python基础

### 数据类型与变量

* 整数，无大小限制
* 浮点数，大数需要用科学计数法表示
		
		e.g. 0.000012可以写成1.2e-5
* 字符串

		'' 或 ""括起来的任意文本，转义字符\，
		Python还允许用r''表示''内部的字符串默认不转义，是什么就输出什么
		'''可以打印多行内容，前面可加r
* 布尔值，`True` or `False`
* 空值， `None`
* 变量，同一个变量可以反复赋值，而且可以是不同类型的变量
* 常量，通常用全部大写的变量名表示常量

		'/' 除法计算结果是浮点数，即使是两个整数恰好整除，结果也是浮点数
		'//'称为地板除，两个整数的除法仍然是整数
		'%' 整数相除，取余数

### 字符串和编码

* 字符编码

	*`ASCII` --> `Unicode` --> `UTF-8`*

		ASCII   编码对应 1byte,只能表达一些符号、数字、字母，127个
		Unicode 编码，通常2byte,生僻字需要4byte把所有语言都统一到一套编码里，避免乱码问题
		UTF-8   可变长编码, 从而节省存储空间
	>从文件读取的UTF-8字符被转换为Unicode字符到内存里，编辑完成后，保存的时候再把Unicode转换为UTF-8保存到文本
	>
	>浏览网页的时候，服务器会把动态生成的Unicode内容转换为UTF-8再传输到浏览器
	>
	>浏览器一般使用的是UTF-8

### Python字符串


Python字符串以Unicode编码，即支持多语言

- ord()函数获取字符的整数表示，chr()函数把编码转换为对应的字符。

- Python的字符串类型是str，在内存中以Unicode表示

- Python对bytes类型的数据用带b前缀的单引号或双引号表示,要注意区分'ABC'和b'ABC',
  前者是str，后者虽然内容显示得和前者一样，但bytes的每个字符都只占用一个字节

- Unicode表示的str通过encode()方法可以编码为指定的bytes.

		'ABC'.encode('ascii')` -> `b'AbC'
		'中文'.encode('utf-8')` -> `b'\xe4\xb8\xad\xe6\x96\x87'


- 如果我们从网络或磁盘上读取了字节流，那么读到的数据就是bytes。要把bytes变为str，就需要用decode()方法

		b'\xe4\xb8\xad\xe6\x96\x87'.decode('utf-8') -> '中文'

- len('中文') == 2[计算str的字符数]， len('中文'.encode('utf-8')) == 6[计算字符存储时的字节数]
	
- 尽量使用 `UTF-8` 对str和bytes进行转换，避免混乱


- Python进行源码保存时，尽量在开头使用如下格

		#!/usr/bin/env python3
		# -*- coding: utf-8 -*-
- 申明了UTF-8编码并不意味着你的.py文件就是UTF-8编码的，必须并且要确保文本编辑器正在使用UTF-8 without BOM编码


### 格式化输出

-  `'Hi, %s, you have $%d.' % ('Michael', 1000000)` --> `Hi, Michael, you have $1000000`

	>常见的占位符有：
	>
	>     %d	整数
	>     %f	浮点数
	>     %s	字符串
	>     %x	十六进制整
	>格式化整数和浮点数还可以指定是否补0和整数与小数的位数
	> 
	>     print('%02d-%02.1f' % (1, 1.0003)) --> 01-1.0

## Python的数组
list和tuple是Python内置的有序集合，一个可变，一个不可变。定义区别是前者[]，后者()

- list可以内嵌list变量，将list当成其中一个变量

		list变量：classmates = ['Michael', 'Bob', 'Tracy']
		classmates[-1] == 'Tracy'，				倒序取值
		classmates.append('Adam')，				末尾添加
		classmates.insert(1, 'Jack')，			classmates[1]处插入，后面后移
		classmates.pop(), 						末尾删除
		classmates.pop(1)，						classmates[1]删除，后面前移
		
- tuple不可变，指的是“指向不变”。没有append()，insert()，pop()等方法

		tuple变量：t = ('a', 'b', ['A', 'B'])	但是t[2][1]/t[2][1]可以改变

	
[1]: https://www.liaoxuefeng.com/wiki/0014316089557264a6b348958f449949df42a6d3a2e542c000 "廖雪峰的官方网站-Python教程"