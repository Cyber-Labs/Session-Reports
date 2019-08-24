# **PRML Notes**(Pages 1 to 28)

05 AUGUST 2019 / 6:30 PM - 8:00 PM / CYBER-LABS CONFERENCE ROOM

## **Attendees**

### ML Team

# **Agenda**

### Reading  pages 1 to 28 of the book Pattern Recognition and Machine Learning 

# **Notes**

## **Introduction**

* The result of running the machine learning algorithm can be expressed as a function y(x) and the precise form of the function y(x) is determined during the training phase.

* The ability to categorize correctly new examples that differ from those used for training is known as generalization.

* Preprocessing is done to transform the original input variables into some new space of variables where, it is hoped, the pattern recognition problem will be easier to solve.(feature extraction stage).

* Applications in which the training data comprises examples of the input vectors along with their corresponding target vectors are known as supervised learning problems.

  * Classification

  * Regression
  
* Input vectors x without any corresponding target values are unsupervised learning problems.

  * Clustering(Discovering groups of similar examples within the data) 
  
  * Density estimation(Determining the distribution of data within the input space)
  
  * To project the data from a high-dimensional space down to two or three dimensions for the purpose of visualization.

* Reinforcement learning (concerned with the problem of finding suitable actions to take in a given situation in order to maximize a reward.)
  
  * Credit assignment problem
  
  * Exploration vs Exploitation trade-off(Useful link: Exploration vs. Exploitation - Denny Britz - Medium)
 

## **Polynomial Curve Fitting**

* Our goal is to exploit this training set in order to make predictions of the value t of the target variable for some new value x of the input variable.
  
  * y(x, w) = w0 + w1x + w2x2 + ... + wMxM = M j=0 wjxj(linear model)

* Error function that measures the misfit between the function y(x, w), for any given value of w
  
  * E(w) = 1 /2 *summation(1 to N) {y(xn, w) − tn} ^2
  
* (M = 0)(M being the degree) and first order (M = 1) polynomials give rather poor fits to the data and consequently rather poor representations of the function(function being sin(2*pi*x)). The third order (M = 3) polynomial seems to give the best fit to the function of the examples shown in Figure 1.4. When we go to a much higher order polynomial (M = 9) then the model over fits.

* For a given model complexity, the overfitting problem become less severe as the size of the data set increases

* By adopting a Bayesian approach, the overfitting problem can be avoided. In a Bayesian model the effective number of parameters adapts automatically to the size of the data set.

* To control the over-fitting phenomenon regularization is introduced.
  
  * E(w) = 1 /2* summation(1 to N) {y(xn, w) − tn} ^2 + λ /2*|| w||^2
  
  * Weight Decay
  
* Shrinkage method to reduce the value of the coefficients.
  
## **Probability Theory**([Basic Probability Theory and Statistics - Towards Data Science](https://towardsdatascience.com/basic-probability-theory-and-statistics-3105ab637213))

* Probability theory provides a consistent framework for the quantification and manipulation of uncertainty and forms one of the central foundations for pattern recognition

* Posterior probability: The statistical probability that a hypothesis is true calculated in the light of relevant observations.

* The Rules of Probability
  
  * sum rule p(X) = summation(over Y)(p(X, Y ))
  
  * product rule p(X, Y ) = p(Y |X)p(X).

*  Combined with decision theory, it allows us to make optimal predictions.

* Probability

   * Joint Probability: The probability that X will take the value xi and Y will take the value yj is written p(X = xi, Y = yj ) and is called the joint probability of X = xi and Y = yj .

   
   * p(X = xi) is sometimes called the marginal probability, because it is obtained by marginalizing, or summing out, the other variables 
   
   * p(Y = yj |X = xi) is called the conditional probability of Y = yj given X = xi
   
   * Bayes’ theorem: p(Y |X) = (p(X|Y )*p(Y ))/ p(X)
   
   * Posterior Probability:  the statistical probability that a hypothesis is true calculated in the light of relevant observations.

* If the joint distribution of two variables factorizes into the product of the marginals, so that p(X, Y ) = p(X)p(Y ), then X and Y are said to be independent. 


* Probabilities in terms of the frequencies of random, repeatable events is referred to as the classical or frequentist interpretation of probability.
## **Probability Density**([The idea of a probability density function - Math Insight](https://mathinsight.org/probability_density_function_idea))

* If the probability of a real-valued variable x falling in the interval (x, x + δx) is given by p(x)δx for δx → 0, then p(x) is called the probability density over x

* The probability that x will lie in an interval (a, b) is then given by: p(x ∈ (a, b)) =  Integration(a->b) p(x) dx.

* The probability that x lies in the interval (−∞, z) is given by the cumulative distribution function defined by P(z) = Integration(-infinity to z) p(x) dx
Multivariate probability density must satisfy:

    * p(x) >= 0 

    * Integration( p(x) dx) = 1

## **Expectations and Covariances**([A Gentle Introduction to Expected Value, Variance, and Covariance](https://machinelearningmastery.com/introduction-to-expected-value-variance-and-covariance/))

* The average value of some function f(x) under a probability distribution p(x) is called the expectation of f(x) and will be denoted by E[f].
    
    * E[f] = Summation(x p(x)f(x))  (For discrete function)
    
    * E[f] = Integration(x p(x)f(x))  (For continuous function)
    
    * Conditional expectation(conditional distribution):
       
        * Ex[f|y] =Summation( x p(x|y)f(x))

* The variance of f(x) is defined by var[f] = E [ (f(x) − E[f(x)]^2)]

* For N of points drawn from the probability distribution or probability density, then the expectation can be approximated as a finite sum over these points.

* In the case of two vectors of random variables x and y, the covariance is a matrix.

    * cov[x, y] = Ex,y[xyT] − E[x]E[yT].

## **Bayesian probabilities**([Bayesian Statistics Explained in Simple English For Beginners](https://www.analyticsvidhya.com/blog/2016/06/bayesian-statistics-beginners-simple-english/))


* Here, probabilities provide a quantification of uncertainty.

* In Bayesian probability we try to quantify our expression of uncertainty and make precise revisions of uncertainty in the light of new evidence, as well as subsequently be able to take optimal actions or decisions as a consequence. This can all be achieved through the elegant, and very general, Bayesian interpretation of probability.

* we would like to address and quantify the uncertainty that surrounds the appropriate choice for the model parameters w.

* From a Bayesian perspective, we can use the machinery of probability theory to describe the uncertainty in model parameters such as w, or indeed in the choice of model itself.

* Bayes’ theorem, which takes the form p(w|D) = p(D|w)p(w)/ p(D) then allows us to evaluate the uncertainty in w after we have observed D in the form of the posterior probability p(w|D).p(D|w)is called the likelihood function(expresses how probable the observed data set is for different settings of the parameter vector w.).

## **Gaussian distribution**([Gaussian Distribution - Hyperphysics](http://hyperphysics.phy-astr.gsu.edu/hbase/Math/gaufcn.html))

* Probability distributions for continuous variables.

* Data points that are drawn independently from the same distribution are said to be independent and identically distributed(iid).

# **Next Meeting Agenda**

Next 30 pages.
 
