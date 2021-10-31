Week 2
=====
Coding
------------
**寻找序列重复substring**

示例：在字符串S0中，寻找substring(某个单词s)的出现频率，S0= "We come from Jupiter, and we love Jupiter. Where do you come from? Do you love Jupiter."

* 1. 将字符串赋值给str类型的S0

``S0='We come from Jupiter, and we love Jupiter. Where do you come from? Do you love Jupiter.'``

* 2. 确定待搜索的substring, 这里以Jupiter为例

``s='Jupiter'``

* 3. 创建一个空的字典substr_frequency用于保存substring的出现次数，同时通过int型变量substr_num记录substring的出现次数，substr_num初值为0。

``substr_frequency={}``

``substr_num=0``

* 4. 通过下标i，遍历字符串S0，找到与substr完全相同的S0切片，

``substr_frequency={}``

``substr_num=0``

``for i in range(len(S0)-len(s)+1):``

    ``if S0[i : i+7] == s:``
    
        ``substr_num += 1``
        
``substr_frequency[s]= substr_num``


python学习参考资料
-------------
廖雪峰Python教程 https://www.liaoxuefeng.com/wiki/1016959663602400 
