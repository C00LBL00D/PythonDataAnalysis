#   Python Introduction

Python虽然是一门优秀的编程语言，但其拥有出色的**数据处理能力**，尤其是**数据量巨大**的时候。

- 数据处理和数据分析任务规模化、自动化
- 有大量标准模块、附加模块及函数
- 使用空白字符和缩进符代表行的结尾和代码分块
- 跨平台、操作系统（shebang #！/usr/bin/env python3）,#!Linux系统才会读取

# Python LIbs/Packages

- 内建/标准库 https://docs.python.org/3/library/

  - 读取各种类型文件
  - 处理数值、字符串和日期型数据
  - 正则表达式
  - 解析CSV文件
  - 计算基本统计两
  - IO

- 附加模块 https://pypi.org/

  - xlrd&xlwt

    解析读写Microsoft Excel

  - mysqlclient/MySQL-python/MySQLdb

    链接MySQL数据库，查询数据库表

  - pandas

    读取各种类型文件

    管理、筛选和转换数据

    聚合数据并计算基本统计量

    创建各种类型得统计图表

  - statsmodels

    估计各种统计模型，包括线性回归模型、广义线性模型和分类模型

  - scikit-learn

    估计机器学习统计模型，包括线性回归模型、广义线性模型，及执行数据处理、维度归约和交叉验证


# Pycharm

- 功能强大的Python编辑工具

- 安装设置
  - https://www.jetbrains.com/pycharm/download/#section=windows
  - 修改配置文件Pycharm.../bin/idea.properties文件，修改用户目录为Pycharm目录
  - 访问 http://idea.lanyus.com 获取激活码，打开Pycharm激活
  - Ctrl+Alt+S打开设置，搜索encode修改为UTF8
  - 搜索Reopen，取消勾选打开上次的项目
  


# Anaconda

- <https://docs.continuum.io/anaconda/install>

- 集成科学计算、数据分析几乎所有常用包

- Numpy、Scipy、Matplotlib、IPython etc

- 不需要用官方原始的Python，自己一个个安装所有包

  - 安装Anaconda后，在打开安装的Anaconda Prompt中查看有哪些库，并添加igraph库

  ```shell
  conda list
  ...
  pip install igraph #不会更新
  conda install igraph #会安装或更新库所依赖的各种库
  ```

- 在Pycharm中测试代码

  ```python
  import matplotlib.pyplot as plt
  plt.plot([1,2,3,4],[4,3,2,1])
  plt.show()
  ```

- 运行如果报错，找不到模块，可以打开安装的Anaconda Prompt，卸载重装相应模块,找不到名字上网搜

  ```
  >pip uninstall matplotlib
  >pip install matplotlib
  >pip uninstall numpy
  >pip install numpy
  ```

# Python Basic

## 1 Basic Operators

　　运算通常可以根据最终获得的值不同，可以分两类，即结果为具体的值，结果为bool值，那么哪些结果为具体的值-->算数运算、赋值运算，哪些结果又为bool值？--->比较运算、逻辑运算和成员运算。

　　**1、算术运算**

| 运算符 | 描述     | 实例       |
| ------ | -------- | ---------- |
| +      | plus     | 1 + 1 = 2  |
| -      | minus    | 1 - 1 = 0  |
| *      | multiply | 1 * 2 = 2  |
| /      | divide   | 4 / 2 = 2  |
| %      | mod      | 5 % 2 = 1  |
| //     | trunc    | 5 // 2 = 2 |
| **     | power    | 2 ** 3 = 8 |

　　**2、赋值运算**

| 运算符 | 描述             | 实例                              |
| ------ | ---------------- | --------------------------------- |
| =      | 简单的赋值运算符 | c = a + b将a + b的运算结果赋值为c |
| +=     | 加法赋值运算符   | c += a等效于c = c + a             |
| -=     | 减法赋值运算符   | c -= a等效于c = c - a             |
| *=     | 乘法赋值运算符   | c *= a等效于c = c * a             |
| /=     | 除法赋值运算符   | c /= a等效于c = c / a             |
| %=     | 取模赋值运算符   | c %= a等效于c = c % a             |
| **=    | 幂赋值运算符     | c \*\*= a 等效于 c = c\*\* a      |
| //=    | 取整除赋值运算符 | c //= a 等效于 c = c // a         |

　　**3、比较运算**

| 运算符 | 描述                                                         | 实例                                  |
| ------ | ------------------------------------------------------------ | ------------------------------------- |
| ==     | 等于-比较对象是否相等                                        | (a == b)返回 False。                  |
| !=     | 不等于-比较两个对象是否不相等                                | (a != b)返回 true.                    |
| <>     | 不等于-比较两个对象是否不相等                                | (a <> b)返回true。这个运 算符类似!=。 |
| >      | 大于-返回x是否大于y                                          | (a > b)返回 False。                   |
| <      | 小于-返回x是否小于y。所有比较运算符返回1表示真，返回0表示假。这分别与特殊的变量 True和False等价。注意，这些变量名的大写。 | (a < b)返回 true。                    |
| >=     | 大于等于-返回x是否大于等于y。                                | (a >= b)返回 False。                  |
| <=     | 小于等于-返回x是否小于等于y。                                | (a <= b)返回 true。                   |

　　**4、逻辑运算**

| 运算符 | 描述                                                         | 实例                     |
| ------ | ------------------------------------------------------------ | ------------------------ |
| and    | 布尔"与"-如果x为False，x and y返回False，否则它返回y的计算值。 | （a and b)返回true。     |
| or     | 布尔"或如果x是True，它返回True，否则它返回y的计算值。        | (a or b)返回 true。      |
| not    | 布尔"非如果x为True，返回False。如果x为False,它返回True。     | not(a and b)返回 false。 |

　　**5、成员运算**

