# Тема 8. Основы объектно-ориентированного программирования
Отчет по Теме #8 выполнил:
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
### Самостоятельно создайте класс и его объект. Они должны отличаться, от тех, что указаны в теоретическом материале (методичке) и лабораторных заданиях. Результатом выполнения задания будет листинг кода и получившийся вывод консоли.

```python
class Person:
    def __init__(self, name, age, gender):
        self.name = name
        self.age = age
        self.gender = gender

    def show_info(self):
        print(f"Информация о человеке:\nИмя: {self.name}\nВозраст: {self.age}\nПол: {self.gender}")

    def greet(self):
        if self.gender == "муж":
            print(f"Здравствуйте, Г-н. {self.name}!\n")
        elif self.gender == "жен":
            print(f"Здравствуйте, Г-жа. {self.name}!\n")
        else:
            print(f"Здравствуйте, {self.name}!\n")

person1 = Person('Данил', 22, 'муж')
person1.show_info()
person1.greet()

person2 = Person("Маша", 21, "жен")
person2.show_info()
person2.greet()

person3 = Person("Саша", 20, " ")
person3.show_info()
person3.greet()
```
### Результат:
![Меню](https://github.com/snaklz/Software-engineering/blob/main/8.1.png)

## Самостоятельная работа №2
### Самостоятельно создайте атрибуты и методы для ранее созданного класса. Они должны отличаться, от тех, что указаны в теоретическом материале (методичке) и лабораторных заданиях. Результатом выполнения задания будет листинг кода и получившийся вывод консоли.

```python
import datetime

today = datetime.date.today()


class Person:
    def __init__(self, name, birthday):
        self.name = name
        self.birthday = birthday
        self.age = today.year - birthday.year - ((today.month, today.day) < (birthday.month, birthday.day))

    def show_info(self):
        print(f"Информация:\nИмя: {self.name}\nВозраст: {self.age}\nДР: {self.birthday}")

    def celebrate_birthday(self):
        if today.day == self.birthday.day and today.month == self.birthday.month:
            print(f"С ДР, {self.name}! исполнилось {self.age} лет.\n")
        else:
            print("Сегодня не Др.\n")
person1 = Person('Данил', datetime.date(2002, 9, 7))
person1.show_info()
person1.celebrate_birthday()

person2 = Person("Маша", datetime.date(2003, 2, 26))
person2.show_info()
person2.celebrate_birthday()

person3 = Person("Саша", datetime.date(2002, 9, 6))
person3.show_info()
person3.celebrate_birthday()
```

### Результат:
![Меню](https://github.com/snaklz/Software-engineering/blob/main/8.2.png)

## Самостоятельная работа 3
### Самостоятельно реализуйте наследование, продолжая работать с ранее созданным классом. Оно должно отличаться, от того, что указано в теоретическом материале (методичке) и лабораторных заданиях. Результатом выполнения задания будет листинг кода и получившийся вывод консоли.

```python
class Person:
    def __init__(self, name, age):
        self.name = name
        self.age = age
    def greet(self):
        print(
            f"Привет! Меня зовут {self.name}. Мне {self.age}.")
class Student(Person):
    def __init__(self,name,age, course):
        super().__init__(name, age)
        self.course = course

    def study(self):
        print(f"{self.name} учится на {self.course} курсе.")

# Создание "объкетов"
person1 = Person('Никита', 22)
person1.greet()
print("")

student1 = Student("Маша", 21, 1)
student1.greet()
student1.study()
```

### Результат:
![Меню](https://github.com/snaklz/Software-engineering/blob/main/8.3.png)

## Самостоятельная работа 4
### Самостоятельно реализуйте инкапсуляцию, продолжая работать с ранее созданным классом. Она должна отличаться, от того, что указана в теоретическом материале (методичке) и лабораторных заданиях. Результатом выполнения задания будет листинг кода и получившийся вывод консоли.

```python
class Person:
    def __init__(self, name, age):
        self._name = name
        self._age = age

    def greet(self):
        return f"Привет,  зовут {self._name} и мне {self._age} лет."

person1 = Person("Глеб", 23)
print(person1._name)
print(person1.greet())
```

### Результат:
![Меню](https://github.com/snaklz/Software-engineering/blob/main/8.4.png)

## Самостоятельная работа 5
### Самостоятельно реализуйте полиморфизм. Он должен отличаться, от того, что указан в теоретическом материале (методичке) и лабораторных заданиях. Результатом выполнения задания будет листинг кода и получившийся вывод консоли.

```python
class Person:
    def __init__(self, name, age):
        self.name = name
        self.age = age

    def show_info(self):
        print(f"Имя: {self.name}\nВозраст: {self.age}\n")


class Student(Person):
    def __init__(self, name, age, course):
        super().__init__(name, age)
        self.course = course

    def show_info(self):
        print(f"Имя: {self.name}\nВозраст: {self.age}\nКурс: {self.course}\n")


class work(Person):
    def __init__(self, name, age, subject):
        super().__init__(name, age)
        self.subject = subject

    def show_info(self):
        print(f"Имя: {self.name}\nВозраст: {self.age}\nПредмет: {self.subject}\n")

person1 = Person("Данил", 22)
person1.show_info()

student1 = Student("Маша", 21, 2)
student1.show_info()

work = work("Степа", 45, "Мл.инженер")
work.show_info()
```

### Результат:
![Меню](https://github.com/snaklz/Software-engineering/blob/main/8.5.png)
