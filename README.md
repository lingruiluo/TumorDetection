# Tumor Detection 

### Applied Deep Learning Final Project, Fall 2020
Lingrui Luo (ll3356), Di Ye (dy2404)

**Objectives:**
* Classify if the image contains tumor
* Localize and visualize the tumors when an image contains tumor 

We try to: 
* Assist pathologists to detect and localize tumor, and make a better decision 
* Reduce cost on diagnosis

**Dataset Overview**
* Using a subset of CAMELYON16 data set
* In total, we are using 21 slides that have tumor
* Each slide is stored in a multi-resolution pyramid structure
* Mask image  of slides indicates the location of tumor cells

**Data Preprocessing**
* Generate smaller image patches extracted from the slide
* Save patches (299*299) as images in a sliding window across the slide
* Assign a ‘tumor’ label a patch as tumor if at least one pixel in the center region (128*128)  is annotated as tumor. Otherwise assign a ‘normal’ label to the patch
* Explore different levels of the slides - Level 3, 4, and 5
* Make sure the unique slides are in different sets (train, validation, and test)
* Slides we use in different sets - Train : Validation : Test  = 15: 3: 3

**Methods & Modeling**
* Single level as  input
* Multiple levels as input
* Fine Tuning on pre-trained models
  * VGG16
  * Inception

**Evaluation & Results**


**Codes** 

**References**  
[1]Liu, Y., Gadepalli, K., Norouzi, M., Dahl, G. E., Kohlberger, T., Boyko, A., ... & Hipp, J. D. (2017). Detecting cancer metastases on gigapixel pathology images. arXiv preprint arXiv:1703.02442.   
[2] Dataset: https://camelyon16.grand-challenge.org/Data/  
[3] Fine-tuning: https://keras.io/guides/transfer_learning/#an-endtoend-example-finetuning-an-image-classification-model-on-a-cats-vs-dogs-dataset  
