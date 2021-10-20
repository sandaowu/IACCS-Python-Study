学习Week1
=====

.. _introduction:

Introduction & Install
------------
**安装Anaconda**
可参考https://cloud.tencent.com/developer/article/1624458

* 下载anaconda https://www.anaconda.com/products/individual
* 以管理员身份运行、安装：All users；不勾选Add Anaconda to the system PATH environment variable（容易出问题，我们自己添加，如下）；安装时间较长大概15分钟
* 搜索框输入``环境变量``-> 弹出的菜单中选择右下方的``环境变量``  -> 在下方的``系统变量``（注意不是用户变量）选中``Path`` -> 单击``编辑`` -> 单击``新建`` -> 将路径（见下）粘贴进去，点确定
* 须显示隐藏项
  ``"C:\ProgramData\Anaconda3"``

  ``"C:\ProgramData\Anaconda3\Scripts"``

  ``"C:\ProgramData\Anaconda3\Lib\site-packages"``

  ``"C:\ProgramData\Anaconda3\Library\bin"``
* 验证  开始菜单打开Anaconda Prompt (Anaconda3) -> 输入conda --version -> 输入python --verison 开始菜单打开Anaconda Navigator查看（Jupyter, Spyder）


示例
