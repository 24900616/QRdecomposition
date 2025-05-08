# Algorithm for QR Decomposition
## Aim:
To implement QR decomposition algorithm using the Gram-Schmidt method.
## Equipment’s required:
1.	Hardware – PCs
2.	Anaconda – Python 3.7 Installation / Moodle-Code Runner
## Algorithm:
1.	Intialize the matrix Q and u
2.	The vector u and e is given by

    ![eqn1](./ex4.jpg)

    ![eqn2](./ex6.jpg)

    ![eqn3](./ex3.jpg)

3.	Obtain the Q matrix   
    ![eqn4](./ex1.jpg)
4.	Construct the upper triangular matrix R
    ![eqn5](./ex2.jpg)



## Program:
```
Program to QR decomposition using the Gram-Schmidt method
Developed by: Swetha K
RegisterNumber: 212224230284
```
### Gram-Schmidt Method
```
import numpy as np
def QR_Decomposition(A):
    n,m=A.shape
    Q=np.empty((n,n))
    U=np.empty((n,n))
    R=np.zeros((n,m))
    U[:,0]=A[:,0]
    Q[:,0]=U[:,0]/np.linalg.norm(U[:,0])
    for i in range(1,n):
        U[:,i]=A[:,i]
        for j in range(i):
            U[:,i]-=(A[:,i]@Q[:,j]*Q[:,j])
        Q[:,i]=U[:,i]/np.linalg.norm(U[:,i])
    R=np.zeros((n,m))
    for i in range(n):
        for j in range(i,m):
            R[i,j]=A[:,j]@Q[:,i]
    print("The Q Matrix is\n",Q)
    print("The R Matrix is\n",R)
a = np.array(eval(input()))
QR_Decomposition(a)

```

## Output

![Screenshot 2025-04-27 063701](https://github.com/user-attachments/assets/ab4bd946-16fe-4c7e-8140-5ca4f19cd658)
![Screenshot 2025-04-27 063715](https://github.com/user-attachments/assets/8be17e18-2d97-46be-b95b-23a27ccae2f4)

## Result
Thus the QR decomposition algorithm using the Gram-Schmidt process is written and verified the result.
