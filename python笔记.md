# 教程

[Python教程-廖雪峰的官方网站](http://www.liaoxuefeng.com/wiki/0014316089557264a6b348958f449949df42a6d3a2e542c000)


# PyQt5安装

## 下载
[pyqt5安装](http://blog.csdn.net/zhulove86/article/details/52298203)

## 教程

[PyQt5教程](http://www.cnblogs.com/archisama/p/5442071.html)


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