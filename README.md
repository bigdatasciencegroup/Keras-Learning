# Keras-Learning
The project is for Learning Keras.

[1] multi-output-classification [2018-10-25 14:00:00]
https://www.pyimagesearch.com/2018/06/04/keras-multiple-outputs-and-multiple-losses/#


[day1 - 2018-11-05]
[mnist_mlp.py](mnist_mlp.py)
Trains a simple deel multi-layer perceptron on the dataset.

Keras有两种模型：
	1.序贯模型
	2.函数式模型


两类模型相同的方法：

model.summary()：打印出模型概况
model.get_config():返回包含模型配置信息的Python字典
model.get_layer()：依据层名或下标获得层对象
model.get_weights()：返回模型权重张量的列表，类型为numpy array
model.set_weights()：从numpy array里将权重载入给模型，要求数组具有与model.get_weights()相同的形状
model.to_json：返回代表模型的JSON字符串，仅包含网络结构，不包含权值。
model.save_weights(filepath)：将模型权重保存到指定路径，文件类型是HDF5（后缀是.h5）
model.load_weights(filepath, by_name=False)：从HDF5文件中加载权重到当前模型中, 默认情况下模型的结构将保持不变。如果想将权重载入不同的模型（有些层相同）中，则设置by_name=True，只有名字匹配的层才会载入权重

·序贯模型
1.主要方法：
add(self, layer) - 向模型中添加一个层 
pop(self) - 弹出模型最后的一层，无返回值
compile(self, optimizer, loss, metrics=None, sample_weight_mode=None) - 编译用来配置模型的学习过程 
fit(self, x, y, batch_size=32, epochs=10, verbose=1, callbacks=None, validation_split=0.0, validation_data=None, shuffle=True, class_weight=None, sample_weight=None, initial_epoch=0) - 本函数将模型训练nb_epoch轮 
evaluate(self, x, y, batch_size=32, verbose=1, sample_weight=None) - 本函数按batch计算在某些输入数据上模型的误差
predict(self, x, batch_size=32, verbose=0) - 本函数按batch获得输入数据对应的输出

2.使用
序贯模型是多个网络层的线性堆叠，也就是“一条路走到黑”。可以通过向Sequential模型传递一个layer的list来构造该模型，也可以通过.add()方法一个个的将layer加入模型中。
[1] 指定输入数据的shape
[2] 编译
[3] 训练

