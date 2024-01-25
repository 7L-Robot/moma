## MOMA & UR5

这里提供了两个ROS工程文件，一个叫 `robot_bringup`，一个叫 `robot_control`，前者是启动机器人的moveit和夹具驱动的，后者是具体的机器臂控制代码。

首先创建一个文件夹，将其作为你的真机开发的文件夹，比如叫 `ws`，将项目克隆编译

    mkdir -p ws/src
    cd ws/src
    git clone https://github.com/7L-Robot/moma.git
    cd ..
    catkin_make

然后source一下

    source ./devel/setup.bash

接着启动机器人控制驱动

    roslaunch robot_bringup robot_bringup.launch

注意，这个工程提供了几种设置，我们实验室目前有3个夹具，分别是吸盘（epick，简称ep），两指夹具（ag95，简称ag），三指夹具（dorahand，简称drh）。可以根据需要在上面的命令上加上夹具参数，比如我装好吸盘，那么执行的时候夹具参数应该是“ep”：

    roslaunch robot_bringup robot_bringup.launch gripper:=ep

如果 gripper:=none 则是无夹具。这个参数会启动对应夹具的驱动。

然后你可以打开rviz看机器人状态或者用moveit界面控制机器人：

    roslaunch robot_bringup viz.launch

要注意的是，当前的urdf文件中，我们机器人末端的姿态都是Z轴朝下的，所以如果你想提供末端姿态的时候，记得确保方向是对的。

![viz](./robot_bringup/viz)

### 代码控制

TODO
