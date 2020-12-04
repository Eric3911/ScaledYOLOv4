


## 第一步：
    在github上下载源代码
    权重下载的百度云地址
    https://pan.baidu.com/s/1teB8xXtUpFisCVkPu1fCJg 提取码: drpa
## 第二步：
    检查pytorch是否>1.6

## 第三步：
    安装requirements文件
    安装命令如下:
    pip install -r requirements.txt
    （注意：如果出现问题可以将pip源码修改为清华或者豆辨）
    
## 第四步:
    首先采用完善的VOC格式的数据集
    mkdir images文件夹
    cp -r JPEGImages images
    修改list.py里面的路径生成ImageSets： train、test、val 等文件夹路径文件
    修改labels.py里面路径生成data：2020_train、2020_test、2020_val的txt文件
    修改coco.names 类别为自己的类别
    修改coco.yaml的datasets自己文件的路径、nc为自己类别、cls names为自己类别名称
    
## 第五步：
    定义自己需要使用的模型
    下载预训练权重初始化自己的模型（这个很重要，一个模型好不好基本看初始化了）
    修改yolov4-csp.cfg中的filters=3*（cls+5）
    
## 第六步：
    cd mish-cuda
    python setup.py install
   （这里如果出现问题需要先配置好pytorch就行）

## 第七步：
    第六步：修改train.py文件中的370行
    修改372行、 传入的初始化参数 default=‘weihgts/yolov4-csp.weights’ 迁移学习的权重文件
    修改374行、 传入的初始化参数 default=’‘models/yolov4-csp.cfg’’
    修改376行、 传入的初始化参数 default=‘data/coco.yaml’
    修改378行、 传入的初始化参数 default=1000 epoch轮次
    修改380行、 传入的初始化参数 default=12 batch批次
    修改393行、 传入的初始化参数 default=‘0’ 这个为调用第一块显卡，cpu的直接写cpu

   训练过程远程使用shell命令时候要对utils里面的general文件中的可视化过程1143、1209、1210、1236、1237、1238行注释，理由远程会启动tensorborard监控训练会导致训练中断。方便调试。
    
