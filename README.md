#Assignment 1
Learning Probability Density Function Using Parametric Modeling (MLE)
Dataset Description

Feature Used: NO₂ Concentration (x)
Dataset Source: Kaggle https://www.kaggle.com/datasets/shrutibhargava94/india-air-quality-data

Dataset Type: Air Quality Monitoring Data (India)
Attribute Selected: NO₂ Concentration Levels

The dataset contains air pollution measurements collected from multiple monitoring stations across India. For this assignment, only the NO₂ concentration feature is treated as the random variable ( x ).

Objective

To model the probability density function (PDF) of a transformed random variable using a parametric Gaussian distribution, where parameters are estimated using Maximum Likelihood Estimation (MLE). The goal is to understand how nonlinear transformation affects statistical modeling.

Mathematical Formulation

Each value of ( x ) is transformed into ( z ) using a roll-number-based transformation:

[z = x + a_r sin(b_r x)]

Where:

[a_r = 0.05 (r mod 7)]

[b_r = 0.3 (r mod 5 + 1)]

Roll Number:

[r = 102316009]

Computed parameters:

a_r = 0.15
b_r = 1.5

Methodology

Phase 1: Data Preprocessing
Dataset downloaded and loaded
Missing values removed
NO₂ feature extracted
Data cleaned and validated

Phase 2: Data Transformation
Compute parameters ( a_r ) and ( b_r )
Apply transformation to obtain ( z )
Inspect transformed distribution

Phase 3: Parameter Estimation
Assume Gaussian PDF:

[\hat{p}(z) = c e^(-λ (z - μ)^2)]

Parameters estimated using Maximum Likelihood Estimation (MLE):

( μ ) → Mean of transformed data
( σ² ) → Variance of transformed data
( λ ) = 1 / (2σ²)
( c ) = 1 / √(2πσ²)

Phase 4: PDF Visualization
Plot normalized histogram
Overlay Gaussian PDF curve

Results

The transformed data exhibits a smooth bell-shaped pattern.
The Gaussian model provides a strong approximation of the empirical density.
MLE successfully estimates parameters directly from the transformed samples.

Conclusion

The roll-number-based transformation introduces controlled nonlinearity in the NO₂ data. A parametric Gaussian model is able to capture the statistical behavior of the transformed variable effectively. This demonstrates the usefulness of MLE in probabilistic modeling.

#Assignment 2
Learning Probability Density Functions Using Data Only (GAN-Based Approach)
Objective

To learn the probability density function of a transformed random variable without assuming any parametric distribution, using a Generative Adversarial Network (GAN) trained purely from data samples.

Mathematical Formulation

[z = x + a_r sin(b_r x)]

Where:

[a_r = 0.5 (r mod 7)]

[b_r = 0.3 (r mod 5 + 1)]

Roll Number:

[r = 102316009]

Parameter values used:

Parameter | Value
a_r | 1.5
b_r | 1.5

Methodology

Phase 1: Data Preprocessing
Load dataset
Remove missing values
Extract NO₂ feature
Normalize data
Reduce outliers

Phase 2: Data Transformation
Compute transformation parameters
Convert ( x ) into ( z )
Visualize transformed distribution

Phase 3: GAN Architecture

A GAN consists of two networks:

Generator
Purpose: Generate synthetic samples ( z_f )

Layer | Units | Activation
Dense | 128 | ReLU
Dense | 64 | ReLU
Dense | 1 | Linear

Input: Random noise ~ N(0,1)

Discriminator
Purpose: Classify real vs fake samples

Layer | Units | Activation
Dense | 128 | ReLU
Dense | 64 | ReLU
Dense | 1 | Sigmoid

Phase 4: Training Process
Generate random noise
Generator produces fake samples
Discriminator trained on real and fake samples
Generator updated to fool discriminator
Repeat for multiple epochs

Training Parameters:

Parameter | Value
Epochs | 5000
Batch Size | 64
Learning Rate | 0.0002
Optimizer | Adam

Phase 5: PDF Estimation

After training:

Generate large number of synthetic samples
Estimate PDF using:
Histogram Density Estimation
Kernel Density Estimation (KDE)
Compare real vs generated distribution

Experimental Results

The GAN successfully learns the transformed data distribution.
Generated samples closely follow the structure of the real data.
Non-parametric modeling captures complex distribution shapes that are difficult to model analytically.

Conclusion

Unlike the parametric Gaussian approach, the GAN does not assume any predefined distribution. The model learns the probability density directly from data samples, making it a powerful tool for non-parametric density estimation.
