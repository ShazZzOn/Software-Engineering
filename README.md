>Отчет по Теме #8 выполнил:
- Губанов Артём Юрьевич
- ИВТ-23-1

| Задание | Лаб_раб | Сам_раб |
| ------ | ------ | ------ |
| Задание 1 | + | + |
| Задание 2 | + | + |
| Задание 3 | + | + |
| Задание 4 | + | + |
| Задание 5 | + | + |

## Лабораторная работа №8
### Создайте класс “Car” с атрибутами производитель и модель. Создайте объект этого класса. Напишите комментарии для кода, объясняющие его работу.
```python
class Car:
    def __init__(self, make, model):
        self.make = make
        self.model = model
my_car = Car("Toyota", "Corolla")
```
### Результат.
<img width="2559" height="1591" alt="1" src="https://github.com/user-attachments/assets/ef7a4e9f-a9a2-48dd-8b31-5af073f2594e" />

## Выводы
1. `class Car:`: создаётся класс Car, который описывает объект «автомобиль».
2. `def __init__(self, make, model):`: конструктор класса, вызывается при создании нового объекта.
3. `self.make = make`: сохраняет марку автомобиля в атрибут make.
4. `self.model = model`: сохраняет модель автомобиля в атрибут model.
5. `my_car = Car("Toyota", "Corolla")`: создаётся объект my_car класса Car с маркой "Toyota" и моделью "Corolla".

### Дополните код из первого задания, добавив в него атрибуты и методы класса, заставьте машину “поехать”. Напишите комментарии для кода, объясняющие его работу. 
```python
class Car:
    def __init__(self, make, model):
        self.make = make
        self.model = model
    def drive(self):
        print(f"Driving the {self.make} {self.model}")
my_car = Car("Toyota", "Corolla")
my_car.drive()
```
### Результат.
<img width="2554" height="1598" alt="image" src="https://github.com/user-attachments/assets/0ad435f8-d829-4f0c-ad1d-58e13579ca99" />

## Выводы
1. `class Car:`: объявляется класс Car, описывающий автомобиль.
2. `def __init__(self, make, model):`: конструктор, который задаёт свойства при создании объекта.
3. `self.make = make`: сохраняет марку автомобиля.
4. `self.model = model`: сохраняет модель автомобиля.
5. `def drive(self):`: метод класса, который описывает действие «ехать».
6. `print(f"Driving the {self.make} {self.model}")`: выводит сообщение с маркой и моделью автомобиля.
7. `my_car = Car("Toyota", "Corolla")`: создаётся объект my_car с маркой "Toyota" и моделью "Corolla".
8. `my_car.drive()`: вызывает метод drive()

### Создайте новый класс “ElectricCar” с методом “charge” и атрибутом емкость батареи. Реализуйте его наследование от класса, созданного в первом задании. Заставьте машину поехать, а потом заряжаться.
```python
class ElectricCar(Car):
    def __init__(self, make, model, battery_capacity):
        super().__init__(make, model)
        self.battery_capacity = battery_capacity
    def charge(self):
        print(f"Charging the {self.make} {self.model} with {self.battery_capacity} kWh")
my_electric_car = ElectricCar("Tesla", "Model S", 75)
my_electric_car.drive()
my_electric_car.charge()
```
### Результат.
<img width="2559" height="1599" alt="image" src="https://github.com/user-attachments/assets/2b0ee3be-58b1-42f2-be51-ea935a72f6ea" />

## Выводы
1. `class ElectricCar(Car):`: создаётся класс ElectricCar, который наследуется от класса Car.
2. `def __init__(self, make, model, battery_capacity):`: конструктор, принимающий марку, модель и ёмкость батареи.
3. `super().__init__(make, model)`: сохраняет марку автомобиля.
4. `self.battery_capacity = battery_capacity`: сохраняет модель автомобиля.
5. `def charge(self):`: метод класса, который описывает действие «ехать».
6. `print(f"Charging the {self.make} {self.model} with {self.battery_capacity} kWh")`: выводит сообщение с маркой и моделью автомобиля.
7. `my_electric_car = ElectricCar("Tesla", "Model S", 75)`: создаётся объект my_car с маркой "Toyota" и моделью "Corolla".
8. `my_electric_car.drive()`: вызывает метод drive() из родительского класса Car.
9. `my_electric_car.charge()`: вызывает метод charge() из текущего класса.
    
