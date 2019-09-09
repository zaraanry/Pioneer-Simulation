Parameters in the configuration files on the svn repository are meant for simulation with stage. When you want to use the navigation stack with the real robot there are some changes that have to be made:

In tomo_navigation/move_base_config/ :
- In slam_gmapping.xml, comment out <remap from="scan" to="base_scan" />
- In costmap_common_params, change base_scan to scan (on the bottom of the file, twice)

WARNING:
- In base_local_planner_params are speed settings, make sure not to set the speeds to high.

In tomo_sim/launch/ :
- In sim.launch, comment out <include file="$(find tomo_sim)/launch/stage.launch" />
- In sim.launch, change the use_sim parameter to false. 

