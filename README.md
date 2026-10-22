# Gaussian Elimination

## AIM:
To write a program to find the solution of a matrix using Gaussian Elimination.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Moodle-Code Runner

## Algorithm
1. Augmented Matrix Setup: Initializes an n \times (n+1) matrix a to store coefficients alongside the constant vector.  
​2. Forward Elimination: Converts the coefficient matrix into upper triangular form by subtracting row ratios (ratio = a[j][i] / a[i][i]) from lower rows.  
​3. Zero Pivot Check: Checks if a diagonal entry a[i][i] is zero to prevent division by zero.    
​4. Output Display: Prints each computed variable X_i rounded to 2 decimal places 
  
 

## Program:
```
### Program to solve a matrix using Gaussian elimination without partial pivoting.
Developed by: Arjun M 
RegisterNumber: 26017171
'''
import os
os.environ["OPENBLAS_NUM_THREADS"]="1"
import numpy as np
import sys
n=int(input())
a=np.zeros((n,n + 1))
x=np.zeros(n)
for i in range(n):
    for j in range(n+1):
        a[i][j]=float(input())
for i in range(n):
    if a[i][i]==0.0:
        sys.exit('divide by zero detected!')
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
    print('X%d = %.2f' % (i,x[i]), end=' ')
    
```

## Output:
![gaussian elimination]()
<img width="811" height="787" alt="image" src="https://github.com/user-attachments/assets/b766f378-e82d-4bdf-ba5b-c6438b7156ac" />



## Result:
Thus the program to find the solution of a matrix using Gaussian Elimination is written and verified using python programming.

