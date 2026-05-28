# Gaussian Elimination

## AIM:
To write a program to find the solution of a matrix using Gaussian Elimination.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Moodle-Code Runner

## Algorithm


1. **Input the Augmented Matrix**
   Read the number of variables `n` and input the augmented matrix of size `n × (n+1)`.

2. **Perform Forward Elimination**
   Convert the matrix into upper triangular form using Gaussian Elimination.
   If any diagonal element is zero, terminate the program.

3. **Apply Back Substitution**
   Find the value of the last variable first, then compute the remaining variables in reverse order.

4. **Display the Solution**
   Print the values of all unknown variables `X0, X1, X2, ...`.


## Program:
```
/*
Program to find the solution of a matrix using Gaussian Elimination.
Developed by: DHIYA D
RegisterNumber: 212225100012
*/
import numpy as np
import sys
n=int(input())
a=np.zeros((n,n+1))
x=np.zeros(n)
for i in range(n):
    for j in range(n+1):
        a[i][j]=float(input())
for i in range(n):
    if a[i][i]==0:
        sys.exit("zero detected")
    for j in range(i+1,n):
        r=a[j][i]/a[i][i]
        for k in range(n+1):
            a[j][k]=a[j][k]-r*a[i][k]
x[n-1]=a[n-1][n]/a[n-1][n-1]
for i in range(n-2,-1,-1):
    x[i]=a[i][n]
    for j in range(i+1,n):
        x[i]=x[i]-a[i][j]*x[j]
    x[i]=x[i]/a[i][i]
for i in range(n):
    print("X%d = %0.2f" % (i,x[i]),end=" ")
    
```

## Output:
![gaussian elimination]()

<img width="963" height="465" alt="image" src="https://github.com/user-attachments/assets/ceaea3d0-ecd8-4e08-939a-0617a3f2f118" />

## Result:
Thus the program to find the solution of a matrix using Gaussian Elimination is written and verified using python programming.

