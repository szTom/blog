[TOC]

# 1 类与对象概念
- 类(Class): 用来描述具有相同的属性和方法的对象的集合。它定义了该集合中每个对象所共有的属性和方法。对象是类的实例。
- 类变量：类变量在整个实例化的对象中是公用的。类变量定义在类中且在函数体之外。类变量通常不作为实例变量使用。
- 数据成员：类变量或者实例变量, 用于处理类及其实例对象的相关的数据。
- 方法重写：如果从父类继承的方法不能满足子类的需求，可以对其进行改写，这个过程叫方法的覆盖（override），也称为方法的重写。
- 局部变量：定义在方法中的变量，只作用于当前实例的类。
- 实例变量：在类的声明中，属性是用变量来表示的。这种变量就称为实例变量，是在类声明的内部但是在类的其他成员方法之外声明的。
- 继承：即一个派生类（derived class）继承基类（base class）的字段和方法。继承也允许把一个派生类的对象作为一个基类对象对待。例如，有这样一个设计：一个Dog类型的对象派生自Animal类，这是模拟"是一个（is-a）"关系（例图，Dog是一个Animal）。
- 实例化：创建一个类的实例，类的具体对象。
- 方法：类中定义的函数。
- 对象：通过类定义的数据结构实例。对象包括两个数据成员（类变量和实例变量）和方法。

基本语法
# 2  class
https://docs.python.org/zh-cn/3/tutorial/classes.html
https://www.runoob.com/python/python-object.html

```
#!/usr/bin/python
# -*- coding: UTF-8 -*-

class MyClass:    # [1. 定义类]，大写字母开头 __name__
    '描述文本'     # 描述文本， __doc__
    i = 123       # 定义类的变量，小写字母开头
    myCount = 0
    def __init__(self, name, page):
        self.name = name
        self.page = page
        MyClass.myCount += 1
    def displayCount(self):
        print ("Total myCount: ", MyClass.myCount)
    def displayName(self):
        print ("name: ", self.name, ", page: ", self.page)
    def f(self):   # 定义类的方法，小写字母开头
        return ('hi py!')
    def prt(self):
        print (self)
        print (self.__class__)

print ("-----内置类属性-----------")    # [2. 内置类属性]
print ("MyClass.__doc__: ", MyClass.__doc__)
print ("MyClass.__name__: ", MyClass.__name__)        # 实例没有这个属性
print ("MyClass.__module__: ", MyClass.__module__)
print ("MyClass.__bases__: ", MyClass.__bases__)      # 实例没有这个属性
print ("MyClass.__dict__: ", MyClass.__dict__)
print ("MyClass.__class__: ", MyClass.__class__)
print ("--------分-割-线--------\n")

x1 = MyClass("python",100)      # [3. 创建类的实例对象]
print ("访问属性:", x1.i)        # [4. 访问属性]，打印实例x1的属性
print ("访问方法:", x1.f())      # 打印实例x1的f方法
print ("total myCount %d" % MyClass.myCount)
print ("--------分-割-线--------\n")

print ('==== x1.prt begin====')
x1.prt()
print ('==== x1.prt end====')
print ("--------分-割-线--------\n")

x1.displayCount()
x1.displayName()
print ("--------分-割-线--------\n")

print ("----内置属性----")  # [5. 内置属性]
print (x1.__doc__)
print (x1.__module__)   # __main__
print (x1.__dict__)     # {}
print (x1.__class__)     # <class '__main__.MyClass'>
print ("--------分-割-线--------\n")

x2 = x1      # [6. ]
print ('x2 = x1')
print ('x1.displayCount():')
x1.displayCount()    # myCound = 1;
print ('x2.displayCount():')
x2.displayCount()    # myCound = 1;
print ("MyClass.myCount %d" % MyClass.myCount)    # myCound = 1;
print ("--------分-割-线--------\n")

x3 = MyClass("python2",200)      # [3. 创建类的实例对象]
print ('x3 = MyClass("python2",200)')
print ('x1.displayCount():')
x1.displayCount()    # myCound = 2;
print ('x3.displayCount():')
x3.displayCount()    # myCound = 2;
print ("MyClass.myCount %d" % MyClass.myCount)    # myCound = 2;
print ("--------分-割-线--------\n")

print (id(x1), id(x2), id(x3))    # 打印对象的id
del x1      # [7. 销毁实例]，回收资源
del x2
del x3
print ('x1,x2,x3已销毁')
print ("销毁后，继续使用实例x1，就会报错: NameError: name 'x1' is not defined")
```
# 3 执行结果
```
> python py01.py
-----内置类属性-----------
MyClass.__doc__:  描述文本
MyClass.__name__:  MyClass
MyClass.__module__:  __main__
MyClass.__bases__:  (<class 'object'>,)
MyClass.__dict__:  {'__module__': '__main__', '__doc__': '描述文本', 'i': 123, 'myCount': 0, '__init__': <function MyClass.__init__ at 0x7f499f92df70>, 'displayCount': <function MyClass.displayCount at 0x7f499f95f040>, 'displayName': <function MyClass.displayName at 0x7f499f95f0d0>, 'f': <function MyClass.f at 0x7f499f95f160>, 'prt': <function MyClass.prt at 0x7f499f95f1f0>, '__dict__': <attribute '__dict__' of 'MyClass' objects>, '__weakref__': <attribute '__weakref__' of 'MyClass' objects>}
MyClass.__class__:  <class 'type'>
--------分-割-线--------

访问属性: 123
访问方法: hi py!
total myCount 1
--------分-割-线--------

==== x1.prt begin====
<__main__.MyClass object at 0x7f499f9a3490>
<class '__main__.MyClass'>
==== x1.prt end====
--------分-割-线--------

Total myCount:  1
name:  python , page:  100
--------分-割-线--------

----内置属性----
描述文本
__main__
{'name': 'python', 'page': 100}
<class '__main__.MyClass'>
--------分-割-线--------

x2 = x1
x1.displayCount():
Total myCount:  1
x2.displayCount():
Total myCount:  1
MyClass.myCount 1
--------分-割-线--------

x3 = MyClass("python2",200)
x1.displayCount():
Total myCount:  2
x3.displayCount():
Total myCount:  2
MyClass.myCount 2
--------分-割-线--------

139954187023504 139954187023504 139954187023744
x1,x2,x3已销毁
销毁后，继续使用实例x1，就会报错: NameError: name 'x1' is not defined
```
