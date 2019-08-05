
# Task1  Python环境搭建、基础知识、Python数值

## 1. 环境搭建
### 1.1 anaconda环境配置
### 1.2 解释器——用来执行`.py`文件
1. CPython 官方解释器，使用最广泛
2. IPython 基于CPython之上的一个交互式解释器，增强了CPython的功能
3. PyPy 采用JIT技术，对Python代码进行动态编译（不是解释），显著提高了Python代码的执行速度
4. Jython 运行在Java平台上的Python解释器，可以直接把Python代码编译成Java字节码执行
5. IronPython 运行在微软.Net平台上的Python解释器，可以把Python代码编译成.Net的字节码

## 2. Python初体验
### 2.1 print用法
`print()`


```python
print('hello, world')
print('first','second','third')
print(40)
print(50+60)
print('50 + 60 =',50+60)
```

    hello, world
    first second third
    40
    110
    50 + 60 = 110
    

### 2.2 input的用法
`input()`


```python
name=input()
name
print(name)
```

    linxi
    linxi
    


```python
name=input()
print('hello',name)
```

     linxi
    

    hello linxi
    


```python
name=input('Please enter your name:')
print('Hello',name)
```

    Please enter your name: Linxi
    

    Hello Linxi
    

* 利用`print()`输出`1024 * 768 = xxx`：


```python
print('1024 * 768 =',1024*768)
```

    1024 * 768 = 786432
    

## 3. Python基础
### 3.1 python变量特性+命名规则
* 变量名必须是大小写英文、数字和_的组合，且不能用数字开头
* 变量名不能包含空格
* 不能使用Python关键字和函数名
* Python是动态语言，变量本身类型不固定，在定义变量时不需要制定变量类型

### 3.2 注释方法
* 以#开头：`#这是一行注释`
* 多行注释  
`"""first line  
secondline  
third line"""  
'''first line  
secondline  
third line'''`

### 3.3 python中“：”作用
* 当语句以冒号`:`结尾时，缩进的语句视为代码块

### 3.4 dir()和help()
* dir() 用来查询一个类或者对象所有属性
* help() 了解模块、类型、对象、方法、属性的详细信息  

#### 举例
* 查看python所有的关键字：help("keywords")
* 查看python所有的modules：help("modules")
* 查看python所有的modules中包含指定字符串的modules： help("modules yourstr")
* 查看python中常见的topics： help("topics")
* 查看python标准库中的module：import os.path + help("os.path")
* 查看python内置的类型：help("list")
* 查看python类型的成员方法：help("str.find") 
* 查看python内置函数：help("open")

