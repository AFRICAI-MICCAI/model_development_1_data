# AFRICAI/MICCAI AI in Medical Imaging in Africa Summer School - 2023
Materials for the 1st AFRICAI Summer School session for the session
"Model Development 1: Data-centric best practices and common pitfalls and open access infrastructures". 
For more information, see the AFRICAI website: https://africai.org/summer-school/. 

You can find  the basic outline and introduction of the sections covered in this session. 
Each section corresponds to the tutorial notebooks included in the `Notebooks` folder. Optional notebooks are added for future reference and are not covered in this session.

# 0. Introduction to Google colab
Google collab is a free notebook environment that runs entirely in the [cloud](https://colab.research.google.com/drive/16pBJQePbqkz3QFV54L4NIkOn1kwpuRrj#scrollTo=BCmeo64HcLfs).

We will be using extensive use of this notebook throught this summer school. Google colab lets us write and execute arbitrary python code through the browser, and is especially well suited to machine learning, data analysis and education. More technically, Colab is a hosted Jupyter notebook service that requires no setup to use, while providing access free of charge to computing resources including GPUs.

# 1. Open Acccess Datasets
Datasets are the entry point and one of the most important aspects of medical imaging research or any research in general. Public and free datasets in the medical field are quite limited. The following links are the best way to get started.

## MedMNIST
The MedNIST dataset was created for educational purposes and contains medical images gathered from several sets from TCIA, the RSNA Bone Age Challenge, and the NIH Chest X-ray dataset. The name MedNIST was inspired by the popular MNIST dataset, which has been called "the 'Hello World' of deep learning."

*Medical MNIST Paper*: https://medmnist.com/

*Medical MNIST Data*: https://www.kaggle.com/datasets/andrewmvd/medical-mnist

## TCIA - The Cancer Imaging Archive
Link:  https://wiki.cancerimagingarchive.net/display/Public/Wiki

*TCIA tutorials*: https://github.com/kirbyju/TCIA_Notebooks

## UK Biobank
UK Biobank is a large-scale biomedical database and research resource, containing in-depth genetic and health information from half a million UK participants. Data can be available to approved researchers.

Link: https://www.ukbiobank.ac.uk/


## Grand Challenge
Grand Challenge is a platform for end-to-end development of machine learning solutions in biomedical imaging. it can be useful to try out your algorithm on public dataset from challenges.

Link: https://grand-challenge.org/documentation/

# 2. Data inspection and curation
To make propoer use of open access data, it is mandatory to understand the content, inspect for irregularities, and curate the data to fit our research needs. Medical imaging data can come in different format. 

[TCIA tutorials repository](https://github.com/kirbyju/TCIA_Notebooks) has many resources on curating dicom data.

[RSNA tutorials](https://github.com/RSNA/AI-Deep-Learning-Lab-2022/blob/main/sessions/data-curation) and [MONAI tutorials](https://github.com/Project-MONAI/tutorials) also contain great resources in this topic.


# 3. Data splitting 
A properly inspected and curated data needs to split into training, validation and testing sets. Depending on the research question we are trying to answer, there might also be a need to withold/exclude some sets from our dataset. This section will cover exclusion / inclusion criteria, training, testing, and external validation.

Link: [Data camp tutorial](https://github.com/datacamp/workspace-tutorial-python-data-preprocessing-train-test-split)

# 4. Data preprocessing 

Image preprocessing (Apostolia) 

**Registration**

Image registration is useful to align data/images in the same space for further processing. Both theoretical and practical tutorials are available for this section.

- Theoretical tutorial: https://github.com/MedicalImageAnalysisTutorials/ImageRegistrationTutorial
- Image registration with MONAI: https://github.com/Project-MONAI/tutorials

# 5. Data augmentation
*Tensorflow tutorials:* https://notebook.community/tensorflow/docs/site/en/tutorials/images/data_augmentation

# 6. Data reporting

# 7. Data loaders

# Contact
Coordinators:

- Apostolia Tsirikoglou (apostolia.tsirikoglou@ki.se)
- Martijn Starmans (m.starmans@erasmusmc.nl)

Contributers:

- Mahlet Birhanu
- Douwe Spaanderman