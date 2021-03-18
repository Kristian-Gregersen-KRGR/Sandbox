# Sandbox

## Setup Tensorflow 1.15 with Cuda 11 

### install nvidia driver (v460)
```
sudo apt-get dist-upgrade
sudo shutdown -r now
sudo apt-get install dkms build-essential
sudo add-apt-repository ppa:graphics-drivers/ppa
sudo apt-get install nvidia-driver-460
sudo shutdown -r now
```
### install anaconda


### create conda environment
```
conda create --name tf-1.15-nvidia python=3.8
conda activate tf-1.15-nvidia
```

### install nvidia python wheel for tensorflow+cuda
```
pip install nvidia-pyindex
```

### install tensorflow with GPU support
```
pip install nvidia-tensorflow[horovod] 
```

## Setup Mask RCNN

### install python libs
```
pip install keras==2.1 matplotlib scikit-image ipython pillow opencv-python imgaug
```

### create folder structure
```
mkdir -p Sandbox/tf-1.15-nvidia/
cd Sandbox/tf-1.15-nvidia/
```

### clone Mask RCNN code from github
```
git clone https://github.com/teknologisk-institut/C073_Segmentation_MaskRCNN.git
cd ./C073_Segmentation_MaskRCNN
git clone https://github.com/matterport/Mask_RCNN.git
```

### export Mask_RCNN to PYTHONPATH
```
export PYTHONPATH=$PYTHONPATH:"Mask_RCNN"
```

## On every login
```
conda activate tf-1.15-nvidia
cd <PATH-TO-C073_Segmentation_MaskRCNN>
export PYTHONPATH=$PYTHONPATH:"Mask_RCNN"
```


## pip installs above using requirements file
```
pip install -r requirements.txt
```
