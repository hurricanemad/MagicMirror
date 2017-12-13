# MagicMirror
Project integrate video capture and face detection with OpenCV and MTCNN.

## Video Capture
With the producer comsumer framework, video capture in one thread and process in another thread using OpenCV library which drive the usbcamera with v4l2 in Linux.

## MTCNN face detection
MTCNN face detection method is a implementation of "[Joint Face Detection and Alignment using Multi-task Cascaded Convolutional Neural Networks](https://arxiv.org/abs/1604.02878)". We use the code edited by the [foreverYoungGitHub](https://github.com/foreverYoungGitHub/MTCNN) and integrate the detection code into comsumer thread. The average time of face detection is 19.7ms/frame.
<img src="https://github.com/foreverYoungGitHub/MTCNN/blob/master/result/result_gpu_2.png" width="1000">

### Pre-Trained model
You can Download th Pre-Trained model in [this](https://pan.baidu.com/s/1bpk6tUf). Uncpmpress the model into the model fodel.

### Compile code
#### Addition library
The addition library of the project is [OpenCV](https://github.com/opencv/opencv.git) and [caffe](https://github.com/BVLC/caffe.git). You must compile the libraries with cmake and add their path into the option.
#### Compile code
You can compile code following the step:
1. cd in the code folder.
2. Copy the downloaded model into model folder and unzip it.
3. cd build && cmake .. -DCMAKE_BUILD_TYPE:STRING=Release -DCMAKE_INSTALL_PREFIX:PATH=. -DCaffe_DIR:PATH=/your/path/of/caffe -DOpenCV_DIR:PATH=/your/path/of/OpenCV
4. make -j 8
5. make install
6. cd install && ./videocapture

# Future work



 
