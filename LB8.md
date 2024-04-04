# Тема 8. Введение в ООП
Отчет по Теме #8 выполнил:
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
## Самостоятельная работы №8

### 1) Самостоятельно создайте класс и его объект.


### 2) Самостоятельно создайте атрибуты и методы для ранее созданного класса
```python
class Book:
    def __init__(self, title, author, year):
        self.title = title
        self.author = author
        self.year = year

    def info(self):
        return f"Title: {self.title},\nAuthor: {self.author},\nYear Published: {self.year}"

my_boot = Book("lalal", "qweww", 1888)
print(my_boot.info())
```
### Результат:
  ![Меню](https://github.com/SergUdav/PI/blob/LR8/pic/2.png)

  ### 3) Самостоятельно реализуйте наследование, продолжая работать с ранее созданным классом.

```python
class Book:
    def __init__(self, title, author, year):
        self.title = title
        self.author = author
        self.year = year

    def info(self):
        return f"Title: {self.title},\nAuthor: {self.author},\nYear Published: {self.year}"
class Form_Book(Book):
  def __init__(self, title, author, year, file_form):
      super().__init__(title, author, year)
      self.file_form = file_form

  def info(self):
    return super().info() + f"\nfile_form: {self.file_form}"

my_boot = Form_Book("lalal", "qweww", 1888, "zip")
print(my_boot.info())
```
### Результат:
  ![Меню](https://github.com/SergUdav/PI/blob/LR8/pic/3.png)

  ### 4) Самостоятельно реализуйте инкапсуляцию, продолжая работать с ранее созданным классом.

```python
class Book:
  def __init__(self, title, author, year_published):
    self.__title = title
    self.__author = author
    self.__year_published = year_published

  def get_title(self):
    return self.__title
  def get_author(self):
    return self.__author
  def get_year(self):
    return self.__year_published

  def info(self):
    return f"Title: {self.get_title()},\nAuthor: {self.get_author()},\nYear Published: {self.get_year()}"

my_boot = Book("lalal", "qweww", 1888)
print(my_boot.info())
```
### Результат:
  ![Меню](https://github.com/SergUdav/PI/blob/LR8/pic/4.png)

  ### 5) Cамостоятельно реализуйте полиморфизм

```python
class Aqq:
    def __init__(self, asdads, model):
        self.asdads = asdads
        self.model = model

    def mo(self):
        pass

class Cat(Aqq):
  def mo(self):
    return f"asdq: {self.asdads}, as {self.model}"

cat = Cat("12", "11qq")
print(cat.mo())
```
### Результат:
  ![Меню](https://github.com/SergUdav/PI/blob/LR8/pic/5.png)

