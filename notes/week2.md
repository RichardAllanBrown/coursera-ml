#Week 2
##Multivariate Linear Regresion
###Multiple Feaures
 - Beyond simple linear regression, having many variables.
 - e.g. House prices derived from size, bedrooms, floors and age. 4 features.
 - h theta(x) = theta(0)x(0) + theta(1)x(1) + ... + theta(n)x(n)
 - This is equal to theta transposed x
###Gradient Descent for Multiple Variables
 - Cost function J(theta(0), theta(1),...,theta(n)) or J(theta) as a vector.
 - More generalised form gradient descent
###Gradient Descent in Practice
####Feature Scaling & Mean Normalization
 - Aim is to make all features to be on a similar scale
 - Our home prediction example, number of bedrooms is limited, but size in square feet can be quite large.
 - Gradient descent takes longer and harder when each feature scales differently
 - So we scale them all of them to be within -1 <= x <= 1, this makes gradient descent take a shorter, simpler path to the global min
 - Slightly outside isn't too much of a problem, say -2 <= x <= 0.4 is fine, but -150 <= x <= 200 isn't
 - Rule of 3. -3 to 3 is max, and -0.3 to 0.3 is min
 - Feature scaling is changing x(i) to (x(i)/range(x(i))
 - Mean normalization is also an acceptable approach that changes x(i) to (x(i) - avg(x(i)))/range(x(i)), so mean is near 0
####Learning Rate
 - Ensure that the J(theta) is decreasing over iterations (when working well, it decreased every iteration)
 - Auto convergence test may be used to stop processing if decrease is less than say 10e-3, but this exact value is hard to specify in advance
 - If J(theta) is increasing over iterations, the learning rate is probably too high
 - If J(theta) swerves between high and low values, then the rate is also too high

