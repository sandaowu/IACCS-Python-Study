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

* 4. 定义函数抓取菜谱中每一道菜做法的网页

>>> def getReceipURL(urlAll, n):
>>>    source = requests.get(urlAll, headers={'user-agent': 'Safari/13.1'}).text
>>>    source = BeautifulSoup(source, "html")
>>>    receip = source.body.find('div', class_='pure-u-2-3 main-panel')
>>>    sc = receip.find_all('div', class_='recipe recipe-215-horizontal pure-g image-link display-block')
>>>    URLs = []
>>>    for i in range(n):
>>>        thisurl = sc[i].find('p', class_='name').a['href']
>>>        URLs.append('https://www.xiachufang.com' + thisurl)
    return URLs

>>> substr_frequency={}
>>> substr_num=0
>>> for i in range(len(S0)-len(s)+1):
>>>     if S0[i : i+7] == s:    
>>>         substr_num += 1
>>>         substr_frequency[s]= substr_num


python学习参考资料
-------------
廖雪峰Python教程 https://www.liaoxuefeng.com/wiki/1016959663602400 
