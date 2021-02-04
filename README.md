# YOLO ROS: Real-Time Object Detection for ROS

## Overview

For an Overview of the original architecture, go to the Master Branch.

### Systemtrio

By default this package runs yolov3-tiny with weights trained by us.

* Changes made to the original repo:
    * Add `yolov3-tiny.cfg` to `/darknet_ros/yolo_network_config/cfg`
    * Add `yolov3-tiny.yaml` to `/darknet_ros/config`
    * Change the camera topic subscriber inside `/darknet_ros/config/ros.yaml` to `topic: /drone0/rgb_camera/image_raw`

* In case we need to run yolov3:
    * Change network_param_file inside /darknet_ros/launch/darknet_ros.launch to  
    ```sh 
        <arg name="network_param_file"         default="$(find darknet_ros)/config/yolov3.yaml"/> 
    ```
    * Download yolov3.weights and save it to darknet_ros/yolo_network_config/weights

* To run the node
    ```sh 
        roslaunch darknet_ros darknet_ros.launch
    ```

