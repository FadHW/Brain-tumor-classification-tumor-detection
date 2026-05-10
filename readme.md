## Overview:    
Classification dataset:   
https://www.kaggle.com/datasets/masoudnickparvar/brain-tumor-mri-dataset  
Classes: glioma,
meningioma,
notumor,
pituitary  
Classification notebook:  
https://www.kaggle.com/code/fadyhanywadie/classfication  

### Tumor Detection:  
#### Understand the data:  
They are three different viewing directions (planes) of the MRI scan.  
A brain MRI is a 3D volume, and doctors can slice/view it from different angles.  
#### The 3 MRI Planes
1) Axial Plane  
This is like slicing the brain horizontally from top to bottom.  
You look at the brain as if you are standing above the patient looking downward.
2) Coronal Plane  
This slices the brain from front to back.  
You view the patient face-to-face.
3) Sagittal Plane  
This slices the brain from left to right.  
You see the side profile of the brain.

#### Why Use Multiple Planes?  
A tumor may be:  
1. Clearly visible in the **axial** view    
2. Partially hidden in the **coronal** view   
3. Better shaped or more clearly defined in the **sagittal** view    
    
Different planes reveal different spatial information.  
This is extremely important in medical imaging because tumors are 3D structures.  

Tumor dataset:   
https://www.kaggle.com/datasets/davidbroberts/brain-tumor-object-detection-datasets  
Tumor detection notebook:   
