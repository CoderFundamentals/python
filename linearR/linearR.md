# Linear Regression 

Crickets, a type of insects chirps when there is a rise of temperature.If we plot rise in temperature against the number of chirps per minute, we will find below graph.

![Cricket Chirping Plot](https://raw.githubusercontent.com/CoderFundamentals/python/master/linearR/img/CricketLine.svg)

Thus it is very easy to relate them as number of chirps per minute is associated with the rise of temperature. Now if we draw a straight line ,this can be simply respresented with the mathematical equation of 
````````````````````````````````````````````````````
                                    Y = mx+b
                                    Y is dependent variable,the temperature we are trying to predict
                                    m is the slope
                                    b is the intercept
                                    x is number of chirps per minute
````````````````````````````````````````````````````
In case of machine learning this equation is simply reperesented as :
`````````````````````````````````````````````````````````````````````
                                    y` = w0 + w1x1
                                    y` is the label or dependent variable we are trying to predict
                                    w0/b is the bias or y-intercept
                                    w1 is the weight or the intercept
                                    x1 is the feature or independent variable
                
``````````````````````````````````````````````````````````````````````