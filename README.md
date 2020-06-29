## Skin Lesion Analysis Towards Melanoma Detection 
<img width="240" align="left" src="https://github.com/j05t/lesion-analysis/blob/master/sample_images.png"> Skin cancer is the most common cancer globally, with melanoma being the most deadly form. Dermoscopy is a skin imaging modality that has demonstrated improvement for diagnosis of skin cancer compared to unaided visual inspection. In order to make expertise more widely available, the International Skin Imaging Collaboration (ISIC) has developed the ISIC Archive, an international repository of dermoscopic images, for both the purposes of clinical training, and for supporting technical research toward automated algorithmic analysis by hosting the ISIC Challenges.

The goal for the [ISIC 2019 challenge](https://challenge2019.isic-archive.com/) is to classify dermoscopic images among nine different diagnostic categories:

    Melanoma (MEL)
    Melanocytic nevus (NV)
    Basal cell carcinoma (BCC)
    Actinic keratosis (AK)
    Benign keratosis (solar lentigo / seborrheic keratosis / lichen planus-like keratosis) (BKL)
    Dermatofibroma (DF)
    Vascular lesion (VASC)
    Squamous cell carcinoma (SCC)
    None of the others (UNK)

25,331 images are available for training across 8 different categories. Additionally, the test dataset contains an additional outlier class not represented in the training data, which developed systems must be able to identify.

### Web App
The best single model has been deployed as a web app at https://lesion-analysis.uc.r.appspot.com/.

### Accuracy
An ensemble of classifiers performs at 0.634 balanced multiclass accuracy: [ISIC 2019 Live Leaderboard](https://challenge2019.isic-archive.com/live-leaderboard.html) (2019: Lesion Diagnosis).

<img width="400" src="https://github.com/j05t/lesion-analysis/blob/master/roc.png" />
<img width="800" src="https://github.com/j05t/lesion-analysis/blob/master/metrics.png" />

### Source
Ensembling ([ensemble.ipynb](ensemble.ipynb)) has been achieved by calculating the arithmetic mean of the predictions of the best performing models. Trained model architectures are 
* Inception-ResNet-v2: [isic_classifier_inceptionresnetv2.ipynb](isic_classifier_inceptionresnetv2.ipynb)
* SE-ResNeXt-101(32x4d): [isic_classifier_se_resnext101_32x4d.ipynb](isic_classifier_se_resnext101_32x4d.ipynb)
* NASNet-A-Large: [isic_classifier_nasnetalarge.ipynb](isic_classifier_nasnetalarge.ipynb)
* EfficientNet-B4: [isic_classifier_efficientnet-b4.ipynb](isic_classifier_efficientnet-b4.ipynb)
* EfficientNet-B5: [isic_classifier_efficientnet-b5.ipynb](isic_classifier_efficientnet-b5.ipynb)

If GitHub is unable to render the notebooks they can be viewed externally at https://nbviewer.jupyter.org/github/j05t/lesion-analysis/tree/master/.
