---
layout: post
title: "Kinect2 on Ubuntu 14.04 with ROS"
comments: true
category: magic
permalink: kinect2-on-ubuntu-14-04-with-ros
---

##THIS IS OLD POST IMPORTED FROM MY WORDPRESS BLOG !

Initially I wanted to run Kinect2 on mac using VMware fusion, but all of those efforts did not have a happy ending. The usb3.0 was acting weirdly while being picked up VMware fusion (even though I am using VMFusion 8). So finally i dual booted mac and here we are.

Quickly installed ROS and configured it. Thankfully, guys at iai_kinect2 have published a ROS wrapper for freenect2 (the drivers for kinect2)   <a title="iai_kinect2" href="https://github.com/code-iai/iai_kinect2" target="_blank">https://github.com/code-iai/iai_kinect2</a>

![Screenshot of working KinectV2 window](/asset/kinect_run.png)

![IR photo of the KinectV2](/asset/IRphoto.png)

I wanted to use ROS for the following reasons :

1. Wanted to fully leverage PCL framework with existing ROS repositories

2. Wanted to have a good default structure to my coding style

3. Its really helpful if I wanted to scale up and integrate with some other system. *cough* *cough* quadrotors

While installing iai_kinect2 repo for ROS, you will have to installed libfreenect2 drivers sinch iai_kinect2 uses them inherently. Freenect2 employs the use of OpenCL but if, like me, you are using Nvidia drivers's opencl because nvidia's OpenCL does not support the headers required by Freenect. So I recommend installing  "ocl-icd-opencl-dev" .  There are going to be a few missing libraries error because the /freenect2/depend/ few libraries locally so just use             "$ sudo ln -s ***  /usr/lib/*** " to create a link (i know its a dirty hack, but it works !)

Currently, everything is connected and seems to be working. I can see that data being polled at 55Hz but I am having troubles with getting the data with visual. It seems there is a issue with the repo which I have posted on freenect, hopefully once that's sorted out I ll post the next steps.
