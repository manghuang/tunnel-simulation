### 包说明
包含两部分：隧道模型和使用环境。


### 文件说明
```
demo：使用环境
	launch:
		simple.launch：打开gazebo，加载world和机器人模型
	media：截图
	meshes:
		wpb_home.dae：启智机器人模型中使用到的网格文件
	src:
		keyboard_vel_ctrl.cpp：键盘控制机器人运动
	urdf:
		wpb_home.gazebo：启智机器人模型
	worlds:
		suidao.world：包含隧道模型的世界
suidao:隧道模型
	meshes:
		suidao.dae：隧道模型中使用到的网格文件
		suidao.stl：隧道模型中使用到的网格文件
	model.cofig：配置
	model.sdf：隧道模型
	
	
```


### 步骤
第一部分：把隧道模型放到gazebo的默认加载路径下

1、到home目录下，快捷键ctrl+h，打开隐藏文件夹

2、进入.gazebo文件夹中，再进入model文件夹中

3、将suidao文件夹复制到model目录下

第二部分：创建工作空间并编译

1、打开一个cmd，到home目录下

```
$ mkdir -p demo_ws/src 
```
2、将demo文件夹复制到src目录下
3、到demo_ws目录

```
	$ rosdep install --from-paths src --ignore-src --rosdistro=kinetic -y
	$ catkin_make 
	$ source ./devel/setup.bash
	$ roslaunch demo simple.launch
```
4、再打开另一个cmd，到demo_ws目录

```
	$ source ./devel/setup.bash
	$ rosrun demo keyboard_vel_ctrl
```


### 结果
![1](.\demo\media\1.png)



![2](.\demo\media\2.png)