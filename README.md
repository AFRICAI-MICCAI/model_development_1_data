# AFRICAI/MICCAI AI in Medical Imaging in Africa Summer School - 2023

<img src="Images/AFRICAI_banner.jpg" alt="Overview"/>

Materials for the 1st AFRICAI Summer School session for the session  
**_Model Development 1: Data-centric best practices and common pitfalls and open access infrastructures_**.   
For more information, see the AFRICAI website: https://africai.org/summer-school/. 

In this file, you can find  the basic outline and extended material on the sections covered in this session. We will have three hands-on [Notebooks](https://github.com/AFRICAI-MICCAI/model_development_1_data/tree/main/Notebooks), namely on [Data inspection and curation](https://github.com/AFRICAI-MICCAI/model_development_1_data/blob/main/Notebooks/2-%20Data-inspection-and-curation-DL.ipynb), [Data preprocessing and augmentation](https://github.com/AFRICAI-MICCAI/model_development_1_data/blob/main/Notebooks/4-5-%20Data-preprocessing-and-augmentation.ipynb), and a final exercise on applying the principles we covered in a [custom PyTorch model](https://github.com/AFRICAI-MICCAI/model_development_1_data/blob/main/Notebooks/custom-DL-PyTorch.ipynb).  
All of the rest notebooks under the same folder, indicated with *[optional]* are simple examples or added for future reference.

# Data-centric AI
What is Data-centric AI?  
[*"Data-centric AI is the discipline of systematically engineering the data used to build an AI system."*](https://datacentricai.org/)    

* Interesting reads and talks
    * [Labeling and Crowdsourcing](https://datacentricai.org/labeling-and-crowdsourcing/), [Data Augmentation](https://datacentricai.org/data-augmentation/), and [Data in Deployment](https://datacentricai.org/data-in-deployment/)
    * [Algorithms for data-centric AI](https://datacentricai.org/blog/algorithms-for-data-centric-ai/) and [Finding millions of label errors with Cleanlab](https://datacentricai.org/blog/finding-millions-of-label-errors-with-cleanlab/)

<br>_Practical resource_: [**Course on Data-centric AI** at MIT](https://dcai.csail.mit.edu/) (free public access)  
&nbsp; with [video lectures](https://dcai.csail.mit.edu/lectures/) and [notebooks](https://github.com/dcai-course/dcai-lab)

## 0. Introduction to Google colab
Google collab is a free notebook environment that runs entirely in the [cloud](https://colab.research.google.com/drive/16pBJQePbqkz3QFV54L4NIkOn1kwpuRrj#scrollTo=BCmeo64HcLfs).

We will be using extensive use of this notebook throught this summer school. Google Colab lets us write and execute arbitrary Python code through the browser, and is especially well suited to machine learning, data analysis and education. More technically, Colab is a hosted Jupyter notebook service that requires no setup to use, while providing access free of charge to computing resources including GPUs.

We have added an introductory [notebook](https://github.com/AFRICAI-MICCAI/model_development_1_data/blob/main/Notebooks/0-%20Into-to-Google-Colab-%5Boptional%5D.ipynb)
on Google Colab to this repository, which we recommend to start with if you've never used it.

# 1. Open Acccess Datasets
Datasets are the entry point and one of the most important aspects of medical imaging research or any research in general. Public and free datasets in the medical field are quite limited. The following links are the best way to get started.

## MedMNIST
The MedNIST dataset was created for educational purposes and contains medical images gathered from several sets from TCIA (see below), the RSNA Bone Age Challenge, and the NIH Chest X-ray dataset. The name MedNIST was inspired by the popular MNIST dataset, which has been called "the 'Hello World' of deep learning."

*Medical MNIST Paper*: https://medmnist.com/

*Medical MNIST Data*: https://www.kaggle.com/datasets/andrewmvd/medical-mnist

We have added an **optional** [notebook](https://github.com/AFRICAI-MICCAI/model_development_1_data/blob/main/Notebooks/1-%20Datasets-MedNist-%5Boptional%5D.ipynb)
to simply introduce you to MedMNIST to this repository.

## TCIA - The Cancer Imaging Archive
The TCIA is one of the largest repositories of public, freely available radiology and histopathology data. While originally aimed at cancer, the TCIA also contains non-cancer datasets. Most datasets besides images also contain annotations and clinical data. For more info, seehttps://wiki.cancerimagingarchive.net/display/Public/Wiki.

We have added an **optional** [notebook](https://github.com/AFRICAI-MICCAI/model_development_1_data/blob/main/Notebooks/1-%20Datasets-TCIA-%5Boptional%5D.ipynb)
to this repository showcasing how to use the TCIA API to download datasets. Many more TCIA tutorials can be found at https://github.com/kirbyju/TCIA_Notebooks.

## UK Biobank
UK Biobank is a large-scale biomedical database and research resource, containing in-depth genetic and health information from half a million UK participants. Data can be available to approved researchers.

Link: https://www.ukbiobank.ac.uk/

Since the UK Biobank is not freely publicly available, no notebooks on this subject have been added.

## Grand Challenge
Grand Challenge is a platform for end-to-end development of machine learning solutions in biomedical imaging. it can be useful to try out your algorithm on public dataset from challenges.

To checkout more info on how to use grand challenge, either the datasets or competing by uploading your own algorithms,
we refer to: https://grand-challenge.org/documentation/


# 2. Know your data
To make most out of the data at hand we need to know the power they carry. It is essential to inspect them according to their format and analyze all the information they contain, from pixel data and ground truth labels statistics, to outliers, irregularities and metadata analysis. 

_Important note_: If you come across data that contain sensitive personal information it is essential to treat them carefully and according to your state's and institution's regulations, usually by either fully anonymize or pseudonymize them. There are several open-source tools and examples available, e.g. for handling DICOM files provided by [pydicom](https://github.com/pydicom/deid). Please look accordingly to your data type and application.

## Data inspection and curation according to types and modalities
Medical imaging comes to various shapes and forms, with 
- radiology modalities (X-ray, CT, MRI, PET, etc.) and 
- digital pathology 

to be the most commonly used in computer vision. 

### Radiology modalities

[**DICOM**](https://www.dicomstandard.org/about-home) (Digital Imaging and Communications in Medicine) is the international standard for medical images and associated information/metadata. DICOM covers almost every radiology modality, with an increasing expand to further domains.

There are several tools for inspecting and handling DICOM data, for example:
- TCIA provides useful DICOM introductory material and examples of [DICOM tools](https://wiki.cancerimagingarchive.net/display/Public/DICOM+Tools), while [TCIA_Notebooks](https://github.com/kirbyju/TCIA_Notebooks) offer examples on downloading and inspecting DICOM data.
- [pydicom](https://pydicom.github.io/pydicom/stable/index.html#) is a python package for working with DICOM files. In their [Tutorials](https://pydicom.github.io/pydicom/stable/tutorials/index.html) and [Examples](https://pydicom.github.io/pydicom/stable/auto_examples/index.html#) you can find code samples ranging from dataset basics to image and metadata processing.  
- MONAI tutorial on [loading medical images](https://github.com/Project-MONAI/tutorials/blob/main/modules/load_medical_images.ipynb) shows briefly how to load 3D data in DICOM format. We will go in more details on using MONAI in the Model Development 2 session.  
_(beginner recommended)_
- [DICOM Data Wrangling](https://github.com/RSNA/AI-Deep-Learning-Lab-2022/blob/main/sessions/dicom-wrangling/DataWranglingRSNA2022.ipynb) hands-on from the RSNA AI Deep Learning Lab 2022 is great for DICOM inspection and curation.  
_(beginner recommended)_ 

[**NIfTI**](https://nifti.nimh.nih.gov/) (Neuroimaging Informatics Technology Initiative) is a neuroimagery-specific file format designed to support analysis beyond the clinical workflow. Nowadays, it's one of the standard compressed file formats used in medical imaging AI beyond neuroimaging.

Selecting between the DICOM and NIfTI format is largely dependent on the needs and niche of the end user. DICOM is complex, comprehensive, and highly specific to support needs across the entire
spectrum of medical imaging and clinical workflows, while NIfTI is comparatively simple, minimalistic, and easy to support, and sometimes better suited for research purposes. Frequently, researchers will convert DICOM data output by a scanning instrument into NIfTI for analysis and dissemination [[source](https://conservancy.umn.edu/handle/11299/216582)].

**In this section's** [**notebook**](https://github.com/AFRICAI-MICCAI/model_development_1_data/blob/main/Notebooks/2-%20Data-inspection-and-curation-DL.ipynb), we will inspect MRI DICOM data points, convert them to the NIfTI file format, visualize them, curate the various sequences of the MRI protocol to correspond to each other, and finally process them along radiology and pathology reports into a unified data file ready for deep learning applications.

### Digital pathology
Useful resources include:
- The [histolab](https://github.com/histolab/histolab/) python-based toolbox for whole slide imaging (WSI) processing.
- The [TIAToolbox](https://github.com/TissueImageAnalytics/tiatoolbox) that provides an PyTorch-based end-to-end API for pathology image analysis.
- The _Digital Pathology_ [MONAI tutorials](https://github.com/Project-MONAI/tutorials).

# 3. Data splitting 
### ** Never use the same data for model training and evaluation **

For training and testing purposes, the data should be broken down into three distinct splits:
- *training* - the set used to train and make the model learn the patterns in the data. The same set is fed to the network in each epoch. It should be diverse, unbiased and include variations, as possible, to cover all or most scenarios.
- *validation* - the set, separate from the training and testing data, used to validate the model performance during training (model evaluation is performed on the validation set after every epoch). It helps to tune the hyperparameters.
- *testing* - the set, separate from the training and validation data, used to test the model performance after completing the training.

#### External/Clinical validation
Under the context of AI in medical imaging, external clinical validation of AI algorithms attracts increasingly more attention, aiming to tackle their robustness and generalizability. This entails validating the developed/deployed model on new cases (that in principle are out of the training/validation/testing distribution) that might come from a different source/centre, collected with a different setup/protocol, in a different timeframe and group of patients.

### Techniques

- *Random* - oldest and most popular method. All data is shuffled, and samples are picked randomly for the train, validation, and the test set based on the split ratio. Works good on class-balanced datasets.
- *Stratified* - alleviates the problem of random splitting in class-imbalanced datasets. Here, random samples are picked but the distribution of classes in each of the train, validation, and test sets is preserved.
- *Non-random* - typically used when the development requires a specific set, e.g., the most recent or external data, as the test set.
- *Cross-validation* - or *K-fold cross-validation* is a robust method, where a model is trained and evaluated *K* times on different samples. The entire dataset is split in *K* approximately equal parts/folds, and each fold is chosen in turn for testing and the remaining parts for training. This way the model is trained independently to different distributions of data (*K* times), alleviating some bias that may occur while selecting the splits. Average and standard deviation values are usually reported.  
*Stratified K-fold cross-validation* is a variation where the data class-ratio is maintained when generating the *K* folds.

There are several online resources, like [this example](https://github.com/christianversloot/machine-learning-articles/blob/main/how-to-use-k-fold-cross-validation-with-pytorch.md) on how to use *K-fold cross-validation* with PyTorch.

### ** There is no optimal split percentage ** 
However, it is clear that the quantity of training data should be higher than the other two sets. The dataset split ratio depends on the number of data samples present and the model. You need to come up with an optimum split that suits the need of the dataset/model.

### Tips and tricks

1. If there are many hyperparameters to tune, a larger validation set is preferred to optimize the model performance.
2. Validate the model after each epoch to make the model learn varied scenarios.
3. Experiment with the split ratio. Try different schemes, like 80/10/10, 70/15/15, 60/20/20, or 70/20/10 (train/val/test) considering that if there are less training data the model might show high variance in training, while if there less validation or testing data the model evaluation metrics and final performance will show higher variance. 

### Hands-on
Experiment with *data spiting* in the indicated places in this [notebook](https://github.com/AFRICAI-MICCAI/model_development_1_data/blob/main/Notebooks/custom-DL-PyTorch.ipynb). You should work on this notebook, as a final exercise - after you complete [Data inspection and curation](https://github.com/AFRICAI-MICCAI/model_development_1_data/blob/main/Notebooks/2-%20Data-inspection-and-curation-DL.ipynb) and [Data preprocessing and augmentation](https://github.com/AFRICAI-MICCAI/model_development_1_data/blob/main/Notebooks/4-5-%20Data-preprocessing-and-augmentation.ipynb).

# 4. Data preprocessing
Data preprocessing operations may include, but not limited to, image orientation correction/transformation, resizing/resampling and anti-aliasing algorithms, cropping or padding, and image registration to align the data in the same space for further processing. 

In the first part of **this and next section's** [**notebook**](https://github.com/AFRICAI-MICCAI/model_development_1_data/blob/main/Notebooks/4-5-%20Data-preprocessing-and-augmentation.ipynb) we will go through a set of data preprocessing steps, while we have already seen some 3D image registration examples in the [data curation notebbok](https://github.com/AFRICAI-MICCAI/model_development_1_data/blob/main/Notebooks/2-%20Data-inspection-and-curation-DL.ipynb).

We additionally provide optional resources on:
- [2D image registration theory](https://github.com/AFRICAI-MICCAI/model_development_1_data/blob/main/Notebooks/4-%20Data-preprocessing-2D-registration-Transforms-%5BTheoretical%5D.ipynb), and 
- [2D image registration with MONAI](https://github.com/AFRICAI-MICCAI/model_development_1_data/blob/main/Notebooks/4-%20Data-preprocessing-2D-registration-MONAI-%5Boptional%5D.ipynb)

# 5. Data augmentation
Data augmentation is a standard practice in deep learning application developement, used to artificially expand the size of a training set by creating modified or synthetic data from the existing ones. It is a type of regularization, used to prevent overfitting and improve the model performance

### Techniques

There are several data augmentation methods. For a comprehensive review on data augmentation for medical imaging, see [this article](https://www.sciencedirect.com/science/article/pii/S001048252201099X). Common practice, as well as more advanced, transformations include: 

- *Geometric* –  flip, crop, rotate, stretch, zoom or translate 
- *Color space* – random change RGB color channels, contrast, intensify and brightness
- *Kernel filters* – sharpen or blur an image 
- *Random erasing* – delete a part of the initial image
- *Mixing images* – blending and mixing multiple images
- *Generative modeling* - synthesize new data points using, e.g., GANs
- *Neural style transfer* - content and style are separated and thus new combinations/samples can be generated.

### Tips and tricks

1. Choose proper augmentations for your task. 
2. Do not use too many augmentations in one sequence, or rather be careful when applying multiple transformations on the same images and take care of the ground truth transformations too, if needed. Make small tests to apply them gradually, where you monitor the model performance - positive impact is desired. 
3. Display augmented data before starting training on them. It’s quite easy to make a mistake when forming an augmenting pipeline. That is why it’s always better to double-check the result.
4. Sometimes time and resources matter. In such case, try to time the augmenting process and check the number of computational resources involved.

In the second part of **this and previous section's** [**notebook**](https://github.com/AFRICAI-MICCAI/model_development_1_data/blob/main/Notebooks/4-5-%20Data-preprocessing-and-augmentation.ipynb) we will go through an extensive set of transformations, including geometric, color space and kernel filters.

### Final hands-on
Experiment with *data augmentation* in the indicated places in this [notebook](https://github.com/AFRICAI-MICCAI/model_development_1_data/blob/main/Notebooks/custom-DL-PyTorch.ipynb). You should work on this notebook, as a final exercise - after you complete [Data inspection and curation](https://github.com/AFRICAI-MICCAI/model_development_1_data/blob/main/Notebooks/2-%20Data-inspection-and-curation-DL.ipynb) and [Data preprocessing and augmentation](https://github.com/AFRICAI-MICCAI/model_development_1_data/blob/main/Notebooks/4-5-%20Data-preprocessing-and-augmentation.ipynb).


<!-- *Tensorflow tutorials:* https://notebook.community/tensorflow/docs/site/en/tutorials/images/data_augmentation -->

# 6. Data documentation
In the data-centric and [FUTURE-AI](https://future-ai.eu/) world, where principles like fairness, accountability and ethical usage is of crucial importance, **data documentation** helps to promote not only deliberate reflection and transparency about how these datasets might affect machine learning models and reveal underlying assumptions and potential risks, but also reproducibility and informed decision-making about whether specific datasets meet developing/evaluating needs. 

We motivate you to look further to the available resources on data documentation, such as the [Datasheets for datasets](https://dl.acm.org/doi/10.1145/3458723) and [Data Cards](https://dl.acm.org/doi/10.1145/3531146.3533231), and include such a dataset documentation, for example, in the appendix or supplementary material of your paper. Especially, for the newly introduced African datasets, a proper data description will add value not only to your paper, but also the medical imaging research community.       

# Contact
Coordinators:

- Apostolia Tsirikoglou (apostolia.tsirikoglou@ki.se)
- Martijn P. A. Starmans (m.starmans@erasmusmc.nl)

Contributors:

- Mahlet Birhanu
- Douwe Spaanderman