| 运算符 | 描述                                                  | 实例                                     |
| ------ | ----------------------------------------------------- | ---------------------------------------- |
| in     | 如果在指定的序列中找到值返回True，否则返回False。     | x在y序列中，如果x在y序列中返回True。     |
| not in | 如果在指定的序列中没有找到值返回True，否则返回False。 | x不在y序列中，如果x不在y序列中返回True。 |

## 2 Basic Varaible Type

1、数字  ---> int类

- 当然对于数字，Python的数字类型有int整型、long长整型、float浮点数、complex复数、以及布尔值（0和1），这里只针对int整型进行介绍学习。

- 在Python2中，整数的大小是有限制的，即当数字超过一定的范围不再是int类型，而是long长整型，而在Python3中，无论整数的大小长度为多少，统称为整型int。

**int -->将字符串数据类型转为int类型,  注：字符串内的内容必须是数字**　

```python
#!/usr/bin/env python
# -*- coding:utf-8 -*-

s = '123'
i = int(s)
print(i)
```

**bit_length() -->将数字转换为二进制，并且返回最少位二进制的位数**

```python
#!/user/bin/env python
#-*- coding:utf-8 -*-

i =123
print( i.bit_length() )

#输出结果为：
>>>5　
```

### Boolean

- 对于布尔值，只有两种结果即True和False，其分别对应与二进制中的0和1。而对于真即True的值太多了，我们只需要了解假即Flase的值有哪些---》None、空（即 [ ]/( ) /" "/{ }）、0；

```python
#以下结果为假，即None、‘’、[]、()、{}以及 0
>>> bool(None)
False
>>> bool('')
False
>>> bool([])
False
>>> bool(0)
False
>>> bool(())
False
>>> bool({})
False
```

### String

- 关于字符串是Python中最常用的数据类型，其用途也很多，我们可以使用单引号 ‘’或者双引号“”来创建字符串。

- 字符串是不可修改的。所有关于字符我们可以从 索引、切片、长度、遍历、删除、分割、清除空白、大小写转换、判断以什么开头等方面对字符串进行介绍。

**创建字符串**

```python
#!/usr/bin/env python
# -*- coding:utf-8 -*-

#字符串的形式：使用‘’或者“”来创建字符串
name ='little_five'
print(name)

#'转义
print("{0:s}".format('I\'m enjoying learning Python.'))

#长字符串用反斜线\（backslash）分割
print("Output #15: {0:s}".format("This is a long string. Without the backslash\
it would run off of the page on the right in the text editor and be very\
difficult to read and edit. By using the backslash you can split the long\
string into smaller strings on separate lines so that the whole string is easy\
to view in the text editor."))

#3个单引号'''或3个双引号"""包裹多行字符串
print("Output #16: {0:s}".format('''You can use triple single quotes
for multi-line comment strings.'''))
print("Output #17: {0:s}".format("""You can also use triple double quotes
for multi-line comment strings."""))

#字符串运算
print("Output #18: {0:s}".format("This is a " + "short string."))
print("Output #19: {0:s} {1:s}{2:s}".format("She is", "very "*4, "beautiful."))
```

**切片(包头不包尾)**

```python
#获取切片，复数代表倒数第几个，从0开始
>>> name ="little-five"
>>> name[1]
'i'
>>> name[0:-2] #从第一个到倒数第二个，不包含倒数第二个
'little-fi'
```

**索引--> index()、find()**

```python
#!/usr/bin/env python
# -*- coding:utf-8 -*-

name = "little_five"
#index-->获取索引，第二个参数指定获取该子字符或者子序列的第几个
print(name.index("l",2)) #结果为 4

#find -->其作用与index相似
print(name.find("l",2))  #结果也为 4
```

index()与find()的不同之处在于：若索引的该字符或者序列不在字符串内，对于index--》ValueError: substring not found，而对于find -->返回 -1。

```python
#!/usr/bin/env python
# -*- coding:utf-8 -*-

name = "little_five"

print(name.index("q",2))
#index--》输出为：
>>>Traceback (most recent call last):
  File "C:/Users/28352/PycharmProjects/learning/Day13/test.py", line 5, in <module>
    print(name.index("q",2))
ValueError: substring not found

print(name.find("q",2))
#find--》输出为：
>>> -1　　　
```

**长度 -->len()**

```python
name = "little_five"
#获取字符串的长度
print(len(name))

#输出为：
>>> 11
```

　　　　注：len()方法-->同样可以用于其他数据类型，例如查看列表、元组以及字典中元素的多少。

**删除 --> del** 

```python
#删除字符串，也是删除变量
>>> name ="little-five"
>>> del name
>>> name
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
NameError: name 'name' is not defined
```

**判断字符串内容 --> isalnum()、isalpha()、isdigit()**　

```python
#判断是否全为数字
>>> a ="123"
>>> a.isdigit()
True
>>> b ="a123"
>>> b.isdigit()
False

#判断是否全为字母
>>> d ="alx--e"
>>> d.isalpha()
False
>>> c ="alex"
>>> c.isalpha()
True

#判断是否全为数字或者字母
>>> e ="abc123"
>>> e.isalnum()
True
```

**大小写转换 --> capitalize()、lower()、upper()、title()、casefold()**

```python
#!/usr/bin/env python
# -*- coding:utf-8 -*-

#大小写的互相转换
>>> name ="little_five"
#首字母大写-->capitalize
>>> name.capitalize()
'Little_five'

#转为标题-->title
>>> info ="my name is little_five"
>>> info.title()
'My Name Is Little_Five'

#全部转为小写-->lower
>>> name ="LITTLE_FIVE"
>>> name.lower()
'little_five'

#全部转为大写-->upper
>>> name = "little_five"
>>> name.upper()
'LITTLE_FIVE'

#大小写转换-->swapcase
>>> name ="lIttle_fIve"
>>> name.swapcase()
'LiTTLE_FiVE'
```

