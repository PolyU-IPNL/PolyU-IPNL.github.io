---
title: 'Blog 2: GNSS Doppler Adied Cycle Slip Detection'
date: 2022-11-11
permalink: /talks/2012-08-14-blog-post-cycleSlip

tags:
  - Doppler measurements
  - Carrier-phase
  - Cycle slip detection
  - GNSS urban canyons
---

<!-- This blog delivers my views of the navigation for robotic systems in urban canyons.  -->

Role of the carrier-phase measurements in GNSS positioning and velocity estimation
======
I was attracted by the carrier-phase for a while due to its high accuracy in positioning or even the velocity estimation. In particular, the observation model of the carrier-phase measurements can be denoted as below: 

$$\varphi_{r,t}^{s}=r_{r,t}^{s}+c(\delta_{r,t}-\delta_{r,t}^{s}) - I_{r,t}^{s}+T_{r,t}^{s} + \lambda *N_{r,t}^{s}+\epsilon_{r,t}^{s}$$

where the $\varphi_{r,t}^{s}$ denotes the carrier-phase measurement (in the unit of meters) received from the satellite $s$ by the receiver $r$. The $r_{r}^{s}$ denotes the real range between the GNSS receiver and satellite. The $c$ denotes the speed of light. The $\delta_{r,t}$ and $\delta_{r,t}^{s}$ denotes the receiver and satellite clock bias. The $I_{r,t}^{s}$ and $T_{r,t}^{s}$ denotes the innospheric and tropospheric errors. The $N_{r,t}^{s}$ denotes the **unknown integer ambiguity** which need to be reliably resolved before its usage in absolute positioning. The $\epsilon_{r,t}^{s}$ denotes the Gaussian noise associated with the carrier-phase measurements. To use the carrier-phase, the following methods are typical:
 - **time differenced carrier-phase (TDCP)**: The unknow integer ambiguity is assumed to be constant across multiple epochs. As a result, the ambiguity can be elliminated by doing the single difference between two epochs of the carrier-phase measurements. However, only relative constraint can be provided by the TDCP constraint which is usually used for the receiver's velocity estimation. 
 - **GNSS-RTK/PPP-RTK**: The unknown integer ambiguity is analytically resolved using the integer adjustment method, such as the [LAMBDA](https://espace.curtin.edu.au/handle/20.500.11937/12982). Usually, this requires the corrections from the reference stations. 
 - **window carrier-phase constraint (WCP)**: this is newly developed recently where the left null space matrix is used to elliminate the unknown integer ambiguities. For more details, one can refer to the paper in [WCP](https://ieeexplore.ieee.org/abstract/document/9707661/?casa_token=qDmsOFC9lDcAAAAA:0RbolqpGJZe3YJkBzIOMRbgBRKALQHVTVXMqtiP9g-q9SUOQWGlRjJpTkOVREKXdcy-liaBZib0).


Cycle slip is of great importance
======
In real case, the ambiguity of the carrier-phase may not be constant across multiple epochs due to the signal reflections from surroundings. This variation of the integer ambiguity is called the cycle slip. 

## TDCP modeling

Take the TDCP constraint as an example, the mathematical form of the TDCP is as below:

$$\Delta \varphi_{r,t,t-1}^{s}=\varphi_{r,t}^{s} - \varphi_{r,t-1}^{s}$$

with 

$$\varphi_{r,t-1}^{s}=r_{r,t-1}^{s}+c(\delta_{r,t-1}-\delta_{r,t-1}^{s}) - I_{r,t-1}^{s}+T_{r,t-1}^{s} + \lambda *N_{r,t-1}^{s}+\epsilon_{r,t-1}^{s}$$

where the $\Delta \varphi_{r,t,t-1}^{s}$ denotes the time differenced measurements. By doing the time-difference, the following equation can be obtained:

$$\Delta \varphi_{r,t,t-1}^{s} = r_{r,t}^{s} - r_{r,t-1}^{s} - (c(\delta_{r,t}-\delta_{r,t}^{s}))- c(\delta_{r,t-1}-\delta_{r,t-1}^{s}) + \epsilon_{r,t, t-1,}^{s}$$

The equation above is obtained given the assumptions of below: 
- the variation of the atmospheric errors are small 
- the integer ambiguity is constant with the epochs $t$ and $t-1$ 

Since the satellite clock bias change between the two epcohs with a short period is small, the equation above can be further refined as below: 

$$\Delta \varphi_{r,t,t-1}^{s} = r_{r,t}^{s} - r_{r,t-1}^{s} - (c*\delta_{r,t}- c*\delta_{r,t-1}) + \epsilon_{r,t, t-1,}^{s}$$

Therefore, the equation above is the modeling of the TDCP measurements. However, once the cycle slip occur, the equation above is not correct and is dangerous! To model the cycle slip, the revised equation should be below:

$$\Delta \varphi_{r,t,t-1}^{s} = r_{r,t}^{s} - r_{r,t-1}^{s} - (c*\delta_{r,t}- c*\delta_{r,t-1}) + \epsilon_{r,t, t-1,}^{s} + \lambda *N_{r,t}^{s} - \lambda *N_{r,t-1}^{s}$$

## Doppler measurement: "derivative of the pseudorange measurement"

The observation function of the Doppler measurements can be derived as below:

$$D_{r,t}^{s}=e_{r}^{s} * (v_{r} - v_{s}) +c(\dot{\delta}_{r,t}-\dot{\delta}_{r,t}^{s})+\epsilon_{r,t}^{s}$$

the $e_{r}^{s}$ denotes the line-of-sight vector connecting the GNSS receiver and the satellite. The $v_{r}$ and $v_{s}$ denote the velocity of the receiver and the satellite, respectively. The observation reveals that the Doppler measurement is related to the velocity of the satellite and the GNSS receiver. However, the equation above is not straintforward enough. One can have the following equation which is in the different way represent the observation function of the Doppler measurements:

$$\lambda*\frac{\partial \rho_{r,t}^{s}}{\partial t} =\frac{\partial (r_{r}^{s}+c(\delta_{r,t}-\delta_{r,t}^{s})+I_{r,t}^{s}+T_{r,t}^{s}+\epsilon_{r,t}^{s})}{\partial t}$$

similarily, the change of the atmospheric error is small. We can get the following form:

$$\lambda*\frac{\partial \rho_{r,t}^{s}}{\partial t} =\frac{\partial (r_{r}^{s}+c(\delta_{r,t}-\delta_{r,t}^{s})+\epsilon_{r,t}^{s})}{\partial t}$$

Therefore, we can found that the right side is exactly the same as the one of the TDCP measurements. Below should be satisfied if there is no cycle slip:


$$\lambda*\frac{\partial \rho_{r,t}^{s}}{\partial t} \approx \Delta \varphi_{r,t,t-1}^{s} $$

As a result, a threshold can be used to detect the potential cycle slip as below:

$$\lambda*\frac{\partial \rho_{r,t}^{s}}{\partial t} - \Delta \varphi_{r,t,t-1}^{s} \geq
T_{thres} $$

An typical value of the threshod $T_{thres} $ can be $10 * \lambda$. Stop here and have a nice weekend! 


<!-- $$\varphi_{r,t}^{s}=r_{r}^{s}+c(\delta_{r,t}-\delta_{r,t}^{s}) - I_{r,t}^{s}+T_{r,t}^{s} + \lambda *N_{r,t}^{s}+\epsilon_{r,t}^{s}$$ -->


References
======
- [1] Using latex to input equations in [Overleaf Link](https://www.overleaf.com/learn/latex/List_of_Greek_letters_and_math_symbols). 
- [2] Zhao, J., Hernández-Pajares, M., Li, Z., Wang, L., & Yuan, H. (2020). High-rate Doppler-aided cycle slip detection and repair method for low-cost single-frequency receivers. GPS Solutions, 24(3), 1-13.
- [3] Teunissen, P. (2006). The LAMBDA method for the GNSS compass. Artificial Satellites, 41(3), 89-103.
- [4] Bai, X., Wen, W., & Hsu, L. T. (2022). Time-correlated Window Carrier-phase Aided GNSS Positioning Using Factor Graph Optimization for Urban Positioning. IEEE Transactions on Aerospace and Electronic Systems.
- [5] [Video for the satellite navigation](https://weisongwen.github.io/teaching/2014-spring-teaching-1)

