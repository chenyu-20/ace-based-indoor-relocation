# ace-based-indoor-relocation
基于ace(加速坐标编码)的较大规模室内重定位实现。  
1.git clone ace项目并根据指引完成复现。  
2.建立自己的数据集对ace进行较大规模场景的测试。采取【从零开始的手机camera+imu+gps】1、采集离线手机数据并标定 - navlaw的文章 - 知乎
https://zhuanlan.zhihu.com/p/639741134 中提到的软件marslogger进行手机imu与相机数据的采集与打包。然后进行标定工作，参考知乎文章。
最后对得到的数据进行处理得到类似ace项目中wayspots数据形式的数据集。数据集包括三种文件，焦距、姿态、图像。焦距、图像都易得，主要需要理解的是姿态这一类数据，本数据集中的姿态
与图像是一一对应的，具体每个姿态是4×4形式的矩阵，ace项目作者未提到这个矩阵是哪个，但应该是比较常见的一种，注意到最后一行为0 0 0 1，搜索相关矩阵结合原项目中数据集文件的注释发现是ground truth pose。ground truth pose有多个解释，依照存储类型确定为4×4转换矩阵（世界到相机）。要取得转换矩阵需要六维位姿，包括三维角度三维位置，三维角度可以通过imu取得精确数据，但是位置信息无法通过imu获得精确数据，因为存在大的漂移会有随时间增长的累计误差。难道要通过slam或者sfm来建个精确地图获得数据集需要的六维位姿？  
3.进行测试。
