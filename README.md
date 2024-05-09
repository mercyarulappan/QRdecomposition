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
### Gram-Schmidt Method
```python
''' 
Program to QR decomposition using the Gram-Schmidt method
Developed by: Mercy A
RegisterNumber: 212223110027
'''
import numpy as np
def QR_Decomposition(a):
    n,m=a.shape 
    u=np.empty((n,m))
    e=np.empty((n,m))
    u[:,0]=a[:,0]
    e[:,0]=u[:,0]/np.linalg.norm(u[:,0])
    for i in range(n):
        u[:,i]=a[:,i]
        for j in range(i):
            u[:,i]-=(a[:,i]@e[:,j])*e[:,j]
            e[:,i]=u[:,i]/np.linalg.norm(u[:,i])
    r=np.zeros((n,m))
    for i in range(n):
        for j in range(i,m):
            r[i,j]=a[:,j]@e[:,i]
    print(e)
    print(r)
a = np.array(eval(input()))
QR_Decomposition(a)
```

## Output
![image](https://github.com/mercyarulappan/QRdecomposition/assets/149233730/10e1cd0e-cac9-4539-9fee-e043d9a13820)

## Result
Thus the QR decomposition algorithm using the Gram-Schmidt process is written and verified the result.
