>Отчет по Теме #9 выполнил:
- Губанов Артём Юрьевич
- ИВТ-23-1

| Задание | Лаб_раб | Сам_раб |
| ------ | ------ | ------ |
| Задание 1 | + | + |
| Задание 2 | + |   |
| Задание 3 | + |   |
| Задание 4 | + |   |
| Задание 5 | + |   |

## Лабораторная работа №9
### Допустим, что вы решили оригинально и немного странно познакомится с человеком. Для этого у вас должен быть написан свой класс на Python, который будет проверять угадал ваше имя человек или нет. Для этого создайте класс, указав в свойствах только имя. Дальше создайте функцию __init__(), а в ней сделайте проверку на то угадал человек ваше имя или нет. Также можете проверить что будет, если в этой функции указав атрибут, который не указан в вашем классе, например, попробуйте вызвать фамилию.
```python
class Ivan:                                  
    __slots__ = ('name',)                    
    def __init__(self, name):                
        self.name = name                     
        if name == 'Иван':                   
            print('Да, я Иван')              
        else:                                
            print(f'Не угадали, я не {name}, а Иван')  
person1 = Ivan('Алексей')                    
person2 = Ivan('Иван')                       
print(person2.name)                          
# person2.surname = 'Петров'                 
#                                            
```
### Результат.
<img width="2559" height="1599" alt="Лаб1" src="https://github.com/user-attachments/assets/7f23e4a7-1dae-42c4-a518-84131c5b3be3" />

## Выводы
1. `class Ivan:`: объявляем класс, описывающий «человека по имени Иван»
2. `__slots__ = ('name',)`: ограничиваем допустимые атрибуты экземпляра только кортежом ('name',)
3. `def __init__(self, name):`: конструктор; запускается при создании объекта
4. `self.name = name`: сохраняем переданное имя в разрешённый слот 'name'
5. `if name == 'Иван':`: сравниваем имя с эталоном
6. `print('Да, я Иван')`: если совпало — выводим подтверждение
7. `else:`: иначе — имя не угадали
8. `print(f'Не угадали, я не {name}, а Иван')`: печатаем сообщение c конкретным именем
9. `person1 = Ivan('Алексей')`: создаём первый объект; в __init__ выведется фраза «не угадали»
10. `person2 = Ivan('Иван')`: создаём второй объект; в __init__ выведется «Да, я Иван»
11. `print(person2.name)`: проверка доступа к допустимому атрибуту 'name'
12. `# person2.surname = 'Петров'`: попытка добавить запрещённый атрибут
13. `#`: вызовет AttributeError из-за __slots__
    
### Вам дали важное задание, написать продавцу мороженого программу, которая будет писать добавили ли топпинг в мороженое и цену после возможного изменения. Для этого вам нужно написать класс, в котором будет определяться изменили ли состав мороженого или нет. В этом классе реализуйте метод, выводящий на печать «Мороженое с {ТОППИНГ}» в случае наличия добавки, а иначе отобразится следующая фраза: «Обычное мороженое». При этом программа должна воспринимать как топпинг только атрибуты типа string.
```python
class Icecream:                                        
    def __init__(self, ingredient=None):               
        self.ingredient = ingredient if isinstance(ingredient, str) else None                 
    def composition(self):                             
        if self.ingredient:                            
            print(f"Мороженое с {self.ingredient}")    
        else:                                          
            print("Обычное мороженое")                 
icecream = Icecream()                                  
icecream.composition()                                 
icecream = Icecream('шоколадом')                       
icecream.composition()                                 
icecream = Icecream(100)                               
icecream.composition() 
```
### Результат.
<img width="2559" height="1599" alt="Лаб2" src="https://github.com/user-attachments/assets/8d7062e3-5870-449d-aec4-6ae8877e5732" />

## Выводы
1. `class Icecream:`: описываем «мороженое»
2. `def __init__(self, ingredient=None):`: конструктор; по умолчанию добавки нет
3. `self.ingredient = ingredient if isinstance(ingredient, str) else None`: если передан аргумент и он строка — сохраняем его; иначе пишем None
4. `def composition(self):`: метод, печатающий состав
5. `if self.ingredient:`: если топпинг задан (строка не пустая)
6. `print(f"Мороженое с {self.ingredient}") `: выводим «Мороженое с ...»
7. `else:`: иначе
8. `print("Обычное мороженое")`: выводим «Обычное мороженое»
9. `icecream = Icecream()`: экземпляр без аргументов → топпинга нет
10. `icecream.composition()`: печать состава (должно быть «Обычное мороженое»)
11. `icecream = Icecream('шоколадом')`: экземпляр с корректной строкой
12. `icecream.composition()`: печать состава (должно быть «с шоколадом»)
13. `icecream = Icecream(100)`: передаём число (не строка)
14. `icecream.composition()`: снова «Обычное мороженое»

