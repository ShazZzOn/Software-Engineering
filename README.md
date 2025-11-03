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
