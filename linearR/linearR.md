# Linear Regression 

Crickets, a type of insects chirps when there is a rise of temperature.If we plot rise in temperature against the number of chirps per minute, we will find below graph.

![Cricket Chirping Plot](https://raw.githubusercontent.com/CoderFundamentals/python/master/linearR/img/CricketLine.svg)

Thus it is very easy to relate them as number of chirps per minute is associated with the rise of temperature. Now if we draw a straight line ,this can be simply respresented with the mathematical equation of 
```
    Y = mx+b
    Y is dependent variable,the temperature we are trying to predict
    m is the slope
    b is the intercept
    x is number of chirps per minute
```
 In case of machine learning this equation is simply reperesented as :
y <sup>'</sup> = w<sub>0</sub>+w <sub>1</sub>x<sub>1</sub>
y` is the label or dependent variable we are trying to predict
w <sub>0</sub> /b is the bias or y-intercept
w <sub>1</sub> is the weight or the intercept
x <sub>1</sub> is the feature or independent variable
                
Above problem statement is a simple representation of linear regression with one independent variable.However a more realistic/real time model will be dependent on more than one variable,eg:
y<sup>'</sup> = w <sub>0</sub>+ w<sub>1</sub>x<sub>1</sub>+ w<sub>2</sub>x2+w  <sub>3</sub>x<sub>3</sub>
### Training And Loss
- In supervised learning the models use already labeled examples to learn from them to predict dependent variables.This process is known as training
- The difference between the actual and prediction is called loss.A perfect model would have the loss of 0 as the prediction matches to actual

    ![Loss Plot](https://raw.githubusercontent.com/CoderFundamentals/python/master/linearR/img/LossSideBySide.png)
    
     In the above picture, plot on the left side has a greater loss in comparision to the one in the right side.The perpendicular distance between the actual value and predicted value(straight line) is bigger.
     To calculate the loss, there are several preferred approaches:
     - Squared Loss:
        -  This is the square of the loss predicted.
        - loss = (actual value - predicted value) <sup>2</sup>
        
    - Mean Squared Error:
        - It is the average squared loss of a prediction.
        - It is calculated by taking the mean of squaring the loss.
        
### Reducing Loss Function
 It is ideal to understand the direction of our model parameters that we tune to reduce the loss and optimize our model. This is called convergence of our model parameters. So in a linear regression problem if we consider the equation:
```             
            y = b + wx
    Here the predicted value y <sup>'</sup> can be calculated iteratively by supplying different values of b and x till we have minimized the loss.This iterative process can be presented as below.
```
![Iterative Approach](https://raw.githubusercontent.com/CoderFundamentals/python/master/linearR/img/GradientDescentDiagram.svg)

-   As per above diagram, ModelPrediction function takes feature(X), initial value of parameters(In the above equation it is the intercept b and weight w which are feed in), and calculates the predictions.
-   This predictions is compared against the label to compute the loss using one of already discussed loss function (Squared loss or Mean Squared Loss)
- If there is a need to reduce the loss, then we have a computeParameterUpdate function where parameters are updated and feed into the ModelPrediction function
- Once we reached an optimal value of y`, the whole iterative process is stopped and model is said to be <bold>Converged</bold>

### Gradient Descent
   In the above diagram, computeParameterUpdate function supplies the weight to the ModelPredict function.This goes on iteratively till we reach a minimum loss. Below diagram depicts the possible value of loss over an iterative values of w~0~
   ![Convex Plott](https://raw.githubusercontent.com/CoderFundamentals/python/master/linearR/img/convex.svg)
   As we can see, the convex plot always has a lowest point, and this is where loss function can be computed.However doing it iteratively over a large dataset is in efficient. Thus a much preferred approach known as 'Gradient Descent' is used. 
   In Gradient Descent algorithm, we take a random value of weight(mostly 0) and then we descent along the convex plot or loss curve by calculating the gradient of the curve which is the slope(derivative) of the curve itself. This Gradient is a vector which has a magnitude as well as a direction.
   At each iteration, we move along the direction of the gradient by factor of the magnitude.
    ![Convex Plott](https://raw.githubusercontent.com/CoderFundamentals/python/master/linearR/img/GradientDescentGradientStep.svg)
    This magnitude, is one of the hyper parameters known as learning rate or step size.The learning rate values is optimized to ensure :
- <Bold> Learning rate is not too small </Bold> to ensure we do not have an inifinite iterations
- <Bold> Learning rate is not too hight </Bold> to ensure we are not skipping or jumping  over lower minima over iteration

#### Stochastic Gradient
- Often datasets are huge and it is difficult to process such data sets as a batch for calculation of gradient descent.
- Thus it is preferred to have only one example in a batch per iteration to have  gradient calculation however with noise
- Also it is preferred to have a lesser number of exampke in a batch per iteration rather than only one example for an efficient gradient calculation without noise.