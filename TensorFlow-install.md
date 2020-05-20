## 配置：

win10-x64 	python 3.6 	tensorflow-1.14

## 安装流程

### 见链接

 https://www.tensorflow.org/install/pip （本人选择在通过安装虚拟环境安装tf）

虚拟环境安装路径：C:\Windows\System32\venv\Lib\site-packages\tensorflow\python

python安装路径：C:\Users\stylite\AppData\Local\Programs\Python\Python36

1. 虚拟环境打开：.\venv\Scripts\activate

2. 退出虚拟环境：deactivate

3. 虚拟环境中相关插件配置（先打开虚拟环境）

   3.1. jupyter安装：pip install jupyter； jupyter notebook ；（ https://blog.csdn.net/yu1014745867/article/details/84191485 ）

   ​	3.1.1. jupyter配置文件路径：C:\Users\stylite\.jupyter

   ​	3.1.2. jupyter安装路径：c:\users\stylite\appdata\local\programs\python\python36\lib\site-packages
   
4. opencv安装：pip install opencv-python


### 涉及问题：

1. 本人python与vs c++安装在默认路径也就是C盘中。

2. 需要打开C:\Windows\systems32的cmd而不是C:\Windows\stylite中，否则会出现调用python问题；

3. 出现ImportError: DLL load failed: 找不到指定的程序时（如下图），时protobuf文件版太新（本人为3.6.1），需改为protobuf==3.6.0即可（ https://blog.csdn.net/lijil168/article/details/82289596?utm_source=blogxgwz5 ）：

   ​							pip install protobuf==3.6.0
   
   ![dll failed](https://raw.githubusercontent.com/Stylite-Y/MyTypora/master/img/dll failed.PNG)

4. jupyter安装问题：

   4.1. 安装后打开python文件右上角显示无法连接服务，pip list 发现tornado版本6.0以上太新了，重新安装5.1.1版本（仍然为成功）：

   ​								 pip install tornado==5.1.1 

   之后降低了 prompt-toolkit版本从3.0.3到2.0.4后成功了（ https://www.jianshu.com/p/98765bcbeb8c ）

    								pip install --upgrade prompt-toolkit==2.0.4 

### Pycharm中使用tf

见链接： https://blog.csdn.net/piaoliudehai/article/details/80280100 

其中python的路径选择已经安装tf的python.exe的路径，如C:\Windows\System32\venv\Scripts\python36