### Петя – начинающий программист и на занятиях ему сказали реализовать икапсу…что-то. А вы хороший друг Пети и ко всему прочему прекрасно знаете, что икапсу…что-то – это инкапсуляция, поэтому решаете помочь вашему другу с написанием класса с инкапсуляцией. Ваш класс будет не просто инкапсуляцией, а классом с сеттером, геттером и деструктором. После написания класса вам необходимо продемонстрировать что все написанные вами функции работают. Также вас необходимо объяснить Пете почему на скриншоте ниже в консоли выводится ошибка.
```python
class MyClass:                                 
    def __init__(self, value):                 
        self._value = value                    
    def set_value(self, value):                
        self._value = value                    
    def get_value(self):                       
        return self._value                     
    def del_value(self):                       
        del self._value                        
    value = property(                          
        get_value,                             
        set_value,                             
        del_value,                             
        "Свойство value")                     
obj = MyClass(42)                              
print(obj.get_value())                         
obj.set_value(45)                              
print(obj.get_value())                         
obj.set_value(100)                             
obj.del_value()                                
# print(obj.get_value())                       
```
### Результат.
<img width="2559" height="1599" alt="Лаб3" src="https://github.com/user-attachments/assets/10bc9e01-de36-419a-ab26-4421ab237224" />

## Выводы
1. `class MyClass:`: класс-демо для инкапсуляции
2. `def __init__(self, value):`: конструктор принимает стартовое значение
3. `self._value = value`: «приватный по соглашению» атрибут
4. `def set_value(self, value):`: setter — задаёт новое значение
5. `self._value = value`: записываем в «приватный» атрибут
6. `def get_value(self):`: getter — возвращает текущее значение
7. `return self._value`: отдаём содержимое
8. `def del_value(self):`: deleter — удаляет атрибут
9. `del self._value`: оператор del снимает атрибут у объекта
10. `value = property(`: создаём объект-свойство с тремя методами
11. `get_value,`: функция чтения
12. `set_value,`: функция записи
13. `del_value,`: функция удаления
14. `"Свойство value")`: строка-докстринг для свойства
15. `obj = MyClass(42)`: создаём экземпляр с _value=42
16. `print(obj.get_value())`: 42 — читаем через getter
17. `obj.set_value(45)`: меняем значение на 45
18. `print(obj.get_value())`: 45 — проверяем
19. `obj.set_value(100)`: ещё раз меняем
20. `obj.del_value()`: удаляем атрибут _value целиком
21. ` print(obj.get_value())`: вызовет AttributeError: _value удалён

### Вам прекрасно известно, что кошки и собаки являются млекопитающими, но компьютер этого не понимает, поэтому вам нужно написать три класса: Кошки, Собаки, Млекопитающие. И при помощи “наследования” объяснить компьютеру что кошки и собаки – это млекопитающие. Также добавьте какой-нибудь свой атрибут для кошек и собак, чтобы показать, что они чем-то отличаются друг от друга.
```python
class Mammal:                               
    className = 'Mammal'                    
class Dog(Mammal):                          
    species = 'canine'                      
    sounds = 'wow'                          
class Cat(Mammal):                          
    species = 'feline'                      
    sounds = 'meow'                         
dog = Dog()                                 
print(f"Dog is {dog.className}, but they say {dog.sounds}")   
cat = Cat()                                 
print(f"Cat is {cat.className}, but they say {cat.sounds}")  
```
### Результат.
<img width="2559" height="1599" alt="Лаб4" src="https://github.com/user-attachments/assets/c9fd1667-6268-40f7-b25c-807db1074086" />

## Выводы
1. `class Mammal:`: базовый класс «Млекопитающее»
2. `className = 'Mammal'`: общая характеристика для всех потомков
3. `class Dog(Mammal):`: класс «Собака» наследует Mammal
4. `species = 'canine'`: свой атрибут — вид
5. `sounds = 'wow'`: свой атрибут — «говорит»
6. `class Cat(Mammal):`: класс «Кошка» наследует Mammal
7. `species = 'feline'`: свой атрибут — вид
8. `sounds = 'meow'`: свой атрибут — «говорит»
9. `dog = Dog()`: экземпляр собаки
10. `print(f"Dog is {dog.className}, but they say {dog.sounds}")`: унаследованный className + свой звук
11. `cat = Cat()`: экземпляр кошки
12. `print(f"Cat is {cat.className}, but they say {cat.sounds}")`: аналогично для кошки

