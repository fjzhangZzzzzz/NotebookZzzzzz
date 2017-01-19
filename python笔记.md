# 教程

[Python教程-廖雪峰的官方网站](http://www.liaoxuefeng.com/wiki/0014316089557264a6b348958f449949df42a6d3a2e542c000)

## pip
* 配置国内源-windows
```bash
# 新建C:\Users\Administrator\pip目录，pip.ini文件，内容如下
[global]
index-url = https://pypi.tuna.tsinghua.edu.cn/simple
[install]
trusted-host=mirrors.aliyun.com
```

# PyQt5安装和使用

## 下载

[pyqt5安装](http://blog.csdn.net/zhulove86/article/details/52298203)

## 教程

[PyQt5教程](http://www.cnblogs.com/archisama/p/5442071.html)

## Pycharm配置PyQt

[ win7安装pycharm5+pyqt5+python3.4](http://blog.csdn.net/justheretobe/article/details/50492094)

* streamax-win7 External Tools配置

 1. Qtdesigner 
 ```
 [Program] C:\Users\Administrator\AppData\Local\Programs\Python\Python35-32\Lib\site-  packages\PyQt5\designer.exe
 [Parameters] 
 [Working dir] $FileDir$
 ```
 2. PyUIC
 ```
 [Program] C:\Users\Administrator\AppData\Local\Programs\Python\Python35-32\python.exe
 [Parameters] -m PyQt5.uic.pyuic $FileName$ -o $FileNameWithoutExtension$.py
 [Working dir] $FileDir$
 ```
 3. Pyrcc
 ```
 [Program] C:\Users\Administrator\AppData\Local\Programs\Python\Python35-32\Lib\site-packages\PyQt5\pyrcc5.exe
 [Parameters] -m PyQt5.uic.pyuic $FileName$ -o $FileNameWithoutExtension$_rc.py
 [Working dir] $FileDir$
```


# 脚下的坑

[常见的几个坑](http://blog.csdn.net/handsomekang/article/details/9294975)

# Some Tips

## 字符串前缀
* r或R：表示raw，（非转义）原始字符串；
* u或U：表示unicode字符串；
* b：表示字节流

## 正则表达式

* [深入理解正则表达式](http://www.cnblogs.com/China3S/archive/2013/11/30/3451971.html)

* [Python爬虫入门之正则表达式](http://cuiqingcai.com/977.html)

* [正则表达式速查表](http://www.jb51.net/shouce/jquery1.82/regexp.html)

* 正则表达式分割字符串
```python
import re
re.split(r'\s+', 'a b    c')
re.split(r'[\s\.\,]+', 'a, b., c')
```

* re模块命名组详解
[](http://blog.csdn.net/x1779702681/article/details/40401471)

## OrderdDict有序字典

* 特殊方法
```python
from collections import OrderedDict
'''
last = True, LIFO, 即为堆栈
last = False, FIFO, 即为队列
'''
OrderedDict.popitem(last=True)
```

## Base64

1. 将3个字节变成4个可打印字符
1. 一种编码转换的方法
1. 有些情况下传输不可见字符不方便

# 关于迭代

## 迭代器和生成器

[如何更好地理解Python中迭代器和生成器](https://www.zhihu.com/question/20829330)

## 迭代方案

1. for循环
```python
def forLoop():
    res = []
    for iter_var in iterable:
        res.append(expr)
    return res
```

1. 列表解析
```python
# 语法1
def listComp():
    return [expr for iter_var in iterable]
```
```python
# 语法2
def listComp():
    return [expr for iter_var in iterable if cond_expr]
```

1. map调用
```python
def mapCall():
    return list(map(expr, iterable))
```

1. 生成器表达式
```python
def genExpr():
    return list(expr for iter in iterable)
```

1. 生成器函数
```python
def genFunc():
    def gen():
        for iter in iterable:
            yield expr
    return list(gen()) 
```