### Реализуйте инкапсуляцию для класса, созданного в первом задании. Создайте защищенный атрибут производителя и приватный атрибут модели. Вызовите защищенный атрибут и заставьте машину поехать. Напишите комментарии для кода, объясняющие его работу.
```python
class Car:
    def __init__(self, make, model):
        self._make = make 
        self.__model = model 
        def drive(self):
            print(f"Driving the {self._make} {self.__model}")
my_car = Car("Toyota", "Corolla")
print(my_car._make) 
my_car.drive()
```
### Результат.
<img width="2559" height="1599" alt="image" src="https://github.com/user-attachments/assets/b058eb4f-6b97-434b-adf1-07e9c2104ef1" />

## Выводы
1. `class Car:`: создаётся класс Car, описывающий автомобиль.
2. `def __init__(self, make, model):`: конструктор, вызываемый при создании объекта.
3. `self._make = make `: атрибут _make с одним подчёркиванием (защищённый), хранит марку автомобиля.
4. `self.__model = model`: атрибут __model с двумя подчёркиваниями (приватный), хранит модель автомобиля.
5. `def drive(self):`: метод, описывающий действие "ехать".
6. `print(f"Driving the {self._make} {self.__model}")`: выводит марку и модель автомобиля.
7. `my_car = Car("Toyota", "Corolla")`: создаётся объект my_car с параметрами "Toyota" и "Corolla".
8. `print(my_car._make)`: выводит значение защищённого атрибута _make.
9. `my_car.drive()`: вызывает метод drive() для объекта my_car.

### Реализуйте полиморфизм создав основной (общий) класс “Shape”, а также еще два класса “Rectangle” и “Circle”. Внутри последних двух классов реализуйте методы для подсчета площади фигуры. После этого создайте массив с фигурами, поместите туда круг и прямоугольник, затем при помощи цикла выведите их площади.
```python
class Shape:
    def area(self):
        pass
class Rectangle(Shape):
    def __init__(self, width, height):
        self.width = width
        self.height = height
    def area(self):
        return self.width * self.height
class Circle(Shape):
    def __init__(self, radius):
        self.radius = radius
    def area(self):
        return 3.14 * self.radius * self.radius
```
### Результат.
<img width="2559" height="1599" alt="image" src="https://github.com/user-attachments/assets/cd09346a-1f2e-4c3a-967b-cbc805f4fc65" />

## Выводы
1. `class Shape:`: создаётся базовый класс Shape, который служит шаблоном для фигур.
2. `def area(self):`: метод-заглушка, который должен быть переопределён в подклассах.
3. `pass`: 
4. `class Rectangle(Shape):`: создаётся класс Rectangle, наследующий Shape.
5. `def __init__(self, width, height):`: конструктор, принимающий ширину и высоту прямоугольника.
6. `self.width = width`: сохраняет ширину прямоугольника.
7. `self.height = height`: сохраняет высоту прямоугольника.
8. `def area(self):`: переопределяет метод area, вычисляя площадь прямоугольника.
9. `return self.width * self.height`: возвращает произведение ширины и высоты.
10. `class Circle(Shape):`: создаётся класс Circle, наследующий Shape.
11. `def __init__(self, radius):`: конструктор, принимающий радиус круга.
12. `self.radius = radius`: сохраняет радиус круга.
13. `def area(self):`:переопределяет метод area, вычисляя площадь круга.
14. `return 3.14 * self.radius * self.radius`: возвращает площадь круга по формуле.

## Самостоятельнаяработа №8
### Самостоятельно создайте класс и его объект. Они должны отличаться, от тех, что указаны в теоретическом материале (методичке) и лабораторных заданиях.
```python
class Book:
    def __init__(self, title, author, year):
        self.title = title
        self.author = author
        self.year = year
book1 = Book("Мастер и Маргарита", "Михаил Булгаков", 1966)
print(f"Название: {book1.title}")
print(f"Автор: {book1.author}")
print(f"Год издания: {book1.year}")
```
### Результат.
<img width="2559" height="1599" alt="image" src="https://github.com/user-attachments/assets/0d26fd0a-4134-408f-89dd-4f95dc151205" />

## Выводы
1. `class Book:`: создаётся класс Book, описывающий книгу.
2. `def __init__(self, title, author, year):`: конструктор, который задаёт основные свойства книги.
3. `self.title = title`: сохраняет название книги.
4. `self.author = author`: сохраняет имя автора.
5. `self.year = year`: сохраняет год издания.
6. `book1 = Book("Мастер и Маргарита", "Михаил Булгаков", 1966)`: создаётся объект book1 с указанными параметрами.
7. `print(f"Название: {book1.title}")`: выводит название книги.
8. `print(f"Автор: {book1.author}")`: выводит имя автора.
9. `print(f"Год издания: {book1.year}")`: выводит год издания книги.

