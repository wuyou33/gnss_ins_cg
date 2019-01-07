# IMU Lab

----

## IMU Tools

* **IMU Pose Calculation**
  - [ccny-ros-pkg/imu_tools](https://github.com/ccny-ros-pkg/imu_tools): ROS tools for IMU devices
    ```bash
    rosrun imu_filter_madgwick imu_filter_node \
           _use_mag:=false /imu/data_raw:=/camera/imu/data_raw
    ```

* **IMU Performance Analysis**
  - [IMU-TK](https://bitbucket.org/alberto_pretto/imu_tk): Inertial Measurement Unit ToolKit
  - [gaowenliang/imu_utils](https://github.com/gaowenliang/imu_utils): A ROS package tool to analyze the IMU performance
  - [rpng/kalibr_allan](https://github.com/rpng/kalibr_allan): IMU Allan standard deviation charts for use with Kalibr and inertial kalman filters
  - [AllanTools](https://pypi.org/project/AllanTools/): A python library for calculating Allan deviation and related time & frequency statistics.
