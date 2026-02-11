Learning Probability Density Functions Using Data Only
📌 Project Title
Learning Probability Density Functions Using Data Only using GAN

📊 Dataset Description
Feature Used: NO₂ Concentration (x)
Dataset Source: Kaggle
https://www.kaggle.com/datasets/shrutibhargava94/india-air-quality-data
Dataset Type: Air Quality Monitoring Data (India)
Attribute Selected: NO₂ Concentration Levels
The dataset contains air pollution records collected from multiple monitoring stations across India. For this assignment, only the NO₂ concentration feature is used as the random variable x.

🎯 Objective
The main objective of this project is:

To learn an unknown probability density function (PDF) of a transformed random variable using only data samples and a Generative Adversarial Network (GAN), without assuming any predefined parametric distribution.

This work focuses on modeling complex data distributions directly from samples.

🧮 Mathematical Formulation
Each value of x is transformed into z using the transformation:

z
=
T
r
(
x
)
=
x
+
a
r
sin
⁡
(
b
r
x
)

Where:

a
r
=
0.5
(
r
mod
7
)

b
r
=
0.3
(
r
mod
5
+
1
)

Here,

r
=
102316099

(University Roll Number)

Transformation Parameters Used
Parameter	Value
a_r	2.0
b_r	1.5
🛠️ Methodology
The complete methodology is divided into five major phases.

Phase 1: Data Preprocessing
The Kaggle dataset is downloaded and loaded.
Missing values are removed.
Only NO₂ concentration values are extracted.
The data is normalized for stable training.
Outliers are handled to reduce noise.
This step ensures that the dataset is clean and suitable for GAN training.

Phase 2: Data Transformation
Using the given transformation equation, each value of x is converted into z.

Steps:

Calculate parameters a_r and b_r.
Apply transformation to each data point.
Store transformed values in a new dataset.
Visualize the transformed distribution.
This transformation introduces non-linearity in the data.

Phase 3: GAN Architecture Design
A Generative Adversarial Network consists of two neural networks.

Generator Network
Purpose: Generate fake samples similar to real z values.

Structure:

Layer	Type	Units	Activation
1	Dense	128	ReLU
2	Dense	64	ReLU
3	Dense	1	Linear
Input: Random noise ~ N(0,1)
Output: Generated value z_f
Discriminator Network
Purpose: Classify samples as real or fake.

Structure:

Layer	Type	Units	Activation
1	Dense	128	ReLU
2	Dense	64	ReLU
3	Dense	1	Sigmoid
Input: Real and generated z values
Output: Probability score
Phase 4: GAN Training
Training is performed using adversarial learning.

Steps:

Generate random noise.
Generate fake samples using Generator.
Train Discriminator on real samples.
Train Discriminator on fake samples.
Update Generator to fool Discriminator.
Repeat for multiple epochs.
Training Parameters:

Parameter	Value
Epochs	5000
Batch Size	64
Learning Rate	0.0002
Optimizer	Adam
Phase 5: PDF Estimation
After training:

Generator produces a large number of samples.
Generated samples are collected.
PDF is estimated using:
Histogram Density Estimation
Kernel Density Estimation (KDE)
Estimated PDF is plotted.
This approximates the unknown probability distribution.

📈 Experimental Results
Result Table
Metric	Value
Final Generator Loss	Recorded during training
Final Discriminator Loss	Recorded during training
Total Epochs	5000
Generated Sample Size	10000+
