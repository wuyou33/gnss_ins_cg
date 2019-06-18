# INS Lab

----

[TOC]

# IMU Data

## IMU Noise Model

* a high frequency additive **White Noise**
* a slower varying sensor **Bias**

Parameter | YAML element | Symbol | Units
--- | --- | --- | ---
Gyroscope "white noise" | `gyr_n` | <img src="https://latex.codecogs.com/svg.latex?{%5Csigma_g}"> | <img src="https://latex.codecogs.com/svg.latex?{%5Cfrac%7Brad%7D%7Bs%7D%5Cfrac%7B1%7D%7B%5Csqrt%7BHz%7D%7D}">
Accelerometer "white noise" | `acc_n` | <img src="https://latex.codecogs.com/svg.latex?{%5Csigma_a}"> | <img src="https://latex.codecogs.com/svg.latex?{%5Cfrac%7Bm%7D%7Bs^2%7D%5Cfrac%7B1%7D%7B%5Csqrt%7BHz%7D%7D}">
Gyroscope "bias Instability" | `gyr_w` | <img src="https://latex.codecogs.com/svg.latex?{%5Csigma_b_g}"> | <img src="https://latex.codecogs.com/svg.latex?{%5Cfrac%7Brad%7D%7Bs^2%7D%5Cfrac%7B1%7D%7B%5Csqrt%7BHz%7D%7D}" />
Accelerometer "bias Instability" | `acc_w` | <img src="https://latex.codecogs.com/svg.latex?{%5Csigma_b_a}"> | <img src="https://latex.codecogs.com/svg.latex?{%5Cfrac%7Bm%7D%7Bs^3%7D%5Cfrac%7B1%7D%7B%5Csqrt%7BHz%7D%7D}"/>

Ref: [IMU Noise Model (kalibr)](https://github.com/ethz-asl/kalibr/wiki/IMU-Noise-Model)

## How To Get

### the Datasheet of the IMU

* White Noise Terms
  - **Rate Noise Density**
  - **Acceleration Noise Density**

* Bias Terms
  - **In-Run Bias Stability**

### the Allan standard deviation (AD)

* "white noise" is at tau=1 (slope -1/2 in a log-log AD plot)
* "random walk" is at tau=3 (slope +1/2 in a log-log AD plot)

<div align=center>
  <img src="https://cloud.githubusercontent.com/assets/1916839/3589506/8f57d0ee-0c4e-11e4-9ab4-33821c040490.png"/>
</div>

## Samples

* MPU6000 / MPU6050

  ```yaml
  core_noise_acc: 0.003924    # [m/s^2/sqrt(Hz)] mpu6000 datasheet
  core_noise_gyr: 0.00008726  # [rad/s/sqrt(Hz)] mpu6000 datasheet
  ```

* ADIS 16448

  ```yaml
  # avg-axis
  gyr_n: 1.8582082627718251e-04
  gyr_w: 7.2451532648461174e-05
  acc_n: 1.9862287242243099e-03
  acc_w: 1.2148497781522122e-03
  ```

# IMU Tools

* **IMU Data Simulation**

  - [HeYijia/vio_data_simulation](https://github.com/HeYijia/vio_data_simulation): Generate imu data and feature in camera frame

* **IMU Pose Calculation**
  - [ccny-ros-pkg/imu_tools](https://github.com/ccny-ros-pkg/imu_tools): ROS tools for IMU devices
    ```bash
    rosrun imu_filter_madgwick imu_filter_node \
           _use_mag:=false /imu/data_raw:=/camera/imu/data_raw
    ```
* [higerra/ridi_imu](https://github.com/higerra/ridi_imu): Robust IMU Double Integration

* **IMU Performance Analysis**
  - [IMU-TK](https://bitbucket.org/alberto_pretto/imu_tk): Inertial Measurement Unit ToolKit
  - [gaowenliang/imu_utils](https://github.com/gaowenliang/imu_utils): A ROS package tool to analyze the IMU performance
  - [rpng/kalibr_allan](https://github.com/rpng/kalibr_allan): IMU Allan standard deviation charts for use with Kalibr and inertial kalman filters
  - [XinLiGH/GyroAllan](https://github.com/XinLiGH/GyroAllan): 陀螺仪随机误差的 Allan 方差分析
  - [AllanTools](https://pypi.org/project/AllanTools/): A python library for calculating Allan deviation and related time & frequency statistics.


# Books

  * ***Global Navigation Satellite Systems, Inertial Navigation, and Integration, 3rd Edition*** ([link](http://bcs.wiley.com/he-bcs/Books?action=index&itemId=111844700X&bcsId=7868))

<div align=center>
  <img src="images/gnss.jpg">
</div>
