# Тема 10. Декораторы и исключения
Отчет по Теме #10 выполнил:
- Кузнецов Данил Дмитриевич
- ИНО ЗБ ПОАС-22-2

| Задание | Лаб_раб | Сам_раб |
| ------ | ------ | ------ |
| Задание 1 | - | + |
| Задание 2 | - | + |
| Задание 3 | - | + |
| Задание 4 | - | + |
| Задание 5 | - | + |
| Задание 6 | - | - |
| Задание 7 | - | - |
| Задание 8 | - | - |
| Задание 9 | - | - |
| Задание 10 | - | - |


Работу проверили:
- к.э.н., доцент Панов М.А.
## Самостоятельная работа №1
### 1	Вовочка решил заняться спортивным программированием на python, но для этого он должен знать за какое время выполняется его программа. Он решил, что для этого ему идеально подойдет декоратор для функции, который будет выяснять за какое время выполняется та или иная функция. Помогите Вовочке в его начинаниях и напишите такой декоратор. Результатом вашей работы будет листинг кода и скриншот консоли, в котором будет выполненная функция Фибоначчи и время выполнения программы.

```python
import time


def timer (func):
    def per(*args, **kwargs):
        start = time.time()
        result = func(*args, **kwargs)
        end = time.time()
        print(f'\nФункция была выполнена за {end - start } сек.')
        return result

    return wrapper


@timer
def fibonacci():
    fib1 = fib2 = 1
    for i in range(2, 400):
        fib1, fib2 = fib2, fib1 + fib2
        print(fib2, end=' ')


if __name__ == '__main__':
    fibonacci()
```
### Результат:
![Меню](https://github.com/snaklz/Software-engineering/blob/main/10.1.png)

## Самостоятельная работа №2
### Посмотрев на Вовочку, вы также загорелись идеей спортивного программирования, начав тренировки вы узнали, что для решения некоторых задач необходимо считывать данные из файлов. Но через некоторое время вы столкнулись с проблемой что файлы бывают пустыми, и вы не получаете вводные данные для решения задачи. После этого вы решили не просто считывать данные из файла, а всю конструкцию оборачивать в исключения, чтобы избежать такой проблемы. Создайте пустой файл и файл, в котором есть какая-то информация. Напишите код программы. Если файл пустой, то, нужно вызвать исключение (“бросить исключение”) и вывести в консоль “файл пустой”, а если он не пустой, то вывести информацию из файла.

```python
def read_file(filename):
    try:
        file = open(filename, 'r', encoding='utf-8-sig')
        content = file.read()
        if not content:
            raise Exception(f"{filename} пустой")
        print(content)
    except Exception as e:
        print(str(e))


if __name__ == '__main__':
    read_file('test.txt')
    read_file('test1.txt')
```

### Результат:
![Меню](https://github.com/snaklz/Software-engineering/blob/main/10.2.png)

## Самостоятельная работа 3
### Напишите функцию, которая будет складывать 2 и введенное пользователем число, но если пользователь введет строку или другой неподходящий тип данных, то в консоль выведется ошибка “Неподходящий тип данных. Ожидалось число.”. Реализовать функционал программы необходимо через try/except и подобрать правильный тип исключения. Создавать собственное исключение нельзя. Проведите несколько тестов, в которых исключение вызывается и нет. Результатом выполнения задачи будет листинг кода и получившийся вывод в консоль.

```python
def sum_num():
    try:
        num = float(input('Введите число:\n'))
        res = num + 2
        return res
    except ValueError:
        return 'Неподходящий тип данных. Ожидалось число.'

print(sum_num())
print(sum_num())
```

### Результат:
![Меню](https://github.com/snaklz/Software-engineering/blob/main/10.3.png)

## Самостоятельная работа 4
### Создайте собственный декоратор, который будет использоваться для двух любых вами придуманных функций. Декораторы, которые использовались ранее в работе нельзя воссоздавать. Результатом выполнения задачи будет: класс декоратора, две как-то связанными с ним функциями, скриншот консоли с выполненной программой и подробные комментарии, которые будут описывать работу вашего кода.

```python
#создание нового класса calc для 2-ух новых функций
class my_decorator:
    def __init__(self, func):
        self.func = func
    def __call__(self, *args, **kwargs):
        print(f'Декоратор до выполнения функции "{self.func.__name__}"')
        result = self.func(*args, **kwargs)
        print(f'Декоратор после выполнения функции "{self.func.__name__}"')
        return result

@my_decorator
def addition(a, b):
    return a + b

@my_decorator
def multiply(a, b):
    return a * b

x = int(input('Введите первое число: '))
y = int(input('Введите второе число: '))

print(addition(x, y))
print(multiply(x, y))
```

### Результат:
![Меню](https://github.com/snaklz/Software-engineering/blob/main/10.4.png)

## Самостоятельная работа 5
### Создайте собственное исключение, которое будет использоваться в двух любых фрагментах кода. Исключения, которые использовались ранее в работе нельзя воссоздавать. Результатом выполнения задачи будет: класс исключения, код к котором в двух местах используется это исключение, скриншот консоли с выполненной программой и подробные комментарии, которые будут описывать работу вашего кода.

```python
class MyException(Exception):
    pass
def positive_number(n):
    try:
        if n <= 0:
            raise MyException(f'{n} не является положительным числом')
        print(f'Введено положительное число: {n}')
    except MyException as e:
        print(f'Поймано исключение: {e}')
def only_letters(s):
    try:
        if not s.isalpha():
            raise MyException(f'{s} содержит не только буквы')
        print(f'Введена строка только из букв: {s}')
    except MyException as e:
        print(f'Поймано исключение: {e}')

test_num = int(input('Введите число: '))
positive_number(test_num)
test_string = input('Введите строку: ')
only_letters(test_string)
```

### Результат:
![Меню](https://github.com/snaklz/Software-engineering/blob/main/10.5.png)
