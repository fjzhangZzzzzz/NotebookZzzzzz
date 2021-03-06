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
 
 
* Beautiful Soup：HTML解析库
> - [BS用法简介](http://cuiqingcai.com/1319.html) 
> - [官方文档](http://beautifulsoup.readthedocs.io/zh_CN/latest/)

 1. 从网页抓取数据；
 1. 自动将输入文档转为unicode，将输出文档转为utf-8；
 1. 解析html，获取标签信息，包括标签本身信息和其中内容和注释；
 1. 遍历文档树，获取各节点信息；
 1. 搜索文档树，搜索指定标签下节点；
 1. CSS选择器，多种查找方式；
 
 
* XPath & lxml：
> - [简介和用法](http://cuiqingcai.com/2621.html)
> - [lxml官方文档](http://lxml.de/index.html)
> - [XPath教程](http://www.w3school.com.cn/xpath/index.asp)

 1. XPath：HTML/XML查询语言；
 1. 解析HTML/XML文档，查找信息；
 

* PhantomJS：
> - [简介和用法](http://cuiqingcai.com/2577.html)
> - [PhantomJS官网](http://phantomjs.org/)
> - [官方文档](http://phantomjs.org/quick-start.html)

 1. 无界面的,可脚本编程的WebKit浏览器引擎；
 1. 基于WebKit的服务器端JS API；
 1. 支持web功能，无需浏览器，渲染JS处理的页面；
 1. 可用于网页自动化、网络监测、网页截屏、无界面测试；
 
 
* Selenium：
> - [简介和用法](http://cuiqingcai.com/2599.html)

 1. Web自动化测试工具，用以模拟用户对浏览器的操作来实现自动化自称；
 1. 支持多种浏览器，包括PhantomJS；
 
 
* 进阶工具小结

 1. HTTP请求
 > - requests库
 
 1. 解析网页
 > - 正则表达式，速度最快
 > - html.parser，python内置解析，速度最慢
 > - Beautiful Soup，使用较简单，性能相对低
 > - pyQuery，语法同iQuery；
 > - XPath，上手需要学习XPath语法；