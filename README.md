# TUM-MLS-2016: An Annotated Mobile LiDAR Dataset of the TUM City Campus for Semantic Point Cloud Interpretation in Urban Areas
his dataset is used as the reference for the semantic labeling of MLS point clouds: TUM-MLS-2016.

### Data introduction

The TUM-MLS-2016 data have been acquired in April 2016 by Fraunhofer IOSB with their MODISSA mobile sensor platform in the area of the city campus of Technical University of Munich (TUM) in Munich, Germany. The MODISSA was equipped with two Velodyne HDL-64E LiDAR sensors above the windshield. The LiDAR data were recorded synchronously with position and orientation data of an Applanix POS LV 520 inertial navigation system (INS). All lever arms and boresight directions of the system components had been thoroughly calibrated beforehand[1]. Although the data acquisition is continuous, for convenience and by convention we split the stream of georeferenced 3D points to a sequence of scans of 1/10 second duration, corresponding to single 360 degree scans of the scanner heads rotating at 10 Hz[2].

For the annotation of points, we have manually labeled this area with eight semantic classes following the ETH standard[3] (0: Unlabeled, 1: Artificial Terrain, 2: Natural Terrain, 3: High Vegetation, 4: Low Vegetation, 5: Building, 6: Hardscape, 7: Artefact, and 8: Vehicle) and points of different labels rendered with different colors.

Based on the annotation of points, we created three datasets serving the evaluation of related methods and algorithms, including a benchmark dataset for semantic labeling, test data for instance segmentation, and test data for individual labeled 360 degree scans. These three datasets are related to the two core tasks of semantic interpretation, namely the semantic labeling and object segmentation.

### Benchmark for semantic labeling
For generating the benchmark dataset for semantic labeling, we started with re-merging all points of all the georeferenced single scans into a large point cloud. Then, the merged point cloud was preprocessed by the statistical outlier removal (SOR) filter and down-sampled, with duplicated points deleted. Sequentially, the distant points in the scan with a sparse density were cropped and removed. Based on the filtered and cropped point cloud, the total number of annotated points is more than 40 million, and we conducted the annotation of points manually. With these annotated points, we created a benchmark dataset for the evaluation of semantic labeling. Here, only annotated points of the eight semantic classes are kept, and those which belong to the unclassified class are removed. We show the entire annotated benchmark dataset with eight object classes. For evaluation purposes, the entire labeled dataset of the TUM city campus has been evenly divided into three areas according to the covered area size, and the numbers of points in these three areas are around 20 million, 16 million, and 13 million, respectively. In Fig.1 a, the separation of these three areas is displayed. Points of each area are saved in the same .ply files. 
<img src="/figures/Fig1_TUM_Benchmark.png" height="80%" width="80%" >

### Annotated data for instance segmentation

Based on the annotated benchmark for semantic labeling, we also conducted an instance segmentation to the labeled points, so that points of the same instance can be separated and assigned with a unique label. 
<img src="/figures/Fig2_TUM_Instance.png" height="80%" width="80%" >

### Annotated data for single 360 degree laser scans

For the single 360 degree laser scans from both scanners, we conducted a nearest neighbor search for assigning the points sequentially with a possible label, according to the annotated points in the large-scale benchmark dataset.
For the points in each scan, a point was given the same label as the nearest neighbor in the annotated scene within a given threshold (0.3m). If there are no points found in the given radius, the point was labeled to belong to the unclassified class. In Fig.3, we also provide an illustration of the annotation result of a sequence of single scans with time index of 04068, 04108, 04148, respectively.
<img src="/figures/Fig3_TUM_ScansSequence.png" height="80%" width="80%" >

### Reference:
[1] Diehm AL, Gehrung J, Hebel M, Arens M. (2020) Extrinsic self-calibration of an operational mobile LiDAR system. Eds. International Society for Optics and Photonics, SPIE, 2020, Vol. 11410, pp. 46 – 61.
[2] Borgmann B, Schatz V, Kieritz H, Scherer-Klöckling C, Hebel M, Arens M. (2018) Data Processing and Recording Using a Versatile Multi-sensor Vehicle. ISPRS Annals of the Photogrammetry, Remote Sensing & Spatial Information Sciences 2018, 4, 21–28
[3] Hackel T, Savinov N, Ladicky L, Wegne J D, Schindler K, Pollefeys M (2017) Semantic3d. net: A new large-scale point cloud classification benchmark. ISPRS Annals of the Photogrammetry, Remote Sensing and Spatial Information Sciences, 2017, Vol. IV-1-W1, pp. 91–98.


### Data access
Please contact [Jingwei Zhu](mailto:jingwei.zhu@tum.de?subject=[TUM-MLS-2016]%20Jingwei%20Zhu), [Prof. Uwe Stilla](mailto:stilla@tum.de?subject=[TUM-MLS-2016]%20Uwe%20Stilla), or [Dr. Marcus Hebel](mailto:marcus.hebel@iosb.fraunhofer.de?subject=[TUM-MLS-2016]%20Marcus%20Hebel) for getting this dataset.

### Copyright
The annotated TUM-MLS-2016 dataset is copyrighted by Fraunhofer IOSB, Ettlingen, Fraunhofer Institute of Optronics, System Technologies and Image Exploitation and Photogrammetry and Remote Sensing, Technical University of Munich. If this annotated data is used in your work, it is made available under the Creative Commons Attribution-NonCommercial-ShareAlike 4.0 International License (CC BY-NC-SA 4.0).

### Please refer the following publication, if this reference dataset is used in your work:
```
@article{zhu2020tum,
  title={TUM-MLS-2016: An Annotated Mobile LiDAR Dataset of the TUM City Campus for Semantic Point Cloud Interpretation in Urban Areas},
  author={Jingwei Zhu,Joachim Gehrung,Rong Huang,Björn Borgmann,Zhenghao Sun,Ludwig Hoegner,Marcus Hebel, Yusheng Xu and Uwe Stilla}
  journal={Remote Sensing},
  year={2020}
}
@article{xu2019classification,
  title={Classification of LiDAR Point Clouds Using Supervoxel-Based Detrended Feature and Perception-Weighted Graphical Model},
  author={Xu, Yusheng and Ye, Zhen and Yao, Wei and Huang, Rong and Tong, Xiaohua and Hoegner, Ludwig and Stilla, Uwe},
  journal={IEEE Journal of Selected Topics in Applied Earth Observations and Remote Sensing},
  year={2019},
  publisher={IEEE}
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
