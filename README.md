#Documentation

##This file is a brief user manual for the inmoov ROS simulation



###Configuration:

- Clone the contents of the repository in the your catkin workspace src folder (That is your source *src* folder contains, inmoov_description folder, robot_manipulator .. etc)

- To build and run the simulation, open terminal and change directory to your catkin workspace and run the following commands
	`catkin_make`
	`catkin_install`
	`source ./devel/setup.bash`
	`cd catkin_ws/src/inmoov_description`
	`roslaunch inmoov_description display.launch model:=robots/inmoov.urdf gui:=True`

	
- To change joint state of the robot either
 1. Use the GUI bar
 2. Send a command over the following format
  `rostopic pub -r 20 /joint_command sensor_msgs/JointState '{header: auto, name: [''], position: [], velocity: [], effort: []}'`

 For example, to change the state of all the joints:
  `rostopic pub -r 20 /joint_command sensor_msgs/JointState '{header: auto, name: ['waist_rotate'], position: [-1.043495838866106], velocity: [], effort: []}'`

 3. Run in a new terminal (will generate a small waiste joint movement as a proof of concept)
  `rosrun robot_manipulator robot_manipulator_publisher`

-To check the state joint states from terminal, insert the following command
 `rostopic echo joint_states sensor_msgs/JointState`

- Note:
URDF description based on AlansRobotLab https://github.com/alansrobotlab/inmoov_ros

# ros_inmoov
