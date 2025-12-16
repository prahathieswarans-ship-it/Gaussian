# Gaussian Elimination

## AIM:
To write a program to find the solution of a matrix using Gaussian Elimination.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Moodle-Code Runner

## Algorithm
Algorithm (Gaussian Elimination)
1. Input Setup
- Read the number of equations n.
- Construct augmented matrix a of size n × (n+1) and solution vector x.
- Fill matrix a with user inputs.
2. Forward Elimination
- For each pivot row, check for zero diagonal (exit if division by zero).
- Eliminate coefficients below the pivot using row operations.
3. Back Substitution
- Start from the last equation, compute solution for each variable.
- Substitute known values into previous equations to solve step by step.
4. Output Solution
- Print all variable values in the format X0, X1, …, Xn.


## Program:
```
'''Program to solve a matrix using Gaussian elimination without partial pivoting.
Developed by: Prahathieswaran 
RegisterNumber: 25013305    
'''
import numpy as np
import sys
n=int(input())
a=np.zeros((n,n+1))
x=np.zeros(n)
for i in range(n):
    for j in range(n+1):
        a[i][j]=float(input())
for i in range(n):
    if a[i][i]==0.0:
        sys.exit("Divide by zero detected!")
        
    for j in range(i+1,n):
        ratio=a[j][i]/a[i][i]
        for k in range(n+1):
            a[j][k]=a[j][k]-ratio*a[i][k]

x[n-1]=a[n-1][n]/a[n-1][n-1]

for i in range(n-2,-1,-1):
    x[i]=a[i][n]
    for j in range(i+1,n):
        x[i]=x[i]-a[i][j]*x[j]
    x[i]=x[i]/a[i][i]
        
for i in range(n):
    print('X%d = %0.2f' %(i,x[i]),end=' ')
```
<img width="1335" height="827" alt="image" src="https://github.com/user-attachments/assets/f5e5199d-758c-4cf9-93f3-7e588c89bb33" />


## Output:
<img width="906" height="515" alt="image" src="https://github.com/user-attachments/assets/5c1d600c-445f-49d5-8c6d-c77123eb45ff" />


## Result:
Thus the program to find the solution of a matrix using Gaussian Elimination is written and verified using python programming.

