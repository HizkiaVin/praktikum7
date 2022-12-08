# Sub Rutin/Fungsi
## Latihan 1
![latihan1](https://user-images.githubusercontent.com/116176746/206343131-5cac03e5-add2-4bfe-b3a9-ab6df0ec315e.png)
```python

import math

def a(x)
    return x**2

#jika menggunakan lambda
A=lambda x:x**2
print(A(2))

def b(x, y):
return math.sqrt(x**2 + y**2)

#jika menggunakan lambda
B=lambda x,y:math.sqrt(x**2 + y**2)
print(B(2,2))

def c(*args):
return sum(args)/len(args)

#jika mengguankan lambda
C= lambda *args:sum(args)/len(args)
print(C(3,5,1,2,4))

