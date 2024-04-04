# Тема 7. Работа с файлами (ввод, вывод)
Отчет по Теме #7 выполнил:
- Удовиченко Сергей Олегович
- ИНО ЗБ ПОАС 22-2

| Задание | Сам_раб |
| ------ | ------ |
| Задание 1 | + |
| Задание 2 | + |
| Задание 3 | + |
| Задание 4 | + |
| Задание 5 | + |

Работу проверили:
- к.э.н., доцент Панов М.А.
## Самостоятельная работы №7

### 1) Найдите в интернете любую статью (объем статьи не менее 200 слов), скопируйте ее содержимое в файл и напишите программу, которая считает количество слов в текстовом файле и определит самое часто встречающееся слово.

```python
words = []
dist_ = {}
with open(""C:/Users/Сергей/Desktop/text.txt", "r") as f:
  for i in f:
    word = i.lower().replace(",", "").replace(".", "").split(" ")

    for w in word:
      if w in dist_:
        dist_[w] += 1
      else:
        dist_[w] = 1
max_ = max(dist_.values())
final = {k: v for k, v in dist_.items() if v == max_}
final
```
### Результат:
  ![Меню](https://github.com/SergUdav/PI/blob/LR7/pic/1.png)

  ### 2) У вас появилась потребность в ведении книги расходов, посмотрев все существующие варианты вы пришли к выводу что вас ничего не устраивает и нужно все делать самому. Напишите программу для учета расходов. Программа должна позволять вводить информацию о расходах, сохранять ее в файл и выводить существующие данные в консоль. Ввод информации происходит через консоль.

```python
import os

def add_():
    amount = float(input("Введите сумму расхода: "))
    des = input("Введите описание расхода: ")

    with open("expenses.txt", "a") as file:
        file.write(f"{amount} | {des}\n")
    print("Расход успешно добавлен.")

def asds():
  with open("expenses.txt", "r") as file:
    print(file.read())

while True:
  print("1. Добавить расход")
  print("2. Просмотреть расходы")
  print("3. Выход")

  choice = input("Выберите действие: ")
  if choice == "1":
    add_()
  elif choice == "2":
    asds()
  elif choice == "3":
    break
  else:
    print("Неверный выбор. Попробуйте еще раз.")
```
### Результат:
  ![Меню](https://github.com/SergUdav/PI/blob/LR7/pic/2.png)

  ### 3) Имеется файл input.txt с текстом на латинице. Напишите программу, которая выводит следующую статистику по тексту: количество букв латинского алфавита; число слов; число строк.

```python
with open("input.txt", "r") as f:
  text = f.read()

  letters = sum(i.isalpha() for i in text)

  words = len(text.split())
with open("input.txt", "r") as f:
  lines = sum(1 for i in f)

  print(f"Input file contains:\n{letters} letters\n{words} words\n{lines} lines")
```
### Результат:
  ![Меню](https://github.com/SergUdav/PI/blob/LR7/pic/3.png)

  ### 4) Напишите программу, которая получает на вход предложение, выводит его в терминал, заменяя все запрещенные слова звездочками * (количество звездочек равно количеству букв в слове). Запрещенные слова, разделенные символом пробела, хранятся в текстовом файле input.txt. Все слова в этом файле записаны в нижнем регистре. Программа должна заменить запрещенные слова, где бы они ни встречались, даже в середине другого слова.

```python
word = "hello email python the exam wor is"
word = word.split()

with open("input.txt") as f:
  r = f.read()

  for wor in word:
    r = r.replace(wor, "*" * len(wor))
with open("input.txt", "w") as f:
  f.write(r)

with open("input.txt") as f:
  print(f.read())
```
### Результат:
  ![Меню](https://github.com/SergUdav/PI/blob/LR7/pic/4.png)

  ### 5) Самостоятельно придумайте и решите задачу, которая будет взаимодействовать с текстовым файлом.

```python
word = ["assad", "qw3r3", "12321", "euh4377"]

with open("words.txt", "w") as f:
  for i in word:
    f.write(i + "\n")

with open("words.txt") as f:
  print(f.read())
```
### Результат:
  ![Меню](https://github.com/SergUdav/PI/blob/LR7/pic/5.png)
