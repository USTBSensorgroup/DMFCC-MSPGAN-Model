Official implementation of the paper "Performance Enhancement of Φ-OTDR Event Classification via Dynamic MFCCs and Multi-Scale Discriminator-Based FastGAN Data Augmentation". This repository contains the complete pipeline for reproducing the results, including:

Preprocessing raw Φ-OTDR vibration signals

Dynamic MFCC (DMFCC) extraction

##################################################
Accessing the two datasets
##################################################
The two datasets can be accessed through the following links, when used, the respective papers should be cited appropriately 

1. Cao et al. (2023) dataset: https://github.com/BJTUSensor/
2. Tomasov et al. (2025) dataset: https://springernature.figshare.com/articles/dataset/Comprehensive_Dataset_for_Event_Classification_Using_Distributed_Acoustic_Sensing_DAS_Systems/27004732


##############################################
Procedures
##############################################
1. Loop the function extract_dmfcc_features to produce images representing all 1D files in dataset folders
2. Run the MSPGAN_Training`function
    This function will train the MSPGAN model, save the sub models and load them for evaluation
3. Generate synthesis images

 Use the GeneratingImages function to generate synthetic  dataset and same them in their respective parent folders (i.e save walking class images in the folder named walking etc.)

4. Training the classification network (DMFCC-MSPGAN ) by Runing the classificationNetTraining(data_dir="path_to/dataset_root", num_epochs=75)

Dataset Folder Structure

dataset_root/

├── BG/
├── DG/
├── KN/
├── WT/
├── SK/
└── WK/

This will train the model (DMFCC-MSPGAN ), save it and load it

5. Perform model evaluations by running the provided evaluation functions. follow the paper details and evaluation functions included in this GitHub such as
PlotConfusionMatrice, tSNEVisualization etc.
