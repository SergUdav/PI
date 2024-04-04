# Тема 9. Концепции и принципы ООП
Отчет по Теме #9 выполнил:
- Удовиченко Сергей Олегович
- ИНО ЗБ ПОАС 22-2

| Задание | Сам_раб |
| ------ | ------ |
| Задание 1 | + |

Работу проверили:
- к.э.н., доцент Панов М.А.
## Самостоятельная работы №9

```python
class Tomato:
    def __init__(self, index):
        self._index = index # Индекс томата, он приватный
        self._state = "отсутствует" # Стадия созревания помидора, он приватный

    # Переход на следующую стадию созревания
    def grow(self):
        if self._state == "отсутствует":
            self._state = "цветение"
        elif self._state == "цветение":
            self._state = "зеленый"
        elif self._state == "зеленый":
            self._state = "красный"

    # Метод для проверки, что помидор созрел
    def is_ripe(self):
        return self._state == "красный"

class TomatoBush:
    def __init__(self, num_tomatoes):
        # Создание списка помидоров
        self.tomatoes = [Tomato(i) for i in range(num_tomatoes)]

    # Ростим все помиды
    def grow_all(self):
        for tomato in self.tomatoes:
            tomato.grow()

    # Проверяем, что все помидоры в кусте созрели
    def all_are_ripe(self):
        return all(tomato.is_ripe() for tomato in self.tomatoes)

    # Очистки списка помидоров
    def give_away_all(self):
        self.tomatoes = []

class Gardener:
    def __init__(self, name, plant):
        self.name = name # Имя садовника, он публичный
        self._plant = plant # Растение, за которым ухаживает садовник, он приватный

    # Метод для ухаживания за растением, что позволяет ему становиться более зрелым
    def work(self):
        self._plant.grow_all()

    # Метод для сбора урожая, если все плоды созрели
    def harvest(self):
        if self._plant.all_are_ripe():
            print(f"{self.name} собрал урожай.")
            self._plant.give_away_all()
        else:
            print("Томаты еще не дозрели.")

list_tom = TomatoBush(5)
gardener = Gardener("Сергей", list_tom) # Создание садовника

gardener.work()

gardener.harvest() # Cборе урожая

gardener.work()
gardener.work() # Рост каждого помидор в кусте

gardener.harvest() # Cборе урожая
```

## Результат:
![Меню](https://github.com/SergUdav/PI/blob/LR9/pic/1.png)

