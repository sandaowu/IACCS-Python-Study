Week 3
=====
Coding
------------
**Python网站数据爬虫**

示例："下厨房"网站的本周最欢迎菜谱数据；网站地址: https://www.xiachufang.com/explore/

* 1. 
（代码块）
>>> S0='We come from Jupiter, and we love Jupiter. Where do you come from? Do you love Jupiter.'

* 2. 

>>> s='Jupiter'

* 3. 

>>> substr_frequency={}
>>> substr_num=0

* 4. 

>>> substr_frequency={}
>>> substr_num=0
>>> for i in range(len(S0)-len(s)+1):
>>>     if S0[i : i+7] == s:    
>>>         substr_num += 1
>>>         substr_frequency[s]= substr_num


python学习参考资料
-------------
廖雪峰Python教程 https://www.liaoxuefeng.com/wiki/1016959663602400 
