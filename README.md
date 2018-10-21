# slam_bot

Map My World Project
Udacity Robotics Software Engineer Nanodegree SLAM project repository.

For this setup, catkin_ws is the name of the active ROS workspace. If your workspace name is different, change the commands accordingly.

1. Create an active ROS workspace:

   mkdir -p ~/catkin_ws/src
   cd ~/catkin_ws
   catkin_make
   source devel/setup.bash
   
2. Clone the required repositories to the ~/catkin_ws/src folder

   cd ~/catkin_ws/src
   git clone rtabmap_ros
   git clone https://github.com/snigdhadongre/slam_bot.git
   
3. Follow the steps to properly setup and build RTAB-map from source using this link -https://github.com/introlab/rtabmap_ros#build-from-source

4. Now install missing dependencies using rosdep install:

   rosdep install -i rtabmap_ros
   rosdep install -i slam_bot

5. Build the project:

   cd ~/catkin_ws
   catkin_make

6. Open four terminals to the ~/catkin_ws/src/slam_bot/launch folder and run each command in one terminal:

   roslaunch slam_bot world.launch world_name:=kitchen_dining.world
   roslaunch slam_bot teleop.launch
   curl -L https://s3-us-west-1.amazonaws.com/udacity-robotics/Term+2+Resources/P3+Resources/models.tar.gz | tar zx -C ~/.gazebo/
   roslaunch slam_bot mapping.launch
