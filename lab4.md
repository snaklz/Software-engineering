# Тема 4. Функции и стандартные модули/библиотеки
Отчет по Теме #4 выполнил:
- Кузнецов Данил Дмитриевич
- ИНО ЗБ ПОАС-22-2

| Задание | Лаб_раб(10) | Сам_раб(5) |
| ------ | ------ | ------ |
| Задание 1 | + | + |
| Задание 2 | + | + |
| Задание 3 | + | + |
| Задание 4 | + | + |
| Задание 5 | + | + |
| Задание 6 | + |  |
| Задание 7 | + |  |
| Задание 8 | + |  |
| Задание 9 | + |  |
| Задание 10 | + |  |


Работу проверили:
- к.э.н., доцент Панов М.А.
## Самостоятельная работа №1
### Дайте подробный коментарий для кода. Коментарий нужен для каждой строчки кода, что она делает.

```python
# Импортируем модули
from datetime import datetime
from math import sqrt

# Определяем функцию main, которая принимает произвольное количество именованных аргументов
def main (**kwargs):
    # Проходим по каждому элементу в словаре kwargs
    for key in kwargs.items():
        # Вычисляем квадратный корень суммы квадратов первого и второго элементов значения для каждого ключа
        result=sqrt(key[1][0]**2+key[1][1]**2)
        # Выводим результат
        print(result)

# Если этот файл запущен как основная программа, то выполняем код ниже
if __name__=='__main__':
    # Записываем текущее время в переменную
    stat_time=datetime.now()
    # Вызываем функцию main с заданными аргументами
    main(
        one=[10, 3],
        two=[5, 4],
        three=[15, 13],
        four=[93,53],
        five=[133,15]
    )
    # Вычисляем время выполнения программы
    time_costs=datetime.now() - stat_time
    # Выводим время выполнения программы
    print(f"Время выполнения программы - {time_costs}")
```
### Результат:
![Меню](https://github.com/snaklz/Software-engineering/blob/main/4.1.png)

## Самостоятельная работа №2
### Напишите программу, которая будет заменять игральную кость с 6 гранями. Если значение равно 5 или 6, то в консоль выводится «Вы победили», если значения 3 или 4, то вы рекурсивно должны вызвать эту же функцию, если значение 1 или 2, то в консоль выводится «Вы проиграли». При этом каждый вызов функции необходимо выводить в консоль значение "кубика". Для выполнения задания необходимо использовать стандартную библиотеку random. Программу нужно написать, используя одну функцию и "точку входа"

```python
import random
def kub():
    result=random.randint(1,6)
    print(result)
    if result==5 or result==6:
        print('Вы победили')
    elif result==3 or result==4:
        kub()
    elif result==1 or result==2:
        print('вы проиграли')
if __name__ == '__main__':
kub()
```

### Результат:
![Меню](https://github.com/snaklz/Software-engineering/blob/main/4.2.png)

## Самостоятельная работа 3
### Напишите программу, которая будет выводить текущее время, с точностью до секунд на протяжении 5 секунд. Программу нужно написать с использованием цикла. Подсказка: необходимо использовать модуль datetime и time, а также вам необходимо как-то "усыплять" программу на 1 секунду.

```python
import datetime, time
currentTime=datetime.datetime.now()
cTime=currentTime + datetime.timedelta(seconds=5)
while currentTime<=cTime:
    currentTime = datetime.datetime.now()
    print(currentTime.strftime('%H:%M:%S'))
    time.sleep(1)
```

### Результат:
![Меню](https://github.com/snaklz/Software-engineering/blob/main/4.3.png)

## Самостоятельная работа 4
### Напишите программу, которая считает среднее арифметическое от аргументов вызываемое функции, с условием того, что изначальное количество этих аргументов неизвестно. Программу необходимо реализовать используя одну функцию и "точку входа".

```python
def rif(*args):
    result = 0
    for i in args:
        result+=i
    return result/len(args)
if __name__ == '__main__':
    main(
print(rif(11,22,100)  )
```

### Результат:
![Меню](https://github.com/snaklz/Software-engineering/blob/main/4.4.png)

## Самостоятельная работа 5
### Создайте два Python файла, в одном будет выполняться вычисление площади треугольника при помощи формулы Герона (необходимо реализовать через функцию), а во втором будет происходить взаимодействие с пользователем (получение всей необходимой информации и вывод результатов). Напишите эту программу и выведите в консоль полученную площадь.
1 файл lab1.py
```python
import test
a = float(input("сторона А:"))
b = float(input("сторона B:"))
c = float(input("сторона С:"))
print(test.treygol(a, b, c))
```
2 файл test.py
```python
import math

def treygol(a,b,c):
    p=a+b+c
    return math.sqrt(p*(p-a)*(p-b)*(p-c))
```
### Результат:
![Меню](https://github.com/snaklz/Software-engineering/blob/main/4.5.png)
![Меню](https://github.com/snaklz/Software-engineering/blob/main/4.5.1.png)