### На разных языках здороваются по-разному, но суть остается одинаковой, люди друг с другом здороваются. Давайте вместе с вами реализуем программу с полиморфизмом, которая будет описывать всю суть первого предложения задачи. Для этого мы можем выбрать два языка, например, русский и английский и написать для них отдельные классы, в которых будет в виде атрибута слово, которым здороваются на этих языках. А также напишем функцию, которая будет выводить информацию о том, как на этих языках здороваются. Заметьте, что для решения поставленной задачи мы использовали декоратор @staticmethod, поскольку нам не нужны обязательные параметры-ссылки вроде self.
```python
class Russian:                              
    @staticmethod                           
    def greeting():                         
        print("Привет")                     
class English:                              
    @staticmethod                           
    def greeting():                         
        print("Hello")                      
def greet(language):                        
    language.greeting()                     
ivan = Russian()                            
greet(ivan)                                 
john = English()                            
greet(john)                                 
```
### Результат.
<img width="2559" height="1599" alt="Лаб5" src="https://github.com/user-attachments/assets/d5222707-22fe-4758-8a7e-1fb4dce67773" />

## Выводы
1. `class Russian:`: класс для «русского языка»
2. `@staticmethod`: метод, независимый от экземпляра 
3. `def greeting():`: интерфейс «как здороваемся»
4. `print("Привет")`: конкретная реализация
5. `class English:`: класс для «английского языка»
6. `@staticmethod`: снова статический метод
7. `def greeting():`: та же «форма» метода
8. `print("Hello")`: но другая реализация
9. `def greet(language):`: полиморфная функция — принимает любой «язык»
10. `language.greeting()`: вызывает одноимённый метод, не заботясь о типе
11. `ivan = Russian()`: объект «русский»
12. `greet(ivan)`: печатает «Привет»
13. `john = English()`: объект «английский»
14. `greet(john)`: печатает «Hello»

## Самостоятельная работа №9
### 1) Создайте класс Tomato 2) Создайте статическое свойство states, которое будет содержать все стадии созревания помидора 3) Создайте метод __init__(), внутри которого будут определены два динамических свойства: _index (передается параметром) и _state (принимает первое значение из словаря states). После написания этого блока кода в комментарии к нему укажите какими являются эти два свойства 4) Создайте метод grow(), который будет переводить томат на следующую стадию созревания 5) Создайте метод is_ripe(), который будет проверять, что томат созрел
```python
class Tomato:                                             
    """Один помидор: индекс и стадия созревания."""       
    states = ('отсутствует', 'цветение', 'зелёный', 'красный')  
    def __init__(self, index: int):                       
        self._index = index                               
        self._state = Tomato.states[0]                    
    def grow(self):                                       
        i = Tomato.states.index(self._state)              
        if i < len(Tomato.states) - 1:                    
            self._state = Tomato.states[i + 1]            
    def is_ripe(self) -> bool:                            
        return self._state == Tomato.states[-1]           
    def __repr__(self):                                   
        return f"Tomato({self._index}, state='{self._state}')"   
class TomatoBush:                                          
    def __init__(self, count: int):                       
        self.tomatoes = [Tomato(i + 1) for i in range(count)]   
    def grow_all(self):                                   
        for t in self.tomatoes:                           
            t.grow()                                      
    def all_are_ripe(self) -> bool:                       
        return all(t.is_ripe() for t in self.tomatoes)    
    def give_away_all(self):                              
        self.tomatoes.clear()                             
class Gardener:                                           
    @staticmethod                                        
    def knowledge_base():                                 
        print("Справка: поливайте и ухаживайте — куст перейдёт через стадии:",", ".join(Tomato.states))                   
    def __init__(self, name: str, plant: TomatoBush):     
        self.name = name                                  
        self._plant = plant                               
    def work(self):                                       
        print(f"{self.name} ухаживает за кустом…")        
        self._plant.grow_all()                            
    def harvest(self):                                    
        if self._plant.all_are_ripe():                    
            print(f"{self.name} собирает урожай!")        
            self._plant.give_away_all()                   
        else:                                             
            print("Предупреждение: есть неспелые плоды — рано собирать.")  
    def __repr__(self):                                   
        return f"Gardener({self.name})"                   
Gardener.knowledge_base()                                  
bush = TomatoBush(3)                                       
g = Gardener("Анна", bush)                                 
g.work()                                                   
print(bush.tomatoes)                                      
g.harvest()                                               
g.work()                                                  
print(bush.tomatoes)                                      
g.harvest()                                               
g.work()                                                  
print(bush.tomatoes)                                      
g.harvest()                                               
print("Состояние после сбора:", bush.tomatoes)                                      
```
### Результат.
<img width="2559" height="1599" alt="Сам1" src="https://github.com/user-attachments/assets/181ce157-dc99-4036-804b-b9b7b42a9ca8" />