### Самостоятельно создайте атрибуты и методы для ранее созданного класса. Они должны отличаться, от тех, что указаны в теоретическом материале (методичке) и лабораторных заданиях.
```python
class Book:
    def __init__(self, title, author, year, pages):
        self.title = title
        self.author = author
        self.year = year
        self.pages = pages
    def book_info(self):
        return f"'{self.title}' ({self.year}) — {self.author}, {self.pages} стр."
    def is_long(self):
        return self.pages > 300
book1 = Book("Мастер и Маргарита", "Михаил Булгаков", 1966, 480)
print(book1.book_info())
print("Толстая книга?" , "Да" if book1.is_long() else "Нет")
```
### Результат.
<img width="2543" height="1596" alt="Сам2" src="https://github.com/user-attachments/assets/2dd32ced-4865-44da-adf8-ad25a7f8ee57" />

## Выводы
1. `class Book:`: создаётся класс Book, описывающий книгу.
2. `def __init__(self, title, author, year, pages):`: конструктор, принимающий название, автора, год издания и количество страниц.
3. `self.title = title`: сохраняет название книги.
4. `self.author = author`: сохраняет имя автора.
5. `self.year = year`:  сохраняет год издания.
6. `self.pages = pages`: сохраняет количество страниц.
7. `def book_info(self):`: метод, возвращающий строку с информацией о книге.
8. `return f"'{self.title}' ({self.year}) — {self.author}, {self.pages} стр."`: форматирует и возвращает информацию о книге.
9. `def is_long(self):`: метод, проверяющий, является ли книга "толстой".
10. `return self.pages > 300`: возвращает True, если страниц больше 300, иначе False.
11. `book1 = Book("Мастер и Маргарита", "Михаил Булгаков", 1966, 480)`: создаётся объект книги book1 с указанными параметрами.
12. `print(book1.book_info())`: выводит информацию о книге.
13. `print("Толстая книга?" , "Да" if book1.is_long() else "Нет")`: выводит, является ли книга "толстой" в зависимости от количества страниц.

### Самостоятельно реализуйте наследование, продолжая работать с ранее созданным классом. Оно должно отличаться, от того, что указано в теоретическом материале (методичке) и лабораторных заданиях.
```python
class Book:
    def __init__(self, title, author, year, pages):
        self.title = title
        self.author = author
        self.year = year
        self.pages = pages
    def book_info(self):
        return f"'{self.title}' ({self.year}) — {self.author}, {self.pages} стр."
class EBook(Book):
    def __init__(self, title, author, year, pages, file_size):
        super().__init__(title, author, year, pages)
        self.file_size = file_size
    def book_info(self):
        return f"Электронная книга: '{self.title}' ({self.year}), размер файла: {self.file_size} МБ"
ebook1 = EBook("Война и мир", "Лев Толстой", 1869, 1225, 5.4)
print(ebook1.book_info())
```
### Результат.
<img width="2559" height="1594" alt="image" src="https://github.com/user-attachments/assets/9539f92e-ca7e-40a5-b1f6-df75edfc5f37" />

## Выводы
1. `class Book:`: создаётся базовый класс Book, описывающий обычную книгу.
2. `def __init__(self, title, author, year, pages):`: конструктор принимает название, автора, год издания и количество страниц.
3. `self.title = title`: сохраняет название книги в атрибут title.
4. `self.author = author`: сохраняет имя автора в атрибут author.
5. `self.year = year`: охраняет год издания книги в атрибут year.
6. `self.pages = pages`: сохраняет количество страниц книги в атрибут pages.
7. `def book_info(self):`: метод, возвращающий информацию о книге в виде строки.
8. `return f"'{self.title}' ({self.year}) — {self.author}, {self.pages} стр."`: форматирует и возвращает строку с информацией о книге.
9. `class EBook(Book):`: создаётся класс EBook, который наследует Book и предназначен для электронных книг.
10. `def __init__(self, title, author, year, pages, file_size):`:  конструктор для электронных книг, принимает параметры обычной книги и размер файла.
11. `super().__init__(title, author, year, pages)`: вызывает конструктор родительского класса Book, чтобы инициализировать стандартные свойства книги.
12. `self.file_size = file_size`: сохраняет размер файла электронного издания в атрибут file_size.
13. `def book_info(self):`: метод переопределяет book_info для электронных книг.
14. `return f"Электронная книга: '{self.title}' ({self.year}), размер файла: {self.file_size} МБ"`: возвращает строку с информацией об электронном издании.
15. `ebook1 = EBook("Война и мир", "Лев Толстой", 1869, 1225, 5.4)`: создаётся объект ebook1 класса EBook с указанными параметрами: название, автор, год, страницы и размер файла.
16. `print(ebook1.book_info())`: вызывает метод book_info() объекта ebook1 и выводит информацию об электронной книге.

