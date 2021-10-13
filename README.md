# qfs-pytorch-yolov5
<!-- 如何训练自己的数据集？ -->
（权重自行下载）
1.找到data/voc
2.将自己的voc的xml放入Annotations,将原图放入images和JPEGImages文件中
3.运行make_voc_txt.py 会在ImageSets中生成train.txt,test.txt,train.txt,val.txt
4.继续运行make_voc_label.py（注意在代码中修改自己的类别 classes） 然后会自动生成labels文件夹和test.txt,train.txt,val.txt
5.修改data下面的voc.yaml  修改nc为类别数，names为类别名称列表， train:修改为data/voc/train.txt  val:修改为data/voc/val.txt
6.找到models下面自己要使用的模型.yaml,修改里面的候选框大小，自己根据官方代码聚类为9种
7.打开train.py,找到主函数的参数那块，修改weights（选择weights/下面的对应模型权重）,cfg（选择models下面对应的模型.yaml）,data（修改为data/voc.yaml）,epoch和batch-size自行根据自己的电脑配置设置
8.执行train.py,权重保存在runs/train/exp下面
9.预测代码执行detect.py,只需修改weights和source地址就可以，然后执行，运行结果在runs/detect/exp下面

B站地址带你收录深度学习代码：https://www.bilibili.com/video/BV1nq4y1D7rQ?spm_id_from=333.999.0.0

