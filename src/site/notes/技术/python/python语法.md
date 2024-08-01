---
{"dg-publish":true,"permalink":"/技术/python/python语法/","dgPassFrontmatter":true}
---

# python环境
## 什么是python环境
python解释器
库和模块
### 什么是python解释器
他用来执行python代码
### 什么是库和模块
#### 什么是模块
其实就是python文件
#### 什么是库
多个模块的集合。
## 如何配置环境
vscode https://code.visualstudio.com/sha/download?build=stable&os=win32-x64-user
miniconda https://repo.anaconda.com/miniconda/Miniconda3-latest-Windows-x86_64.exe
### 如何配置vscode和miniconda
# python语法
## 什么是import
用于导入其他模块或库。
```
import math
result = math.sqrt(16)
```
## 什么是字典
字典由一个个元素构成。元素由键值对构成。
```
my_dict = {
    "name": "Alice",
    "age": 30,
    "city": "New York"
}
```
在这个字典中，存在三个键，`name`、`age` 与 `city`，这些键分别对应值 "Alice"，30 和 "New York"
```
name = my_dict["name"]  # name will be "Alice"
```
https://dl.google.com/android/repository/platform-tools-latest-windows.zip?hl=zh-cn
## .代表了什么
可以简单翻译为`的`
当我们看到了os.，代表他使用了os模块中的一个方法、属性或者功能
```
os.getcwd() 
os.chdir("/path/to/new/directory")
os.listdir("/path/to/new/directory")
os.mkdir("/path/to/new/directory")
os.remove("/path/to/new/directory")
```
## 为什么使用`os.environ['path'] = "platform-tools;" + os.environ['path']`
这段代码的功能是将platform-tools文件夹添加到系统环境变量中。系统环境变量是一个包含多个目录路径的列表。操作系统将在这些目录中查找可执行文件。通过在环境变量中添加新的目录，应用程序可以更容易色使用该目录中的可执行文件
获取当前系统环境变量的值 `os.environ['path']
将platform-tools文件目录添加到系统环境变量的开头 `"platform-tools;" + os.environ['path']
更新系统环境变量 `os.environ['path'] = "platform-tools;" + os.environ['path']`
这样我们就使得应用程序（python）能够轻松调用platform-tools 下的可执行文件
## python如何使用可执行文件
python调用subprocess库，subprocess调用cmd，cmd再去调用可执行文件
## 什么是python函数
函数是一组组织好的，可以重复使用的代码，用于执行特定的任务或者计算值。可以使用`def` 关键字来定义一个函数。比如
```
def greeting(name):
	return f'Hello,{name}'
```
该函数接受一个参数`name`。使用`return` 关键字返回一个基于参数的字符串。比如传递一个参数`alice`
```
result = greeting('alice') #返回Hello, Alice!
print(result) #直接在屏幕上打印出Hello, Alice
```
python提供了许多内置参数，比如print()用来打印
函数可以有多个参数，也可以有可选参数或者默认参数值。
## 什么时候使用缩进（tab）
1. 函数定义 当定义函数时，要缩进函数体内的所有语句
2. 控制流语句 if、for、while需要再代码块内缩进
3. 异常处理语句 需要缩进相应代码块
4. 类定义 需要缩进类体内的所有语句
## 什么时候使用换行（回车）
当一条语句结束，要开始下一条语句时要使用换行
在函数定义、控制流语句、异常处理语句和类定义中，新的代码应该从新的一行开始且需要缩进
## 什么是类
类是一个模版，他用于描述具有相同属性和方法的对象
要定义一个类，要使用关键字`class`，后跟类名，`:`以及一个缩进的代码块
## 什么是构造函数
`__init__`是一个特殊的函数（方法），被称为构造函数（初始化函数）。他会在创建类的实例（对象）时自动调用。他可以用于在创建对象时设置对象的初始状态、分配资源或者其他与对象相关的操作
定义`__init__`函数必须遵循以下格式：
```
class Mycalss():
	def __init__(self,param1,param2,.....)
	#构造函数体，初始化操作
```
## 什么是对象（实例）
他由类实例化创建
类 一组具有相同属性和方法（函数）的对象的模版。
## self是什么
他就是对象。他是一个指向类对象的引用。
## 类在实例化对象的时候需要什么参数
创建对象所需的参数与构造函数的参数相同。但是实际调用构造函数时，python会自动传递self参数.
`__new__`方法负责创建并返回类的对象。当调用该方法时，我们传递是类而不是实例，因为实际上我们调用该方法时还没有创建对象
```
class MyClass:
    def __init__(self, param):
        self.param = param


my_instance = MyClass.__new__(MyClass)  # 新建一个实例，但没有执行__init__
my_instance.__init__(my_instance,"a_parameter")     # 然后手动调用__init__并提供self参数

my_instance = MyClass(param)
```
## `:`的作用？
控制结构，函数定义和类定义后都需要加`:`，并且冒号后需要增加缩进
## `()`的作用
函数 紧跟在函数名后的括号包含传递给函数的参数
类 实现类继承时，父类放在类名后的括号内
元组 `t = (1,2,3)`
表示优先顺序 `result = (1 + 2) * 3  # 结果为 9，因为先计算括号内的加法`
![image.png](https://raw.githubusercontent.com/DapperZhengLong/imgroom/main/obsidian/20240801183523.png)
