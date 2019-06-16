## 介绍
1. 使用flask+keras构建一个森林大火识别API
2. 模型构建和训练在first.py中，使用Adam能提高准确率
## 使用方式
1. 启动photo_process.py：开启Flask服务器，调用模型，准备接图片
2. 在页面中选择本地图片，获得预测结果
## 模型结果
![accuracy&loss](https://github.com/Callmewuxin/forest_fire_detection/raw/master/model_result/model_result.PNG)
## 注意事项
1. 在flask框架中进行预测 需要将预测语句放在with graph.as_default()中，否则会报错
2. 加载模型语句不要放在app启动语句后，速度会很慢
## `ImageDataGenerator`函数注意:
1. 例如在`data`文件夹下有`N`类图片，则每类图片都放在一个文件夹内，生成器能够遍历所有文件夹的图片，并能够根据文件夹字典序分配类标签
2. 如果训练时用到生成器，则测试时也需要用生成器
3. 训练时`epoch`是`sample / batch_size` 预测时是`1`