**判断以什么开头结尾 --> startswith()、endswith()**　

```python
#判断以什么开头、结尾
>>> name ="little-five"

#判断以什么结尾
>>> name.endswith("e")
True

#判断以什么开头
>>> name.startswith("li")
True
```

**扩展-->expandtabs()**

```python
#expandtabs -->返回字符串中的 tab 符号('\t')转为空格后生成的新字符串。通常可用于表格格式的输出

info ="name\tage\temail\nlittlefive\t22\t994263539@qq.com\njames\t33\t66622334@qq.com"
print(info.expandtabs(10))

#输出为：
name      age       email
little-five         22        994263539@qq.com
james     33        66622334@qq.com
```

**格式化输出-->format()、format_map()**

```python
#格式化输出-->format、format_map

#forma方法
#方式一
>>> info ="my name is {name},I'am {age} years old."
>>> info.format(name="little-five",age=22)
"my name is little-five,I'am 22 years old."

#方式二
>>> info ="my name is {0},I'am {1} years old."
>>> info.format("little-five",22)
"my name is little-five,I'am 22 years old."

#方式三
>>> info ="my name is {name},I'am {age} years old."
>>> info.format(**{"name":"little-five","age":22})
"my name is little-five,I'am 22 years old."

#format_map方法
>>> info ="my name is {name},I'am {age} years old."
>>> info.format_map({"name":"little-five","age":22})
"my name is little-five,I'am 22 years old."
```

 **jion方法**

```python
#join--> join(): 连接字符串数组。将字符串、元组、列表中的元素以指定的字符(分隔符)连接生成一个新的字符串

#字符串
>>> name ="littefive"
>>> "-".join(name)
'l-i-t-t-e-f-i-v-e'

#列表
>>> info = ["xiaowu","say","hello","world"]
>>> "--".join(info)
'xiaowu--say--hello--world'
```

**分割 --> split()、partition()**

```python
#分割，有两个方法-partition、split

#partition -->只能将字符串分为三个部分，生成列表
>>> name ="little-five"
>>> name.partition("-")
('little', '-', 'five')

#split-->分割字符串，并且可以指定分割几次，并且返回列表
>>> name ="little-five-hello-world"
>>> name.split("-")
['little', 'five', 'hello', 'world']
>>> name.split("-",2)  #指定分割几次
['little', 'five', 'hello-world']
>>>

#split 默认分割符为空格
>>> print("My deliverable is due in May".split())
['My', 'deliverable', 'is', 'due', 'in', 'May']
>>> print("My deliverable is due in May".split()[-1])
May
```

**替代 -->replace**

```python
#替代
>>> name ="little-five"
>>> name.replace("l","L")
'LittLe-five'
#也可以指定参数，替换几个
>>> name.replace("i","e",2)
'lettle-feve'
```

**清除空白 --> strip()、lstrip()、rstrip()**

```python
#去除空格
>>> name ="  little-five   "

#去除字符串左右两边的空格
>>> name.strip()
'little-five'

#去除字符串左边的空格
>>> name.lstrip()
'little-five   '

#去除字符串右边的空格
>>> name.rstrip()
'  little-five'
```

 **替换 -->makestran 、translate**

```python
1 #进行一一替换
2 
3 >>> a ="wszgr"
4 >>> b="我是中国人"
5 >>> v =str.maketrans(a,b) #创建对应关系，并且两个字符串长度要求一致
6 >>> info ="I'm a Chinese people,wszgr"
7 >>> info.translate(v)
8 "I'm a Chine是e people,我是中国人"
```

### Date

```python
from datetime import date, time, datetime, timedelta

#date
today = date.today()
print(today)
>>> 2019-10-20
print('{!s}'.format(today))
>>> 2019-10-20
print(today.year)
>>> 2019
print(today.month)
>>> 10
print(today.day)
>>> 20

#datetime
print(datetime.today())
>>> 2019-10-20 21:27:25.528661

# timedelta日期运算
one_day = timedelta(days=-1)
yesterday = date.today() + one_day
print(yesterday)
>>> 2019-10-19
eight_hours = timedelta(hours=-8)
print('{!s} {!s}'.format(eight_hours.days,eight_hours.seconds))
>>> -1 57600

# 日期直接加减
date_diff = date.today() - (date.today() + timedelta(days = -1))
print("{0!s}".format(date_diff))
>>> 1 day, 0:00:00
print("{!s}".format(str(date_diff).split()[0]))
>>> 1

# strftime
print("{:s}".format(today.strftime('%m/%d/%Y')))
>>> 10/20/2019
print("{:s}".format(today.strftime('%b %d, %Y')))
>>> Oct 20, 2019
print("{:s}".format(today.strftime('%Y-%m-%d')))
>>> 2019-10-20
print("{:s}".format(today.strftime('%B %d, %Y')))
>>> October 20, 2019
```

### List

列表是由一系列特定元素顺序排列的元素组成的，它的元素可以是任何数据类型即数字、字符串、列表、元组、字典、布尔值等等，同时其元素也是可修改的。

