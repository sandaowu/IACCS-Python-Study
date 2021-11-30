Week6. 面向对象编程
===========

python是面向对象编程，就是说给我们一个任务，我们不需要做具体的完成任务的每一个具体步骤，而是把这个任务交给对象来做，对象具有完成这个任务的技能。

------------

类是某一个具体对象特征的抽象。根据对象可以抽象出一个类，通过类可以实例化为具体对象。

* 1. 定义一个类
>>> import matplotlib.pyplot as plt   #导入模块要写在类前面
>>> class SMARTSTRING(object):    #定义一个类，类名是SMARTSTRING  
>>>     def __init__(self, str0):  #初始化
>>>         self.data = str0
>>>         self.histdata = None
>>> 
>>>     def FindDup(self):   #定义一个实例方法，第一个形参是它本身
>>>         x = self.data
>>>         hist = {}
>>>         for i in range(len(x)):
>>>             for j in range(i+1, len(x)+1):
>>>                 substr = x[i:j]
>>>                 n = 1
>>>                 if substr not in hist:
>>>                     for k in range(i+1,len(x)+1):
>>>                         substr_tocompare = x[k:k+len(substr)]
>>>                         if substr == substr_tocompare:
>>>                             n += 1
>>>                     if n > 1:
>>>                         hist[substr] = n
>>>         self.histdata = hist
>>>         
>>>     def Plot(self, n, figname=None):      #定义一个方法
>>>         x = list(self.histdata.keys())[:n]
>>>         y = list(self.histdata.values())[:n]
>>>         plt.bar(list(range(len(y))), y)
>>>         plt.ylabel('Counts')
>>>         plt.xlabel('Substrings')
>>>         ax = plt.gca() # grab the current axis
>>>         ax.set_xticks(list(range(n))) 
>>>         ax.set_xticklabels(x)
>>>         if figname is not None:
>>>             plt.savefig(figname)

* 2. 根据这个类，创建(实例化)一个对象

>>> x = 'We come from Jupiter, and we love Jupiter. Where do you come from? Do you love Jupiter.'
>>> mystr = SMARTSTRING(x)   #根据SMARTSTRING类实例化出来的对象，由mystr接收

* 3. 调用方法

>>> mystr.FindDup()  #调用方法FindDup，调用方法需要先创建实例mystr,即 mystr = SMARTSTRING(x), 然后再通过 目标.方法. 
>>> mystr.Plot(10)   #必须传入一个参数，第一个参数自动传入，我们只需要传入n就可以. 