### Самостоятельно реализуйте инкапсуляцию, продолжая работать с ранее созданным классом. Она должна отличаться, от того, что указана в теоретическом материале (методичке) и лабораторных заданиях.
```python
class BankAccount:
    def __init__(self, owner, balance):
        self.owner = owner
        self.__balance = balance
    def deposit(self, amount):
        if amount > 0:
            self.__balance += amount
    def withdraw(self, amount):
        if 0 < amount <= self.__balance:
            self.__balance -= amount
    def get_balance(self):
        return self.__balance
acc = BankAccount("Иван Петров", 1000)
acc.deposit(500)
acc.withdraw(300)
print(f"Баланс счёта {acc.owner}: {acc.get_balance()} руб.")
```
### Результат.

## Выводы
1. `class BankAccount:`: создаётся класс BankAccount, описывающий банковский счёт.
2. `def __init__(self, owner, balance):`: конструктор класса, принимает имя владельца и начальный баланс.
3. `self.owner = owner`: сохраняет имя владельца счёта.
4. `self.__balance = balance`: сохраняет баланс счёта в приватный атрибут __balance.
5. `def deposit(self, amount):`: метод для пополнения счёта.
6. `if amount > 0:`: проверяет, что сумма положительная.
7. `self.__balance += amount`: добавляет сумму к балансу счёта.
8. `def withdraw(self, amount):`: метод для снятия денег со счёта.
9. `if 0 < amount <= self.__balance:`: проверяет, что сумма положительная и не превышает баланс.
10. `self.__balance -= amount`: вычитает сумму из баланса.
11. `def get_balance(self):`: метод для получения текущего баланса.
12. `return self.__balance`: возвращает текущее значение баланса.
13. `acc = BankAccount("Иван Петров", 1000)`: создаётся объект acc с владельцем "Иван Петров" и начальным балансом 1000 руб.
14. `acc.deposit(500)`: пополняет счёт на 500 руб.
15. `acc.withdraw(300)`: снимает со счёта 300 руб.
16. `print(f"Баланс счёта {acc.owner}: {acc.get_balance()} руб.")`: выводит текущий баланс владельца счёта.

### Самостоятельно реализуйте инкапсуляцию, продолжая работать с ранее созданным классом. Она должна отличаться, от того, что указана в теоретическом материале (методичке) и лабораторных заданиях.
```python
class Animal:
    def speak(self):
        return "Животное издаёт звук"
class Dog(Animal):
    def speak(self):
        return "Собака лает"
class Cat(Animal):
    def speak(self):
        return "Кошка мяукает"
class Cow(Animal):
    def speak(self):
        return "Корова мычит"
animals = [Dog(), Cat(), Cow()]
for animal in animals:
    print(animal.speak())
```
### Результат.
<img width="2558" height="1599" alt="image" src="https://github.com/user-attachments/assets/4ecf1eaf-d8b1-455b-9700-c9ba5b1d25c3" />

## Выводы
1. `class Animal:`: создаётся базовый класс Animal, представляющий животное.
2. `def speak(self):`: метод, который должен возвращать звук, издаваемый животным.
3. `return "Животное издаёт звук"`: возвращает строку с общим звуком животного.
4. `class Dog(Animal):`: создаётся класс Dog, наследующий Animal.
5. `def speak(self):`: переопределяет метод speak для собаки.
6. `return "Собака лает"`: возвращает звук собаки.
7. `class Cat(Animal):`: создаётся класс Cat, наследующий Animal.
8. `def speak(self):`: переопределяет метод speak для кошки.
9. `return "Кошка мяукает"`: возвращает звук кошки.
10. `class Cow(Animal):`: создаётся класс Cow, наследующий Animal.
11. `def speak(self):`: переопределяет метод speak для коровы.
12. `return "Корова мычит"`: возвращает звук коровы.
13. `animals = [Dog(), Cat(), Cow()]`: создаётся список объектов животных: собака, кошка, корова.
14. `for animal in animals:`: начинается цикл по списку животных.
15. `print(animal.speak())`: вызывает метод speak() для каждого объекта, выводя соответствующий звук.
