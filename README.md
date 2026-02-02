1.Objective

The goal is to model a probability density function (PDF) of transformed NO₂ air pollution data using a roll-number-based nonlinear transformation and estimate its parameters.

2.Methodology

i.Data Preparation
The NO₂ column is extracted from the dataset and missing values are removed.

ii.Nonlinear Transformation
Each value x is transformed into: 

z=x+a​sin(b​x) where 𝑎=0.05(𝑟 mod 7) and 𝑏=0.3(𝑟 mod 5+1)

This step introduces controlled distortion to the data.

iii.Parameter Estimation
The transformed data is fitted to a Gaussian-like PDF:

p^​(z)=ce^−λ(z−μ)2
	
μ = mean of z

σ² = variance of z

λ = 1 / (2σ²)

c = 1 / √(2πσ²)

3.Results

The computed parameters μ, λ, and c describe the learned PDF of the transformed variable. These values summarize the center and spread of the distribution.

4.Graph Interpretation

The histogram of z approximates the empirical probability density.
Its bell-shaped structure confirms that the transformed data follows a Gaussian-like distribution.

5.Conclusion

The experiment demonstrates nonlinear data transformation and statistical parameter estimation. The learned PDF successfully models the transformed air-quality data.
