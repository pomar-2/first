# PWStableNet: Learning Pixel-wise Warping Maps for Video Stabilization

## Headers

# This is a [PyTorch](http://pytorch.org/) implementation of PWStableNet: Learning Pixel-wise Warping Maps
for Video Stabilization.

If you have any questions, please refer to github: https://github.com/mindazhao/PWStableNet


## Prerequisites

- Linux
- Python 3.6
- NVIDIA GPU (12G or 24G memory) + CUDA cuDNN
- pytorch 0.4.0+
- numpy
- cv2
- ...

## Datasets

The dataset for is the DeepStab dataset (7.9GB) http://cg.cs.tsinghua.edu.cn/download/DeepStab.zip thanks to Miao Wang [1]. 

## Testing

Put the test video at the folder named original.

Open terminal -> cd to pwstablenet -> python ./test.py  


### Download a pre-trained network
- Author provide a pre-trained model.
- Torch models:
       model can be get from  home.ustc.edu.cn/~zmd1992/PWStableNet/netG_model.pth
- You can test your own unstable videos by changing the parameter "train"    with False and adjust the path yourself in function "process()".

## Training 
- The code will download the [VGG-16](https://arxiv.org/abs/1409.1556) PyTorch base network weights at:             https://download.pytorch.org/models/vgg16-397923af.pth automatically.

- To train PWNet using the train script simply specify the parameters listed in `./lib/cfg.py` as a flag or manually change them.
- The default parameters are set for the use of two NVIDIA 1080Ti graphic cards with 24G memory.


```Shell
CUDA_VISIBLE_DEVICES=0,1 python main_new.py
```

- Note:
  * For training, an NVIDIA GPU is strongly recommended for speed.
  * Before training, you should ensure the location of preprocessed dataset, which will be supplied soon.
