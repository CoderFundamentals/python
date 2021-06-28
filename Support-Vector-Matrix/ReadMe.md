## SVM

### Vector
- Vectors can be thought of as list of things, and in multivariable calculus it can be numbers mostly.
- So when we think of numbers, then it can be represented with a magnitude and direction and can be considered as points in space
 
  ![Vector](https://raw.githubusercontent.com/CoderFundamentals/python/master/Support-Vector-Matrix/img/Vector.png)
-Vectors also support basic operations such as addition, scalar multiplication. A
lso the general question of how long a vector is, is represented as Magnitude of the vector. The magnitude is calculated by using the Pythagoras formulae of distance.
![Vector](https://raw.githubusercontent.com/CoderFundamentals/python/master/Support-Vector-Matrix/img/Vector-Magnitude.png)

#### Dot Product
- The Dot Product tells how much two vectors point in the same direction.
- The Dot Product of two vectors a, b is computed as cosine of the magnitude of a and b.	
	-	$\vec{a}$ . $\vec{b}$  =  a.b $\cos( \theta$)
	-	When Both a, b are in same direction then the dot product is at its largest , as $\theta$ is 0 degree
	![Vector](https://raw.githubusercontent.com/CoderFundamentals/python/master/Support-Vector-Matrix/img/Vector-dot.png)
- However it is also represented in a simplified manner:
	-  If  $\vec{a}$ = ( a$_1$, a$_2$, a$_3$) and $\vec{b}$ = (b$_1$,b$_2$,b$_3$)
	-  $\vec{a}$ . $\vec{b}$ = a$_1$.b$_1$+a$_2$b$_2$+a$_3$b$_3$
### Support Vector Machine
- The idea of a support vector machine is to classify the data into two different class.
- Given a dataset, SVM tries to find a straight line which is at a maximum possible distance from the data points of two classes.
- However it is possible that betweeen two classes, it is possible to have infinite separators inbetweeen.
![SVM](https://raw.githubusercontent.com/CoderFundamentals/python/master/Support-Vector-Matrix/img/SVM-classification.png)
- In the above diagram, the classifications can be separated by multiple line.SVM tries to find a line that is a generalized line and is not a biased one.Thus it tries to find a line which is of equal distance from both the classification.
- According to SVM, in each classification it tries to find data points which are nearest to the line.These data points are called <Bold>Support Vectors</Bold>.The algorithm tries to maximise the distance called as margin.
![svm](https://raw.githubusercontent.com/CoderFundamentals/python/master/Support-Vector-Matrix/img/svm.png)
- However it is always not possible to have data which can be classfied that easily.
![SVM](https://raw.githubusercontent.com/CoderFundamentals/python/master/Support-Vector-Matrix/img/SVM-NonLinearData.png)
- For eg: In the above diagram, the data is not linearly separable by a straight line.In that case, we plot them in the higher dimensions to ensure that data is linearly separable.This is called Kernel function, which is responsible for transforming the data so that they can be linearly separable in a higher dimenion.
#### Tuning Parameters:
1. C:
    - C value decides how the decision boundary must be plotted to classify the data. Given a large value of C, the algorithm tries to fit the data into two classifications with maximum accuracy. However this also results in overfitting of data and may not be always required.
    ![SVM](https://raw.githubusercontent.com/CoderFundamentals/python/master/Support-Vector-Matrix/img/SVM-Reg.png)
2. Gamma:
    - It defines how far each single training example influences the SVM. 
    - If Gamma value is higher, then the decision boundary is mostly reliant upon the points that are closer than that are far from it.
    - If Gamma is low, then the decision boundary also takes far off points into consideration as well.
     ![SVM](https://raw.githubusercontent.com/CoderFundamentals/python/master/Support-Vector-Matrix/img/SVM-Gamma.png)