```python
1 names = ['little-five","James","Alex"]
2 #或者
3 names = list(['little-five","James","Alex"])

# 使用方括号创建一个列表
a_list = [1, 2, 3]
# 用count()计算出列表中某个值出现的次数
print("{}".format(a_list))
# 用len()计算列表中元素的数量
print("{}".format(len(a_list)))
# 用max()和min()找出最大值和最小值
print("{}".format(max(a_list)))
print("{}".format(min(a_list)))
#count 返回列表中某个元素出现的次数
print("{}".format(a_list.count(1)))

# 使用[:]复制一个列表
a_new_list = a_list[:]
print("{}".format(a_new_list)) 

# 使用+将两个或更多个列表连接起来
a_longer_list = a_list + another_list
print("Output #78: {}".format(a_longer_list))

# 使用in和not in来检查列表中是否有特定元素
a = 2 in a_list
print("Output #79: {}".format(a))
if 2 not in a_list:
print("Output #80: 2 is in {}.".format(a_list))

# for 循环和定位索引（也就是range(len())）在列表中循环
listr = (['penney'], ['pl'], ['princess'])
for i in range(len(listr)) :
    print('{:d}:{!s}'.format(i,listr[i]))

'''
创建一个列表，其中的元素是具有相同长度的列表
在列表的列表中循环，将每个列表中的值以逗号隔开的字符串形式打印在屏幕上
并在每个列表的最后一个值后面加上一个换行符。
'''
list1 = [['penney', 'pl', 'PrincessPenney'], ['Nyotengu', 'Honoka', 'MarieRose'], [1, 2, 3]]
for list2 in list1 :
    string1 = ''
    for i in range(len(list2)) :
        string1 += '{!s}'.format(list2[i]) + ','
    print(string1[:-1] + '\r\n')
```

**索引、切片**

```python
 1 #索引-->从0开始，而不是从一开始
 2 name =["xiaowu","little-five","James"]
 3 print(name[0:-1])
 4 
 5 
 6 #切片-->负数为倒数第几个，其为左闭右开，如不写，前面表示包含前面所有元素,后面则表示后面所有元素
 7 m1 =name[1:]
 8 print(m1)
 9 #输出为-->['little-five', 'James']
10 m2 =name[:-1]
11 print(m2)
12 #输出为-->['xiaowu', 'little-five']

# 使用索引值访问列表中的特定元素
# [0]是第1个元素，[-1]是最后一个元素
print("Output #65: {}".format(name[0]))
print("Output #66: {}".format(name[1]))
print("Output #67: {}".format(name[2]))
print("Output #68: {}".format(name[-1]))
print("Output #69: {}".format(name[-2]))
```

**追加-->append()**

```python
1 #追加元素-->append()
2 name =["xiaowu","little-five","James"]
3 name.append("alex")
4 print(name)
5 
6 #输出为--》['xiaowu', 'little-five', 'James', 'alex']
```

**拓展-->extend()**

```python
 1 #扩展--》其将字符串或者列表的元素添加到列表内
 2 #一、将其他列表元素添加至列表内
 3 name =["xiaowu","little-five","James"]
 4 name.extend(["alex","green"])
 5 print(name)
 6 #输出为-->['xiaowu', 'little-five', 'James', 'alex', 'green']
 7 
 8 #二、将字符串元素添加到列表内
 9 name =["xiaowu","little-five","James"]
10 name.extend("hello")
11 print(name)
12 #输出为-->xiaowu', 'little-five', 'James', 'alex', 'green', 'h', 'e', 'l', 'l', 'o']
13 
14 #三、将字典元素添加至列表内，注：字典的key。
15 name =["xiaowu","little-five","James"]
16 name.extend({"hello":"world"})
17 print(name)
```

注：扩展extend与追加append的区别：-->前者为添加将元素作为一个整体添加，后者为将数据类型的元素分解添加至列表内。例：

```python
 1 #extend-->扩展
 2 name =["xiaowu","little-five","James"]
 3 name.extend(["hello","world"])
 4 print(name)
 5 输出为-->['xiaowu', 'little-five', 'James', 'hello', 'world']
 6  
 7 #append -->追加
 8 name.append(["hello","world"])
 9 print(name)
10 输出为 -->['xiaowu', 'little-five', 'James', ['hello', 'world']]
```

**insert() -->插入**

```python
1 #insert（）插入-->可以指定插入列表的某个位置，前面提到过列表是有序的
2 name =["xiaowu","little-five","James"]
3 name.insert(1,"alex") #索引从0开始，即第二个
4 print(name)
```

**pop() -->取出**

```python
1 #pop()--取出，可将取出的值作为字符串赋予另外一个变量
2 name =["xiaowu","little-five","James"]
3 special_name =name.pop(1)
4 print(name)
5 print(special_name,type(special_name))
6 
7 #输出为：['xiaowu', 'James']
8 #           little-five <class 'str'>
9     
```

**remove()-->移除、del -->删除**

```python
 1 #remove -->移除，其参数为列表的值的名称
 2 name =["xiaowu","little-five","James"]
 3 name.remove("xiaowu")
 4 print(name)
 5 
 6 #其输出为：['little-five', 'James']
 7 
 8 #del -->删除
 9 name =["xiaowu","little-five","James"]
10 #name.remove("xiaowu")
11 del name[1]
12 print(name)
13 
14 #其输出为：['xiaowu', 'James']
```

**sorted()、reverse()-->排序，默认正序，加入reverse =True，则表示倒序**

```python
 1 #正序
 2 num =[11,55,88,66,35,42]
 3 print(sorted(num)) -->数字排序
 4 name =["xiaowu","little-five","James"]
 5 print(sorted(name)) -->字符串排序
 6 #输出为：[11, 35, 42, 55, 66, 88]
 7 #    ['James', 'little-five', 'xiaowu']
   print(sorted(name, key=lambda index_value:index_value[3]))
 8 
 9 #倒序
10 num =[11,55,88,66,35,42]
11 print(sorted(num,reverse=True))
12 print(reverse(num))
13 #输出为：[88, 66, 55, 42, 35, 11] 

#from operator import itemgetter
my_lists = [[123,2,2,444], [22,6,6,444], [354,4,4,678], [236,5,5,678],  [578,1,1,290], [461,1,1,290]]
#：先按照索引位置3 中的值对列表进行排序，然后，在这个排序基础上，按照索引位置0 中的值对列表进一步排序。
my_lists_sorted_by_index_3_and_0 = sorted(my_lists, key=itemgetter(3,0))
print("Output #92: {}".format(my_lists_sorted_by_index_3_and_0))
```

### Tuple

