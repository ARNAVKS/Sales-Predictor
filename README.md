# Sales-Predictor
Hey! I made this sales-predictor using matrix method for Multivariate Linear Regression.

In the given table ***advertising.csv*** there are 4 columns. We denote columns **TV** as $x_1$, **Radio** as $x_2$ and **Newspaper** as $x_3$. Column **Sales** will be our target variable which we denote as $y$.

General formula for Multivariate Linear Regression for 3 input will be,
\
$y_{pred}=\beta_{0}+\beta_{1}{x_{1}}+\beta_{2}{x_{2}}+\beta_{3}{x_{3}}$ 

where $y_{pred}$ is the predicted value of the input value $\{ x_1, x_2 \ \text{and} \ x_3 \}$ and $\beta_{0}, \beta_{1}, \beta_{2} \ \text{and} \ \beta_{3}$ are the parameter that gives you the best prediction.

We can write this genreal equation as,
\
$X\cdot\beta=y_{pred}$

In which $\beta$ is an array that contain $\beta_{0}, \beta_{1}, \beta_{2}, \beta_{3}$.
To find $\beta$ we have a formula,
\
$\beta=(X^{T}\cdot{X})^{-1}\cdot({X^{T}\cdot{y}})$

$X$ is an array that contain $x_1, x_2, x_3$ but with a 
