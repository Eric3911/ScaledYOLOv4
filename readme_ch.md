


** 第一步：
    在github上下载源代码

** 第二步：
    检查pytorch是否>1.6

** 第三步：
    安装requirements文件
    安装命令如下:
    pip install -r requirements.txt
    （注意：如果出现问题可以将pip源码修改为清华或者豆辨）
    
** 第四步:
    定义自己的数据集
    在data文件夹下使用标准的voc格式数据集
    运行list.py
    运行labels.py
    修改voc.yaml中文件路径
    
** 第五步：
    定义自己需要使用的模型，从小到大依次是s、m、l、x
    在yolov5s.yaml中对nc类别参数设置为自己的
    下载预训练权重初始化自己的模型（这个很重要，一个模型好不好基本看初始化了）
    
** 第六步：
    修改自己的train文件的411行
    
    