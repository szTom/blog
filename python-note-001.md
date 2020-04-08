[TOC]

# 1	输入和输出
## 1.1	print()
打印括号里的内容
 - 无引号，打印数字，计算机阅读并理解括号里的内容，打印结果（数字间若有计算符号，会输出计算结果）；`` print(1+1) ``
 - 单/双引号，打印字符串，计算机不管引号中的内容（原样输出）；
 ``print("Let's go")`` ``print('Let\'s go') ``
 - 三引号，打印段落（原样输出）；
同html的``<pre>多行文本</pre>``标签

**单/双引号里适当使用 \n 换行，可实现与三引号相同效果；**

 转义字符列表
 | 转义字符 | 意义 |
 |

## 1.2	input()
收集从键盘输入的信息:
```
  name = input('请输入你的 ID: ')
  print(str(input('pls input\n')))
```
 **input()函数的输入值永远会被【强制性】地转换为【字符串】类型。(Python3固定规则)**

# 2	变量和赋值
```
  name='xxx'
  print(name)
  xxx
```
 - =  **是赋值符号，将右边的内容赋值给左边的变量；**
 - == **是比较运算符号，表示两边相等；**

## 2.1	变量的命名规范
1. 只能是一个词；
2. 只能包含字母，数字和下划线；
3. 不能以数字开头；
4. 尽量描述包含的数据内容；
5. 不要使用Python函数名或关键字；
 - number = 34
 - name = 'forchange'
 - list_class = ['基础语法课程','爬虫分析初阶','爬虫分析进阶','自动化办公']
_以上number，name，list_class都是是变量名_

## 2.2	查看python的关键字
```
 import keyword
 keyword.kwlist
  ['False', 'None', 'True', 'and', 'as', 'assert', 'async', 'await', 'break', 'class', 'continue', 'def', 'del', 'elif', 'else', 'except', 'finally', 'for', 'from', 'global', 'if', 'import', 'in', 'is', 'lambda', 'nonlocal', 'not', 'or', 'pass', 'raise', 'return', 'try', 'while', 'with', 'yield']
```
False, None, True, and, or, not, def, del, import,
if, elif, else, for, while, break, continue, return, pass, try, except,
as, in, is, from, with,
assert, async, await, class, finally, global, lambda, nonlocal, raise, yield

判断是否为关键字:
```
  keyword.iskeyword('false')
  False
  keyword.iskeyword('False')
  True
```
# 3	条件判断
 - if [条件0] : (缩进的内容)  \\ 单向判断
 - if [条件0] : (缩进的内容) else: (缩进的内容)  \\ 双向判断
 - if [条件0] : (缩进的内容) elif [条件1] : (缩进的内容) else: (缩进的内容)  \\ 多向判断
对于Python而言，冒号和缩进是一种语法。它会帮助Python区分代码之间的层次，理解条件执行的逻辑及先后顺序。
【注：缩进是四个空格或一个Tab键】
**IndentationError: expected an indented block(缩进错误：期望一个缩进块)**

if嵌套，就是在上面任何一个(缩进的内容)中添加一个if结构

# 4	常见的数据类型
 - srt string字符串, 用引号括起来的文本;
 - int integer整数, 不带小数点的数字;
 - float 浮点数, 带小数点的数字，运算结果存在误差;
 - bool 布尔值, True or False;
 - dice dictionary字典, 使用键值对(key-value)作为存储方式. 标识是大括号{};
 - list 列表, 有序的集合，可以随时添加或删除其中的元素. 标识是中括号[];
 - tuple 元组, 类似列表的数据类型，但是不能被修改。

## 4.1	浮点数的运算误差
```
print(0.55+0.3)
0.8500000000000001
```
为什么不是【0.85】，而尾巴多了一个【1】呢？这是因为，Python计算浮点数时，会先把0.55和0.3转化成二进制数. **[注：二进制数由0和1表示，逢二进一]**，如下:

进制转换:
```
0.55(十进制) = 0.1000110011001100110011001100110011001100110011001101(二进制)
0.3 (十进制) = 0.0100110011001100110011001100110011001100110011001101(二进制)
```
而在这个转化过程中存在误差，这样，就造成了我们与程序计算结果的差异。


# 5	数据的操作
## 5.1	字符串的拼接
 - '+' print(hero+action+organization+identity+ID) //字符串拼接, 不是字符串需要转换为字符串
 - '%' print ('print%dnam%s'%(number,name)) ///不同类型的拼接

## 5.2	四则运算
 - +
 - -
 - *
 - /
 - % 取模-返回除法的余数；5%2，返回1
 - // 取整除-返回商的整数部分；5//2, 返回2
 - ** 幂-返回x的y次幂；2**3, 2的3次方

**与平时运算优先级一样：从左到右顺着来，括号里的优先算，乘除排在加减前。**

## 5.3  数据转换
 - str() 强制转换为字符串
 - int() 将整数形式的字符串转换为整数，(文本和浮点数不能转换为整数)
   - print(int(3.3)) 浮点数直接抹零取整数
 - float() 将整数和数字形式的字符串转换为浮点数，(文字类字符串无法转转)
 - list() 将数据转换为列表类型
```
>>> name = 'python'
>>> print(list(name))
['p', 'y', 't', 'h', 'o', 'n']
```
 - len() 返回数据长度
 ```
>>> namelist=list(name)
>>> list2= ['py','th','on']
>>> len(name)
6
>>> len(namelist)
6
>>> len(list2)
3
```

