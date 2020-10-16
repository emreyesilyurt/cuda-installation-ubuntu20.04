* Installing Cuda 10.1.
* Installing cuDNN v7.6.5.
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

To download cuDNN we must have an nvidia account. From [this link](https://developer.nvidia.com/rdp/cudnn-download), you can go to the page where you can download cuDNN, after logging in, you can download cuDNN.

Let's download the compatible cuDNN v7.6.5 version.


