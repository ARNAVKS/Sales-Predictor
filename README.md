# Sales-Predictor
Hey! I made this sales-predictor using matrix method for Multivariate Linear Regression.

**NOTE** : In this project we denote $x_{j}$ as the input column name where $j=1,2\ \text{and}\ 3$. Also $x_{j}^{i}$ is denoted as the data in $x_{j}$ column where $i=1,2,3,.......,200$.
##

In the given table ***advertising.csv*** there are 4 columns. We denote columns **TV** as $x_1$, **Radio** as $x_2$ and **Newspaper** as $x_3$. Column **Sales** will be our target variable which we denote as $y$.

General formula for Multivariate Linear Regression for 3 inputs will be,
\
$y_{pred}=\beta_{0}+\beta_{1}{x_{1}}+\beta_{2}{x_{2}}+\beta_{3}{x_{3}}$ 

where $y_{pred}$ is the predicted value of the input value $\{ x_1, x_2 \ \text{and} \ x_3 \}$ and $\beta_{0}, \beta_{1}, \beta_{2} \ \text{and} \ \beta_{3}$ are the parameter that gives you the best prediction.
##

We can write this generel equation as,
\
$y_{pred}=X\cdot\beta$

$X$ is an array that contain $x_1, x_2, x_3$ but with a extra constant 1 in each row. As the given table has total 200 data, so that array $X$ will be a shape of $(200\text{x}4)$ and the array will look like this,

$$X=\begin{bmatrix}
     1 & x_{1}^{1} & x_{2}^{1} & x_{3}^{1} \\
     1 & x_{1}^{2} & x_{2}^{2} & x_{3}^{2} \\
     : & : & : & : \\
     : & : & : & : \\
     1 & x_{1}^{200} & x_{2}^{200} & x_{3}^{200} \\
     \end{bmatrix}_{200\text{x}4}$$
  
where, $i=1,2,3,......,200$.
So that $\beta_0$ would be without any variable after the dot product between $X$ and $\beta$ as per the general formula.

$X^{T}$ will be denoted as the transpose of $X$.

Target data $y$ array will be like $y^{i}$ where $i=1,2,3,......,200$.

$$y=\begin{bmatrix}
     y^{1} \\
     y^{2} \\
     : \\
     : \\
     y^{200}
     \end{bmatrix}_{200\text{x}1}$$

In which $\beta$ is an array that contain $\beta_{0}, \beta_{1}, \beta_{2}, \beta_{3}$.
To find $\beta$ we have a formula,
\
$\beta=(X^{T}\cdot{X})^{-1}\cdot({X^{T}\cdot{y}})$

The $\beta$ array will be like this,

$$\beta=\begin{bmatrix}
    \beta_0  \\
    \beta_1  \\
    \beta_2  \\
    \beta_3
  \end{bmatrix}_{4\text{x}1}$$
##

As per the formula $y_{pred}=X\cdot\beta$,

$$y_{pred}=\begin{bmatrix}
     1 & x_{1}^{1} & x_{2}^{1} & x_{3}^{1} \\
     1 & x_{1}^{2} & x_{2}^{2} & x_{3}^{2} \\
     : & : & : & : \\
     : & : & : & : \\
     1 & x_{1}^{200} & x_{2}^{200} & x_{3}^{200} \\
     \end{bmatrix} \cdot \begin{bmatrix}
                                      \beta_0  \\
                                      \beta_1  \\
                                      \beta_2  \\
                                      \beta_3
                                      \end{bmatrix}$$

After dot product it will look like this,

$$y_{pred}=\begin{bmatrix}
     \beta_{0}+{\beta_{1}}x_{1}^{1}+{\beta_{2}}x_{2}^{1}+{\beta_{3}}x_{3}^{1} \\
     \beta_{0}+{\beta_{1}}x_{1}^{2}+{\beta_{2}}x_{2}^{2}+{\beta_{3}}x_{3}^{2} \\
     :  \\
     :  \\
     \beta_{0}+{\beta_{1}}x_{1}^{200}+{\beta_{2}}x_{2}^{200}+{\beta_{3}}x_{3}^{200} \\
     \end{bmatrix}_{200\text{x}1}$$

We can write the $y_{pred}$ array also as,

$$ y_{pred}=\begin{bmatrix}
        y_{pred}^{1} \\
        y_{pred}^{2} \\
           : \\
        : \\
        y_{pred}^{200} \\
        \end{bmatrix}_{200\text{x}1}$$

This above $y_{pred}$ array has all the predicted value of all the the data $x_{1}$, $x_{2}$ and $x_{3}$.

To find the prediction with random $x_{1}, x_{2}\ \text{and} \ x_{3}$, which is inputted by the user,

$$\text{prediction}=\begin{bmatrix} 1 & x_{1} & x_{2} & x_{3} \end{bmatrix} \cdot \begin{bmatrix}
                                      \beta_0  \\
                                      \beta_1  \\
                                      \beta_2  \\
                                      \beta_3
                                      \end{bmatrix}$$

from above equation we will get a $(1\text{x}1)$ shape $\text{prediction}$ array with a prediction in it.     
##