## 5.4  type(),查询数据类型
```
  print(type(who))
  <class 'str'>
```
## 5.5 list列表语法
- 偏移量: 列表元素的位置编号, 从0开始
- 对列表元素的处理: 增, 删, 改, 查(提取)
  - 提取: list[0] 取出位置0的元素; list[a:b] 取出位置a到b, 但不包括b的所有元素(a<=X小于b); list[:]全部;
  - 修改: list[0]='tree0'
  - 增加: list.append('tree3') 添加到列表末尾，注意append()函数后面是小括号,不是方括号
  - 删除: del list[0]
- 对列表的处理: 增, 删, 改, 查(提取)
  - 提取: list[1:2] 列表的切片(子列表, 列表片段)，一次提取多个元素
  - 删除: del list[1:2] 删除切片(子列表, 列表片段)，一次删除多个元素
  - 增加(合并): list = list1 + list2 列表的合并
  - 修改(赋值): list = ['0','1','2']; list[:] = ['xx'] 对列表赋值
- 嵌套列表的提取
```
>>> list = [['0','0a'],['1','1b'],['2','2c']]
>>> print(list[0][1])
  0a
```
## 5.6  dict字典语法
group={'k1':'v1','k2':'v2','k3':'k3'}
- 增加: group['k4']=v4 ;
- 删除: del group['k4'] ;
- 修改: group['k1']=v11 ;
- 提取: group['k1'] 取出v1 ; 列表使用偏移量来提取，字典使用键来提取
- dict.deys() 提取字典中所有键
  -  group.keys() 元组的形式
  -  list(group.keys()) 将元组转换为列表
- dict.valus() 提取字典中所有的值
  -  group.values()
- dict.items() 提取字典中所有键值对
  -  group.items()

## 5.7  bool()
检查数值的真假
```
>>> print(bool(1))
  True
```
值本身作为条件

| Type   | 假值  | 其他都是真值     |
| ------ | ----- | ---------------- |
| bool   | False | True             |
| number | 0     | 非0数值(int, fl) |
| srt    | '’    | 非空字符串       |
| list   | []    | 非空列表         |
| dict   | {}    | 非空字典         |
|        | None  |                  |

比较运算符产生布尔值

| 运算符 | 释义     |
| ------ | -------- |
| '==    | 等于     |
| !=     | 不等于   |
| >      | 大于     |
| <      | 小于     |
| >=     | 大于等于 |
| <=     | 小于等于 |

**运算符之间不用空格，不可以写成= =、> =**

成员运算符产生布尔值

| 运算符 | 释义   |
| ------ | ------ |
| in     | 属于   |
| not in | 不属于 |

逻辑运算符产生布尔值

| 运算符 | 释义 |
| ------ | ---- |
| and    | 与   |
| or     | 或   |
| not    | 非   |

# 6 循环
## 6.1  for循环
for 条件 : (缩进的内容)

 - 遍历字符串
 ```
# py01.py文件内容:
for i in 'code':
    print(i)
# bash下执行:
> python py01.py
c
o
d
e
```

- 遍历列表
```
# py01.py文件内容:
for i in ['code','py']:
    print(i)
# bash下执行:
> python py01.py
code
py
```
- 遍历字典的键
```
# py01.py文件内容:
list = {1:'a',2:'b',3:'c'}
for i in list:
    print(i)
# bash下执行:
> python py01.py
1
2
3
```

- 遍历字典的值
```
# py01.py文件内容:
list = {1:'a',2:'b',3:'c'}
for i in list.values():
    print(i)
# bash下执行:
> python py01.py
a
b
c
```

- 遍历字典的键值对
```
# py01.py文件内容:
list = {1:'a',2:'b',3:'c'}
for k, v in list.items():
    print(k)
    print(v)
# bash下执行:
> python py01.py
1
a
2
b
3
c
```

### range()函数
range()有最基本的三种用法：range(a)， range(a,b)，range(a,b,c)。
* a：计数从a开始。不填时，从0开始；b：计数到b结束，但不包括b；c：计数的间隔，不填时默认为1。
```
range(5)
# 计数依次为0，1，2，3，4
range(1,5)
# 计数依次为1，2，3，4
range(2,8,2)
# 计数依次为2，4，6
```

### for…in range()
处理指定次数的循环
```
for i in range(3):
    print('第%d行' %i)
```
## 6.2  while循环
只要条件为真，便会一直循环
```
count = 3
while count > 1:
    print('happy coding')
    count = count -1
happy coding
happy coding
```
while循环和for循环的区别:
- for擅长处理固定次，自动遍历各序列
- while处理不定次数的循环，条件为False便停止

## 6.3  循环进阶
- break, 结束循环
- continue, 跳过当前循环的剩余语句, 直接开始下一轮循环
- else, 无论是否进入循环, 最后都会执行esle语句, 除非执行break语句跳出循环
```
while True:
    print('happy coding')
    break
```
循环嵌套
```
>for i in ['qw','ert']:    #首先遍历列表元素
...    for t in i:         #然后遍历元素(字符串)
...        print(t)
```

## 6.4  补充: Python风格规范
Docs » Python 风格指南 - 内容目录 » Python风格规范

https://zh-google-styleguide.readthedocs.io/en/latest/google-python-styleguide/python_style_rules/
