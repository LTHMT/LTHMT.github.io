Python 的基础语句涵盖了变量赋值、数据类型、条件控制、循环、函数等基础知识。以下是一些常用的基础 Python 语句。

## 1. 变量赋值与数据类型

Python 是动态类型语言，可以直接声明并赋值变量，常见的数据类型有 `int`、`float`、`str`、`list`、`dict`、`bool` 等。

```python
# 整数和浮点数
x = 5           # 整数
y = 3.14        # 浮点数

# 元组(tuple)
num=(0,2,3)
num[0]          # 可以取值，但是不可修改

# 字符串
name = "Alice"

# 布尔类型
is_active = True

# 列表
numbers = [1, 2, 3, 4, 5]

# 字典
person = {"name": "Alice", "age": 25}
person['gender']='female'   # 添加
del person['gender']        # 删除
person.clear()              # 清空
person.items()              # 查看所有项；返回（键；值）
person.keys()               # 查看所有键；返回列表
person.values()             # 查看所有值，返回列表
len(person)                 # 查看项数，返回数字
a={}                        # 定义一个空字典



# 格式化输出
age =1
name='lt'
num= 1234567.89
print('my name is %s, and %d years old' % (name,age)) #必须按顺序
print('number is %.2f' % num ) #`%f`默认小数点六位。`%.2f`可以限定2位小数点

print('{},{}'.format(a,b))             # 不需要考虑数据类型
print('{0},{1},{0}'.format('1','lt'))  # 输出 `1 lt 1`

print(f'名字是:{name},年龄是{age}') # 用`f'`方式输出,无需要考虑数据类型
print(f'数字{num:.2f}')   # 这样可以限制小数点
print(f'数字{num:,.2f}')  # 增加千位符，输出：数字1,234,567.89 

