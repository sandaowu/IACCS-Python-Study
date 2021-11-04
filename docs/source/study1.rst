Week1. Python安装
=====

.. _introduction:

介绍 & 安装（Windows 10）
------------
**安装Anaconda**
可参考 https://cloud.tencent.com/developer/article/1624458

* 下载anaconda https://www.anaconda.com/products/individual
* 以管理员身份运行、安装：All users；不勾选Add Anaconda to the system PATH environment variable（容易出问题，我们自己添加，如下）；安装时间可能较长，大概15分钟
* 搜索框输入 ``环境变量`` -> 弹出的菜单中选择右下方的 ``环境变量`` -> 在下方的 ``系统变量`` （注意不是用户变量）选中 ``Path`` -> 单击 ``编辑`` -> 单击 ``新建`` -> 将路径（见下）粘贴进去，点确定
* 须显示隐藏项

  ``"C:\ProgramData\Anaconda3"``

  ``"C:\ProgramData\Anaconda3\Scripts"``

  ``"C:\ProgramData\Anaconda3\Lib\site-packages"``

  ``"C:\ProgramData\Anaconda3\Library\bin"``
  
* 验证  
  开始菜单打开Anaconda Prompt (Anaconda3) 
  
  -> 输入 ``conda --version`` 
  
  -> 输入 ``python --verison`` 
  
  开始菜单打开Anaconda Navigator查看（Jupyter, Spyder）

如何打开Jupyter
------------------
打开Anaconda Prompt -> 输入 ``cd 你的程序所需要放置的目录`` 回车
（比如 ``cd C:\ErnestLocal\PythonCodes\StudySession1`` ） 

！！！注意：文件夹名称不要有空格（建议在你建任何文件、文件夹的时候都不要有空格，实在需要间隔可以用下划线 _ 或短横杠 - ）

-> 输入 ``jupyter notebook`` （注：Ctrl+C是退出）

-> 点击 ``New`` -> 点击 ``Python 3`` 则进入编译环境

设置虚拟环境
---------------
* 查看已有的虚拟环境

Anaconda Prompt命令行下 -> ``conda env list`` 

* 创建新的虚拟环境

-> ``conda create -n 你设置的虚拟环境名称（例如test）`` （注：可以跟或不跟python=3.x）

* 进入虚拟环境（可以看到前面的括号里有test，而不是base）

-> ``conda activate test`` 

* 退出虚拟环境 

-> ``conda deactivate`` 

* 删除虚拟环境 

-> ``conda remove -n 虚拟环境名称 --all`` 

添加Package
-------------
Anaconda Prompt切换到你需要安装package到的环境中（可以是虚拟环境，可以是base）

（！！！一定要用管理员权限打开，否则例如pandas都无法安装）

-> conda install 后面跟命令（例如： ``conda install pandas`` ）

常用的package安装：

-> ``conda install pandas`` 

-> ``conda install -c openbabel openbabel`` 

-> ``conda install -c rdkit rdkit`` 

Q & A
-----
* 解决Anaconda Prompt里可以导入某package，但jupyter里不能导入的问题（比如rdkit），参考 https://www.pianshen.com/article/3252266007/

-> ``conda install ipykernel`` 

-> ``conda install -n 虚拟环境名称 ipykernel`` （在虚拟环境中安装）

-> ``conda activate 虚拟环境名称`` 

-> ``python -m ipykernel install --user --name 虚拟环境名称 --display-name 显示名称`` 

-> 重启jupyter，改变kernel到“显示名称”

另，删除kernel：-> ``jupyter kernelspec remove 虚拟环境名称`` 


* 安装anaconda和python出现问题的同学，建议可以把原来的anaconda卸载了，然后照昨天的流程重新安装一下（建议不要更改默认安装路径），试试行不行，便于大家以后都 on the same page. 如果你以往的系统用习惯了，你知道怎么调虚拟环境等等的话，那也行