元组即为不可修改的列表。其于特性跟list相似。其使用圆括号而不是方括号来标识。 

```python
# 使用圆括号创建元组
my_tuple = ('x', 'y', 'z')
print("Output #93: {}".format(my_tuple))
print("Output #94: my_tuple has {} elements".format(len(my_tuple)))
print("Output #95: {}".format(my_tuple[1]))
longer_tuple = my_tuple + my_tuple
print("Output #96: {}".format(longer_tuple))

# 使用赋值操作符左侧的变量对元组进行解包
my_tuple = ('x', 'y', 'z')
one, two, three = my_tuple
print("Output #97: {0} {1} {2}".format(one, two, three))
var1 = 'red'
var2 = 'robin'
print("Output #98: {} {}".format(var1, var2))
# 在变量之间交换彼此的值
var1, var2 = var2, var1
print("Output #99: {} {}".format(var1, var2))

# 将元组转换成列表，列表转换成元组
my_list = [1, 2, 3]
my_tuple = ('x', 'y', 'z')
print("Output #100: {}".format(tuple(my_list)))
print("Output #101: {}".format(list(my_tuple)))
```

### Dict

- 字典为一系列的键-值对，每个键值对用逗号隔开，每个键都与一个值相对应，可以通过使用键来访问对应的值。无序的。
- 
- 键的定义必须是不可变的，即可以是数字、字符串也可以是元组，还有布尔值等。
- 而值的定义可以是任意数据类型。

```python
#字典的定义
empty_dict = { }
a_dict = {'one':1, 'two':2, 'three':3}
info ={
    1:"hello world",  #键为数字
    ("hello world"):1, #键为元组
    False:{ 
        "name":"James"
    },
    "age":22
}    

# 使用copy()复制一个字典
a_new_dict = a_dict.copy()
print(a_new_dict)

# 使用keys()、values()和items()
# 分别引用字典中的键、值和键-值对
print("Output #109: {}".format(a_dict.keys()))
a_dict_keys = a_dict.keys()
print("Output #110: {}".format(a_dict_keys))
print("Output #111: {}".format(a_dict.values()))
print("Output #112: {}".format(a_dict.items()))

#使用in、not in和get
if 'y' in another_dict:
print("Output #114: y is a key in another_dict: {}."\
.format(another_dict.keys()))
if 'c' not in another_dict:
print("Output #115: c is not a key in another_dict: {}."\
.format(another_dict.keys()))
print("Output #116: {!s}".format(a_dict.get('three')))
print("Output #117: {!s}".format(a_dict.get('four')))
print("Output #118: {!s}".format(a_dict.get('four', 'Not in dict')))

'''
创建两个同样长度的不同列表,其中一个列表包含具有唯一性的字符串
再创建一个空字典
使用for 循环、定位索引和if 语句检查字符串列表中的每个元素是否是字典中的键
如果不是，将这个元素作为字典键,将另一个列表中具有同样索引位置的元素作为字典值
把它们添加到字典中
最后在屏幕上,打印出字典的键和值
'''
list1 = [1,2,3]
list2 = ['penney', 'pl', 'princess']
dict1 = {}
for i in range(len(list2)):
    if list2[i] not in dict1 :
        dict1[list2[i]] = list1[i]
print(dict1.items())
for x,y in dict1.items() :
    print(x , y)
```

**遍历 -->items、keys、values**

```python
 info ={
   "name":"little-five",
   "age":22,
   "email":"99426353*@qq,com"
}
#键
for key in info:
    print(key)
print(info.keys())
#输出为：dict_keys(['name', 'age', 'email'])

#键值对
print(info.items())
#输出为-->dict_items([('name', 'little-five'), ('age', 22), ('email', '99426353*@qq,com')])
print(info['name'])
#输出为：little-five

#值
print(info.values())
#输出为：dict_values(['little-five', 22, '99426353*@qq,com'])


```

 **排序**

```python
# 使用sorted()对字典进行排序
# 要想对字典排序的同时不修改原字典
# 先复制字典
print("Output #119: {}".format(a_dict))
dict_copy = a_dict.copy()
ordered_dict1 = sorted(dict_copy.items(), key=lambda item: item)
print("Output #120 (order by keys): {}".format(ordered_dict1))
ordered_dict2 = sorted(dict_copy.items(), key=lambda item: item[1])
print("Output #121 (order by values): {}".format(ordered_dict2))
ordered_dict3 = sorted(dict_copy.items(), key=lambda x: x[1], reverse=True)
print("Output #122 (order by values, descending): {}".format(ordered_dict3))
ordered_dict4 = sorted(dict_copy.items(), key=lambda x: x[1], reverse=False)
print("Output #123 (order by values, ascending): {}".format(ordered_dict4))
```



### Set

关于集合set的定义：在我看来集合就像一个篮子，你可以往里面存东西也可往里面取东西，但是这些东西又是无序的，你很难指定单独去取某一样东西；同时它又可以通过一定的方法筛选去获得你需要的那部分东西。故集合可以 创建、增、删、关系运算。

**集合的特性：**

　　　　　　1、去重

　　　　　　2、无序

　　　　　　3、每个元素必须为不可变类型即（hashable类型，可作为字典的key）。

**创建：set、frozenset**

```python
1 #1、创建，将会自动去重,其元素为不可变数据类型，即数字、字符串、元组
2 test01 ={"zhangsan","lisi","wangwu","lisi",666,("hello","world",),True}
3 #或者
4 test02 =set({"zhangsan","lisi","wangwu","lisi",666,("hello","world",),True})
5 
6 #2、不可变集合的创建 -->frozenset()
7 test =frozenset({"zhangsan","lisi","wangwu","lisi",666,("hello","world",),True})

```

**增：   add、update**

