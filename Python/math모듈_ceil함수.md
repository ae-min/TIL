
math 모듈의 ceil함수

=> 나눗셈이 딱 나누어 떨어지지 않을 경우 올림처리

```
[백준 5532]

import math
L = int(input())
A = int(input())
B = int(input())
C = int(input())
D = int(input())

k = math.ceil(A/C)
m = math.ceil(B/D)

free = max(k,m)
print(L-free)
```
