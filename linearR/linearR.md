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
```
                                    y` = w0 + w1x1
                                    y` is the label or dependent variable we are trying to predict
                                    w0/b is the bias or y-intercept
                                    w1 is the weight or the intercept
                                    x1 is the feature or independent variable
                
```
Above problem statement is a simple representation of linear regression with one independent variable.However a more realistic/real time model will be dependent on more than one variable,eg:
```
                               y`  = w0 + w1x1 + w2x2 + w3x3
```
### Training And Loss
- In supervised learning the models use already labeled examples to learn from them to predict dependent variables.This process is known as training
- The difference between the actual and prediction is called loss.A perfect model would have the loss of 0 as the prediction matches to actual

    ![Loss Plot](https://raw.githubusercontent.com/CoderFundamentals/python/master/linearR/img/LossSideBySide.png)
    
     In the above picture, plot on the left side has a greater loss in comparision to the one in the right side.The perpendicular distance between the actual value and predicted value(straight line) is bigger.
     To calculate the loss, there are several preferred approaches:
     - Squared Loss:
        -  This is the square of the loss predicted.
        - loss = (actual value - predicted value)<sup>2</sup>
        
    - Mean Squared Error:
        - It is the average squared loss of a prediction.
        - It is calculated by taking the mean of squaring the loss.
        
### Reducing Loss Function
 It is ideal to understand the direction of our model parameters that we tune to reduce the loss and optimize our model. This is called convergence of our model parameters. So in a linear regression problem if we consider the equation:
```             
                                            y = b + wx
    Here the predicted value y` can be calculated iteratively by supplying different values of b and x y till we have minimized the loss.This iterative process can be presented as below.
```
![Iterative Approach](https://raw.githubusercontent.com/CoderFundamentals/python/master/linearR/img/GradientDescentDiagram.svg)

-   As per above diagram, ModelPrediction function takes feature(X), initial value of parameters(In the above equation it is the intercept b and weight w which are feed in), and calculates the predictions.
-   This predictions is compared against the label to compute the loss using one of already discussed loss function (Squared loss or Mean Squared Loss)
- If there is a need to reduce the loss, then we have a computeParameterUpdate function where parameters are updated and feed into the ModelPrediction function
- Once we reached an optimal value of y`, the whole iterative process is stopped and model is said to be <bold>Converged</bold>