```python
#更新单个值 --->add
names ={"zhangsan","lisi","wangwu"}
names.add("james") #其参数必须为hashable类型
print(names)

#更新多个值 -->update
names ={"zhangsan","lisi","wangwu"}
names.update({"alex","james"})#其参数必须为集合
print(names)

```

**删除：pop、remove、discard**

```python
#随机删除 -->pop
names ={"zhangsan","lisi","wangwu","alex","james"}
names.pop()
print(names)

#指定删除，若要删除的元素不存在，则报错 -->remove
names ={"zhangsan","lisi","wangwu","alex","james"}
names.remove("lisi")
print(names)

#指定删除，若要删除的元素不存在，无视该方法 -->discard
names ={"zhangsan","lisi","wangwu","alex","james"}
names.discard("hello")
print(names)

```

**关系运算：交集 & 、并集 | 、差集 - 、交差补集 ^ 、 issubset 、isupperset**

比如有两个班英语班和数学班，我们需要统计这两个班中报名情况，例如既报名了英语班有报名数学班的同学名字等等，这时候我们就可以应用到集合的关系运算：

```python
english_c ={"ZhangSan","LiSi","James","Alex"}
math_c ={"WangWu","LiuDeHua","James","Alex"}

#1、交集-->  in a and in b
#统计既报了英语班又报了数学班的同学
print(english_c & math_c)
print(english_c.intersection(math_c))
#输出为：{'Alex', 'James'}

#2、并集--> in a or in b
#统计报名了两个班的所有同学
print(english_c | math_c)
print(english_c.union(math_c))
#输出为：{'James', 'ZhangSan', 'LiuDeHua', 'LiSi', 'Alex', 'WangWu'}

#3、差集--> in a not in b
#统计只报名英语班的同学
print(english_c - math_c)
print(english_c.difference(math_c)) 
#输出为：{'LiSi', 'ZhangSan'}

4、交差补集 
#统计只报名一个班的同学
print(english_c ^ math_c)
#输出为：{'LiuDeHua', 'ZhangSan', 'WangWu', 'LiSi'}

```

判断两个集合的关系是否为子集、父集 -->  **issubset 、isupperset**

```python
#5、issubset-->n 是否为 m 的子集
#   issuperset --> n 是否为 m 的父集
n ={1,2,4,6,8,10}
m ={2,4,6}
l ={1,2,11}

print(n >= m)
#print(n.issuperset(m)) #n 是否为 m的父集
#print(n.issuperset(l))
print(m <=n)    
#print(m.issubset(n))    #m 是否为 n的子集

```

## 3 Control Flow

1. **if-else**

   ```python
   # if-else语句
   x = 5
   if x > 4 or x != 9:
   print("Output #124: {}".format(x))
   else:
   print("Output #124: x is not greater than 4"
   ```

2. **if-elif-else**

   ```python
   if x > 6:
   print("Output #125: x is greater than six")
   elif x > 4 and x == 5:
   print("Output #125: {}".format(x*x))
   else:
   print("Output #125: x is not greater than 4")if-elif-else
   ```

3. **for**

   ```python
   y = ['Jan', 'Feb', 'Mar', 'Apr', 'May', 'Jun', 'Jul', 'Aug', 'Sep', 'Oct', \
   'Nov', 'Dec']
   z = ['Annie', 'Betty', 'Claire', 'Daphne', 'Ellie', 'Franchesca', 'Greta', \
   'Holly', 'Isabel', 'Jenny']
   print("Output #126:")
   
   for month in y:
   	print("{!s}".format(month))
   
   print("Output #127: (index value: name in list)")
   
   # 定位索引
   for i in range(len(z)):
   	print("{0!s}: {1:s}".format(i, z[i]))
   
   print("Output #128: (access elements in y with z's index values)")
   
   for j in range(len(z)):
   	if y[j].startswith('J'):
   		print("{!s}".format(y[j]))
   
   print("Output #129:")
   
   for key, value in another_dict.items():
   	print("{0:s}, {1}".format(key, value))
   ```

4. **简化for循环：列表、集合与字典生成式**

   ```python
   # 列表生成式
   my_data = [[1,2,3], [4,5,6], [7,8,9]]
   rows_to_keep = [row for row in my_data if row[1] > 5]
   print("Output #130 (list comprehension): {}".format(rows_to_keep))
   
   # 集合生成式
   my_data = [(1,2,3), (4,5,6), (7,8,9), (7,8,9)]
   set_of_tuples1 = {x for x in my_data}
   print("Output #131 (set comprehension): {}".format(set_of_tuples1))
   set_of_tuples2 = set(my_data)
   print("Output #132 (set function): {}".format(set_of_tuples2))
   
   # 字典生成式
   my_dictionary = {'customer1': 7, 'customer2': 9, 'customer3': 11}
   my_results = {key : value for key, value in my_dictionary.items() if value > 10}
   print("Output #133 (dictionary comprehension): {}".format(my_results))
   ```

5. **while**

   ```python
   print("Output #134:")
   x = 0
   while x < 11:
   print("{!s}".format(x))
   x += 
   ```

## 4 Function

```python
# 计算一系列数值的均值
def getMean(numericValues):
	return sum(numericValues)/len(numericValues) if len(numericValues) > 0 else float('nan')
my_list = [2, 2, 4, 4, 6, 6, 8, 8]
print("Output #135 (mean): {!s}".format(getMean(my_list)))

import numpy as np
print np.mean(my_list)
```

## 5 Exception

- **try-except**

  ```python
  # 计算一系列数值的均值
  def getMean(numericValues):
  	return sum(numericValues)/len(numericValues)
  my_list2 = [ ]
  # 简单形式
  try:
  	print("Output #138: {}".format(getMean(my_list2)))
  except ZeroDivisionError as detail:
  	print("Output #138 (Error): {}".format(float('nan')))
  	print("Output #138 (Error): {}".format(detail))
  ```

