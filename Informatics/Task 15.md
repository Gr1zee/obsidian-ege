Простой прототип ДЕЛ:
![[Pasted image 20250203101411.png]]
Решение:
```Python
def f(x, a):  
    return ((x % a == 0) and (x % 24 == 0) and (x % 16 != 0)) <= (x % a != 0)  
  
for A in range(1, 10000):  
    if all(f(x, A) == 1 for x in range(1, 10000)):  
        print(A)
```
