# GSLAM (A General SLAM Framework and BenchMark)

## 1. Introduction

### 1.1. What is GSLAM?
GSLAM is aimed to provide a general open-source SLAM framework and benchmark with following features :

-> 1. Share the same API while maintain compatibility with different SLAM systems (such as feature based or direct methods).

-> 2. Support Monocular, Stereo, RGB-D or any custom input types (SAR, IMU, GPS and so on).

-> 3. Provide high efficient implementations of SLAM util classes like SO3, SE3, Camera, IMU, GPS, Bundle and so on.

-> 4. Support other features like coorperation SLAM to build a singular map.

-> 5. Provide benchmark tools for SLAM performance evaluation, make it easy to compare between SLAM systems.

### 1.2. What we can do with GSLAM?
1. *For SLAM developers* : Everyone can develop their own SLAM implementation based on GSLAM and publish it as a plugin with open-source or not. 
2. *For SLAM users* : Applications are able to use different SLAM plugins with the same API without recompilation and implementations are loaded at runtime.

### 1.3. Folder structure
* GSLAM -- source folder
 - core    -- Common SLAM APIs with only headers [c++11]
 - utils   -- Utils for GSLAM implementations including Optimizer(PnP,ICP,BA,PoseGraph .etc), LoopDetector and so on. [Eigen3 ceres-solver]
 - gslam   -- Test system of GSLAM (Apllication demo) [Qt OpenCV OpenGL GLEW GLUT QGLViewer]

* doc			--- documents

### 1.4. Implemented SLAM plugin
| SLAM Plugin Name        |  Plugin Authers  | Demostration  |
| ------- |:------:|:-------------:|
| DSO     | Yong Zhao | ![DSO](./doc/images/gslam_dso_calib_wideGamma_scene1.small.png) |
| ORBSLAM | Yong Zhao | ![ORBSLAM](./doc/images/gslam_orbslam_calib_wideGamma_scene1.small.png) |


## 2. Compilation and Install

### 2.1. Compile on linux (Tested in Ubuntu 14.04 and 16.04)

#### 2.1.1 Install dependency

**OpenCV** : sudo apt-get install libopencv-dev 

**Qt** : sudo apt-get install build-essential g++ libqt4-core libqt4-dev libqt4-gui qt4-doc qt4-designer 

**OpenGL**:sudo apt-get install freeglut3 freeglut3-dev libglew-dev libglew1.10

**QGLViewer** : sudo apt-get install libqglviewer-dev libqglviewer2 

#### ** WARNING: It it Qt4 instead of Qt5 that should be installed! For Ubuntu 16.06 libqglviewer-qt4 should be linked. **

#### 2.1.2 Compile and insall GSLAM

```
mkdir build;cd build;
cmake ..;make;sudo make install
```

###2.2 Compile on windows
Not tested yet.

## 3. Run the demo

### 3.1. Test modules
```
gslam Act=Tests --gtest_filter=*
```
### 3.2. Test slam system
```
gslam Dataset=(dataset file) SLAM=(the slam plugin)
```
### 3.3. Configuration with Svar
More parameters can be setted with Svar at file *.cfg.
See more details of Svar at [PILBASE](https://github.com/zdzhaoyong/PIL2/blob/master/apps/SvarTest/README.md).

## 4. Contacts

YongZhao: zd5945@126.com

ShuhuiBu: bushuhui@nwpu.edu.cn

