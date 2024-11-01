Python 的基础语句涵盖了变量赋值、数据类型、条件控制、循环、函数等基础知识。以下是一些常用的基础 Python 语句。

## 1. 变量赋值与数据类型

Python 是动态类型语言，可以直接声明并赋值变量，常见的数据类型有 `int`、`float`、`str`、`list`、`dict`、`bool` 等。

```python
# 整数和浮点数
x = 5           # 整数
y = 3.14        # 浮点数

# 字符串
name = "Alice"

# 布尔类型
is_active = True

# 列表
numbers = [1, 2, 3, 4, 5]

# 字典
person = {"name": "Alice", "age": 25}
```

## 2. 条件控制

Python 使用 `if-elif-else` 进行条件控制。

```python
age = 18
if age >= 18:
    print("成年人")
elif age >= 13:
    print("青少年")
else:
    print("儿童")
```

## 3. 循环

#### `for` 循环
用于遍历列表、字符串、字典等可迭代对象。

```python
# 遍历列表
for num in numbers:
    print(num)

# 使用 range() 函数
for i in range(5):
    print(i)  # 输出 0 到 4
```

#### `while` 循环
在条件为 `True` 时循环执行代码。

```python
count = 0
while count < 5:
    print(count)
    count += 1
```

## 4. 函数

函数通过 `def` 关键字定义。

```python
def greet(name):
    return f"Hello, {name}!"

print(greet("Alice"))  # 输出：Hello, Alice!
```

## 5. 列表与字典操作

- 列表操作：增删改查、排序等。
- 字典操作：增删键值对、查找等。

```python
# 列表
fruits = ["apple", "banana", "cherry"]
fruits.append("orange")   # 添加元素
fruits.remove("banana")   # 移除元素
print(fruits[0])          # 访问元素

# 字典
person["gender"] = "female"   # 添加键值对
print(person.get("name"))     # 获取键对应的值
del person["age"]             # 删除键值对
```

## 6. 文件操作

用于读写文件。

```python
# 写入文件
with open("example.txt", "w") as f:
    f.write("Hello, World!")

# 读取文件
with open("example.txt", "r") as f:
    content = f.read()
    print(content)
```

## 7. 异常处理

Python 使用 `try-except` 捕获异常，避免程序因错误而崩溃。

```python
try:
    result = 10 / 0
except ZeroDivisionError:
    print("不能除以零")
finally:
    print("执行结束")
```

## 8. 列表解析（List Comprehensions）

列表解析是 Python 中简洁地创建新列表的语法。

```python
squares = [x ** 2 for x in range(10)]  # 生成 0 到 9 的平方列表
print(squares)
```

## 9. 类和面向对象编程（OOP）

定义类和创建对象。

```python
class Person:
    def __init__(self, name, age):
        self.name = name
        self.age = age

    def greet(self):
        print(f"Hello, my name is {self.name} and I am {self.age} years old.")

p = Person("Alice", 25)
p.greet()  # 输出：Hello, my name is Alice and I am 25 years old.
```

## 10. 导入模块

Python 拥有大量内置模块，可以使用 `import` 导入模块。

```python
import math

print(math.sqrt(16))  # 计算平方根
```

`class` 语句用于定义一个新的类。类是 Python 面向对象编程 (OOP) 的核心，允许我们封装数据和方法。下面是 `class` 语句的结构和一些示例：

## 11.class 类
#### a. 类的基本定义

类通过 `class` 关键字定义，并包含初始化方法 `__init__`，用于初始化对象属性，还可以包含其他方法来定义对象的行为。

```python
class Dog:
    # 初始化方法，定义实例属性
    def __init__(self, name, age):
        self.name = name  # 实例属性 name
        self.age = age    # 实例属性 age

    # 方法，用于描述狗的行为
    def bark(self):
        print(f"{self.name} is barking!")

# 创建类的实例
my_dog = Dog("Buddy", 5)
print(my_dog.name)  # 输出: Buddy
print(my_dog.age)   # 输出: 5
my_dog.bark()       # 输出: Buddy is barking!
```

#### b. 类属性与实例属性

- **实例属性**：每个对象独立的属性，在 `__init__` 方法中通过 `self` 赋值。
- **类属性**：所有实例共享的属性，可以在类体中直接定义。

```python
class Dog:
    species = "Canis lupus familiaris"  # 类属性

    def __init__(self, name, age):
        self.name = name
        self.age = age

my_dog = Dog("Buddy", 5)
print(my_dog.species)  # 输出: Canis lupus familiaris
```

#### c. 类方法、实例方法与静态方法

- **实例方法**：第一个参数为 `self`，表示对当前实例的操作。
- **类方法**：使用 `@classmethod` 装饰器，第一个参数为 `cls`，表示对类本身的操作。
- **静态方法**：使用 `@staticmethod` 装饰器，通常与实例和类都无关，仅是类中的一个功能函数。

```python
class MathOperations:
    # 类方法
    @classmethod
    def pi(cls):
        return 3.14159

    # 静态方法
    @staticmethod
    def add(x, y):
        return x + y

# 调用类方法和静态方法
print(MathOperations.pi())  # 输出: 3.14159
print(MathOperations.add(5, 7))  # 输出: 12
```

#### d. 继承

继承允许我们创建一个基于现有类的类，继承父类的属性和方法，并添加或修改功能。

```python
class Animal:
    def __init__(self, name):
        self.name = name

    def speak(self):
        print("The animal speaks.")

class Dog(Animal):
    def speak(self):  # 重写父类方法
        print(f"{self.name} barks.")

# 使用继承
dog = Dog("Buddy")
dog.speak()  # 输出: Buddy barks.
```

#### e. 使用 `super()` 调用父类方法

在子类中调用父类的方法，可以使用 `super()`，避免直接引用父类名，增强灵活性。

```python
class Animal:
    def __init__(self, name):
        self.name = name

class Dog(Animal):
    def __init__(self, name, age):
        super().__init__(name)  # 调用父类的初始化方法
        self.age = age

dog = Dog("Buddy", 5)
print(dog.name)  # 输出: Buddy
print(dog.age)   # 输出: 5
```

#### f. 私有属性与方法

在 Python 中，属性和方法以双下划线开头表示私有（无法直接访问）。

```python
class BankAccount:
    def __init__(self, balance):
        self.__balance = balance  # 私有属性

    def deposit(self, amount):
        self.__balance += amount

    def __show_balance(self):  # 私有方法
        print(f"Balance: {self.__balance}")

# 实例化并操作
account = BankAccount(1000)
account.deposit(500)
# account.__show_balance()  # 会报错，无法直接访问私有方法
```

#### g. 类的完整示例

```python
class Employee:
    # 类属性
    company = "Tech Solutions"

    def __init__(self, name, salary):
        self.name = name          # 实例属性
        self.__salary = salary     # 私有属性

    # 实例方法
    def get_salary(self):
        return self.__salary

    # 类方法
    @classmethod
    def get_company_name(cls):
        return cls.company

    # 静态方法
    @staticmethod
    def greet():
        print("Welcome to the company!")

# 使用类
emp = Employee("Alice", 70000)
print(emp.get_salary())            # 输出: 70000
print(Employee.get_company_name())  # 输出: Tech Solutions
emp.greet()                        # 输出: Welcome to the company!
```