- **try-except-finally**

  ```python
  # 计算一系列数值的均值
  def getMean(numericValues):
  	return sum(numericValues)/len(numericValues)
  my_list2 = [ ]
  # 完整形式
  try:
      result = getMean(my_list2)
  except ZeroDivisionError as detail:
      print ("Output #142 (Error): " + str(float('nan')))
      print ("Output #142 (Error):", detail)
  else:
      print ("Output #142 (The mean is):", result)
  finally:
      print ("Output #142 (Finally): The finally block is executed every time")
  ```

## 6 Regular Expression

```python
#!/usr/bin/env python3
#coding=utf8

import re

# 使用match(正则表达式,要匹配的字符串)匹配以“xxx”开头的字符串
result = re.match(正则表达式,要匹配的字符串)

# 如果上一步匹配到数据的话，可以使用group方法来提取数据
result.group()

#例子
result = re.match('penney', 'penney princess')
print('{!s}'.format(result.group()))

# r 表示原生字符串
str1 = "c:\\a\\b\\c"
rtl1 = re.match('c:\\\\a', str1).group()
print(rtl1)
# c:\a
rtl2 = re.match(r'c:\\a', str1).group()
print(rtl2)
# c:\a

string_list = "The quick brown fox jumps over the lazy dog.".split()

#计算字符串中模式出现的次数
pattern = re.compile(r"The", re.I)
#re.compile 函数将文本形式的模式编译成为编译后的正则表达式,编译是可以显著提高程序运行速度
#re.I 函数确保模式是不区分大小写的，能同时在字符串中匹配“The”和“the”
#原始字符串标志r 可以确保Python 不处理字符串中的转义字符,如\t\r\n

count = 0
for word in string_list:
	if pattern.search(word):
		count += 1
print("Output #38: {0:d}".format(count))

#在字符串中每次找到模式时将其打印出来
pattern = re.compile(r"(?P<match_word>The)", re.I)
#第一个新代码片段是(?P<name>)，这是一个出现在re.compile 函数中的元字符
#这个元字符使匹配的字符串可以在后面的程序中通过组名符号<name> 来引用。
#在这个示例中，这个组被称为<match_word>。

for word in string_list:
    if pattern.search(word):
        print("{:s}".format(pattern.search(word).group('match_word')))

#正则表达式替换字符串中的字符
string = 'come on baby. Let\'s go baby!'
pattern = re.compile(r'baby', re.I)
print(pattern.sub('PrincessPenny', string))

```

- 说明

  `Python中字符串前面加上 r 表示原生字符串`，

  与大多数编程语言相同，`正则表达式里使用"\"作为转义字符`，这就可能造成反斜杠困扰。假如你需要匹配文本中的字符"\"，那么使用编程语言表示的正则表达式里将需要4个反斜杠"\\"：前两个和后两个分别用于在编程语言里转义成反斜杠，转换成两个反斜杠后再在正则表达式里转义成一个反斜杠。

  Python里的原生字符串很好地解决了这个问题，有了原始字符串，你再也不用担心是不是漏写了反斜杠，写出来的表达式也更直观。

- 表达式中常用特殊字符含义

| 字符 | 功能                             |
| ---- | -------------------------------- |
| .    | 匹配任意1个字符（除了\n）        |
| [ ]  | 匹配[ ]中列举的字符              |
| \d   | 匹配数字，即0-9                  |
| \D   | 匹配非数字，即不是数字           |
| \s   | 匹配空白，即 空格，tab键         |
| \S   | 匹配非空白                       |
| \w   | 匹配单词字符，即a-z、A-Z、0-9、_ |
| \W   | 匹配非单词字符                   |

- 匹配多个字符的相关格式

| 字符  | 功能                                                |
| ----- | --------------------------------------------------- |
| *     | 匹配前一个字符出现0次或者无限次，即可有可无         |
| +     | 匹配前一个字符出现1次或者无限次，即至少有1次        |
| ?     | 匹配前一个字符出现1次或者0次，即要么有1次，要么没有 |
| {m}   | 匹配前一个字符出现m次                               |
| {m,}  | 匹配前一个字符至少出现m次                           |
| {m,n} | 匹配前一个字符出现从m到n次                          |

- 表示边界

| 字符 | 功能               |
| ---- | ------------------ |
| ^    | 匹配字符串开头     |
| $    | 匹配字符串结尾     |
| \b   | 匹配一个单词的边界 |
| \B   | 匹配非单词边界     |

```python
#匹配163邮箱
str1 = 'penney5828@163.com'
rtl1 = re.match(r'^[\w_]{4,20}[@]163.com$', str1).group()
print('{!s}'.format(rtl1))
```

- 匹配分组

| 字符         | 功能                             |
| ------------ | -------------------------------- |
| \|           | 匹配左右任意一个表达式           |
| (ab)         | 将括号中字符作为一个分组         |
| `\num`       | 引用分组num匹配到的字符串        |
| `(?P<name>)` | 分组起别名                       |
| (?P=name)    | 引用别名为name分组匹配到的字符串 |

```python
#匹配0~100的数字
ret = re.match("[1-9]?\d$|100","100")
ret = re.match('[\d]{1,2}$|100', '100')
ret.group()

#分组获取
str1 = '010-6825245'
rst1 = re.match(r'([0-9]*)-([0-9]{7})', str1)
print(rst1.group())
#010-6825245
print(rst1.group(1))
#010
print(rst1.group(2))
#6825245

#使用\1引用分组匹配的数据，匹配如<html>hh</html>或<p>xxx</p>的字符串
list1 = ['<body><p>...</p></body>', '<html>hh</html>', '<p>xxx</p>']
for i in range(len(list1)):
    print(re.match(r'<([a-zA-Z]+)>.+</\1>', list1[i]).group())
    print(re.match(r'<(\w*)><(\w*)>.*</\2></\1>', list1[i]).group())
```



## 7 IO

- **open()**

