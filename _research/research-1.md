---
title: "Research on 3D LiDAR Aided (3DLA) Urban GNSS Positioning for Robotics Navigation"
excerpt: "Investigate reliable methods to improve the GNSS positioning in urban canyons for reliable robotic navigation, by leveraging the active environment perception from 3D LiDAR to detect, correct the NLOS/Multipath signals <br/><img src='/images/3DLA-GNSS.emf.jpg'>"
collection: research
---

<!-- **The Cauchy-Schwarz Inequality**

$$\left( \sum_{k=1}^n a_k b_k \right)^2 \leq \left( \sum_{k=1}^n a_k^2 \right) \left( \sum_{k=1}^n b_k^2 \right)$$ -->

[Dr. Li-ta Hsu](https://www.polyu-ipn-lab.com/), [Dr. Weisong Wen](https://weisongwen.github.io/), [Xikun Liu](https://www.polyu-ipn-lab.com/people), [Xiwei Bai](https://www.polyu-ipn-lab.com/people), [Yihan Zhong](https://www.polyu-ipn-lab.com/people), [Feng Huang](https://www.polyu-ipn-lab.com/people). 

## Recent News
- May 2022, 1 paper get accepted in **IEEE Transactions on Intelligent Transportation Systems**.
  - **Wen, W**., and Hsu, L.T., 2022. 3D LiDAR Aided GNSS NLOS Mitigation in Urban Canyons. IEEE transactions on intelligent transportation systems. ([Paper](https://arxiv.org/ftp/arxiv/papers/2112/2112.06108.pdf), [Video](https://www.youtube.com/watch?v=YQPn3sHlcEg&list=PLiBu9nX8VXKVmNaz7TdETPrlhum-g3vil&index=2))

- 23th April 2022, our conference paper was accepted in ION GNSS+ 2022. 
  - Liu, X., **Wen, W***., and Hsu, L.T. 2022, September. 3D LiDAR Aided GNSS Real-time Kinematic Positioning via Coarse-to-fine Batch Optimization for High Accuracy Mapping in Dense Urban Canyons. In Proceedings of the 35th International Technical Meeting of the Satellite Division of The Institute of Navigation (ION GNSS+ 2022).

## Abstract
Positioning in urban environments is becoming essential due to the increasing demand for autonomous driving vehicles (ADV). The global navigation satellite system (GNSS) is currently one of the principal means of providing globally-referenced positioning for ADV localization. With the increased availability of multiple satellite constellations, GNSS can provide satisfactory performance in open-sky areas. However, the positioning accuracy is significantly degraded in highly-urbanized cities such as Hong Kong, due to signal reflection caused by static buildings and dynamic objects such as double-decker buses. If the direct light-of-sight (LOS) is blocked, and reflected signals from the same satellite are received, the notorious non-light-of-sight (NLOS) receptions occur. According to a recent review paper, NLOS is currently the major difficulty in the use of GNSS in intelligent transportation systems. Because of NLOS receptions, the performance of GNSS positioning is highly influenced by real-time surrounding environmental features, such as buildings and dynamic objects. Therefore, effectively sensing and understanding surrounding environments is the key to improve GNSS positioning in urban areas, as GNSS positioning relies heavily on sky view visibility. 

Inspired by the strong perception capability of ADV using onboard sensors (such as 3D LiDAR), we continuously developed the perception-aided NLOS mitigation methods where the 3D LiDAR is employed to timely reconstruct the surrounding environments to identify the NLOS receptions. The idea was also reported in the industrial magazine in 2018. The work was further improved in 2020, where several drawbacks are relaxed and was awarded the Best Presentation Award in the session of Navigation in Urban Environments. Interestingly, this award is selected by the session chairs from Waymo (a company focused on the realization of L4 autonomous driving) and Swift Navigation (a company that focused on GNSS precise positioning solutions). Meanwhile, the idea is transferred into industrial applications for high-accuracy offline mapping applications. However, the accuracy from GNSS single point positioning is still limited due to the systematic errors, such as clock and atmospheric errors. Recently, we extended the LiDAR aided GNSS NLOS mitigation to the GNSS Real-time Kinematic (RTK), leading to sub-meter level accuracy. Unfortunately, the fixed rate of the RTK is still not guaranteed as: 
  - The exisitng method does not fully mitigate the NLOS with multiple reflections and multipath. It is still **an unknown questions to model the multiple reflection and multipath**. 
  - Poor satellite geometry due to the signal blockage and potential NLOS exclusion. It is still an unknown question to **effective improve the geometry of the satellite constraints in dense urban canyons**. 


<p align="center">
  <img width="800" src="/images/3DLA-GNSS.emf.jpg">
</p>
<center> 3D LiDAR Aided GNSS Positioning for Robotics Urban Navigation​ </center>

## Related Papers: (*: Corresponding author)
### 2022

1.  Li, X., Li, S., Shen, Z., Zhou, Y., Wang, X., Li, X., and **Wen, W**., 2021. Continuous and precise positioning in urban environments by tightly coupled integration of GNSS, INS, and Vision, IEEE Robotics and Automation Letters. ([Paper](https://ieeexplore.ieee.org/document/9866851))
2.  Zhang, J., **Wen, W***., Huang, F., Wang, Y., Chen, X., & Hsu, L. T. (2022). GNSS-RTK Adaptively Integrated with LiDAR/IMU Odometry for Continuously Global Positioning in Urban Canyons. Applied Sciences, 12(10), 5193. ([Paper](https://www.mdpi.com/2076-3417/12/10/5193))
3.  Liu, X., **Wen, W***., and Hsu, L.T. 2022, September. 3D LiDAR Aided GNSS Real-time Kinematic Positioning via Coarse-to-fine Batch Optimization for High Accuracy Mapping in Dense Urban Canyons. In Proceedings of the 35th International Technical Meeting of the Satellite Division of The Institute of Navigation (ION GNSS+ 2022). 

### 2021
3.  **Wen, W**., and Hsu, L.T., 2021. 3D LiDAR Aided GNSS NLOS Mitigation in Urban Canyons. IEEE transactions on intelligent transportation systems. ([Paper](https://arxiv.org/ftp/arxiv/papers/2112/2112.06108.pdf), [Video](https://www.youtube.com/watch?v=YQPn3sHlcEg&list=PLiBu9nX8VXKVmNaz7TdETPrlhum-g3vil&index=2))

4. Bai, X., **Wen, W**.* and Hsu, L.T., 2022. Time-correlated Window Carrier-phase Aided GNSS Positioning in Urban Canyons, IEEE Transactions on Aerospace and Electronic Systems. ([Paper](https://ba0b7fda-849d-46f9-ad0b-6a691cd3ab4a.usrfiles.com/ugd/ba0b7f_cb9ee5547c184a05903efa0e2b417f44.pdf))
5. **Wen, W**., Zhang, G. and Hsu, L.T., 2021. Gnss outlier mitigation via graduated non-convexity factor graph optimization. IEEE Transactions on Vehicular Technology, 71(1), pp.297-310. ([Paper](https://ba0b7fda-849d-46f9-ad0b-6a691cd3ab4a.usrfiles.com/ugd/ba0b7f_a051506bced94481a8d414f6494bfa47.pdf))
6. **Wen, W**., Pfeifer, T., Bai, X. and Hsu, L.T., 2021. Factor graph optimization for GNSS/INS integration: A comparison with the extended Kalman filter. NAVIGATION, Journal of the Institute of Navigation, 68(2), pp.315-331. ([Paper](https://ba0b7fda-849d-46f9-ad0b-6a691cd3ab4a.usrfiles.com/ugd/ba0b7f_74fd9aea2d8348b4b176185fa8b84dba.pdf), [Video](https://www.youtube.com/watch?v=f5bIh96SRsk))
7. **Wen, W**. and Hsu, L.T., 2021, September. 3D LiDAR Aided GNSS Real-time Kinematic Positioning. In Proceedings of the 34th International Technical Meeting of the Satellite Division of The Institute of Navigation (ION GNSS+ 2021) (pp. 2212-2220). ([Paper](https://ba0b7fda-849d-46f9-ad0b-6a691cd3ab4a.usrfiles.com/ugd/ba0b7f_ef71d598729740c797b35b6759660862.pdf), [Video](https://www.youtube.com/watch?v=_Sh25vIe-xk))


### 2020
7. **Wen, W**., Bai, X., Zhang, G., Chen, S., Yuan, F. and Hsu, L.T., 2020. Multi-agent collaborative GNSS/camera/INS integration aided by inter-ranging for vehicular navigation in urban areas. IEEE Access, 8, pp.124323-124338. ([Paper](https://ieeexplore.ieee.org/stamp/stamp.jsp?arnumber=9130714))
8. Zhang, G., Ng, H.F., **Wen, W**. and Hsu, L.T., 2020. 3D mapping database aided GNSS based collaborative positioning using factor graph optimization. IEEE Transactions on Intelligent Transportation Systems. ([Paper](https://ba0b7fda-849d-46f9-ad0b-6a691cd3ab4a.usrfiles.com/ugd/ba0b7f_fa9b08982fd641299bfc3acbc382f6fd.pdf))
9.  Zhang, G., **Wen, W**., Xu, B. and Hsu, L.T., 2020. Extending shadow matching to tightly-coupled GNSS/INS integration system. IEEE Transactions on Vehicular Technology, 69(5), pp.4979-4991. ([Paper](https://ba0b7fda-849d-46f9-ad0b-6a691cd3ab4a.usrfiles.com/ugd/ba0b7f_565930330e8b4bcaa42958fed1ca292e.pdf))
10. **Wen, W**., Zhang, G. and Hsu, L.T., 2020. Object-Detection-Aided GNSS and Its Integration With Lidar in Highly Urbanized Areas. IEEE Intelligent Transportation Systems Magazine, 12(3), pp.53-69. ([Paper](https://ba0b7fda-849d-46f9-ad0b-6a691cd3ab4a.usrfiles.com/ugd/ba0b7f_6d366f88f06343078df7f5739384f674.pdf))
11. Bai, X., **Wen, W**. * and Hsu, L.T., 2020. Using Sky-pointing fish-eye camera and LiDAR to aid GNSS single-point positioning in urban canyons. IET Intelligent Transport Systems, 14(8), pp.908-914. ([Paper](https://ba0b7fda-849d-46f9-ad0b-6a691cd3ab4a.usrfiles.com/ugd/ba0b7f_bf75ccffde1b42148fb3b6871fd2b229.pdf))
12. **Wen, W**., 2020, September. 3D LiDAR Aided GNSS and Its Tightly Coupled Integration with INS Via Factor Graph Optimization. In Proceedings of the 33rd International Technical Meeting of the Satellite Division of The Institute of Navigation (ION GNSS+ 2020) (pp. 1649-1672). ([Paper](https://ba0b7fda-849d-46f9-ad0b-6a691cd3ab4a.usrfiles.com/ugd/ba0b7f_4826c55cd63d4bae84c2c539e66583e0.pdf), [Video](https://www.youtube.com/watch?v=YZut8BTfYXU))
8. **Wen, W**., Bai, X., Hsu, L.T. and Pfeifer, T., 2020, April. GNSS/LiDAR integration aided by self-adaptive Gaussian mixture models in urban scenarios: An approach robust to non-Gaussian noise. In 2020 IEEE/ION Position, Location and Navigation Symposium (PLANS) (pp. 647-654). ([Paper](https://ba0b7fda-849d-46f9-ad0b-6a691cd3ab4a.usrfiles.com/ugd/ba0b7f_423d7226984947c8a3dc214e046b1277.pdf))

### 2019
12. **Wen, W**., Bai, X., Kan, Y.C. and Hsu, L.T., 2019. Tightly coupled GNSS/INS integration via factor graph and aided by fish-eye camera. IEEE Transactions on Vehicular Technology, 68(11), pp.10651-10662. ([Paper](https://ba0b7fda-849d-46f9-ad0b-6a691cd3ab4a.usrfiles.com/ugd/ba0b7f_9eb96eab4da64320a998dafc3be32cd1.pdf))
13. **Wen, W**., Zhang, G. and Hsu, L.T., 2019. GNSS NLOS exclusion based on dynamic object detection using LiDAR point cloud. IEEE transactions on intelligent transportation systems. ([Paper](https://ba0b7fda-849d-46f9-ad0b-6a691cd3ab4a.usrfiles.com/ugd/ba0b7f_1775ccf7f7294494aea2ed843e9c06d1.pdf))
14. **Wen, W**., Zhang, G. and Hsu, L.T., 2019. Correcting NLOS by 3D LiDAR and building height to improve GNSS single point positioning. Navigation, 66(4), pp.705-718. ([Paper](https://ba0b7fda-849d-46f9-ad0b-6a691cd3ab4a.usrfiles.com/ugd/ba0b7f_788e6fb5513a449e94f43f653db3135b.pdf))
15. Zhang, G., **Wen, W**. and Hsu, L.T., 2019. Rectification of GNSS-based collaborative positioning using 3D building models in urban areas. GPS solutions, 23(3), pp.1-12. ([Paper](https://ba0b7fda-849d-46f9-ad0b-6a691cd3ab4a.usrfiles.com/ugd/ba0b7f_2a1af8cd368e4955af11bb5c54fd2440.pdf))

### 2018
11. **Wen, W**., Zhang, G. and Hsu, L.T., 2018, September. Correcting GNSS NLOS by 3D LiDAR and building height. In Proceedings of the 31st International Technical Meeting of the Satellite Division of The Institute of Navigation (ION GNSS+ 2018) (pp. 3156-3168). ([Paper](https://ba0b7fda-849d-46f9-ad0b-6a691cd3ab4a.usrfiles.com/ugd/ba0b7f_e27e05a2124e4e37a243331dc2a1638e.pdf))
12. **Wen, W**., Zhang, G. and Hsu, L.T., 2018, April. Exclusion of GNSS NLOS receptions caused by dynamic objects in heavy traffic urban scenarios using real-time 3D point cloud: An approach without 3D maps. In 2018 IEEE/ION Position, Location and Navigation Symposium (PLANS) (pp. 158-165). IEEE. ([Paper](https://ba0b7fda-849d-46f9-ad0b-6a691cd3ab4a.usrfiles.com/ugd/ba0b7f_99c6522e361943eeb4985f90768fa9fe.pdf))

## Video Demonstration
<p align="center">
  <iframe width="560" height="315" src="https://www.youtube.com/embed/tvdkKQU9Lro" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
</p>
<center> Demonstration: 3D LiDAR Aided NLOS Exclusion for GNSS Real-time Kinematic (RTK) Positioning in Urban Canyons </center>

<p align="center">
  <iframe width="560" height="315" src="https://www.youtube.com/embed/_Sh25vIe-xk" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
</p>
<center> Presentation in ION GNSS+ 2021: 3D LiDAR Aided NLOS Exclusion for GNSS Real-time Kinematic (RTK) Positioning in Urban Canyons </center>

<p align="center">
  <iframe width="560" height="315" src="https://www.youtube.com/embed/YQPn3sHlcEg" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
</p>
<center> Demonstration: 3D LiDAR Aided NLOS Exclusion for GNSS Single Point Positioning in Urban Canyons </center>

<p align="center">
  <iframe width="560" height="315" src="https://www.youtube.com/embed/YZut8BTfYXU" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
</p>
<center> Presentation in ION GNSS+ 2020: 3D LiDAR Aided NLOS Exclusion for GNSS Single Point Positioning in Urban Canyons </center>

<p align="center">
  <iframe width="560" height="315" src="https://www.youtube.com/embed/PJOSsWc8AhE" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
</p>
<center> Presentation in ION GNSS+ 2021: Continuous GNSS-RTK Aided by LiDAR/Inertial Odometry with Intelligent GNSS Selection in Urban Canyons
 </center>
## Press Coverage
- [Inside GNSS](https://insidegnss.com/perceived-environment-aided-gnss-single-point-positioning-an-example-using-lidar-scanner/) 
- [Innovation Award from TechConnect](https://www.polyu.edu.hk/aae/people/academic-staff/dr-weisong-wen/~/link.aspx?_id=8DBBF8BDC8F84AB5A2F92B1C73DC6584&_z=z)
- [Best Presentation Award in ION GNSS+ 2020](https://www.ion.org/gnss/) 


## Acknowledgement and Collaborator
This research was funded by the government and industry partners, such as funding from Hong Kong Polytechnic University, Guangdong Basic and Applied Basic Research Foundation, Riemann Laboratory, Huawei Technologies, etc,.

<p align="center">
  <img width="800" src="/images/funding.jpg">
</p>
<center> ​ </center>