# Gaussian Elimination

## AIM:
To write a program to find the solution of a matrix using Gaussian Elimination.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Moodle-Code Runner

## Algorithm
1. Import the NumPy library and define the coefficient matrix A and constant matrix B.
2. Convert the matrices into floating-point type and form the augmented matrix [A∣B].
3. Apply Gaussian Elimination by performing row operations to convert the augmented matrix into upper triangular form.
4. Use back substitution (or NumPy functions) to calculate and display the solution of the matrix equations.

## Program:
```
'''Program to solve a matrix using Gaussian elimination without partial pivoting.
Developed by: Vinodhini M.k
RegisterNumber: 212225230305
'''
import os
os.environ["OPENBLAS_NUM_THREADS"]="1"
import numpy as np
n=int(input())
a=[]
X=np.zeros(n)
for i in range(n):
    row=[]
    for j in range(n+1):
        row.append(float(input()))
    a.append(row)
for i in range(n):
    for k in range(i+1,n):
         factor=a[k][i]/a[i][i]
         for j in  range(i,n+1):
             a[k][j]-=factor*a[i][j]
x=[0]*n
for i in range(n-1,-1,-1):
    x[i]=a[i][n]
    for j in range(i+1,n):
        x[i]-=a[i][j]*x[j]
    x[i]/=a[i][i]
for i in range(n):
    print(f"X{i} = {x[i]:.2f}",end=" ")
    
```

## Output:
![alt text](<Screenshot 2026-05-24 231432.png>)
## Result:
Thus the program to find the solution of a matrix using Gaussian Elimination is written and verified using python programming.

