---
{"dg-publish":true,"permalink":"//python/python/","dgPassFrontmatter":true}
---

# 环境配置


## vscode
https://code.visualstudio.com/sha/download?build=stable&os=win32-x64-user
## miniconda

https://repo.anaconda.com/miniconda/Miniconda3-latest-Windows-x86_64.exe

## 语法
### 编码
默认情况下，python使用UTF-8编码。
```
# -*- coding: UTF-8 -*-
```
python会将文件先拿UTF-8做字典翻译为数字，再使用Unicode翻译为数字 0100
python会将文件先拿GB2312做字典翻译为数字（和UTF-8做字典翻译成的数字是不一样的）
在vs2022中，我们需要再扩展中安装“Force UTF-8”插件
## 语句
赋值语句：给变量赋值
```
Kumamon = 10
Kumamon = "你好"
```
函数语句：调用一个函数
```
print("Kumamon")
print("Kumamon")
```
条件和循环语句：如果，当，直到。需要缩进
```
if True: 
	print ("1")
```
函数定义：定义个可重复直接的代码块。需要缩进
```
def name(x,y,z):
	r = x + y + z
	return r
```
类定义：定义一个具有属性和方法(函数)的数据结构。需要缩进
```
class Car:
	def __init__(self,x,y):
		self.x = x
		self.y = y
		
```
导入模块：导入已存在的python库已便在代码中使用
```
import math
```
### import 与 from...import
import直接将整个模块、文件夹、文件导入
```
import sys
sys.argv
from sys import argv
argv

def argv():
	return 0
```