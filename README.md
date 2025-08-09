# Performance-Enhancement-of--OTDR-Event-Classification-via-Dynamic-MFCCs-and-Augmentation
Official implementation of the paper "Performance Enhancement of Φ-OTDR Event Classification via Dynamic MFCCs and Multi-Scale Discriminator-Based FastGAN Data Augmentation".  This repository contains the complete pipeline for reproducing the results, including:  Preprocessing raw Φ-OTDR vibration signals  Dynamic MFCC (DMFCC) 
#1 Training The MSPGAN models

first: Run the MSPGAN_Training`function
    This function will train the MSPGAN model, save the sub models and load them for evaluation

#2 Generate synthesis images

 Use the GeneratingImages function to generate synthetic  dataset and same them in their respective parent folders (i.e save walking class images in the folder named walking etc.)


#3 Training the classification network (DMFCC-MSPGAN )

Dataset Folder Structure

dataset_root/

├── BG/
├── DG/
├── KN/
├── WT/
├── SK/
└── WK/


first: Run the classificationNetTraining(data_dir="path_to/dataset_root", num_epochs=75)

This will train the model (DMFCC-MSPGAN ), save it and load it

Second: Perform model evaluations by running the provided evaluation functions. follow the paper details and evaluation functions included in this GitHub such as PlotConfusionMatrice, tSNEVisualization etc.
