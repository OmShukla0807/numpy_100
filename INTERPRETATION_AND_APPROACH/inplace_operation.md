# The problem 

when we do A=A+B then it creates an extra temp array and then assign 
A to point that temp array.

```python
A=np.array([1,2,3,4])
A_initial=id(A)
B=np.array([5,6,7,8])
A=A+B
A_final=id(B)
print(A_initial==A_final)
```
output: False

---
solution 
use `python np.add(A,B,out=B)` with the out parameter.

conceptually it uses:
```text 
for every element:
    B[i] = A[i] + B[i]
```



