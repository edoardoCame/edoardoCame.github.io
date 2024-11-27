
---
title: MLE Estimation in Python
layout: default
nav_order: 3
---


# Index

1. [Introduction](#introduction)
2. [Imports](#imports)
3. [Binomial Distribution Parameters](#binomial-distribution-parameters)
4. [Explanation of Binary Sample Generation](#explanation-of-binary-sample-generation)
5. [Calculate Likelihood](#calculate-likelihood)
6. [Plot Likelihood](#plot-likelihood)


## Introduction
This notebook demonstrates the process of generating a binary sample from a binomial distribution, calculating the likelihood for different values of the probability of success, and plotting the likelihood.


## Imports
The necessary libraries for this analysis are imported.


```python
import numpy as np
import matplotlib.pyplot as plt
import math
from scipy.special import comb
```

## Binomial Distribution Parameters
The parameters for the binomial distribution are defined, and a binary sample is generated.


```python
# Parameters for the binomial distribution
p = 0.4  # probability of success
n = 10  # number of trials

binary_sample = np.random.binomial(1, p, n)
print(binary_sample)
k= sum(binary_sample)
print(k)
```

    [0 1 0 1 1 0 0 1 0 0]
    4


## Explanation of Binary Sample Generation
An explanation of how the binary sample is generated and the significance of the variables used.

In this code, the parameters for the binomial distribution are defined with p = 0.4 representing the probability of success in each trial, and n = 10 representing the number of trials. The np.random.binomial function from the NumPy library is used to generate a sample of size n from a binomial distribution with the specified probability p. The function call np.random.binomial(1, p, n) generates an array of n binary values (0s and 1s), where each value represents the outcome of a single trial (0 for failure and 1 for success).

The generated sample is stored in the variable binary_sample, and the print function is used to output this sample to the console. The sum function is then used to calculate the total number of successes in the sample by summing the values in binary_sample. Since the array consists of binary values, the sum directly gives the count of successes. This count is stored in the variable k.



## Calculate Likelihood
The likelihood for different values of the probability of success is calculated.


```python
p_hat = np.linspace(0, 1, 1000) #create an array of 1000 values between 0 and 1
likelihood_for_given_p = np.zeros(1000) #create an array of 1000 zeros for the likelihood values
for i in range(1000): #for each value of p_hat
    likelihood_for_given_p[i] = comb(n,k) * (p_hat[i]**k) * ((1-p_hat[i])**(n-k)) #calculate the likelihood for that value of p_hat
```

The goal is to estimate the probability parameter ( p ) that maximizes the likelihood of observing the given data.

First, the code uses np.linspace(0, 1, 1000) to create an array p_hat of 1000 evenly spaced values between 0 and 1. This array represents the different possible values of the probability parameter ( p ) that we want to evaluate.

Next, an array likelihood_for_given_p of 1000 zeros is created using np.zeros(1000). This array will store the likelihood values corresponding to each value in p_hat.

The code then iterates over each value in p_hat using a for loop. For each value of ( p ) (denoted as p_hat[i]), it calculates the likelihood of observing the given data using the binomial likelihood formula. The formula used is comb(n, k) * (p_hat[i]** k) * ((1-p_hat[i])** (n-k)), where comb(n, k) calculates the binomial coefficient (the number of ways to choose ( k ) successes out of ( n ) trials), p_hat[i]** k represents the probability of ( k ) successes, and ((1-p_hat[i])**(n-k)) represents the probability of ( n-k ) failures.

By the end of the loop, likelihood_for_given_p contains the likelihood values for each possible value of ( p ) in p_hat. This allows us to identify the value of ( p ) that maximizes the likelihood, which is the MLE for the probability parameter of the binomial distribution.

## Plot Likelihood
The likelihood values are plotted against the probability of success.


```python
plt.plot(p_hat, likelihood_for_given_p)
plt.xlabel('p_hat')
plt.ylabel('Likelihood')
plt.title('Likelihood for different values of p_hat')
plt.show()
```


    
![png](MLE%20estimation%20in%20Python_files/MLE%20estimation%20in%20Python_12_0.png)
    

