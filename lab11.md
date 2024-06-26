# Тема 11. Итераторы и генераторы
Отчет по Теме #11 выполнил:
- Кузнецов Данил Дмитриевич
- ИНО ЗБ ПОАС-22-2

| Задание | Лаб_раб | Сам_раб |
| ------ | ------ | ------ |
| Задание 1 | + | + |
| Задание 2 | + | + |

Работу проверили:
- к.э.н., доцент Панов М.А.
## Самостоятельная работа №1
### Вас никак не могут оставить числа Фибоначчи, очень уж они вас заинтересовали. Изучив новые возможности Python вы решили реализовать программу, которая считает числа Фибоначчи при помощи итераторов. Расчет начинается с чисел 1 и 1. Создайте функцию fib(n), генерирующую n чисел Фибоначчи с минимальными затратами ресурсов. Для реализации этой функции потребуется обратиться к инструкции yield (Она не сохраняет в оперативной памяти огромную последовательность, а дает возможность “доставать” промежуточные результаты по одному). Результатом решения задачи будет листинг кода и вывод в консоль с числом Фибоначчи от 200.

```python
def fib(n):
    a, b = 1, 1
    count = 0
    while count < n:
        yield a
        a, b = b, a + b
        count += 1
for num in fib(400):
    print(num)
```
### Результат:
![Меню](https://github.com/snaklz/Software-engineering/blob/main/11.1.png)

## Самостоятельная работа №2
### К коду предыдущей задачи добавьте запоминание каждого числа Фибоначчи в файл “fib.txt”, при этом каждое число должно находиться на отдельной строчке. Результатом выполнения задачи будет листинг кода и скриншот получившегося файла

```python
def fib(n):
    a, b = 1, 1
    count = 0
    with open('test.txt', 'w') as txt:
        while count < n:
            yield a
            a, b = b, a + b
            txt.write(str(a) + '\n')
            count += 1
print(*[i for i in fib(200)])
```

### Результат:
![Меню](https://github.com/Dirtzzz/Tema_11/blob/main/11.2.png)
файлик:
(https://github.com/snaklz/Software-engineering/blob/main/test.txt)
