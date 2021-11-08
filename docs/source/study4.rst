Week4. 寻找重复序列(下)
===========

寻找序列重复substring
------------

示例：在字符串x中，寻找substring(某个单词s)的出现频率，x= "We come from Jupiter, and we love Jupiter. Where do you come from? Do you love Jupiter."

* 1. 重新运行一下x序列

>>> x = "We come from Jupiter, and we love Jupiter. Where do you come from? Do you love Jupiter."

* 2. 把这一个序列变成单词, 然后对每个单词计数, 用split函数, 输出为list. split函数是把一个序列按某个sep截开, 默认是空格, 也可以按其他的分隔符或别的元素隔开.

>>> y = x.split()

* 3. 以每个单词为元素, 计数每个元素出现的次数

>>> hist = {}   #新建一个字典, 用来存储元素以及出现的次数
>>> for i in range(len(y)):   #遍历y中的每个元素
>>>     if y[i] not in hist:     #not in用来判断y[i]是否在hist中
>>>         n = 1 
>>>         for j in range(i+1, len(y)):
>>>             if y[i] == y[j]:
>>>                 n += 1
>>>         if n>1:
>>>             hist[y[i]] = n

* 4. 接下来用spyder编译器, 为了便于设置断点, 来调试程序, 比如停在循环内部, 查看当前变量值. 设置断点: 光标移至要设置断点的行, debug —— Set/Clear breakpoint; 设置断点后, 不用run file, 而是用debug file来运行; 然后点击continue, 可看到变量的变化.

* 5. 将以上这几行代码写成函数, 函数名为counthist.

>>> def counthist(x):
>>>     y = x.split()
>>>     hist = {}   #新建一个字典，用来存储元素以及出现的次数
>>>     for i in range(len(y)):   #遍历y中的每个元素
>>>         if y[i] not in hist:     #not in用来判断y[i]是否在hist中
>>>             n = 1 
>>>             for j in range(i+1, len(y)):
>>>                 if y[i] == y[j]:
>>>                     n += 1
>>>             if n>1:
>>>                 hist[y[i]] = n
>>>     return hist

* 6. 调用刚刚写的函数

>>> x = "We come from Jupiter, and we love Jupiter. Where do you come from? Do you love Jupiter."
>>> temp = counthist(x)

* 7. 把函数放在一个单独的文件, 然后写另外的程序调用该函数. 此时可将包含该函数的文件写成一个.py文件, 在别的程序中调用, 比如包含该函数的.py文件名为stringsep.py, 调用方式为文件名.函数名, 以该函数为例:

>>> import stringsep
>>> x = "We come from Jupiter, and we love Jupiter. Where do you come from? Do you love Jupiter."
>>> temp = stringsep.counthist(x)

* 8. 也可以直接用: from 文件名 import 函数名, 此时适用于只需要调用该文件中的某个函数, 而不需要所有函数.

>>> from stringsep import counthist
>>> x = "We come from Jupiter, and we love Jupiter. Where do you come from? Do you love Jupiter."
>>> temp = counthist(x)

* 9. 文件名的缩写格式, 如若文件名过长, 后续操作不便, 则可以as简写.

>>> import stringsep as strs
>>> import matplotlib as plt