### 3.5 import使用
import module1[, module2[,... moduleN] #导入模块  
 from modname import name1[, name2[, ... nameN]] #导入模块中的指定部分  
 from … import * #导入模块全部内容

### 3.6 pep8
PEP8是Python的编码规范，其中心在于提高代码的可读性
详见https://www.jianshu.com/p/8f6d38551559

## 4. python数值基本知识
### 4.1 数值类型


```python
#整数
a=1
b=-42536
c=0xffacd45
print(a,b,c)

#浮点数
m=-1.56     #数学写法
n=1.23e9    #科学记数法
p=12.3e8
q=1.2e-6
print(m,n,p,q)

#字符串
char_1='xyz'
char_2="I'm Linxi"
char_3='I\'m \"OK\"!'  #如果字符串内部既包含'又包含"怎么办？可以用转义字符\来标识
print(char_1,char_2,char_3)

print('I\'m learning\nPython.')
print('\\\n\\')
print(r'\\\t\\')  #用r''表示''内部的字符串默认不转义

print('''line1
line2
line3''')   #用'''...'''的格式表示多行内容

#布尔值
#只有True、False两种值，要么是True，要么是False
#在Python中，可以直接用True、False表示布尔值（请注意大小写），也可以通过布尔运算计算出来：
print(3>5)
print(5>1)
```

    1 -42536 268094789
    -1.56 1230000000.0 1230000000.0 1.2e-06
    xyz I'm Linxi I'm "OK"!
    I'm learning
    Python.
    \
    \
    \\\t\\
    line1
    line2
    line3
    False
    True
    

### 4.2 算术运算符
* `+` 加
* `-` 减
* `*` 乘
* `**` 乘方
* `/` 除
* `//` 整除
* `%` 取模
* `<<` 左移
* `>>` 右移
* `==` 等于
* `!=` `<>` 不等于
* `>` `<` `>=` `<=`
* `=` 赋值
* `+=` `-=` `*=` `/=` `%=` `**=` `//=` 其中，`c+=a`等效于`c=c+a`，其余同理

### 4.3 逻辑运算符
* `&` 按位与
* `|` 按位或
* `^` 按位异或
* `~` 按位取反
> x 的按位取反结果为 -(x+1)  
* `and` 逻辑与
* `or` 逻辑或
* `not` 逻辑非

### 4.4 成员运算符
* `in` 如果在指定的序列中找到值返回 True，否则返回 False。
* `not in` 如果在指定的序列中没有找到值返回 True，否则返回 False。

### 4.5 身份运算符
* 身份运算符用于比较两个对象的存储单元
* `is`   
判断两个标识符是不是引用自一个对象  
x is y, 类似 id(x) == id(y) , 如果引用的是同一个对象则返回 True，否则返回 False  
* `is not`  
判断两个标识符是不是引用自不同对象  
x is not y ， 类似 id(a) != id(b)。如果引用的不是同一个对象则返回结果 True，否则返回 False。 

### 4.6 运算符优先级
![image.png](attachment:image.png)


```python
m=1
n=2
m+=n
m
```




    3




```python
#乘法和乘方
x1=3
x2=2
x3=x1*x2
x4=x1**x2
print(x3,x4)
```

    6 9
    


```python
#除法
m=10
n=3
y1=m/n
y2=m//n
y3=m%n
y1,y2,y3
```




    (3.3333333333333335, 3, 1)




```python
a = 10
b = 20
list = [1, 2, 3, 4, 5] 
if ( a in list ):
   print("1 - 变量 a 在给定的列表中 list 中")
else:
   print("1 - 变量 a 不在给定的列表中 list 中")
 
if ( b not in list ):
   print("2 - 变量 b 不在给定的列表中 list 中")
else:
   print("2 - 变量 b 在给定的列表中 list 中")
 
# 修改变量 a 的值
a = 2
if ( a in list ):
   print ("3 - 变量 a 在给定的列表中 list 中")
else:
   print ("3 - 变量 a 不在给定的列表中 list 中")
```

    1 - 变量 a 不在给定的列表中 list 中
    2 - 变量 b 不在给定的列表中 list 中
    3 - 变量 a 在给定的列表中 list 中
    


```python
a = 20
b = 20
 
if ( a is b ):
   print ("1 - a 和 b 有相同的标识")
else:
   print ("1 - a 和 b 没有相同的标识")
 
if ( id(a) == id(b) ):
   print ("2 - a 和 b 有相同的标识")
else:
   print ("2 - a 和 b 没有相同的标识")
 
# 修改变量 b 的值
b = 30
if ( a is b ):
   print ("3 - a 和 b 有相同的标识")
else:
   print ("3 - a 和 b 没有相同的标识")
 
if ( a is not b ):
   print ("4 - a 和 b 没有相同的标识")
else:
   print ("4 - a 和 b 有相同的标识")
```

    1 - a 和 b 有相同的标识
    2 - a 和 b 有相同的标识
    3 - a 和 b 没有相同的标识
    4 - a 和 b 没有相同的标识
    

##### question：  
1. is和==区别
2. 按位取反计算方法
3. 如果两个变量数据类型不同，是不是意味着不能进行运算


```python

```
