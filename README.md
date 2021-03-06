# SRKernels
<img src="Figures/0010x4bc.png" width="400" hspace="20"/> <img src="Figures/0010x4.png" width="400"/> 

Super-Resolution models are typically trained using LR images that were generated by downsampling HR images with a bicubic kernel (this is shown in the left image which is image number 10 from the DIV2K dataset). A better performance can be acheived by using realisic blur kernels (right image). This repo contains Blur Kernels that can be used to develop datasets for Super Rresolution models. The original work and much of the code is adapted from [Zhou and Strusstrunk](https://github.com/IVRL/Kernel-Modeling-Super-Resolution).

## Dark Channel Kernels
Kernels generated from the [DPED dataset](https://people.ee.ethz.ch/~ihnatova/) using [Dark Channels](https://faculty.ucmerced.edu/mhyang/papers/cvpr16_dark_channel_deblurring.pdf). The code to generate these kernels can be found in Zhou and Strusstrunk's repo. This repo contains 1825 of these kernels. These kernels are saved in `Kernel_Generator/Dark Channel Kenrels.7z` as `.mat` files and can be read using `scipy.io.loadmat`.  

## GAN Kernels 
Matlab kernels were used to train a GAN to generate more kernels. These kernels containe a more diverse set of features and are better suited for training SR models. To generate these kernels download the decriminator and generator weights from [here](https://drive.google.com/file/d/1lvUSaJi_X6SJYIOka6Y44gFqXuVfggN2/view?usp=sharing). Then add `Kernel_Generator/utils/` to the path. The kernels can be generated by running `wgan-edit.ipnyb` but make sure the model is pointed to the weights to generate kernels. 

<img src="Figures/kernels (2).png" width="425">

Top row: images of Dark Channel blur kernels.<br />
Bottom row: images devloped using a GAN

