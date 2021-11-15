Week5. 寻找重复序列（终结版）
===========

寻找字符串中所有重复序列substr以及出现频次并画出条形图
------------

示例：在字符串s中，寻找substr(所有重复的亚结构)出现次数，s= "We come from Jupiter, and we love Jupiter."

* 1. 运行一个序列s

>>> s = "We come from Jupiter, and we love Jupiter."

* 2. 把这一个序列用for循环从第一个字符开始到最后遍历序列所有亚结构

>>> for i in range(len(s)):
>>>     for j in range(i+1,len(s)+1):
>>>         substr = s[i:j]
>>>         print(substr)
        
* 3. 计算每个substr出现的次数,并将出现重复次数大于1的存入字典hist中

>>> n = 1   #出现的亚结构默认次数为1
>>> if substr not in hist:
>>>     for k in range(i+1,len(s)+1):
>>>         substr_tocompare = s[k:k+len(substr)]
>>>         if substr == substr_tocompare:
>>>             n += 1
>>>     if n > 1:
>>>         hist[substr] = n


* 4. 画出所有亚结构及其出现频次的条形图并保存
>>> import matplotlib.pyplot as plt #导入画图工具

>>> x = list(hist.keys())[:10]    #横坐标画出前10个重复的亚结构
>>> y = list(hist.values())[:10]  #纵坐标相应的重复次数
>>> plt.bar(x,y)  #画出条形图
>>> plt.ylabel('Counts')  #设置纵坐标的名称
>>> plt.xlabel('Substrings') #设置横坐标的名称
>>> plt.savefig('fig1.png')  #将图片保存到工作区
