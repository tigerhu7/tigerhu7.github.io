---
layout: post
section-type: post
title: My Profile
category: Life
tags: [ 'profile, interests' ]
---


<!--
### Abstract
-->

This page contains links to my interests and list of my projects. :-)


### My Interests

I love to travel and keep track of my footprints. Welcome to visit my [**travel website**](https://www.polarsteps.com/tigerhu7).

<!--
### List of My Projects
-->

### My Projects

#### 【Medical Image Processing and Analysis】  

<!--    这个地方 **？？** 右面**后空两个格子 , 包括下面的 - 文字要顶着-写， 然后最后也要空两个格子  -->


<!--    主动脉项目          -->
**Aorta Segmentation, Visualization and Calculation**  
-preprocess Phase Contrast MRI data, including bias field correction and flow field denoising  
-segment aorta in subpixel precision and retrieve flow field from Phase Contrast MRI  
-retrieve aortic centerline and perpendicular plane
-generate 3D mesh from point cloud of aortic surface  
-make a moving picture of blood flow  
-calculate aortic Wall Shear Stress(WSS) from PC-MRI, and compare it with the result from computational fluid simulation

<img width="30%"  src="/img/profile/research/aorta_orthoplane.png">  
<img width="30%"  src="/img/profile/research/aorta_surface.png">  
<img width="30%"  src="/img/profile/research/aorta_streamline.png">     
<img width="30%"  src="/img/profile/research/aorta_wss.png">  



<!--    冠状动脉项目        -->
**Coronary Artery Segmentation, 3D Reconstruction and Computation**       `
-preprocess CTA data and apply vesselness filters  
-segment coronary arteries  
-retrieve centerlines, calculate its arclength to inflow point and get radius of perpendicular section plane  
-coronary artery centerline refinement
-generate 3D mesh from point cloud of coronary artery surface  
-display coronary arteries using MPR
-compare Fractional Flow Reserve by CFD with the one measured with PressureWire    
-detect suspicious stenosis     

<img width="30%"  src="/img/profile/research/coronary_3D.png">  
<img width="30%"  src="/img/profile/research/carefine.png">  
<img width="30%"  src="/img/profile/research/coronary_FFR.png">  
<img width="30%"  src="/img/profile/research/coronary_mpr.png">  




<!--    医学影像软件开发项目        -->
**3D Me`    dical Imaging Integrated Software Development**  
-add/modify segmentation algorithms (Graph Cut, Fast Marching, Live Wire and etc)and integrate them into the software   
-integrate live cancer reporting and diagnostic system (LiRADS)    
-integrate trained liver cancer LiRADS features classifier  

<img width="20%"  src="/img/profile/research/graphcut.png">  


<!--    药效评估项目        -->
**Evaluation on Effectiveness of Liver Cancer Drug**     
-segment liver tumor in a time series    
-compute drug permeation parameters (Ktrans, ve and etc)   
-evaluate effectiveness through statistics    
<img width="30%"  src="/img/profile/research/Ktrans.png">



<!--    CT与MRI配准项目        -->
**Aorta CT and MRI Registration**    
-segment aortas of same patient from different sources (CT, MRI)  
-retrieve surface point cloud   
-use revised Iterative Closest Point method and RANSAC affine transform for registeration     
<img width="30%"  src="/img/profile/research/aorta_registration.png">     




<!--    对称性脑肿瘤检测项目        -->
**Brain Tumor Detection using Asymmetry**  
-find 3 major axis through PCA, fine tune using a homogeneous transform and last get symmtery plane   
-apply SLICO superpixel algorithm on image slices  
-compute the texture difference of corresponding superpixels on each side of symmetry plane     
-estimate tumor position using texture difference measures       
<img width="20%"  src="/img/profile/research/braintumor.jpg">  
<img width="20%"  src="/img/profile/research/braintumor2.jpg">  



<!--    肝脏血管抽取及分段项目        -->
**Liver Vessels Segmentation and Couinaud Hepatic Classification (unfinished)**    
-retrieve hepatic veins  
-find centerline, arclength, curvature, radius of perpendicular plane and other geometries    
-locate bifurcation points
-conduct Couinaud Hepatic Classification according to previous geometries and bifurcations     
<img width="30%"  src="/img/profile/research/hepaticveincc.png">    




#### 【Shape Deformation】

**Geodesic Shooting Method in Image Registration**   
-set up geodesic shooting equations for Large Diffeomorphic Deformation Metric Mapping that is used for registering source image to target image      
-using various kernels/filters, to compare the results  
-calculate transform field and get transformed image  
-compute geodesic distance between transformed image and target image          
<img width="30%"  src="/img/profile/research/diff.png">


<!--
**Use Reaction-Advection-Diffusion Equation to simulate brain tumor growth**  
-set up reaction-advection-diffusion equation to simulate tumor growth  
-find optimal parameters  
-generate meshgrid and use Finite Element Method to find numerical solution  
<img width="30%"  src="/img/profile/research/labtocat.png">
-->


#### 【General Image Processing】   
**Beef Marbling Grading**    
-segment beef ribeye       
-utilize superpixel algorithm to obtain blocks, then distinguish fat and lean blocks   
-calculate far portion, fat blocks portion, fractal dimension and other texture features     
-set up a marbling ranking classifier using these features    
<img width="30%"  src="/img/profile/research/beefmarbling_AC.png">  
<img width="30%"  src="/img/profile/research/beefmarbling_SP.png">  

#### 【Teaching Experience】   
**Teaching Assistant**  
-I have been instructing students in problem sessions at University of Texas at Dallas   
-classes include Calculus(1,2,3), Linear Algebra, Ordinary Differential Equation, Calculus(Cohort), Multivariable Calculus and ect    
-my average rating from students is 4.4 out of 5   
<img width="30%"  src="/img/profile/research/labtocat.png">
