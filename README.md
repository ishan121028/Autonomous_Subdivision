# MRT

This workspace contains a gazebo environment and a bot which can be used for testing path planning algorithms. All of this has been tested and built on ROS Noetic

## To use this on your system, you must have the following:
- ROS
- Python3
- Gazebo
- Various dependencies of ROS such as Rviz, Robot State Publisher. (if you have installed full desktop version of ROS, you already have them by default)

## To run the files on your system:
1. Clone the workspace 
```
git clone https://github.com/iitbmartian/Autonomous_Subdivision.git
# git clone git@github.com:iitbmartian/Autonomous_Subdivision.git
```
3. Open terminal and cd to the repo, install dependencies and build the ws (run catkin_make)
```
cd Autonomous_Subdivision
## This may take time, also requires sudo access
rosdep install -y --from-paths . --ignore-src --rosdistro noetic
catkin_make
```
5. source the ws and launch the simulation
```
source devel/setup.bash
# source devel/setup.zsh
roslaunch motion_plan autonomous.launch
```


## Preventing Common Errors:
- run command `source devel/setup.bash` everytime you open a new terminal
- If while running the spawn.launch file you see errors on the terminal, google them most of them are missing dependency errors.
- If spawn.launch doesn't open gazebo and the terminal shows 'Waiting for services...', then open 2 new terminals and run `roscore` and `rosrun gazebo_ros gazebo`. This should work

## File Structure: This workspace has 4 packages.
- **motion_plan** : has the script for lidar reading
- **gazebo_envs** : has the files for various gazebo envs
- **bot_description** : has the files for bot and it's gazebo plugins.
- **teleop** : to enable manual navigation
