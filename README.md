# Implementation-of-Simple-Linear-Regression-Model-for-Predicting-the-Marks-Scored

## AIM:
To write a program to predict the marks scored by a student using the simple linear regression model.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
1.Import the standard Libraries.

2.Set variables for assigning dataset values. 

3.Import linear regression from sklearn. 

4.Assign the points for representing in the graph.

5.Predict the regression for marks by using the representation of the graph. 

6.Compare the graphs and hence we obtained the linear regression for the given datas.

## Program:
```
Program to implement the simple linear regression model for predicting the marks scored.
Developed by: MUGIL RAJ S A
RegisterNumber: 212223220062
```
Obtaining x and y value from csv file
```
df=pd.read_csv(r"student_scores.csv")
print(df.head())
print(df.tail())
x=df.iloc[:,:-1].values
y=df.iloc[:,1].values
print("x values:",x)
print("y values:",y)
```
Spliting dataset for testing and training
```
from sklearn.model_selection import train_test_split
x_train,x_test,y_train,y_test=train_test_split(x,y,test_size=1/3,random_state=0)
```
Training the model by linear regression
```
from sklearn.linear_model import LinearRegression
regressor=LinearRegression()
regressor.fit(x_train,y_train)

y_pred=regressor.predict(x_test)

print("Y Prediction:",y_pred)
print("Actual Value:",y_test)
plt.scatter(x_train,y_train,color="black")
plt.plot(x_train,regressor.predict(x_train),color="brown")
plt.title("Hours vs Score (Training Set)")
plt.xlabel("Hours")
plt.ylabel("Scores")
plt.show()

plt.scatter(x_test,y_test,color="red")
plt.plot(x_test,regressor.predict(x_test),color="blue")
plt.title("House vs Score (Test Set)")
plt.xlabel("Hours")
plt.ylabel("Scores")
plt.show()
```
Measuring the error percentage for the model
```
mse=mean_squared_error(y_test,y_pred)
print("MSE =",mse)
mae=mean_absolute_error(y_test,y_pred)
print("MAE =",mae)
rmse=np.sqrt(mse)
print("RMSE =",rmse)
```
## Output:

Head and tail values

![Screenshot 2025-03-06 142136](https://github.com/user-attachments/assets/19ea8c5b-b38b-48ab-8da2-568354334040)

X and Y values

![Screenshot 2025-03-06 142158](https://github.com/user-attachments/assets/abdbe3ae-a4c1-42ae-b04e-f967e3c3aa2a)


Prediction values

![Screenshot 2025-03-06 142220](https://github.com/user-attachments/assets/e652f75a-13c8-4b29-992b-73cfdd664683)


mse,mae,mrse

![Screenshot 2025-03-06 142313](https://github.com/user-attachments/assets/b414be52-4b8d-4598-b2fa-98de43ebdee3)


Training set

![Screenshot 2025-03-06 142405](https://github.com/user-attachments/assets/633ac7b5-27f5-46a7-b949-281bf22fb9ab)
![Screenshot 2025-03-06 142423](https://github.com/user-attachments/assets/61199b21-beea-48fd-b70d-92fd2b1e09c3)



## Result:
Thus the program to implement the simple linear regression model for predicting the marks scored is written and verified using python programming.
