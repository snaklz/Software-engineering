# Тема 9. Базовые операции языка Python
Отчет по Теме #9 выполнил:
- Кузнецов Данил Дмитриевич
- ИНО ЗБ ПОАС-22-2

| Задание | Лаб_раб | Сам_раб |
| ------ | ------ | ------ |
| Задание 1 | - | + |


Работу проверили:
- к.э.н., доцент Панов М.А.
## Самостоятельная работа №1
### Задание Садовник и помидоры.
1) Вызовите справку по садоводству
2) Создайте объекты классов TomatoBush и Gardener
3) Используя объект класса Gardener, поухаживайте за кустом с помидорами
4) Попробуйте собрать урожай, когда томаты еще не дозрели. Продолжайте ухаживать за ними
5) Соберите урожай
Результатом работы вашей программы будет листинг кода с подробными комментариями и скриншоты выполенния всех тестов.

```python
class Tomato:
    states = ['отсутствует', 'цветение', 'зеленый', 'красный']
    def __init__(self, index):
        self._index = index
        self._state = Tomato.states[0]

    def grow(self):
        self._state = Tomato.states[(Tomato.states.index(self._state) + 1) % len(Tomato.states)]

    def is_ripe(self):
        return self._state == 'красный'

class TomatoBush:
    # Список всех томатов
    def __init__(self, num_tomatoes):
        self.tomatoes = [Tomato(i) for i in range(num_tomatoes)]

    def grow_all(self):
        for tomato in self.tomatoes:
            tomato.grow()

    def all_are_ripe(self):
        return all(tomato.is_ripe() for tomato in self.tomatoes)

    def give_away_all(self):
        self.tomatoes = []

class Gardener:
    def __init__(self, name, plant):
        self.name = name
        self._plant = plant

    def work(self):
        self._plant.grow_all()
        print(f'{self.name} Позаботился(ась) о растении.')

    def harvest(self):
        if self._plant.all_are_ripe():
            print(f'Томаты красные. {self.name} собрал(а) урожай.')
            self._plant.give_away_all()
        else:
            print('Томаты ещё не красные')

    @staticmethod
    def knowledge_base():
        print('Справка по садоводству')


Gardener.knowledge_base()

tomato_bush = TomatoBush(int(input('Сколько томатов на кусте?: ')))
gardener = Gardener(input('Ваше имя: '), tomato_bush)

while len(tomato_bush.tomatoes) != 0:
    action = int(input('Выберите действие: 1 - позаботиться о саде; 2 - Попробовать собрать урожай: '))
    if action == 1:
        gardener.work()
    elif action == 2:
        gardener.harvest()
        print()
    else:
        print('Ошибка')
```
### Результат:
![Меню](https://github.com/snaklz/Software-engineering/blob/main/9.png)
Полный вывод с консоли:
![Меню](https://github.com/snaklz/Software-engineering/blob/main/9.1.png)
