---
{"dg-publish":true,"permalink":"/技术/python/python语法/","dgPassFrontmatter":true}
---

# python环境
## 什么是python环境
1. python解释器 用来读取和执行python代码
2. 包管理器 用来安装、更新和删除库与模块
3. python库 有时我们也将其称为python模块。他是一系列预先编写好的代码，他可以帮助我们快速实现功能。比如我们使用opencv的库就能实现读取图像的功能
## 如何配置python环境
1. 下载vscode并安装 https://code.visualstudio.com/sha/download?build=stable&os=win32-x64-user
2. 下载miniconda并安装 https://repo.anaconda.com/miniconda/Miniconda3-latest-Windows-x86_64.exe
## 如何使用python环境
# python语法
## 什么是python类
python类是面向对象编程中的一个核心概念。类是一种描述相同属性和方法（函数）的抽象数据类型的蓝图。他包含了对象（类的实例化实例）共享的属性和方法。
### 什么是面向对象编程
他使用对象作为代码的基本单位。对象具有2个主要成分，即属性和方法。他的核心思想是将数据及其操作封装到能够模拟现实世界的对象中，以提高代码的可读性、可扩展性和可维护性
他有3个主要特征
1. 封装 封装是将对象的内部实现细节（属性和方法）隐藏起来
2. 继承 允许新创建的类从已有的类中继承属性和方法
3. 多态 不同类的对象可以使用相同的方法
##### 什么是封装继承和多态
1. 子类多态
```
class Animal:
	def make_sound(self):
		pass
class Dog(Animal):
	def make_sound(self):
		return 'wangwangwang'
class Cat(Animal):
	def make_sound(self):
		return 'miaomiaomiao'
dog = Dog()
dog.make_sound()
cat = Cat()
cat.make_sound()

```
2. 鸭子类型
```
class Dog(Animal):
	def make_sound(self):
		return 'wangwangwang'
class Cat(Animal):
	def make_sound(self):
		return 'miaomiaomiao'
def play_sound(thing):
    print(thing.make_sound())
```
### 什么是属性和方法
属性也被称为成员变量，用于表示类的对象的状态或者数据。他们一般在类的`__init__` 中定义并初始化。
方法也被称为成员函数。方法表示对象的行为，即对象使用的函数。
#### 什么是变量，什么是函数
变量 我们可以将他理解为一个容器（杯子），他可以存储一些值
函数（方法） 函数将一段代码（操作）封装起来，以便重复使用或者执行特定任务。
##### 如何使用变量和函数
```
a = 1
a = 2
a = 3.14
a = '你好'
```
函数使用def关键字进行定义，后跟函数名称和一对圆括号。圆括号内可以包含参数，函数体则已冒号和缩进表示出区域，函数体就是函数的操作,并且使用return返回函数的结果
```
def add(x,y):
	z = x + y
	return z
add(100,200)
```
### 什么是对象，他和类有什么区别
类 他描述了一组具有相似属性和方法的对象，他是一个抽象的概念。类是对象的蓝图（模版），他定义了如何构造（实例化）一个对象，以及对象具有哪些属性和行为，他仅仅表示了如何为程序创造对象
对象 对象是类的实例，由类创建。创建对象时，基于类的定义来创建具体的数下和方法。每个对象都有自己的状态，通常有属性值表示。一个类创造的多个对象会具有相同的方法，但可能会有不同的属性
#### 如何使用一个对象
如果要使用一个对象，首先要有一个定义好的类，该类描述了此对象的特征和行为。接下来才能根据这个类创建一个对象并且使用他。
```
class Penson():
	def __init__(self,name,age):
		self.name = name
		self.age = age
	def say_hello(self):
		print(f'{name},{age}')
zga = Penson(name='zga',age='18')
zga.say_hello()
```
##### python中什么时候使用缩进
缩进用于表示代码块的开始和结束。有以下使用场景
1. 函数
2. 条件、判断与循环语句
3. 异常处理语句
4. 类定义
5. 上下文管理器
###### 什么是代码块
1. 函数中的代码为一个代码块
2. 条件、判断与循环语句中的代码为一个代码块
3. ......
###### 什么是条件语句
```
if x > 5:
	pass
else:
	pass
```
###### 什么是循环语句
for
```
fruits = ["apple", "banana", "orange"]

for fruit in fruits:
    print(fruit)
```
while 
```
while x < 20:
	print(x)
	x = x + 1

```
###### 什么是异常处理语句
异常处理语句是一种用于捕获和处理程序中运行时可能出现的错误或异常的编程结构。运行时的错误可能由于代码编写错误或者外部因素（内存空间不足，硬盘空间不足，文件不存在等等）导致的问题，
1. try
用于放置可能引发异常的代码
2. except
如果捕获到try中引发的异常，定义如何处理他们
3. finally
可选的，不管try是否发生异常，他都要执行
###### 什么是上下文管理器
```
with open('file.txt','r') as file:
	content = file.read()
```