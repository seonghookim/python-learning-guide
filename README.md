### 使用 selenium webdriver
* 打开本地htm文件
```
from selenium import  webdriver
import os

browser = webdriver.Chrome()
browser.get('file:///'+os.path.abspath('template.htm'))
```
* 打开百度
```
from selenium import  webdriver

browser = webdriver.Chrome()
browser.get('http://www.baidu.com/')
# 隐式地等待一个元素被发现或一个命令完成；这个方法每次会话只需要调用一次
browser.implicitly_wait(2)
# 按ID查找搜索框。搜索框里输入字符(“韩国美女写真”)
browser.find_element_by_id('kw').send_keys("韩国美女写真")
# 模拟点击“百度一下”按钮
browser.find_element_by_id("su").click()
```
* [selenium库的用法](https://www.cnblogs.com/mzc1997/p/7814002.html)
* [Selenium之选择元素](https://blog.csdn.net/chengsw1993/article/details/92633313)
    

### 使用 BeautifulSoup
* [Beautiful Soup 4.4.0 文档](https://www.crummy.com/software/BeautifulSoup/bs4/doc.zh/) 

* 打开本地htm文件
```
from bs4 import BeautifulSoup

soup = BeautifulSoup(open("template.htm"))
print(soup.body.text)
```

* 打开百度
```
import requests
from bs4 import BeautifulSoup

response = requests.post('http://www.baidu.com')
soup = BeautifulSoup(response.content, "html5lib")
print(soup.body.text)
```
