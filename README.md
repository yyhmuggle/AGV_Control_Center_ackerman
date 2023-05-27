# AGV_Control_Center_ackerman
目前本项目仍在初始阶段。在原有项目AGV_Control_Center基础上新修改了阿克曼车辆模型，在racecar_description中存放四轮小车.urdf。bringup中存放着地图gazebo的信息。最后在agv_control存放控制指令（反正暂时我还没用到）。start_navigation_test.launch为最终要的文件。
1.   catkin_make本项目
2.   source devel/setup.bash
3.   roslaunch agv_control start_navigation_test.launch
4.1  rosrun racecar_description keyboard_teleop.py  开启键盘控制模式，wasd
\cmd_vel的信息转化为ackermann_cmd_mux/output, 消息类型为AckermannDriveStamped
4.2  rosrun racecar_description nav_sim.py  开启自主SLAM模式

5.   <node pkg="rviz" type="rviz" name="rviz" args="-d $(find agv_control)/config/0326shiyan.rviz"/> 指令加载之前保存过的地图信息
