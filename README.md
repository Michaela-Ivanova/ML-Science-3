# Predicting laminar Fluid Flow through Porous Media using Deep Learning

### Overview 
This project predicts the laminar fluid flow field through a porous medium using deep learning. The goal is to train neural networks that estimate the transversal flow rate field q(x, y) based on the porous geometry and physical parameters:

- Pressure drop (ΔP)
- Channel length (L)
- Fluid viscosity (μ)
- Pixel area (ΔA)

The physics is guided by Darcy’s law, and different deep learning architectures (CNN, VGG-like, and U-Net) are explored, with a focus on physics-informed scaling and symmetry-aware training.

### Dataset

The dataset contains 1500 samples of 32×64 binary grids representing porous cross-sections: 1 = open (fluid flows through), 0 = closed (impermeable). Furthermore, there is a second dataset with physical parameters provided for each grid: ΔP, L, μ, ΔA.
The labels represent the true flow rate field q(x, y) for each grid.

The flow physics follows a local formulation of Darcy’s law (used for homogeneous and dimensionless formulation):
q(x, y) ∝ (ΔP × ΔA) / (μ × L)

### Methods 

- Symmetry-aware training: Impelemented data augmentation (horizontal/vertical flips, 180° rotations).
- Implemented Group-Equivariant U-Net (GU-Net) for enforcing physical consistency.
- CNN (basic 5-layer)
- VGG-like (simplified 7-layer)
- U-Net and Group-Averaging U-Net 
- Custom loss functions: Relative Error (RE) Loss; Symmetry Loss to enforce flip consistency


## Running the code 

In order to run the code, go to CodeImplementation-A3.ipynb. Make sure to have installed all the required packages in the first cell of the notebook, and then run all the cells. 
