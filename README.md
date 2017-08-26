## Table of contents ##
- [Bubbles technique](#bubbles-technique) 
- [Mutual Information (MI)](#mutual-informationmi)
- [Reverse analyses](#reverse-analyses)

## Bubbles technique ##

Participants are shown images in which contiguous image pixels were sampled by randomly Gaussian apertures (hereafter, Bubbles) on each trial. At the same time behaviour and EEG responses are recorded. 

- Bubbles take values between 0 and 1, controlling the relative transparency of the mask at each pixel, with 0 being completely opaque and 1 being completely translucent. 
<img src="/imagewithbubbles.png" alt="" width="400">

- Bubbles that randomly sampling the input image changes the visibility of pixels across trials, thus we can determine which pixels visibility affected responses. To do so, we applied information-theoretic analyses and reverse analyses.  


## Mutual Information(MI) ##
MI provides a non-parametric estimation of the linear or nonlinear statistical dependencies between pairs of variables. It can also be viewed as the effect size for a statistical test of independence. A [tutorial](http://onlinelibrary.wiley.com/doi/10.1002/hbm.23471/abstract) with [Matlab & Python code](https://github.com/robince/sensorcop) is available in Ince et al. (2016). 

<img src="/MI.png" alt="" width="600">

- Blue frame: for the pixel marked in red, we can compute MI between two vectors: the distribution of behaviour performance (i.e. RT, correct or not) and pixel intensity from Bubble mask. To obtain classification image, we repeat MI calculation per each pixel within the face oval.

- Orange frame: similarly, we can obtain classification image that depict relationship between each pixel intensity from Bubble mask and ERP bivariate responses ([ERP, ERPg]) at each time point and electrode. For example, the figure below showed sensitivity of ERP bivariate responses recorded from the right hemisphere to left eye ERP bivariate responses.   

<img src="/MI_results.png" alt="" width="200">


## Reverse analyses ##
Reverse analyses can determine how the pixel representing left eye region affected single-trial ERP distributions from the right hemisphere. To do so, we group distributions of single-trial ERP into 10 binns according to the availability of eye information. The figure below indicates Increased visibility of the right eye caused larger and earlier N170. 

<img src="/reverseanalyses.png" alt="" width="500">
