---
layout: post
title: 安装OpenCV/Kinect
tags:
- Technique
- OpenCV
- Ubuntu
---
Ubuntu 下安装 OpenCV/Kinect

## 1. 安装OpenCV
	wget http://superb-sea2.dl.sourceforge.net/project/opencvlibrary/opencv-unix/2.3.1/OpenCV-2.3.1a.tar.bz2  
	mkdir build  
	cd build  
	cmake ~/opencv/Opencv2.3.1 //或者 cmake .. (表示到上级目录)  
	make && make install  


## 2. 安装PCL-1.4 （
同时安装各种依赖包：cminpack-1.1.3，flann-1.7.1，eigen3等等）

	sudo apt-get install python-sphinx     
	sudo apt-get install libgtest-dev



## 3.安装OpenNI 
安装usb driver和NITE middleware
## 4. 安装kinectSensor

## 5. 下载RGBDemo0.61，
<font color="blue"> 注意要从github上下载新的nestk文件夹覆盖原有的nestk/目录。安装各种依赖包（qhull etc.）</font>

	./linux_configure.sh  
	cd build  
	make

## 6. References：

- [http://nicolas.burrus.name/index.php/Research/KinectRgbDemoV6?from=Research.KinectRgbDemoV2](http://nicolas.burrus.name/index.php/Research/KinectRgbDemoV6?from=Research.KinectRgbDemoV2) 
- [https://github.com/nburrus/nestk/tree/](https://github.com/nburrus/nestk/tree/)  
- [https://launchpad.net/ubuntu/+source/flann](https://launchpad.net/ubuntu/+source/flann)  
- [https://launchpad.net/ubuntu/+source/minpack](https://launchpad.net/ubuntu/+source/minpack)  
- [http://www.20papercups.net/programming/kinect-on-ubuntu-with-openni/](http://www.20papercups.net/programming/kinect-on-ubuntu-with-openni/)  
- [http://pointclouds.org/downloads/source.html](http://pointclouds.org/downloads/source.html)  
- [http://blog.csdn.net/firefight/article/details/7211773](http://blog.csdn.net/firefight/article/details/7211773)  
