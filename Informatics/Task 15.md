# Простой прототип ДЕЛ:
![[Pasted image 20250203101411.png]]
Решение:
```Python
def f(x, a):  
    return ((x % a == 0) and (x % 24 == 0) and (x % 16 != 0)) <= (x % a != 0)  
  
for A in range(1, 10000):  
    if all(f(x, A) == 1 for x in range(1, 10000)):  
        print(A)
```

# Прототип Коньюкция
![[Pasted image 20250203184157.png]]
Решение:
```Python
def f(x, a):  
    func = ((x & 26 != 0) or (x & 29 != 0)) <= ((x & 29==0) <= (x&a!=0))  
    return func  
  
for a in range(1, 1000000):  
    if all(f(x, a) for x in range(1, 1000000)):  
        print(a)
```