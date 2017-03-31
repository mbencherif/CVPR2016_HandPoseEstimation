# CVPR2016_HandPoseEstimation

An implementation of the Multi-View CNNs based 3D Hand Pose Estimation Method.
 
 
    Robust 3D Hand Pose Estimation in Single Depth Images: from Single-View CNN to Multi-View CNNs
    
    Liuhao Ge, Hui Liang, Junsong Yuan and Daniel Thalmann.
    
    Proceedings of IEEE International Conference on Computer Vision & Pattern Recognition (CVPR'16).
    Las Vegas, NV, USA, June 2016.
	
Please cite this paper if you use our released code.

# Installation Instructions

## Database

Download the MSRA Hand Gesture database at:

~http://research.microsoft.com/en-us/um/people/yichenw/handpose/cvpr15_MSRAHandGestureDB.zip~

https://www.dropbox.com/s/bmx2w0zbnyghtp7/cvpr15_MSRAHandGestureDB.zip?dl=0

Unzip it and put folders "P0"~"P9" in the "cvpr15_MSRAHandGestureDB" directory.

Please cite "Xiao Sun, Yichen Wei, Shuang Liang, Xiaoou Tang and Jian Sun. Cascaded Hand Pose Regression. IEEE Conference on Computer Vision and Pattern Recognition (CVPR), 2015", if you use this database.

## Projection

The "Projection" project is used to generate projection images for training CNNs. Results are stored in "./cvpr15_MSRAHandGestureDB/Px" (x=0~8) as matlab files. You can use these results for training.

This project should be compiled using Visual Studio 2013. OpenCV 2.4.10 should be installed in your computer. If you are using other version of OpenCV, please modify the solution property.

## CNN

We use Torch7 for CNN training. Download and install Torch7 at: http://torch.ch/

We released our source code for training CNN of XY view. If you want to train the other two views, please modify the files "1_data.lua" and "6_test_offline.lua" following the instruction in these files.

The released codes are run in Linux. If you want to run the forward propogation of CNN in Windows, please follow the instruction at:

	https://github.com/jonathantompson/jtorch

## Fusion

The "Fusion" project uses heat-maps generated by CNNs to estimate 3D joint locations. The heat-maps should be put in the "heatmaps" folder for every subject. The PCA files should be put in the "PCA" folder for every subject.

In this subject, we only test on subject "P0". P0's heat-maps are generated by CNNs trained by data of "P1"-"P8". P0's PCA parameters are generated by performing PCA on ground truth of "P1"-"P8".

This project should be compiled using Visual Studio 2013. OpenCV 2.4.10 should be installed in your computer. If you are using other version of OpenCV, please modify the solution property.
