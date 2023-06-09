#-----------------------------------------------------------------------
# MoveIt Planner Executor Server Node:
# for planning and executing MoveIt trajectories
#-----------------------------------------------------------------------
add_executable(moveit_planner_executor_server_node moveit_planner_executor_server_node.cpp)
target_link_libraries(moveit_planner_executor_server_node ${catkin_LIBRARIES})
add_dependencies(moveit_planner_executor_server_node val_moveit_planner_executor_generate_messages_cpp)

#-----------------------------------------------------------------------
# MoveIt Filter Joint States Node:
# for filtering joint state messages for MoveIt
#-----------------------------------------------------------------------
add_executable(moveit_filter_joint_states_node moveit_filter_joint_states_node.cpp)
target_link_libraries(moveit_filter_joint_states_node ${catkin_LIBRARIES})

#-----------------------------------------------------------------------
# MoveIt Planning Scene Collision Detector:
# for detecting collisions between bodies in MoveIt planning scene
#-----------------------------------------------------------------------
add_executable(moveit_planning_scene_collision_detector moveit_planning_scene_collision_detector.cpp)
target_link_libraries(moveit_planning_scene_collision_detector ${catkin_LIBRARIES})
add_dependencies(moveit_planning_scene_collision_detector val_moveit_planner_executor_generate_messages_cpp)

#-----------------------------------------------------------------------
# Arm Goal Interactive Marker Node:
# for (hack-ily) setting targets MoveIt plans
#-----------------------------------------------------------------------
install(PROGRAMS
	arm_goal_interactive_marker_node.py
	DESTINATION ${CATKIN_PACKAGE_SHARE_DESTINATION}
)