```python
# 读取一个文本文件（旧方法）
input_file='C:/Users/CoolBlood/Desktop/123.txt'
filereader=open(input_file, 'r')
for row in filereader:
    print(row.strip())
filereader.close()

# 读取一个文本文件（新方法）
with open(input_file, 'r', newline='') as filereader:
    for row in filereader:
        print("{}".format(row.strip()))
```

- **glob**

```python
#!/usr/bin/env python3
import os
import glob

inputPath='C:/Users/CoolBlood/Desktop/'

# 读取多个文本文件
for input_file in glob.glob(os.path.join(inputPath,'*.txt')):
    with open(input_file, 'r', newline='') as filereader:
        for row in filereader:
            print("{}".format(row.strip()))
```

- **write**

```python
#!/usr/bin/env python3

# 写入文件
# 写入一个文本文件
my_letters = ['a', 'b', 'c', 'd', 'e', 'f', 'g', 'h', 'i', 'j']
max_index = len(my_letters)
output_file = 'C:/Users/CoolBlood/Desktop/123.txt'

filewriter = open(output_file, 'w')

for index_value in range(len(my_letters)):
    if index_value < (max_index-1):
        filewriter.write(my_letters[index_value]+'\t')
    else:
        filewriter.writelines(my_letters[index_value]+'\n')

filewriter.close()

# 写入CSV文件
my_numbers = [0, 1, 2, 3, 4, 5, 6, 7, 8, 9]
max_index = len(my_numbers)
output_file = 'C:/Users/CoolBlood/Desktop/123.csv'
filewriter = open(output_file, 'a')
for index_value in range(len(my_numbers)):
    if index_value < (max_index-1):
        filewriter.write(str(my_numbers[index_value])+',')
    else:
        filewriter.write(str(my_numbers[index_value])+'\n')
        filewriter.close()

filewriter.close()
```

# Python Script



## 1 Create Python Script

- SheBang at first row

  ```python
  #!/usr/bin/env python3
  ```

- 导入添加模块

  ```python
  from math import exp, log, sqrt
  ```

  4 种数值类型（整数int、浮点数float、长整数long、复数）

- Variable reference

  ```python
  #指定为数值digital类型
  a = 1
  print("a + b = {0:d}".format(a))
  #变量引用开始得Index为0
  x = ['1', '2', '3']
  y = ['a', 'b', 'c']
  z = x + y
  print("x = {0} y = {1} z = {2}".format(x, y, z))
  #幂次方符号**
  print('{0}'.format(3**4))#相当于3^4=81
  #整数integer_number
  print('{0}'.format(int(2.4123+3.489)))#5
  print('{0}'.format(int(2.4123)+int(3.489)))#5
  #浮点数floating_point_number
  print('{0}'.format(2.1123+3.323))#5.4353
  print('{0:.1f}'.format(2.1123+3.323))#5.4
  print('{0:.2f}'.format(2.1123+3.323))#5.44
  #长整数long_number
  
  #复数
  ```

- type(varible) 会返回Python 中的数据类型

# Python Packages/Modules

| Type  | Name              | Description                                                  |
| ----- | ----------------- | ------------------------------------------------------------ |
| Excel | openpyxl          | The recommended package for reading and writing Excel 2010 files (ie: .xlsx) |
| Excel | xlrd(EXcel Read)  | This package is for reading data and formattinng information from older Excel files (ie: .xls) |
| Excel | xlwt(Excel Write) | This package is for writing data and fromatting information to older Excel files (ie: .xls) |
| Excel | xlutils           | This package  collects utilities that require both xlrd and xlwt, including the ability to copy and modify or filter existing excel files |



# Numpy Package

## 1 Numpy Introduction

- Numpy是Python开源的数值计算扩展

- 用于存储和处理大型矩阵，比Python自身数据结构高效

- Numpy将Python变为免费的强大Matlab系统

## 2 Core Object: ndarray

- 创建方式

  从python的基础数据对象转化

  通过Numpy内生的函数生成

  从硬盘（文件）读取数据

-   索引和切片

    print c[1:5]

    print c[:5]

    print c[::-1]

## 3 Basic Functions

- 
  

# Matplotlib Package

## 1 Matplotlib Introduction

- Matplotlib是基于Python的开源项目，旨在为Python提供一个数据绘图包
- 函数式绘图和面向对象式绘图
  - 函数式绘图，参考matlab的绘图函数语法，上手快
  - 面向对象式绘图，贴近matplotlib底层架构，功能多
- 前置依赖

| Requirement     | Description |
| --------------- | ----------- |
| numpy           |             |
| python-dateutil |             |
| kiwisolver      |             |
| pyparsing       |             |
| cycler          |             |
| six             |             |



## 2 2D Plot Basic

### (1) Basic Plots

- 散点图
- 折线图
- 条形图
- 直方图
- 饼状图
- 箱线图

### (2) Colors & Styles

- 直接调整
- 使用style sheets

### (3) Coordinate Axes

- 坐标区间设置
- 网络线设置
- 自动标注坐标轴刻度

### (4) Text

- 基本文字插入和调整
- Tex公式

### (5) 图例

- 位图
- 外观

### (6) Tags & Comments



### (7) 分面

- 同一坐标轴绘制多图
- 同一画板绘制多图

### (8) 交互式Orders



### (9) Other Plots

- 路径图
- 形状图
- 热图

## 3 Project Training

### (1) Functions Plot

### (2) 温度、湿度、密度和距离的关系图

### (3) 球员能力分析

### (4) 股票数据图



# Usually Errors

| KeyWords              | Description                                    | Solve                              |
| --------------------- | ---------------------------------------------- | ---------------------------------- |
| no attribute 'loader' | target packages or depend pacakges are damaged | Reinstall target or depend package |
|                       |                                                |                                    |
|                       |                                                |                                    |
|                       |                                                |                                    |

