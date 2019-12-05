# INS

An **inertial navigation system (INS)** is a navigation device that uses a computer, motion sensors (**accelerometers**) and rotation sensors (**gyroscopes**) to continuously calculate by dead reckoning the position, the orientation, and the velocity (direction and speed of movement) of a moving object without the need for external references. Often the inertial sensors are supplemented by a **barometric altimeter** and occasionally by **magnetic sensors (magnetometers)** and/or speed measuring devices.

* [Open Source Inertial Navigation Toolkit](http://www.instk.org/)
* [Inertial Navigation System (INS) Toolbox (matlab)](https://www.mathworks.com/products/connections/product_detail/inertial-navigation-system-toolbox.html)
* [Aided Inertial Navigation System (AINS) Toolbox for MatLab Software](https://mms.geomatics.ucalgary.ca/ains)
* [NaveGo](https://github.com/rodralez/NaveGo): an open-source MATLAB/GNU Octave toolbox for processing integrated navigation systems and performing inertial sensors analysis
* [Aceinna Navigation Studio](https://developers.aceinna.com/): Simulate, Deploy, and Analyze Navigation Systems
* [priseborough/InertialNav](https://github.com/priseborough/InertialNav): Inertial Navigation Estimation Library
* [RoNIN](https://ronin.cs.sfu.ca/): Robust Neural Inertial Navigation

-----

[TOC]

# IMU

## IMU Overview

陀螺仪知道“我们转了个身”，加速计知道“我们又向前走了几米”，而磁力计则知道“我们是向西方向”的。

加速度计在较长时间的测量值（测量飞行器的角度）是正确的，然而在较短时间内由于信号噪声以及运动方向的加速度存在，会有很大的误差。具体表现为加速度静止不动时值很稳定，但是移动起来数据波动很大。
陀螺仪测得的是角速度，在较短时间内则比较准确，而较长时间则会有积分漂移产生误差。

9轴传感器：3轴加速度计、3轴陀螺仪、3轴磁力计

* [飞行控制器——惯性测量模块IMU](http://www.crazepony.com/wiki/main-controller-sensor.html)

* [HeYijia/vio_data_simulation](https://github.com/HeYijia/vio_data_simulation): Generate imu data and feature in camera frame

* [introlab/OpenIMU](https://github.com/introlab/OpenIMU): Open Source Analytics & Visualisation Software for Inertial Measurement Units

* [mohamedamjad/IMUViewer](https://github.com/mohamedamjad/IMUViewer)

### Accelerometer

加速计（Accelerometer、G-Sensor）也叫重力感应器，检测设备受到的加速度的大小和方向。

加速度计有两种：一种是角加速度计，是由陀螺仪（角速度传感器）改进的；另一种就是线加速度计。

加速度传感器利用重力加速度，根据测某方向重力加速度分量与重力加速度的关系，可以用于检测设备的倾斜角度，但是它会受到运动加速度的影响，使倾角测量不够准确，所以通常需利用陀螺仪和磁传感器补偿。

加速度传感器可以检测交流信号以及物体的振动，人在走动的时候会产生一定规律性的振动，而加速度传感器可以检测振动的过零点，从而计算出人所走的步或跑步所走的步数，从而计算出人所移动的位移。并且利用一定的公式可以计算出卡路里的消耗。

### Gyroscope

陀螺仪（Gyroscope、GYRO-Sensor）也叫地感器，它的轴由于陀螺效应始终与初始方向平行，这样就可以通过与初始方向的偏差计算出实际方向。

三轴陀螺仪的工作原理是通过测量三维坐标系内陀螺转子的垂直轴与设备之间的夹角，并计算角速度，通过夹角和角速度来判别物体在三维空间的运动状态。三轴陀螺仪可以同时测定上、下、左、右、前、后等6个方向（合成方向同样可分解为三轴坐标），最终可判断出设备的移动轨迹和加速度。

### Magnetometer

磁力计（Magnetic、M-Sensor）也叫地磁、磁感器，可用于测试磁场强度和方向，定位设备的方位，磁力计的原理跟指南针原理类似，可以测量出当前设备与东南西北四个方向上的夹角。

即使使用了加速度计和陀螺仪，也只可以用于测得飞机的俯仰和横滚角度；对于偏航角度，由于偏航角和重力方向正交，无法用加速度计测量得到，而只用陀螺仪测的角度会存在积分漂移的问题。

* [ST集成传感器方案实现电子罗盘功能](http://www.dzsc.com/data/2010-11-29/87454.html)


## IMU Errors

imu_errors.md


## IMU with Embedded

imu_embedded.md


# Strapdown Inertial Navigation & AHRS

sins_ahrs.md
