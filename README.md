# TouchDesigner to Yolo_v3 (object detection)
![GitHub Logo](https://github.com/furmanlukasz/TouchDesigner_YOLOv3/blob/master/td_yolo.PNG)
 
## Summary 
Integration of Yolo<->Tensorflow object-detection model to TouchDesigner.
Big thanks to authors of all below repositories:
Spout <-> Python please refer here
Tensorflow -> Yolo integration and training please refer here
To get an idea how to train orginal Tensorflow-GPU object detection please refer here
Socket and subprocess tutorial
Installation
Install and create an Anaconda environment for Python = 3.7:
download Anaconda and install it.
open Anaconda Prompt
create a new python environment named cnn : conda create -n cnn python=3.7
activate environment we just create: conda activate cnn
Download and install Cuda 10.0 after installing Cuda make sure you have it in system environment if not just add separately following paths
C:\Program Files\NVIDIA GPU Computing Toolkit\CUDA\v10.0\lib\x64
C:\Program Files\NVIDIA GPU Computing Toolkit\CUDA\v10.0\bin
C:\Program Files\NVIDIA GPU Computing Toolkit\CUDA\v10.0\include
C:\Program Files\NVIDIA GPU Computing Toolkit\CUDA\v10.0
Download and copy CUDNN (cudnn-10.0-windows10-x64-v7.6.5.32) following files
\cudnn-10.0-windows10-x64-v7.6.5.32.zip\cuda\bin\cudnn64_7.dll --> C:\Program Files\NVIDIA GPU Computing Toolkit\CUDA\v10.0\bin
\cudnn-10.0-windows10-x64-v7.6.5.32.zip\cuda\include\cudnn.h --> C:\Program Files\NVIDIA GPU Computing Toolkit\CUDA\v10.0\include
\cudnn-10.0-windows10-x64-v7.6.5.32.zip\cuda\lib\x64\cudnn.lib --> C:\Program Files\NVIDIA GPU Computing Toolkit\CUDA\v10.0\lib\x64
Open Anaconda Prompt and install dependencies for a new environment("copy->paste" line by line these commands and install it. If it's your first time with the command line and anaconda please watch the cmd line logs to take the right action when it aksing you for permission (y/n)):
pip install tensorflow-gpu=1.14
pip install pillow
conda install -c conda-forge lxml
conda install -c anaconda cython
conda install -c anaconda contextlib2
conda install -c conda-forge matplotlib
conda install -c anaconda pandas
pip install opencv-python
conda install -c conda-forge tqdm
pip install pygame
pip install PyOpenGL
pip install python-osc
Add site-packages to the python system path, fill the path with your details in places marked with apostrophes and execute it in anaconda prompt as before:
set PYTHONPATH=C:\Users\'your_user_name'\.conda\envs\cnn\Lib\site-packages
Download and install Visual Studio Code
Setup VSCode:
download this project folder (include pre-train models) and unzip it
open vscode as administrator
open folder /YOLOv3_TF
if ask you to install python extension say 'yes'
activate pop up menu: ctrl+shift+p
Set vscode to us 'cnn' environment as default python interpreter, type: Python: Select Interpreter and set it to Python 3.7.5 64-bit ('cnn':conda)
open TouchDesigner project file: /YOLOv3_TF/TD_Yolo.toe
in the VScode - go to Explorer (ctrl+shift+e) and find the file named ObjectDetection.py right-click on a file and select 'Run Python File In Terminal'
How to use it:
Inside TD_Yolo.toe project you will find spout output to send the texture.
There is also little parser witch gives you back 10 objects at the time,(accuracy and bounding box position on screen). The code in python is not limited so you can build your own parser or extend this one. It will be updated in the future. This version is a very experimental level.
to set different resolution change line 26 and 27 in ObjectDetection.py and set the same size to 'constant1' in TD_Yolo.toe *note for now is working only with a square resolution

### TO DO:

* ### Training module
* ### parser optimalization 
