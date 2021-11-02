Week 3
=====
Coding
------------
**Python网站数据爬虫**

示例："下厨房"网站的本周最欢迎菜谱数据；网站地址: https://www.xiachufang.com/explore/

* 1. 导入BeautifulSoup库

# BeautifulSoup是python的一个库，最主要的功能是从网页抓取数据；BeautifulSoup已经被移植到bs4了，也就是说导入时我们需要 import bs4

>>> from bs4 import BeautifulSoup

* 2. 导入requests的整个模块（所有类）

# requests是一个Python第三方库，处理URL资源特别方便

>>> import requests

* 3. 定义需要抓取数据网页的URL

>>> urlALL = 'https://www.xiachufang.com/explore/'

* 4. 定义getReceipURL函数抓取菜谱中每一道菜做法的网页

>>> def getReceipURL(urlAll, n):
>>>    source = requests.get(urlALL, headers={'user-agent': 'Safari/13.1'}).text
       # 创建source对象。使用.get访问一个urlALL页面，设置了headers，对爬虫的浏览器进行设置，最后以字符串形式返回对象
>>>    source = BeautifulSoup(source, "html")
       # 创建了BeautifulSoup对象
>>>    receip = source.body.find('div', class_='pure-u-2-3 main-panel')
       # 在source的body中找到title为div，类为'pure-u-2-3 main-panel'的对象
>>>    sc = receip.find_all('div', class_='recipe recipe-215-horizontal pure-g image-link display-block')
       # 在receip中find所有满足条件的对象
>>>    URLs = []
       # 定义一个空列表
>>>    for i in range(n):
>>>        thisurl = sc[i].find('p', class_='name').a['href']
           # 在sc[i]中find对应类中标签为href的对象
>>>        URLs.append('https://www.xiachufang.com' + thisurl)
           # 将thisurl与列表中元素'https://www.xiachufang.com'
>>>    return URLs
           # 返回URLs
           
* 4. 输出每一道菜的做法

>>> url = URLs[1]
>>> [title, ings, steps] = getReceipFromURL(url)
>>> print(title)
>>>  for i in ings:
         print(i, ':', ings[i])
>>>  for i in steps:
         print(i, ':', steps[i])


python学习参考资料
-------------
廖雪峰Python教程 https://www.liaoxuefeng.com/wiki/1016959663602400 
