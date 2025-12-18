# Gaussian Elimination

## AIM:
To write a program to find the solution of a matrix using Gaussian Elimination.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Moodle-Code Runner

## Algorithm
1. Start
2. Read the value of n (number of variables)
3.Read the augmented matrix A[n][n+1]
4.Forward Elimination
5.Back Substitution
6.Display the solution values x[1], x[2], …, x[n]
7.Stop 

## Program:
```
/*
Program to find the solution of a matrix using Gaussian Elimination.
Developed by: VIGNESH.K
RegisterNumber: 25018207
*/
```
```
import numpy as np
import sys
n=int(input())
a=np.zeros((n,n+1))
X=np.zeros(n)
for i in range(n):
    for j in range(n+1):
        a[i][j]=float(input())
for i in range(n):
    if a[i][i] == 0:
        sys.exit('Divide by zero detected!')
    for j in range(i+1,n):
        ratio=a[j][i]/a[i][i]
        for k in range(n+1):
            a[j][k] = a[j][k] - ratio * a[i][k]
X[n-1] = a[n-1][n] / a[n-1][n-1]
for i in range(n-2, -1, -1):
    X[i] = a[i][n]
    for j in range(i+1, n):
        X[i] = X[i] - a[i][j] * X[j]
    X[i] = X[i] / a[i][i]
for i in range(n):
    print("X%d = %0.2f"%(i,X[i]),end=' ')
```
## Output:

<img width="1235" height="485" alt="Screenshot 2025-12-18 233252" src="https://github.com/user-attachments/assets/770783c8-8b33-4970-a537-36cc1fee69e7" />

## Result:
Thus the program to find the solution of a matrix using Gaussian Elimination is written and verified using python programming.

