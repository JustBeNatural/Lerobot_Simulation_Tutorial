# Lerobot_Simulation_Tutorial
面向初学者的 LeRobot 入门教程，包含 ACT、Pi0、SmolVLA 等具身智能模型的原理解析与实践记录。
# 基础（ACT模型）

这个项目的核心运行逻辑是：

人类遥操作 → 生成演示数据 → 训练模型 → 模型学会操作 → 在仿真中执行

# 一、准备阶段

Linux系统：Ubuntu22.04

编程IDE:：Vscode

下载链接：https://code.visualstudio.com/

![img](基础(ACT模型).assets\1776325694887-24.png)

![img](基础(ACT模型).assets\1776325694885-1.png)

在这个下载页面，右键并选择“在终端打开”：

在终端内输入：

`sudo dpkg -i xxxxxxxxxx`这里的xxxxxxxxxx替换为下载文件名称，如图所示：

![img](基础(ACT模型).assets\1776325694885-2.png)

即可安装完成vscode

# 二、下载源文件

可以直接下载这个压缩包，并解压：

暂时无法在飞书文档外展示此内容

也可以在官网上下载：

文件网址：https://github.com/jeongeun980906/lerobot-mujoco-tutorial?tab=readme-ov-file#installation

![img](基础(ACT模型).assets\1776325694885-3.png)

![img](基础(ACT模型).assets\1776325694885-4.png)

并将文件夹放在主目录下：

![img](基础(ACT模型).assets\1776325694885-5.png)

# 三、安装依赖

安装mujoco依赖和Lerobot：

按住ctrl+alt+T打开终端，依次输入：

```
cd lerobot-mujoco-tutorial-master
pip install typeguard pytest
pip install -r requirements.txt
```

![img](基础(ACT模型).assets\1776325694885-6.png)

![img](基础(ACT模型).assets\1776325694885-7.png)

再解压文件，在终端继续输入：

```
cd asset/objaverse
unzip plate_11.zip
```

![img](基础(ACT模型).assets\1776325694886-8.png)

# 四、运行仿真

## 4.1 采集数据

打开之前下载的lerobot-mujoco-tutorial-master文件，并右键，选择“在终端中打开”

输入代码，打开vscode：

```
code .
```

![img](基础(ACT模型).assets\1776325694886-9.png)

![img](基础(ACT模型).assets\1776325694886-10.png)

点击第一个collect_date.ipynb:

点击“全部运行”运行程序：

![img](基础(ACT模型).assets\1776325694886-11.png)

运行程序后会自动弹出仿真窗口：

![img](基础(ACT模型).assets\1776325694886-12.png)

WASD → 平面移动

 RF → 上下

 QE → 倾斜

 方向键 → 旋转

 空格 → 开/关夹爪

将红色杯子放置到盘子内程序会自动终止并保存数据文件到 /lerobot-mujoco-tutorial/demo_data 文件夹内：

![img](基础(ACT模型).assets\1776325694886-13.png)

此时的文件夹内结构应该是这样的：

![img](基础(ACT模型).assets\1776325694886-14.png)

## 4.2 查看自己采的数据

运行2.collect_data.ipynb文件：

![img](基础(ACT模型).assets\1776325694886-15.png)

可以看到刚刚自己采的数据过程：

![img](基础(ACT模型).assets\1776325694886-16.png)

再次点击程序运行，并在这里的文本框输入“n”，点击回车：

![img](基础(ACT模型).assets\1776325694886-17.png)

重复刚刚的流程，采集20组以上的数据

![img](D:\桌面\北京华晟经世\工作\LeRobot仿真项目\课程设计\基础(ACT模型).assets\1776325694886-18.png)

# 五、训练数据

打开 3.train.ipynb，点击“全部运行”，进行模型训练，这里可以看到训练过程：

![img](基础(ACT模型).assets\1776325694886-19.png)

训练结束：

![img](基础(ACT模型).assets\1776325694886-20.png)

保存的模型和权重会保存在ckpt文件夹内：

![img](基础(ACT模型).assets\1776325694886-21.png)

# 六、部署模型

打开 4.deploy,ipynb 文件，点击“全部运行”部署刚刚训练好的模型，会弹出仿真窗口，机械臂会使用训练的模型进行抓取：

![img](基础(ACT模型).assets\1776325694886-22.png)

P.S. 如果电脑没有GPU，也可以直接下载google上面的训练好的模型进行部署：

暂时无法在飞书文档外展示此内容

将这个文件夹进行解压，放在lerobot_mujoco_tutorial目录下：

![img](基础(ACT模型).assets\1776325694886-23.png)

同样的方法，打开文件全部运行即可查看模型效果
