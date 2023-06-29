---
permalink: /code_data/
title: "Code & Data"
classes: wide
---

Only the possibility to evaluate the algorithms of others makes research comparable.
Therefore, I provide the datasets and source code for all my publications below of my publications below. 

## Open Source Software

### libRSF -- A Robust Sensor Fusion Library

The libRSF is an open source C++ library that provides the basic components for robust sensor fusion.
It can be used to describe an estimation problem as a factor graph and solves it with least squares, powered by the Ceres Solver.

This library is the result of many years of coding and the practical implementation of my PhD thesis and many of my papers.
Its mot important contribution is the adaptive factor graph approach, based on Gaussian mixtures.
The libRSF contains multiple algorithms to represent Gaussian mixtures as cost function of least squares and to estimate them from data.

[Visit the **libRSF** on GitHub.](https://github.com/TUC-ProAut/libRSF) 


### gnss_converter -- A ROS Package for GNSS Preprocessing

This ROS package is a simple RINEX-to-Rosbag converter written in C++. It decodes observations from a multi-constellation GNSS receiver and augments them with an ephemeris, atmospheric corrections, and the individual satellite clock bias.

The gnss_converter can be used to generate a Rosbag file containing raw GNSS pseudoranges.
In addition, it contains an estimated fix of the rover's position and a velocity estimate based on Doppler data, both calculated by the RTKLIB.
A Matlab script can ultimately be used to convert the Rosbag file to a .mat file.

Please note that this repository holds just a stripped-down version of the [GraphGNSSLib](https://github.com/weisongwen/GraphGNSSLib), which provides a full factor graph back-end.
I created this fork for a more straightforward maintainability of the gnss_preprocessor package.

[Visit the **gnss_converter** on GitHub.](https://github.com/TUC-ProAut/gnss_converter) 


## Public Datasets


### smartLoc -- GNSS Datasets from Urban Environments

During the project smartLoc, we recorded four GNSS datasets in the urban centers of Berlin and Frankfurt.
Each dataset consists of raw pseudo-range measurements from multiple satellite systems along with relative motion information from the recording vehicle's wheel odometry.
The pseudo-ranges are recorded using a low-cost receiver from uBlox and a ground truth is provided by a high-class one from NovAtel.
Three variants of this dataset are available:

1. The original CSV version of the datasets is provided on the [smartLoc website](https://mytuc.org/gnss).

2. A version in the more common RINEX format is available as part of the [gnss_converter repository](https://github.com/TUC-ProAut/gnss_converter/tree/main/gnss_preprocessor/dataset/smartLoc).

3. Since pre-processing GNSS data can be exhausting, I provide an already processed version along with the [libRSF](https://github.com/TUC-ProAut/libRSF/tree/9e145b4ed9a0c51dd35e354ac6420141ea9df111/datasets/smartLoc-RTKLIB).

We describe the dataset in detail here:
> Reisdorf, P.; Pfeifer, T.; Breßler, J.; Bauer, S.; Weissig, P.; Lange, S.; Wanielik, G. & Protzel, P. (2016)  
> The Problem of Comparable GNSS Results -- an Approach for a Uniform Dataset with Low-Cost and Reference Data, 
> Proc. of Int. Conf. on Advances in Vehicular Systems, Technologies and Applications (VEHICULAR)

### Chemnitz City -- An Urban GNSS Dataset

The Chemnitz City datasets was originally recorded by Marcus Obst and Niko Sünderhauf.
It follows the same structure as the smartLoc datasets but has a lower amount of none-line-of-sigh measurements.

I provide only a preprocessed version along with the libRSF [here](https://github.com/TUC-ProAut/libRSF/tree/master/datasets/Chemnitz%20City).

### TUC SLAM -- A Indoor SLAM Dataset

Recorded by Peer Neubert and Stefan Schubert, this 2D indoor SLAM datasets consist of relative odometry measurements and loop closures.
The loop closures are detected by an omnidirectional camera and a visual place recognition algorithm.

I provide a CSV version along with the libRSF [here](https://github.com/TUC-ProAut/libRSF/tree/master/datasets/SLAM).

Please cite:
> Neubert, P., Schubert, S. & Protzel, P. (2019)  
> A neurologically inspired sequence processing model for mobile robot place recognition, 
> Robotics and Automation Letters (RA-L), DOI: [10.1109/LRA.2019.2927096](https://dx.doi.org/10.1109/LRA.2019.2927096)

### Labyrinth -- A Small UWB Dataset

Recorded using a small mobile robot consists this dataset of wheel odometry and range measurements to beacons with known positions.

I provide a CSV version along with the libRSF [here](https://github.com/TUC-ProAut/libRSF/tree/master/datasets/Indoor_UWB).
