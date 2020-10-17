Detaylı Türkçe anlatım -->  [Medium](https://medium.com/@emreyesilyurt/cuda-ve-cudnn-nedir-tensorflow-gpu-deste%C4%9Fi-nas%C4%B1l-sa%C4%9Flan%C4%B1r-2b03cf8b7687)

![alt-text](https://github.com/emreyesilyurt/cuda-installation-ubuntu20.04/blob/main/images/tensorflow.png?raw=true)

* Installing Cuda 10.1.
* Installing cuDNN v7.6.5
* Adding the cuda environment variables to the bash profile.
* Installing Tensorflow.

##### This utility was created assuming you are using Ubuntu 20.04 and Nvidia> = 418.39 driver.

##### CUDA Toolkit and Compatible Driver Versions
![alt-text](https://github.com/emreyesilyurt/cuda-installation-ubuntu20.04/blob/main/images/cuda1.png?raw=true)

##### Hardware Support
![alt-text](https://github.com/emreyesilyurt/cuda-installation-ubuntu20.04/blob/main/images/cuda2.png?raw=true)

##### Checking the driver.
![alt-text](https://github.com/emreyesilyurt/cuda-installation-ubuntu20.04/blob/main/images/driver.png?raw=true)

If you see the "Continue using a manually installed driver" warning, you must uninstall the manually installed driver's repo.
> $ sudo nano /etc/apt/sources.list

Then remove the repo.

> $ sudo apt update

Reboot

> $ reboot

##### Installing Cuda Toolkit 10.1

> sudo apt install nvidia-cuda-toolkit

##### Let's check it out.

> nvcc -V

##### Expected output

![alt-text](https://github.com/emreyesilyurt/cuda-installation-ubuntu20.04/blob/main/images/output.png?raw=true)

##### Installing cuDNN

To download cuDNN we must have an nvidia account. From [this link](https://developer.nvidia.com/rdp/cudnn-archive), you can go to the page where you can download cuDNN, after logging in, you can download cuDNN.

Let's download the compatible cuDNN v7.6.5 for CUDA 10.1 version.

Then in the directory where we downloaded cuDNN;

> $ tar -xvzf cudnn-10.1-linux-x64-v7.6.5.32.tgz

Then we copy the extracted files to the directory where the cuda is installed.

> $ sudo cp cuda/include/cudnn.h /usr/lib/cuda/include/

> $ sudo cp cuda/lib64/libcudnn* /usr/lib/cuda/lib64/

Set file permissions.

> $ sudo chmod a+r /usr/lib/cuda/include/cudnn.h /usr/lib/cuda/lib64/libcudnn*

Adding cuda environment variables to the bash profile.

> $ nano ~/.bashrc

Add the following lines at the end of the lines.

> export LD_LIBRARY_PATH=/usr/lib/cuda/lib64:$LD_LIBRARY_PATH

> export LD_LIBRARY_PATH=/usr/lib/cuda/include:$LD_LIBRARY_PATH

Rerun the bash profile.

> source ~/.bashrc

Installing TensorFlow

> $ pip3 install tensorflow

Check that everything is fine.

> import tensorflow as tf

> tf.config.list_physical_devices("GPU")  

![alt-text](https://github.com/emreyesilyurt/cuda-installation-ubuntu20.04/blob/main/images/check.png?raw=true)


