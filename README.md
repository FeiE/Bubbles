## Table of contents ##
- [Experimental Design (Bubbles sampling)](#experimental-design-bubbles-sampling) 
- [Analyses Framework](#analyses-framework)
  - [Mutual Information (MI)](#mutual-informationmi)
  - [Reverse analyses](#reverse-analyses)

## Experimental Design (Bubbles sampling) ##

Participants are shown images in which contiguous image pixels were sampled by randomly Gaussian apertures (hereafter, Bubbles) on each trial. At the same time responses are recorded. 

- Bubbles take values between 0 and 1, controlling the relative transparency of the mask at each pixel, with 0 being completely opaque and 1 being completely translucent. 
<img src="/imagewithbubbles.png" alt="" width="400">

- Bubbles that randomly sampling the input image changes the visibility of pixels across trials, thus we can determine which pixels visibility affected responses. To do so, we applied information-theoretic analyses and reverse analyses.  


## Analyses Framework ## 
### Mutual Information(MI) ###
MI provides a non-parametric estimation of the linear or nonlinear statistical dependencies between pairs of variables. It can also be viewed as the effect size for a statistical test of independence. A [tutorial](http://onlinelibrary.wiley.com/doi/10.1002/hbm.23471/abstract) with [Matlab & Python code](https://github.com/robince/sensorcop) is available in Ince et al. (2016). 

<img src="/MIERP.png" alt="" width="600">

We compute MI between ERP bivariate responses ([ERP, ERPg]) and one pixel intensity distribution from Bubble mask per each time point and electrode. We repeat this MI calculation per each pixel within the face oval to obtain classification image, producing 4D MI matrix (pixel x pixel x electrode x time point) for each participant. For example, the classification images below show strong dependence between ERP bivariate responses recorded from the right hemisphere and pixels representing left eye region on face trials.

<img src="/MI_results.png" alt="" width="200">


### Reverse analyses ###
Reverse analyses can determine how the left eye visibility affected single-trial ERP distributions from the right hemisphere. To do so, we group distributions of single-trial ERP into 10 binns according to the availability of left eye information. The figure below indicates increased visibility of the left eye causes the larger and earlier N170. 

<img src="/reverseanalyses.png" alt="" width="500">