```
- 常用格式化输出主要符号
    |  格式符号 |   转换 |
    |----------|--------|
    |`%c`|字符|
    |`%s`|字符串|
    |`%d`|有符号十进制整数|
    |`%o`|八进制整数|
    |`%x`|十六进制整数|
    |`%f`|浮点型|
    |`%e`|科学计数法|



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


# 三元表达式
a=1
b=2

print(a if a>b else b) # 如果a>b输出a，否则b （`true` if `condition` else `false`）
print('a最大',end=' ') if a>b else print('b最大’, end=' ')  # 输出：b最大

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
    if i == 3
        break 
    print(i)    # 输出 0 到 2

for i in range(5):
    if i == 3
        continue   # 输出 0 1 2 4 (continue会跳过当前循环)
    print(i) 
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

# 可变参数
def greet(*args):  # *args将实际参数接收，放置于一个元组中
    print(args)
def greet(a,b=2,*c):
    print(a,b,c)

greet(1,2,3,4) # 这里a=1,b=2,c=(3,4)

def greet2(**kwargs): 
    print(kwargs)# 接受所有关键字参数，然后将其转换为一个字典赋值给  kwargs这个形式参数(key=value)
greet2(name='lt',age='20')

funx=lambda x,y : x+y  # lambda 形参：公式 
funx(x,y)

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

# 索引
name ='abcdef'
print(name[2])  # 输出 c 
print(name[-2]) # 输出 e

# 切片 
name ='abcdefg'
print(name[0:2:1]) # 输出 abc [起始索引：结束：步长默认为1]
print(name[-1:3:-1]) # 倒序输出 gfed [起始索引：结束：步长控制方向]
 
# 字典
person["gender"] = "female"   # 添加键值对
print(person.get("name"))     # 获取键对应的值
del person["age"]             # 删除键值对

# 查找（find）
a= 'hello world'
print(a.find('e')) # 返回第一次找到的索引值 ，输出 1
print(a.index('e')) # index(str,开始下标，结束下标) ，输出 1  但是找不到时候会报错
print(a.find('e',1,3)) #从下标1到下标3内查找，没找到不会报错

# 计数（count）
a= 'hello world'
print(a.count('l')) # count(str,开始下标，结束下标)
                    # 返回出现次数 ： 3

# 替换（replace）
#replace（旧str，新str，替换次数）
a= 'hello world'
print(a.replace('world','shijie')) # hello shijie

# 分割（split）
# split（str，切的次数）
a= 'he，llo，wor，ld'
print（a.split(',')) #用,切分 输出列表：['he','llo','wor','ld']

# 字符串修改
a.capitalize()   # 第一个字符大写
a.lower()        # 大写字符转换为小写
a.upper()        # 小写字符转换为大写
a.startswith()   # 是否以某字符为开头
a.endwith()      # 是否以某字符结束
a.titile()       # 把每个单词首字母大写

a.islower()      # 检验是否都为小写
a.isupper()      # 检验是否都为大写
a.isdigit()      # 检验是否都为数字

a.join()
a='hello'
print('*'.join(a)) # 输出：h*e*l*l*o

# 列表操作
    # 添加元素：
        .append()
        .extend()
        .insert()
        a + b
    # 查找元素:
        in/not in
        index
        count
    # 修改元素：
        a[0]='123'
    # 删除元素：
        del a[0:2]
        .pop(index) #默认删除列表最后一个元素
        .remove()
    # 排序：
        .sort()
        .reverse()

# 集合（set）
a=set()  #定义一个空集合
a={10,20,30}  
a=set('ashfbl')
a.add(100)  #输出 a={100,10,20,30} 添加元素
a.updata([100])  # update()只能是可迭代的对象（列表、集合、字典、元组）
a.remove(10) # 移除
a.discard(10) #丢弃，如果不存在则报错
a.pop() # 随机删除某个数据

x={'a','b','c'}
y={'b','h','i'}
x.update(y)  # 输出为 x={'a','b','c','h','i'} 集合内不重复

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
except ZeroDivisionError as zero :  # 可以把报错改名
    print("不能除以零")
finally:
    print("执行结束")

---
try :
    print(可能引发异常现象的代码)
except Exception:                   # Exception：万能异常
    出现异常才运行的代码
else:                               # 不出现异常则...
    没有异常才运行的代码
finally:  
   无论如何都运行的代码             # finally 无论是否有异常都会执行




```
| 异常类型            | 含义                                                                 |
|---------------------|----------------------------------------------------------------------|
| `AttributeError`    | 尝试访问一个对象没有的属性时抛出该异常。                              |
| `IOError`           | 输入/输出异常，通常在无法打开文件或文件操作失败时抛出。                |
| `ImportError`       | 无法导入模块或包，通常是路径或模块名称错误导致。                      |
| `IndentationError`  | 代码缩进错误（语法错误的子类）。                                      |
| `IndexError`        | 访问序列（如列表或元组）时，索引超出范围时抛出。                      |
| `KeyError`          | 访问字典中不存在的键时抛出该异常。                                   |
| `KeyboardInterrupt` | 用户中断执行（通常是按 `Ctrl+C` 时触发）。                           |
| `NameError`         | 使用了未定义的变量时抛出该异常。                                     |
| `SyntaxError`       | 代码不符合Python语法规则时抛出（如缺少括号）。                        |
| `TypeError`         | 传入对象的类型与操作或函数要求的不匹配时抛出。                        |
| `ValueError`        | 传入值类型正确，但值不符合要求时抛出（如无法将字符串转为整数）。        |


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
print(my_dog.species)   # 输出: Canis lupus familiaris

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
print(MathOperations.pi())       # 输出: 3.14159
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

## 12.内置函数
```python 

# map(函数，可迭代对象)
a=[1,2,3,4]
map(func,a) #会依次把a列表里的元素执行
map(lambda x,y:x+y , a)

# zip(可迭代对象，可迭代对象) 
a=[1,2,3]
b=['a','b','c','d','e','f']
C= zip(a,b) #仅能被迭代一次 比如被print(list(c))之后，就不能再使用了

# reduce(函数，可迭代对象)  
functools.reduce(lambda x,y:x+y  ) #会依次把a列表里的元素执行并累加

# enumerate() 枚举
a=['s','j','i','p']
for n,i in enumerate(a)
    print(n,i)             # 0,s 1,j 2,i 3,p

# 元组拆包
a= (1,2,3,4)
b,*c,d =a  # b =1, c=[2,3] , d =4

``` 







