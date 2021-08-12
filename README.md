# Prediction of subject's response in n-back test based on ECOG features
_________________________________________________________________________________________________________________________________

Understanding the dataset:
What is the mean about the memory_nback\data\al_nback.mat data(shape is (360120, 40)) 40 column

## Select just one of the recordings here. This is subject 1, block 1.
dat = alldat[1][1] 
Which one is subject 1 (CA/CC/AL/UG)
_________________________________________________________________________________________________________________________________

![image](https://user-images.githubusercontent.com/50405601/129152851-24910075-945e-4ba3-9460-4415db53139e.png)

_________________________________________________________________________________________________________________________________

## Possible research questions/hypotheses: 

Can we use a hybrid model using the ERP (P300) and spectral power (alpha: 8-12 Hz & theta: 3-7 Hz) combined to predict the workload of the participants (i.e. whether they are performing a 0-back, 1-back or 2-back task)? 
Workload (increase) = alpha (decrease) over parietal regions
Workload (increase) = theta (increase) over frontal channels 
Workload (increase) = P300 (increase) to target stimuli
Predict the level of uncertainty based on spectral power & ERPs 
Difference in activity between target versus non-target trials 
Difference in activity when target was present and participants was able to detect it versus he was not able detect it 
_________________________________________________________________________________________________________________________________

## Possible Problems: 
In the literature usually working memory load is detected over frontal and parietal central channels 
 
## Analysis ideas: 
Make predictions on a  single trial level (online analysis possible) e.g. with SVM classifier
Train a classifier on one patient and test on the other

## MNE toolbox: 
Feature extraction from each trial (-400 - 1600) → popular methods used (literature) 
Feature selection/reduction (features in EEG, e.g. mean amplitude, power/entropy)
Channel selection 
_________________________________________________________________________________________________________________________________

![image](https://user-images.githubusercontent.com/50405601/129152977-27069309-fc54-4642-a701-7c58e0596918.png)
_________________________________________________________________________________________________________________________________
![image](https://user-images.githubusercontent.com/50405601/129153066-231e6bf1-29bf-451c-9f5e-3e76a5c0c5e5.png)
_________________________________________________________________________________________________________________________________
![image](https://user-images.githubusercontent.com/50405601/129153170-f9d433c1-98d6-48b2-a7c9-8d1958a52957.png)
_________________________________________________________________________________________________________________________________
With the use of multichannel recordings, it is now possible to gain insights into spatio-temporal patterns of brain activity, which can be linked to relevant behavior. This is particularly interesting for investigating functions with known spatial profiles, such as working memory (WM). Parietal and premotor regions have been associated with the rehearsal of items and maintenance of visuospatial attention in WM tasks. Recently, it has also been shown that local-field potential (LFP) power is modulated in the alpha and theta band with increasing working memory load. Therefore, we are examining ECoG data over parietal and posterior frontal regions of two epilepsy patients performing a 0-back, 1-back and 2-back task. WM load was increased with increasing n. It is expected that alpha power over parietal and premotor regions decreases with increasing WM load while theta power may increase in these areas with larger n. We classified the three task variants based on spectral features using a KNN-algorithm and a combination of spectral and temporal features using a CNN followed by a PCA. The results of both models are expected to complement each other in the time and frequency domain. Our findings may contribute to further understand the neural implementation of WM by discerning temporal and spatial features related to WM load.
