# bag2mp4

### Reference [https://github.com/tssc67/bag2mp4](https://github.com/tssc67/bag2mp4)

## Usage

### 1. Download OpenCV for cpp

* git clone https://github.com/opencv/opencv.git
* cd opencv
* git checkout <version>
* mkdir build
* cd build
* -D CMAKE_BUILD_TYPE=RELEASE \
            -D CMAKE_INSTALL_PREFIX=/usr/local \
            -D INSTALL_C_EXAMPLES=ON \
            -D INSTALL_PYTHON_EXAMPLES=ON \
            -D WITH_TBB=ON \
            -D WITH_V4L=ON \
        -D WITH_QT=ON \
        -D WITH_OPENGL=ON \
        -D BUILD_EXAMPLES=ON ..
* sudo make -j4
* sudo make install
 
* reference: [https://www.learnopencv.com/install-opencv-4-on-ubuntu-18-04/](https://www.learnopencv.com/install-opencv-4-on-ubuntu-18-04/)


### 2. Clone this repo

* Go to your ros workspace
* catkin_make
* If error please check install path (CMAKE_INSTALL_PREFIX=/usr/local) 
  - If your path is not /usr/local. please change directory in CMakeLists.txt line 7 SET(OpenCV_DIR /usr/local/lib/cmake/opencv4/)


### 3. Execute

* rosrun bag2mp4 bag2mp4 <filename.bag> <topicname> <fps> <output.mp4>