## Выводы
1. `class Tomato:`: описывает один помидор
2. `"""Один помидор: индекс и стадия созревания.""" `: докстринг для читаемости
3. `states = ('отсутствует', 'цветение', 'зелёный', 'красный') `: статическое свойство со всеми стадиями
4. `def __init__(self, index: int):`: конструктор принимает порядковый номер плода
5. `self._index = index`: «приватный» индекс плода 
6. `self._state = Tomato.states[0]`: начальная стадия — первая из списка states
7. `def grow(self):`: переводит плод на следующую стадию
8. `i = Tomato.states.index(self._state)`: находим текущую позицию стадии в кортеже
9. `if i < len(Tomato.states) - 1:`: если это не последняя стадия
10. `self._state = Tomato.states[i + 1]`: двигаем состояние на один шаг вперёд
11. `def is_ripe(self) -> bool:`: проверяет, дозрел ли помидор
12. `return self._state == Tomato.states[-1]`: True, если стадия — последняя 
13. `def __repr__(self):`: «служебное» представление для печати списков
14. `return f"Tomato({self._index}, state='{self._state}')"`: удобная строка со стадией
15. `class TomatoBush:`: куст содержит несколько помидоров
16. `def __init__(self, count: int):`: конструктор принимает количество плодов
17. `self.tomatoes = [Tomato(i + 1) for i in range(count)]`: создаём список объектов Tomato 
18. `def grow_all(self):`: все помидоры растут на шаг
19. `for t in self.tomatoes:`: перебираем каждый плод
20. `t.grow()`: переводим его на следующую стадию
21. `def all_are_ripe(self) -> bool:`: True, если все плоды дозрели
22. `return all(t.is_ripe() for t in self.tomatoes)`: проверяем методом is_ripe у каждого плода
23. `def give_away_all(self):`: «сбор урожая»: очищаем список плодов
24. `self.tomatoes.clear()`: удаляем все элементы списка на кусте
25. `class Gardener:`: садовник ухаживает за растением
26. `@staticmethod`: справка — статический метод, не требует self
27. `def knowledge_base():`: выводит базовые советы
28. `print("Справка: поливайте и ухаживайте — куст перейдёт через стадии:",", ".join(Tomato.states))`: соединяем стадии в строку
29. `def __init__(self, name: str, plant: TomatoBush):`: конструктор принимает имя и объект куста
30. `self.name = name`: публичное динамическое свойство — имя садовника
31. `self._plant = plant`: «приватное» динамическое свойство — ссылка на куст
32. `def work(self):`: работа садовника: ухаживать за растением
33. `print(f"{self.name} ухаживает за кустом…")`: информируем о действии
34. `self._plant.grow_all()`: просим куст «расти» — все плоды переходят на шаг
35. `def harvest(self):`: попытка собрать урожай
36. `if self._plant.all_are_ripe():`: если все плоды дозрели
37. `print(f"{self.name} собирает урожай!")`: сообщение об успешном сборе
38. `self._plant.give_away_all()`: очищаем список плодов на кусте
39. `else:`: иначе
40. `print("Предупреждение: есть неспелые плоды — рано собирать.")`: предупреждаем пользователя
41. `def __repr__(self):`: наглядное представление объекта Gardener
42. `return f"Gardener({self.name})"`: возвращаем строку с именем
43. `Gardener.knowledge_base()`: выводим справку по садоводству
44. `bush = TomatoBush(3)`: создаём куст с тремя помидорами
45. `g = Gardener("Анна", bush)`: создаём садовника Анну, привязываем куст
46. `g.work()`: первый цикл ухода: все плоды переходят на «цветение»
47. `print(bush.tomatoes)    `: печать текущих состояний плодов
48. `g.harvest()`: пробуем собрать — ещё рано
49. `g.work()`: второй цикл ухода: «зелёный»
50. `print(bush.tomatoes)`: печать текущих состояний
51. `g.harvest()`: всё ещё рано
52. `g.work()`: третий цикл ухода: «красный»
53. `print(bush.tomatoes)`: проверяем: все «красные»
54. `g.harvest()`: теперь можно собирать — список очистится
55. `print("Состояние после сбора:", bush.tomatoes)`: убеждаемся, что плодов на кусте не осталось
