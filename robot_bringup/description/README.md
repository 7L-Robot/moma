# Generate URDF from XACRO
- rosrun xacro xacro ./robot/moma_robot.xacro > ./robot/moma_robot.urdf
- This command will generate moma_robot.urdf

# Visualzie URDF
- cd robot
- urdf_to_graphiz ./moma_robot.urdf
- This command will create moma_robot.pdf and moma_robot.gv

# Test the moma_robot.urdf
- roslaunch moma_description test.launch

