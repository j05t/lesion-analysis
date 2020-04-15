# Skin Lesion Analysis Towards Melanoma Detection 
![Sample images](https://github.com/j05t/lesion-analysis/blob/master/sample_images.png)

## Background
Skin cancer is the most common cancer globally, with melanoma being the most deadly form. Dermoscopy is a skin imaging modality that has demonstrated improvement for diagnosis of skin cancer compared to unaided visual inspection. However, clinicians should receive adequate training for those improvements to be realized. In order to make expertise more widely available, the International Skin Imaging Collaboration (ISIC) has developed the ISIC Archive, an international repository of dermoscopic images, for both the purposes of clinical training, and for supporting technical research toward automated algorithmic analysis by hosting the ISIC Challenges.

## Task
The goal for [ISIC 2019](https://challenge2019.isic-archive.com/) is to classify dermoscopic images among nine different diagnostic categories:

    Melanoma
    Melanocytic nevus
    Basal cell carcinoma
    Actinic keratosis
    Benign keratosis (solar lentigo / seborrheic keratosis / lichen planus-like keratosis)
    Dermatofibroma
    Vascular lesion
    Squamous cell carcinoma
    None of the others

25,331 images are available for training across 8 different categories. Additionally, the test dataset contains an additional outlier class not represented in the training data, which developed systems must be able to identify.

## Results
![ROC](https://github.com/j05t/lesion-analysis/blob/master/ensemble_plot.png)

![ROC](https://github.com/j05t/lesion-analysis/blob/master/ensemble_metrics.png)

## Source
An ensemble of classifiers performs at 0.624 overall score: https://challenge2019.isic-archive.com/live-leaderboard.html (2019: Lesion Diagnosis). 

Trained model architectures are 
* Inception-ResNet-v2: [isic_classifier_inceptionresnetv2.ipynb](isic_classifier_inceptionresnetv2.ipynb)
* SE-ResNeXt-101(32x4d): [isic_classifier_se_resnext101_32x4d.ipynb](isic_classifier_se_resnext101_32x4d.ipynb),  [isic_classifier_se_resnext101_32x4d_add_tr.ipynb](isic_classifier_se_resnext101_32x4d_add_tr.ipynb)

Ensembling ([ensemble.ipynb](ensemble.ipynb)) has been achieved by calculating the simple arithmetic mean of the predictions of the best performing models.

If GitHub is unable to view the notebooks they can be viewed externally at

https://nbviewer.jupyter.org/github/j05t/lesion-analysis/blob/master/ensemble.ipynb

https://nbviewer.jupyter.org/github/j05t/lesion-analysis/blob/master/isic_classifier_inceptionresnetv2.ipynb

https://nbviewer.jupyter.org/github/j05t/lesion-analysis/blob/master/isic_classifier_se_resnext101_32x4d.ipynb

https://nbviewer.jupyter.org/github/j05t/lesion-analysis/blob/master/isic_classifier_se_resnext101_32x4d_add_tr.ipynb
