# Пары чисел
![[Pasted image 20250204120700.png]]
```Python
lst = [int(x) for x in open("17_1993.txt")]  
res = [lst[i] + lst[i+1] for i in range(len(lst)-1) if (lst[i]+lst[i+1])%6!=0 and (lst[i]+lst[i+1])%3==0 and str(lst[i]*lst[i+1])[-1]=="8"]  
print(len(res), max(res))
```