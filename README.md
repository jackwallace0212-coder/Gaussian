# Gaussian Elimination

## AIM:
To write a program to find the solution of a matrix using Gaussian Elimination.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Moodle-Code Runner

## Algorithm
1.Import the numpy module to use the built-in functions for calculation

2.Prepare the lists from each linear equations and assign in np.array()

3.Apply Gaussian elimination to convert the matrix into upper triangular form.

4.End the Program

## Program:
```
import os
os.environ["OPENBLAS_NUM_THREADS"]="1"

n = int(input())

a = []

for i in range(n):
    row = []
    for j in range(n + 1):
        row.append(float(input()))
    a.append(row)

for i in range(n):
    for j in range(i + 1, n):
        ratio = a[j][i] / a[i][i]
        for k in range(n + 1):
            a[j][k] = a[j][k] - ratio * a[i][k]

x = [0 for i in range(n)]

x[n - 1] = a[n - 1][n] / a[n - 1][n - 1]

for i in range(n - 2, -1, -1):
    x[i] = a[i][n]
    for j in range(i + 1, n):
        x[i] = x[i] - a[i][j] * x[j]
    x[i] = x[i] / a[i][i]

for i in range(n):
    print("X%d = %.2f" % (i, x[i]), end=" ")
```

## Output:
<img width="865" height="582" alt="Screenshot 2026-05-29 090529" src="https://github.com/user-attachments/assets/f3f7433e-571d-472d-8a0a-7bd8c9df3850" />



## Result:
Thus the program to find the solution of a matrix using Gaussian Elimination is written and verified using python programming.

