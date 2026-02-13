# Algorithm for QR Decomposition
## Aim:
To implement QR decomposition algorithm using the Gram-Schmidt method.
## Developed by: Harini P
## Reg.No: 212224230082
## Equipment’s required:
1.	Hardware – PCs
2.	Anaconda – Python 3.7 Installation / Moodle-Code Runner
## Algorithm:
1.	Intialize the matrix Q and u
2.	The vector u and e is given by

   <img width="627" height="302" alt="image" src="https://github.com/user-attachments/assets/4e092e0c-c52d-43bf-966c-9b6a59fabc4c" />

3.	Obtain the Q matrix   
 <img width="744" height="143" alt="image" src="https://github.com/user-attachments/assets/782aa661-1d90-4c98-894b-eacccb135e79" />

4.	Construct the upper triangular matrix R
    
## Program:
### Gram-Schmidt Method
```

import numpy as np
def qr_Decomposition(A):
    A=np.array(A, dtype=float)
    m,n=A.shape
    Q=np.zeros((m,n))
    R=np.zeros((n,n))
    
    for j in range(n):
        v=A[:,j]
        for i in range(j):
            R[i,j]=np.dot(Q[:,i],A[:,j])
            v=v-R[i,j]*Q[:,i]
        R[j,j]=np.linalg.norm(v)
        Q[:,j]=v/R[j,j]
    return Q,R
    
A = np.array(eval(input()))
Q,R=qr_Decomposition(A)

print("The Q Matrix is\n",Q)
print("The R Matrix is\n",R)


```

## Output
<img width="1223" height="603" alt="image" src="https://github.com/user-attachments/assets/15e56783-e0de-48b6-992e-e9aa012c761c" />

## Result
Thus the QR decomposition algorithm using the Gram-Schmidt process is written and verified the result.
