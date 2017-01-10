# 关于迭代

## 迭代器和生成器

[如何更好地理解Python中迭代器和生成器](https://www.zhihu.com/question/20829330)

## 迭代方案

1. for循环
```python
def forLoop():
    res = []
    for iter_var in iterable:
        ...
    return expr
```

1. 列表解析
```python
def listComp():
    return [expr for iter_var in iterable]
```
```python
def listComp():
    return [expr for iter_var in iterable if cond_expr]
```

1. map调用
```python
def mapCall():
    return 
```

1. 生成器表达式
```python
def 
```

1. 生成器函数