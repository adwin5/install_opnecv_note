# Install opencv 3.0.0 for Ubuntu 14.04 and python 2.7


### General install article
* http://www.pyimagesearch.com/2015/06/22/install-opencv-3-0-and-python-2-7-on-ubuntu/
* My Cmake (path might vary in your PC)
* Note: turn off C_EXAMPLE
```
cmake -D CMAKE_BUILD_TYPE=RELEASE -D CMAKE_INSTALL_PREFIX=/usr/local -D INSTALL_C_EXAMPLES=OFF -D INSTALL_PYTHON_EXAMPLES=ON -D OPENCV_EXTRA_MODULES_PATH=~/opencv_contrib/modules -D WITH_TBB=ON -D WITH_V4L=ON -D WITH_QT=ON -D WITH_OPENGL=ON -D WITH_GSTREAMER=ON -D BUILD_EXAMPLES=ON -D BUILD_NEW_PYTHON_SUPPORT=ON -D BUILD_PYTHON_SUPPORT=ON -D PYTHON_LIBRARY=/usr/lib/x86_64-linux-gnu/libpython2.7.so ..
```

### [bug fixed]
#### 1, error faced during make:
check out the same version for both opencv folder and opencv_contrib, I am using 3.0.0.
check what is the branch by
```
git branch
```
####  2, error faced during make:
Make clean, and check your Cmake command
http://stackoverflow.com/questions/37562642/error-in-make-j4-in-opencv3-1-python-ubuntu-gnome-16-04

#### 3, cannot find cv2.so even successful make:
Set path for include python library
http://answers.opencv.org/question/45585/cannot-find-python-libraries-for-cmake-in-opencv300/
And find where it is by
```
find / -name “cv2.so”
```
#### 4, cannot find cv2.so even successful make:
check your $PYTHONPATH by command export and double check the ouput of Cmake if numpy is readed properly

### [extra]
#### 1, install CUDA in Ubuntu 14.04:
Clean all installed Nvidia library 
Please don’t use apt-get install …., but download correct driver/library directly from Nvidia website
* https://askubuntu.com/questions/451672/installing-and-testing-cuda-in-ubuntu-14-04
