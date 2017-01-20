# 参考
[如何入门Python爬虫 - 知乎](https://www.zhihu.com/question/20899988)

# Some Tricks

* gzip和zlib：gzip是针对文件来压缩与解压缩的。，而对于数据压缩与解压，是用zlib，所以在对获取到的html数据read后调用gzip.decompress报错

* 获取html后解码失败：[urlopen获取网页过程添加gzip解压](http://www.crifan.com/compress_html_in_urllib2_open_then_decompress_returned_gzip_data_in_python/)

# Some Tips

* 爬虫框架scrapy配置

 1. 安装pywin32
```
pip3 install pypiwin32
```
 1. 安装pyOPENSSL
```
pip3 install pyOPENSSL
```
 1. 安装lxml
```
pip3 install lxml
```
 1. 安装scrapy
```
# 要求Microsoft Visual C++ 14.0以上，下载地址：
# http://landinghub.visualstudio.com/visual-cpp-build-tools
pip3 install scrapy
```

* 父类异常的捕获应该放到子类异常后面

* HTTP Header中字段
```
User-Agent    : 请求用户的身份
Content-Type  : HTTP中body内容类型
Referer       : 用以判断请求来源
```

* HTTP请求方法，HTTP服务器应至少实现GET和HEAD/POST请求
```
GET     : 向指定资源发出请求
POST    : 向指定资源提交数据进行处理请求
PUT     : 向指定资源上传其最新内容
DELETE  : 请求服务器删除Request-URL资源
OPTIONS : 返回服务器针对特定资源所支持的HTTP请求方法
HEAD    : 与GET请求相同，但只请求返回页面首部
TRACE   : 回显服务器收到的请求，主要用于测试
CONNECT :
```
 1. GET请求
```python
# python3
from urllib.request import urlopen, Request
request = Request("www.xxoo.com")
reponse = urlopen(request)
print(reponse.read())
```
 1. POST请求
```python
# python3
import urllib
from urllib.request import urlopen, Request
signin_info = {"username":"fjzhang", "password":"xxoo"}
data = urllib.urlencode(signin_info)
url = "www.xxoo.com"
request = Request(url, data)
reponse = urlopen(request)
print(reponse.read())
```
 1. HEAD请求
```python
# python3
from urllib.request import urlopen, Request
request = Request("www.xxoo.com")
request.get_method = lambda : 'HEAD'
reponse = urlopen(request)
print(reponse.read())
```

## urllib设置项
1. 设置Header
1. 设置代理Proxy
1. 设置超时Timeout

## urlopen使用
[Python urlopen使用示例](http://blog.csdn.net/leer168/article/details/8643103)
```python
# 
```

## 进阶工具

* requests：
> - [requests用法简介](http://cuiqingcai.com/2556.html)
> - [官方文档](http://docs.python-requests.org/en/master/api/)

 1. 封装基本请求方法；
 1. cookies获取与发送；
 1. 超时设置；
 1. 创建持久会话；
 1. SSL证书验证；
 1. 代理；
 
 
* Beautiful Soup：
> - [BS用法简介](http://cuiqingcai.com/1319.html) 
> - [官方文档](http://beautifulsoup.readthedocs.io/zh_CN/latest/)

 1. 从网页抓取数据；
 1. 自动将输入文档转为unicode，将输出文档转为utf-8；
 1. 解析html，获取标签信息，包括标签本身信息和其中内容和注释；
 1. 遍历文档树，获取各节点信息；
 1. 搜索文档树，搜索指定标签下节点；
 1. CSS选择器，多种查找方式；
 
 
* lxml：
> - [官方文档](http://lxml.de/index.html)
> - [XPath教程](http://www.w3school.com.cn/xpath/index.asp)

 1. 使用XPath语法；
 1. 解析xml文档，查找信息；