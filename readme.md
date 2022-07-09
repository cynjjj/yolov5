训练数据的生成方法
1.数据集的生成：
			(a)使用原有手册中的图片（以下统一用电解电容图例）
			![enter description here](./images/1656990927557.png)
			（b）在例图中进行标注
			![enter description here](./images/1656991219202.jpg)
2.制作train
			（a)使用脚本对图片进行旋转，放大缩小，水平翻转，拉伸变形处理
			![](./images/1656991348544.png)
			(b)对特殊元器件进行特殊标记
			![enter description here](./images/1656991441758.png)
			（c)对部分困难识别图形采用数量翻倍来使其训练更有效果
3.制作valid
			（a)选取train中图片每一类5-20张
			![enter description here](./images/1656999356367.png)
4.制作lable标签
		我使用的是labelImg画标签区域生成*.xml文件，再使用xmltoyolo脚本自动生成*.txt.
		并确定class内容和nc数，和更改yolo模型。
		![enter description here](./images/1656999800462.png)
		![](./images/1656999854202.png)
		
5.训练模型的思路
		训练使用yolov5自主学习方式，优先使用小模型训练，在小模型精度到0.7左右，训练带测试的图，必要时可以取特征加强学习。
		
6.训练过程中的中间结果
召回率，lost,map(这里使用的是wandb线上可视化工具):
![](./images/1657000702812.png)
![enter description here](./images/1657000833876.png)

7.测试结果
			结果能做到90%的识别效果。（以下为部分效果展示）
			![enter description here](./images/1657001295187.jpg)
			![](./images/1657001306127.jpg)
			![enter description here](./images/1657001326331.jpg)
			![enter description here](./images/1657001354477.jpg)
			![enter description here](./images/1657001369629.jpg)
			
			