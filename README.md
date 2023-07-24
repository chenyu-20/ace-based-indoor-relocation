# ace-based-indoor-relocation
基于ace(加速坐标编码)的较大规模室内重定位实现。  
1.git clone ace项目并根据指引完成复现。  
2.建立自己的数据集对ace进行较大规模场景的测试。采取【从零开始的手机camera+imu+gps】1、采集离线手机数据并标定 - navlaw的文章 - 知乎
https://zhuanlan.zhihu.com/p/639741134 中提到的软件marslogger进行手机imu与相机数据的采集与打包。然后进行标定工作，参考知乎文章。
最后对得到的数据进行处理得到类似ace项目中wayspots数据形式的数据集。  
3.进行测试。
