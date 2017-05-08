#Week 1
##Introduction
###Welcome
 - Learning algorithms used everywhere, Google, Facebook et al.
 - Long way to strong AI, but ML is a step on the path
 - Big in data mining, unprogrammable problems, customizations, real AI
 - Highly sought after skillset

###What is ML
 - Giving compiters ability to learn without explicit programming
 - Checkers playing program that played better than the programmer (Arthur Samuel)
 - "A computer program is said to learn from experience E with respect to some class of tasks T and performance measure P, if its performance at tasks in T, as measured by P, improves with experience E." - Tom Mitchell
 - Can classify broadly as Supervised or Unsupervised (Reinforcement and Recommenders are less common)

###Supervised Learning
 - Always have a data set of inputs (features) and correct outputs
 - Can be classed as either regression (continuous output e.g. number of sales) or classification type problems (hacked or not)
 - Using an example of predicting house prices against the area of it.
   - Right answers (i.e. training data) provided
   - Straight or quadratic fit
   - Continuous function makes it a regression problem
 - Breast Cancer example (size vs. malignancy)
   - Taking data of tumor size vs. malignancy
   - Outputs a discrete value of 0 (no cancer) or 1 (cancer)
   - Example of a classification problem
   - Might have more inputs (features), such as tumor size and age
   - Infinite number of features would help to make a more accurate model (and it is possible!)
 - Other regression example might be how much of a product you could sell over 3 months
 - Other classification example, deciding for each customer account if it has been hacked or not
 
###Unsupervised Learning
 - When we have no idea what results may look like
 - e.g. Group millions of genes into groups that correcate to lifespan, location etc.
 - Say, group news articles into categories on the same story
 - Take customer data and find market segments
 - When we don't have answers, we are unsupervised
 - Clustering algorithms that attempt to segment a data set
 - Social net analysis, market segmentation, astronomy
 - (Cocktail party)[https://en.wikipedia.org/wiki/Cocktail_party_effect] algorithm
   - 2 microphones recording 2 speakers
   - Can split the voices into 2 seperate recordings!
   - Applications - remove music from background noise
 - Octave is foss useful for dealing with ML (provides a higher level interface)
 - Usually prototype in Octave to get something good, then move over to java/C to program production code

##Model and Cost Function
###Model Representation
 - Linear regression is one type of model
 - A training set of hous eprices may have area (x) and price (y). (x,y) being a single example, (x^(i), y^(i)) being the (i)th pair of set
 - Set goes through an algorithm that crate a hypothesis (h). Hopefully y = h(x), if the model works. (written in a more formal manner)
 - Linear regression with one variable aka Univariate linear regression

 ###Cost Function
 - Used to calculate best line to fit the data
 - Our linear model of (a+bx) will be different lines for different values of a and b (theta 0 and theta 1)
 - One cost could be to minimize the sum of error squared (h(x) - y)^2
 - J(a, b) is the cost function, we aim to minimize this
 - More parameters into J, the more dimensionality your cost function plot can get. i.e. height is J(a, b), a and b in other 2 axes.
 - A linear model of (a+bx) typically gives a bowl shape, with a minimum point being the bottom of the bowl (and multiple combinations of a and b can make the same cost)
 - Ideally we want to have a machine automatically tune the values of a and b to find the minimum cost.
 
##Parameter Learning
###Gradient Descent
 - Attempts to minimize cost function for n number of parameters into J
 - Starts at a random point, evaluates the derivative (or partials for multi params) and then updates all thetas to move in the steepest direction
 - Dependant on where that first point is
 - Uses a learning rate (alpha) to control how much it moves per iteration
###Gradient Descent Intuitions
 - Setting alpha to small, it takes too long to get to the answer, too big and you can overshoot / diverge
 - Problems arise with local minimums, where you are stuck in the valley and cannot move out of it easily
 - With a fixed alpha, as we approach the minimum, the steps taken get smaller as the gradient decreases
###Gradient Descent for Linear Regression
 - Computing partial derivatives requires some complex calculus to do (but we can skip this)
 - In gradient descent we always get a convex function (i.e. there is always a minimum point and no local optima, so gradient descent always converges to the best answer)
 - "Batch" gradient descent where we use all the training data for each step (you can sample as other ways)
 - You can use another approach to solve, but this approach works less well with large datasets
##Linear Algebra Review
###Matrices and Vectors
 - Matrix is basically a 2d array
 - Described as Rows x Columns (4x2 has 4 rows and 2 columns)
 - Refer to an entry in the matrix as ij subscript. So matrix A can have element A(sub ij)
 - Vector is a matrix with 1 column. (nx1)
 - May be 0 or 1 indexed (usually 1)
###Addition and Scalar Multiplication
 - Adding 2 matrices that are the same dimension is easy. Add each position (ij) at a time to create a new matrix
 - Scalar multiplication is simple too. This is when the entire matrix is multiplied by a single number. Multiply all elements. to create a new matrix
 - Operators have same precidence as usually
###Matrix Vector Multiplication
 - With a matrix of ixj, and a vector of m, the result will be a vector of i
 - j must equal m. Otherwise it doesn't work.
 - First element is first row of matrix, multiplied by coresponding element in vector all added together
 - Second element is the second row of matrix, multiplied by corresponding element in vector, added together. etc.
###Matrix Matrix Multiplication
 - Similar idea to Matrix Vector. Split the second matrix into seperate columns and matrix vector multiply. Then take the results to construct a new matrix.
 - a axb matrix multiplies by a ixj matrix (where b=i) will have a axj matrix as the answer
 - Computers with multiple cores can perform matrix operations quickly. This ties in to why frameworks like TensorFlow can use lots of cores effectivly. Matricies everywhere.
