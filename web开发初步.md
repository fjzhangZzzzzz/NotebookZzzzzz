* 利用python自带wsgiref模块编写简单web应用

```python
'''
浏览器端通过http:\\localhost:8888访问
'''

import sys

from wsgiref.simple_server import make_server

def application(environ, start_response):
    start_response('200 OK', [('Content-Type', 'text/html')])
    __body = '<h1>Hello, {0} on {1}!'.format(environ['PATH_INFO'][1:] or 'Web', sys.platform)
    return [__body.encode('utf-8')]

if __name__ == '__main__':
    _port = 8888
    _httpd = make_server('', _port, application)
    print('Serving HTTP on Port[{0}]'.format(_port))
    _httpd.serve_forever()
```