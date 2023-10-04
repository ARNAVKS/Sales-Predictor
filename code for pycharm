#using matrix linear regression method for this multivariate data

#importing the required libraries
import numpy as np
import pandas as pd
import streamlit as st

#setting the title
st.title("Sales Predictor")

#loading the data
adv = pd.read_csv("advertising.csv")

#breaking the data into two array X and y
#but in X we are adding another line of in the array X of 1 because according to the formula there will be a beta parameter without any input value 
X = np.zeros(800)
X = X.reshape(200,4)
for i in range(0,200):
  X[i,0] = 1
  X[i,1] = adv['TV'][i]
  X[i,2] = adv['Radio'][i]
  X[i,3] = adv['Newspaper'][i]
y = np.zeros(200)
y = y.reshape(200,1)
for i in range(0,200):
  y[i] = adv['Sales'][i]

#making transpose of X
Xt = np.transpose(X)

#using beta=(Xt.X)^(-1).(Xt.y) for finding the beta array of (4,1)
#beta will be the parameter that is best parameter among all parameter for giving a best prediction
into = np.matmul(Xt,X)
into_inv = np.linalg.inv(into)
cx = np.matmul(Xt,y)
Beta = np.matmul(into_inv,cx)

#for finding the predicted value we will do dot product between X(input values) with Beta

#writing code for taking the three input
tv = st.number_input("Enter the TV price :")
rad = st.number_input("Enter the radio price :")
news = st.number_input("Enter the newspaper price :")

# making an array of (1,4) of input data above with additional value 1 in that array, it will look like this : [1 , tv, rad, news]
zero = np.zeros(4)
zero = zero.reshape(1,4)
zero[0,0] = 1
zero[0,1] = tv
zero[0,2] = rad
zero[0,3] = news

#finding prediction (input_data_array).(parameter_beta_array)=prediction_array
#we will get output array of (1,1), so we will print the [0,0] to print the actual predicted values
prediction = np.matmul(zero, Beta)
st.write("**Sales :**",prediction[0,0])
