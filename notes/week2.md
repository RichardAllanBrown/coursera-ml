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
###Features and Polynomial Regression
 - If you have more insight into a problem, you may be able to reduce the number of features. Such as plot width and length being condensed into area
 - May want a quadratic fit over a linear one. You can do so, but it would come down again eventually, so you may jump to a cubic model to ensure it doesn't fall back down
 - Can set feature to be the square and then cube of the area to fit the model and get a cubic fit (feature scaling becomes more concerning in cubic models)
 - Can also use square roots this way
##Computing Parameters Analytically
###Normal Equasion
 - Can solve for theta in an analytical approach, so we don't need to keep iterating with gradient descent
 - Use derivitives to work out when the slope is 0
 - Create a matrix (X) m.(n+1) dimensions of all training data
 - Construct a vector (y) of m size of the results
 - Value of theta to minimize cost function is (XT.X)^-1.XTy
 - Normal equasion benefits from no need to choose a learning rate and no need to iterate
 - Gradient descent benefits from working well with large n (normals performance sinks at large n)
 - Calculating the inverse of a matrix can take time
###Normal Equasion Noninvertibility
 - XTX must be invertible to work. If it isn't this means you either have too many features (and not enough data), or redundant features
 - Prefer Octave pinv over inv as pinv will work when XTX is non invertible
##Octave Tutorial

