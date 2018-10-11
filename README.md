# TUM-Semantic-Labeling-Benchmark
This dataset is used as the reference for the semantic labeling of MLS point clouds

### Manually labeled reference

The testing area is the Arcisstrasse along the main entrance of Technical University of Munich (TUM) city campus, which covers
about an area of around 29000 m2. This dataset is initially acquired by [Fraunhofer Institute of Optronics, System Technologies and Image Exploitation (IOSB)](https://www.iosb.fraunhofer.de/servlet/is/71825/). Two Velodyne HDL-64E measured the used point clouds mounted at an angle of 35 degrees on the front roof of the vehicle. In the following provides sketch about how the two scanners are mounted (Gehrung et al., 2017). The original raw point clouds are also preprocessed by a statistical outlier removal for down-sampling and noise suppressing. The number of points after preprocessing is around 50 million. 

With thousands of scans acquired by the laser scanners, the scene contains various kinds of objects according to the eight semantic classes, including building, hight vegetation, low vegetation, vehicles, human-made terrain, natural terrain, hardscape, and scanning artifacts. For the evaluation process, an accurate manually labeled point cloud for the experimental dataset as ground truth is also generated manually by [Photogrammetry & Remote Sensing](http://www.pf.bgu.tum.de) of TUM. The manual work is conducted following the ETH standard (Semantic3D Benchmark) and consumed nearly 30 hours. As a consequence, a highly accurate reference of the Arcisstrasse is generated with only a subset of the entire dataset. 

![ScreenShot](/figures/arcisstr_labeled.gif)

Besides, an additional reference dataset with the instance-level segmented objects will come soon, with 817 objects of eight classes mentioned above labeled and segmented. 

![Illustration](/figures/Github_TUMGT.png)

### Data acquisition

Please contact [Prof. Uwe Stilla, Dr. Ludwig Hoegner, or Yusheng Xu](http://www.pf.bgu.tum.de/sta.html) for getting this dataset. 

### Copyright
The original MLS dataset is copyrighted by Fraunhofer IOSB and it is made available under the Creative Commons Attribution-NonCommercial-ShareAlike 4.0 International License (CC BY-NC-SA 4.0).

### Reference:

Please refer the following publications, if this reference dataset is used in your work:

```
@article{sun2018classification,
  title={Classification of mls point clouds in urban scenes using detrended geometric features from supervoxel-based local contexts},
  author={Sun, Z and Xu, Y and Hoegner, L and Stilla, U},
  journal={ISPRS Annals of Photogrammetry, Remote Sensing and Spatial Information Sciences},
  volume={4},
  number={2},
  year={2018}
}

@article{gehrung2017approach,
  title={An approach to extract moving objects from MLS data using a volumetric background representation},
  author={Gehrung, Joachim and Hebel, Marcus and Arens, Michael and Stilla, Uwe},
  journal={ISPRS Annals of the Photogrammetry, Remote Sensing and Spatial Information Sciences},
  volume={4},
  pages={107},
  year={2017}
}
```
