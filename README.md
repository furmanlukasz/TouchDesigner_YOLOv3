# TouchDesigner to Yolo_v3 (object detection)
![GitHub Logo](https://github.com/furmanlukasz/TouchDesigner_YOLOv3/blob/master/td_yolo.PNG)
 
## Summary 
Integration of Yolo<->Tensorflow objectdetection model to TouchDesigner.  
### Big thanks to autors of all below repositories:
* Spout <-> Python   please refere [here](https://github.com/spiraltechnica/Spout-for-Python) 
* Tensorflow -> Yolo integration and training please refere [here](https://github.com/wizyoung/YOLOv3_TensorFlow)
* To get idea how to train orginal Tensorflow-gpu object detection please refere [here](https://github.com/EdjeElectronics/TensorFlow-Object-Detection-API-Tutorial-Train-Multiple-Objects-Windows-10)
* Socket and subprocess [tutorial](https://matthewragan.com/2019/08/14/touchdesigner-python-and-the-subprocess-module/?fbclid=IwAR3Jg4byLlK7_PwDKc1DTQalAYUBrLykMM_6rXGNjeoi17CC5PExHmlZwWU)


## Installation 

1. Install and create a Anaconda enviroment for Python = 3.7:

- [download Anaconda](https://www.anaconda.com/distribution/?gclid=EAIaIQobChMIk8aHlZaQ5gIVyKQYCh3aGgmgEAAYASAAEgLAp_D_BwE) and install it.
- open Anaconda Prompt 
- create a new python enviroment named __cnn__ :
  `conda create -n cnn python=3.7`
- activate enviroment we just create : `conda activate cnn`
2. Download and install [Cuda](https://developer.nvidia.com/cuda-10.0-download-archive) 10.0 after installing cuda make shure you have it in system envinroments if not just add seperetly following paths 
- `C:\Program Files\NVIDIA GPU Computing Toolkit\CUDA\v10.0\lib\x64`
- `C:\Program Files\NVIDIA GPU Computing Toolkit\CUDA\v10.0\bin`
- `C:\Program Files\NVIDIA GPU Computing Toolkit\CUDA\v10.0\include` 
- `C:\Program Files\NVIDIA GPU Computing Toolkit\CUDA\v10.0` 
3. Download and copy [CUDNN](https://developer.nvidia.com/compute/machine-learning/cudnn/secure/7.6.5.32/Production/10.0_20191031/cudnn-10.0-windows10-x64-v7.6.5.32.zip) (cudnn-10.0-windows10-x64-v7.6.5.32) following files     
- `\cudnn-10.0-windows10-x64-v7.6.5.32.zip\cuda\bin\cudnn64_7.dll` --> `C:\Program Files\NVIDIA GPU Computing Toolkit\CUDA\v10.0\bin`
- `\cudnn-10.0-windows10-x64-v7.6.5.32.zip\cuda\include\cudnn.h` --> `C:\Program Files\NVIDIA GPU Computing Toolkit\CUDA\v10.0\include`
- `\cudnn-10.0-windows10-x64-v7.6.5.32.zip\cuda\lib\x64\cudnn.lib` --> `C:\Program Files\NVIDIA GPU Computing Toolkit\CUDA\v10.0\lib\x64`

4. Open Anaconda Prompt and install dependencies for new enviroment("copy->paste" line by line this commands and install it. If it's your first time with comannd line and anaconda please watch the cmd line logs to take right action when it aksing you for permition (y/n)):
- `pip install tensorflow-gpu=1.14`
- `pip install pillow`
- `conda install -c conda-forge lxml`
- `conda install -c anaconda cython`
- `conda install -c anaconda contextlib2`
- `conda install -c conda-forge matplotlib`
- `conda install -c anaconda pandas`
- `pip install opencv-python`
- `conda install -c conda-forge tqdm`
- `pip install pygame`
- `pip install PyOpenGL`
- `pip install python-osc`

5. Add site-packages to the python system path, fill the path with your details in places marked with apostrophes and execute it in anaconda prompt as before: 
- `set PYTHONPATH=C:\Users\'your_user_name'\.conda\envs\cnn\Lib\site-packages` 
5. [Download](https://code.visualstudio.com/) and install Visual Studio Code

6. Setup VSCode:
- download [this](https://drive.google.com/open?id=1aBPk3tAOk6WPLBuQ61MZAV0ajvuwIEQA) project folder (includs pre train models) and unzip it 
- open vscode as administrator
- open folder /YOLOv3_TF
- if ask you to install python extension say 'yes'
- activate pop up menu:  `ctrl+shift+p` 
- Set vscode to us 'cnn' enviroment as default python interpreter, type: `Python: Select Interpreter` and set it to `Python 3.7.5 64-bit ('cnn':conda) `
- open TouchDesigner project file: /YOLOv3_TF/TD_Yolo.toe
- in the VScode - go to Explorer (ctrl+shift+e) and find the file named `ObjectDetection.py` right click on file and select 'Run Python File In Terminal'

7. How to use it: 
* Inside `TD_Yolo.toe` project you will find spout output to send the texture. 
* There is also little parser witch give you back 10 objects at the time,(accuracy and bounding box position on screen). The code in python is not limited so you can build you own parser or extend this one. It will be update in future. This version is very experimantal level.    
* to set diffrent resolution change line 26 and 27 in `ObjectDetection.py` and set the same size to 'constant1' in `TD_Yolo.toe` _*note for now is working only with square resolution_

### TO DO:

* ### Training module
* ### parser optimalization 
