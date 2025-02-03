

# Прототип "Товары A и B"

```Python
M = 4000000  
suma = 0  
data = open("26 (5).txt").read().splitlines()  
A = []  
B = []  
for s in data:  
    st = s.split()  
    if st[2] == "A":  
        A.append((int(st[0]), int(st[1])))  
    if st[2] == "B":  
        B.append((int(st[0]), int(st[1])))  
A.sort()  
B.sort()  
for elem in A:  
    if suma + elem[0] < M:  
        count = min(((M - suma) // elem[0]), elem[1])  
        suma += elem[0] * count  
    else:  
        break  
  
c = 0  
if M > 0:  
    for elem in B:  
        if suma + elem[0] <= M:  
            count = min(((M - suma) // elem[0]), elem[1])  
            suma += elem[0] * count  
            c += count  
        else:  
            break  
print(c, M - suma)
```


# Прототип Торт (ЕГЭ 2024)
```Python
data = open("1_26.txt").read().splitlines()  
lst = list(map(int, data))  
lst.sort(reverse=True)  
d = lst[0]  
c = 1  
for i in range(0, len(lst)-1):  
    if d - lst[i] >= 4:  
        c += 1  
        d = lst[i]  
print(c, d)
```

# Прототип Парковка
```Python 
f = open('inf_26_04_21_26 (2).txt')n = f.readline()
parking = [[] for i in range(100)]
cnt_a = 0cnt = 0
# Рассматриваем каждую приехавшую машину, предварительно отсортировав массив в экселеfor i in f:
    car = i.split()
    parked  = False
    # Если приехала легковушка    if car[-1] == 'A':
        # Пробегаемся по всем местам на парковке
    for park in range(len(parking)):
            # Если место не было занято вообще
            if not parking[park]:
	            parking[park].append(car)
                parked = True
                cnt_a += 1
                break            
            else:
                # Рассматриваем, точно ли нам подходит место:                # Если время прибытия последнего запаркованного авто + кол-во времени, которое ему нужно меньше 
                # времени приезда нового авто                if int(parking[park][-1][1]) + int(parking[park][-1][0]) <= int(car[0]):
                    # Добавляем приехавшее авто в место на парковке, отмечаем, что оно запарковано и прибавляем счётчик                    parking[park].append(car)
                    parked = True
                    cnt_a += 1
                    break    # Аналогично с авто типа В, отличие только в цикле
    elif car[-1] == 'B':        # Т.к. авто типа В не может встать на место для А, то рассматриваем только места типа В (т.е. с 80 до 100)
        for park in range(80, len(parking)):            # Если место свободно, просто добавляем
            if not parking[park]:                         parking[park].append(car)
                parked = True
                break
            else:                # Аналогично автомобилям А
                if int(parking[park][-1][1]) + int(parking[park][-1][0]) <= int(car[0]):                    parking[park].append(car)
                    parked = True                    break
    # Если машину запарковать не удалось, то прибавляем счётчик    if not parked:
        cnt += 1for i in parking:
    print(i)
print(cnt)print(cnt_a)
```
# Прототип концерт
```Python
f = open('2626.txt')  
n, m, k = 15050, 1000, 100  
data = [list(map(int, i.split())) for i in f]  
hall = [[0 for i in range(k)] for _ in range(m)]  
for i in data:  
    hall[i[0] - 1][i[1] - 1] = 1  
cnt = mx = 0  
number = 0  
for i in range(len(hall[0])):  
    for j in range(len(hall)):  
        if hall[j][i] == 0:  
            cnt += 1  
            if cnt - 1 >= mx:  
                mx = cnt - 1  
                number = j + 1  
        else:  
            cnt = 0  
print(number, mx)
```