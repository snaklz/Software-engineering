# Тема 2. Базовые операции языка Python
Отчет по Теме #2 выполнил:
- Кузнецов Дани Дмитриевич
- ИНО ЗБ ПОАС-22-2

| Задание | Лаб_раб | Сам_раб |
| ------ | ------ | ------ |
| Задание 1 | + | + |
| Задание 2 | + | + |
| Задание 3 | + | + |
| Задание 4 | + | + |
| Задание 5 | + | + |
| Задание 6 | + | + |
| Задание 7 | + | + |
| Задание 8 | + | + |
| Задание 9 | + | + |
| Задание 10 | + | + |


Работу проверили:
- к.э.н., доцент Панов М.А.
## Самостоятельная работа №1
### Выведите в консоль булевую переменную False, не используя слово False в строке или изначально присвоенную булевую переменную. Программа должна занимать не более двух строк редактора кода.

```python
print(1 == 2)
```
### Результат:
![Меню](https://github.com/snaklz/Software-engineering/blob/main/2.1.png)

## Самостоятельная работа №2
### Присвоить значения трем переменным и вывести их в консоль, используя только две строки редактора кода

```python
a, b, c = 1, 2, 3;
print(a, b, c)
```

### Результат:
![Меню](https://github.com/snaklz/Software-engineering/blob/main/2.2.png)

## Самостоятельная работа 3
### Реализуйте ввод данных в программу, через консоль, в виде только целых чисел (тип данных int). То есть при вводе буквенных символов в консоль, программа не должна работать. Программа должна занимать не более двух строк редактора кода.

```python
a = int(input("Введите число: "))
print(a) 
```

### Результат:
![Меню](https://github.com/snaklz/Software-engineering/blob/main/2.3.png)
![Меню](https://github.com/snaklz/Software-engineering/blob/main/2.3.1.png)

## Самостоятельная работа 4
### Создайте только одну строковую переменную. Длина строки должна не превышать 5 символов. На выходе мы должны получить строку длиной не менее 16 символов. Программа должна занимать не более двух строк редактора кода.

```python
s = 'a' * 16;
print(s)
```

### Результат:
![Меню](https://github.com/snaklz/Software-engineering/blob/main/2.4.png)

## Самостоятельная работа 5
### Создайте три переменные: день (тип данных - числовой), месяц (тип данных - строка), год (тип данных - числовой) и выведите в консоль текущую дату в формате: "Сегодня день месяц год. Всего хорошего!" используя F строку и оператор end внутри print(), в котором вы должны написать фразу "Всего хорошего!". Программа должна занимать не более двух строк редактора кода.
Поправочка: в 2 строки кода не получается создать, как бы я не пытался :(

```python
from datetime import datetime
today = datetime.now()э
print(f"Сегодня {today.day} {today.strftime('%B')} {today.year}. ", end="Всего хорошего!\n")
```

### Результат:
![Меню](https://github.com/snaklz/Software-engineering/blob/main/2.5.png)

## Самостоятельная работа 6
### В предложении 'Hello World' вставьте 'my' между двумя словами. Выведите полученное предложение в консоль в одну строку. Программа должна занимать не более двух строк редактора кода.


```python
print('Hello ' + 'my ' + 'World')
```

### Результат:
![Меню](https://github.com/snaklz/Software-engineering/blob/main/2.6.png)

## Самостоятельная работа 7
### Узнайте длину предложения 'Hello World', результат выведите в консоль. Программа должна занимать не более двух строк редактора кода.


```python
print(len('Hello World'))
```

### Результат:
![Меню](https://github.com/snaklz/Software-engineering/blob/main/2.7.png)

## Самостоятельная работа 8
### Переведите предложение 'HELLO WORLD' в нижний регистр. Программа должна занимать не более двух строк редактора кода


```python
print('HELLO WORLD'.lower())
```

### Результат:
![Меню](https://github.com/snaklz/Software-engineering/blob/main/2.8.png)

## Самостоятельная работа 9
### Придумать свою задачу, связанную с взаимодействием числовых значений. 
Задача: простейший калькулятор со сложением и вычитанием чисел

```python
num1 = int(input("Введите число1:"))
num2 = int (input("Введите число2:"))
dev = str (input("Введите знак:"))
print (num1 + num2)
print (num1 - num2)
```

### Результат:
![Меню](https://github.com/snaklz/Software-engineering/blob/main/2.9.png)

## Самостоятельная работа 10
### Придумать свою задачу, связанную с взаимодействием строковых значений. 
Задача: сложение слов

```python
slovo1 = str(input("введите слово1"))
slovo2 = str(input("введите слово2"))
print (slovo1 +" "+ slovo2)
```

### Результат:
![Меню](https://github.com/snaklz/Software-engineering/blob/main/2.10.png)
