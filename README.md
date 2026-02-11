### Assignment 1

Learning Probability Density Function Using Parametric Modeling (MLE)

### Dataset Description

Feature Used: NO₂ Concentration (x)

Dataset Source: Kaggle
https://www.kaggle.com/datasets/shrutibhargava94/india-air-quality-data

Dataset Type: Air Quality Monitoring Data (India)

Attribute Selected: NO₂ Concentration Levels

The dataset contains air pollution measurements collected from monitoring stations across India. For this assignment, only the NO₂ concentration feature is treated as the random variable 
𝑥.

### Objective

To model the probability density function (PDF) of a transformed random variable using a parametric Gaussian model, where parameters are estimated using Maximum Likelihood Estimation (MLE).

Mathematical Formulation

Each value of 𝑥 is transformed into :

z = x + a_r \sin(b_r x)

Where:

a_r = 0.5 (r \mod 7)

b_r = 0.3 (r \mod 5 + 1)​

Roll number:
𝑟=102316009

> ### Transformation Parameters Used
> 
> | Parameter | Value |
> |-----------|--------|
> | a_r | 1.5 |
> | b_r | 1.5 |

### Methodology
Phase 1 — Data Preprocessing

Dataset loaded
Missing values removed
NO₂ feature extracted
Data cleaned

Phase 2 — Data Transformation

Compute parameters 
a_r,b_r
Apply nonlinear transformation
Inspect transformed distribution

Phase 3 — Parameter Estimation

Assume Gaussian PDF
[\hat{p}(z) = c e^{-\lambda (z - \mu)^2}]

MLE estimates:
μ → Mean
σ² → Variance
λ = 1/(2σ²)
c = 1/√(2πσ²)

Phase 4 — Visualization

Histogram plotted
Gaussian PDF overlaid

### Results

Transformed data shows bell-shaped behavior

Gaussian model approximates density well

Parameters are stable and interpretable

### Conclusion (Assignment 1)

The nonlinear transformation preserves statistical structure. A Gaussian parametric model successfully captures the transformed distribution using MLE.

### Assignment 2

Learning Probability Density Functions Using Data Only (GAN-Based Approach)

### Objective

To learn the probability density of a transformed variable without assuming any parametric distribution, using a Generative Adversarial Network trained purely from data samples.

Mathematical Formulation

Each value of 𝑥 is transformed into :

z = x + a_r \sin(b_r x)

Where:

a_r = 0.5 (r \mod 7)

b_r = 0.3 (r \mod 5 + 1)​

Roll number:
𝑟=102316009

### Methodology
Phase 1 — Data Preprocessing

Dataset loaded
Missing values removed
NO₂ feature extracted
Data cleaned

Phase 2 — Data Transformation

Compute parameters 
a_r,b_r
Apply nonlinear transformation
Inspect transformed distribution

Phase 3 — GAN Architecture

Generator
Dense(128) → ReLU
Dense(64) → ReLU
Dense(1) → Linear
Input: noise ~ N(0,1)

Discriminator
Dense(128) → ReLU
Dense(64) → ReLU
Dense(1) → Sigmoid

Phase 4 — Training

Generate noise
Create fake samples
Train discriminator
Update generator
Repeat for many epochs
> ### Training settings
> 
> | Parameter | Value |
> |----------|------|
> | Epochs | 5000 |
> | Batch Size | 64 |
> | Learning Rate | 0.0002 |
> | Optimizer | Adam |

Phase 5 — PDF Estimation

Generate large synthetic sample set
Estimate density using histogram + KDE
Compare real vs generated distributions

### Experimental Results

GAN learns distribution structure
Generated samples match real data
Complex shapes captured
No Gaussian assumption required

### Conclusion (Assignment 2)

GAN-based modeling learns the probability density directly from samples. This non-parametric approach is powerful for representing unknown and complex distributions.
