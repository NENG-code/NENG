# task1文档1

## 基础容器：list 和 dict 的使用技巧

### **list**

#### 1.list的创建

##### (1)空列表
        ```python
        a = []
        b = list()
        ```

##### (2)字面量
        ```python
        nums = [1,2,3]
        ```

##### (3)list的转换
        ```python
        list("abc") #['a','b','c']
        list(d.keys()) #等价于list(d),任何直接传字典等于传键、
        list(d.valus())
        list(d.items())
        list(range(5)) #0,1,2,3,4
        list(range(1,6))#1,2,3,4,5
        ```

#### 2.list的访问

##### (1)list的下标
        ```python
        list[0] #第一个
        list[-1] #最后一个
        ```

##### (2)切片
        ```python
        #list[起始；结尾；步长] 左闭右开
        list[1:3]
        list[:3]
        list[2:]
        list[:]#全部
        list[::-1]#倒序输出
        ```
#### 3.list的添加

##### (1)append()
        ```python
        s.append() #结尾添加
        ```

##### (2)insert(下标，元素)
        ```python
        s.insert(2,3)
        ```

##### (3)extend()
        ```python
        s.extend([1,2,3])#在结尾插入多个元素
        ```

#### 4.list的删除

##### (1)remove()
        ```python
        s.remove(20) #删除第一个遇到的匹配项
        ```

##### (2)pop(下标)
        ```python
        num = s.pop(1) #删除该下标元素并且返回
        ```

##### (3)del
        ```python
        del nums[0] #删除不返回
        ```

##### (4)clear()
        ```python
        nums.clear() # 全部删除
        ```

#### 5.list的查找

##### (1)in
        ```python
        2 in nums # 返回值是布尔类型
        ```

##### (2)index
        ```python
        nums.index(2) #返回第一次遇见匹配值的下标
        ```

##### (3)count
        ```python
        nums.count(3) #查找3在列表中出现了几次
        ```

#### 6.list的排序

##### (1)sort
        ```python
        nums.sort() #升序
        nums.sort(reverse = True) #降序
        nums.sort(key=abs) #按照绝对值排序
        ```

##### (2)sorted
        ```python
        nums1 = sorted(nums) # 创立一个新的列表
        ```

#### 7.list的复制
        ```python
        a = b #浅复制
        a = b.copy() #深复制
        a = b[:] #深复制
        ```

#### 8.list的列表推导式
        ```python
        nums[i*2 for i in range(5)]
        #等于:
        #        for i in range(5):
        #               nums.append(i*2)
        nums[x for x in range(5) if x%2 == 0]#加条件
        ```


### **dict**

#### 1.dict的创建

##### (1)空字典

```python
d = {}
d = dict()
```

##### (2)字面量

```python
d = {"name": "Tom", "age": 18}
```

##### (3)dict的转换

```python
dict([("a", 1), ("b", 2)]) # {'a': 1, 'b': 2}
dict(name="Tom", age=18) # {'name': 'Tom', 'age': 18}

# 字典的键必须是可哈希的对象
# 字符串、整数、符合条件的元组可以作为键
# 列表、字典、集合不能直接作为键
```

#### 2.dict的访问

##### (1)通过键访问

```python
d = {"name": "Tom", "age": 18}

d["name"] # 'Tom'
d["age"] # 18

# 如果键不存在，会报KeyError
```

##### (2)get()访问

```python
d.get("name") # 'Tom'
d.get("score") # None
d.get("score", 0) # 0

# get(键, 默认值)
# 键存在时返回对应的值
# 键不存在时返回默认值
# 不指定默认值时，返回None
# 不会因为键不存在而报KeyError
```

#### 3.dict的添加与修改

##### (1)通过键添加或修改

```python
d = {"name": "Tom", "age": 18}

d["score"] = 95 # 添加新键值对
d["age"] = 19 # 修改已有键对应的值
```

##### (2)update()

```python
d.update({"age": 20, "score": 100})

# 一次添加或修改多个键值对
# 如果键已经存在，就修改对应的值
```

##### (3)setdefault()

```python
d = {}

d.setdefault("a", 0) # 如果a不存在，添加a:0
d.setdefault("a", 10) # a已经存在，不会修改原来的值

# 返回该键对应的值
# 键不存在时，添加指定的默认值
```

#### 4.dict的删除

##### (1)del

```python
del d["name"] # 删除指定键值对
# 键不存在时会报KeyError
```

##### (2)pop()

```python
num = d.pop("age") # 删除age并返回对应的值
d.pop("score", 0) # 键不存在时返回0，不报错
```

##### (3)clear()

```python
d.clear() # 清空字典
```

#### 5.dict的查找

##### (1)in

```python
"name" in d # 判断键是否存在，返回布尔值
18 in d.values() # 判断值是否存在
```

##### (2)get()

```python
d.get("name") # 获取对应的值
d.get("score", 0) # 获取值，不存在时返回0
```

##### (3)keys()

```python
d.keys() # 获取所有键
list(d.keys()) # 将所有键转换成列表
```

##### (4)values()

```python
d.values() # 获取所有值
list(d.values()) # 将所有值转换成列表
```

##### (5)items()

```python
d.items() # 获取所有键值对
list(d.items()) # 将所有键值对转换成元组列表
```

#### 6.dict的遍历

##### (1)遍历键

```python
for key in d:
    print(key)

# 直接遍历字典，默认遍历键
```

##### (2)遍历值

```python
for value in d.values():
    print(value)
```

##### (3)同时遍历键和值

```python
for key, value in d.items():
    print(key, value)
```

#### 7.dict的统计技巧

##### (1)使用get()统计

```python
nums = [1, 2, 1, 3, 2, 1]
counts = {}

for x in nums:
    counts[x] = counts.get(x, 0) + 1

print(counts)
# {1: 3, 2: 2, 3: 1}

# get(x, 0)获取已有次数
# 没有该键时默认次数为0
# 每遇到一次就加1
```

##### (2)使用if判断统计

```python
counts = {}

for x in nums:
    if x in counts:
        counts[x] += 1
    else:
        counts[x] = 1
```

##### (3)使用Counter统计

```python
from collections import Counter

nums = [1, 2, 1, 3, 2, 1]
counts = Counter(nums)

print(counts)
# Counter({1: 3, 2: 2, 3: 1})
```

#### 8.dict的排序

##### (1)按照键排序

```python
d = {"c": 3, "a": 1, "b": 2}

d1 = dict(sorted(d.items()))

# {'a': 1, 'b': 2, 'c': 3}
# sorted()返回排序后的列表
# dict()将排序结果重新转换成字典
```

##### (2)按照值排序

```python
scores = {"Tom": 90, "Amy": 85, "Jack": 95}

d1 = sorted(scores.items(), key=lambda item: item[1])

# [('Amy', 85), ('Tom', 90), ('Jack', 95)]
# item[0]表示键
# item[1]表示值
# key=lambda item: item[1]表示按照值排序
```

##### (3)按照值降序排序

```python
d1 = sorted(
    scores.items(),
    key=lambda item: item[1],
    reverse=True
)

# reverse=True表示降序
# sorted()返回列表，不是字典
```

#### 9.dict的字典推导式

##### (1)基础写法

```python
squares = {x: x*x for x in range(1, 6)}

# {1: 1, 2: 4, 3: 9, 4: 16, 5: 25}

# 等价于：
squares = {}
for x in range(1, 6):
    squares[x] = x*x
```

##### (2)带条件的字典推导式

```python
d = {x: x*x for x in range(6) if x % 2 == 0}

# {0: 0, 2: 4, 4: 16}
# 只保留偶数，并将偶数与其平方对应
```

#### 10.dict的常见注意事项

##### (1)键不能重复

```python
d = {"a": 1, "a": 2}

print(d) # {'a': 2}
# 后面的值会覆盖前面的值
```

##### (2)in默认判断键

```python
d = {"a": 100}

"a" in d # True
100 in d # False
100 in d.values() # True
```

##### (3)get()和pop()的区别

```python
d = {"a": 1}

d.get("a") # 1，只读取，不删除
d.pop("a") # 1，删除并返回对应的值
```

##### (4)遍历时不要随意增删键

```python
# 不建议在遍历字典时直接添加或删除键
# 可以先保存需要删除的键，再统一删除
```

##### (5)字典的键必须可哈希

```python
d = {"name": "Tom", 1: "数字键", (1, 2): "元组键"}

# d[[1, 2]] = "列表键" # 错误，会报TypeError
```

## 函数：Lambda匿名函数与Decorator装饰器
### **Lambda匿名函数**
#### 1. Lambda的基本概念
```python
#普通函数
def add(a, b):
    return a + b
#Lambda匿名函数
add = lambda a, b: a + bprint(add(2, 3)) # 5
#Lambda不需要使用return
```
#### 2. Lambda的基本语法

lambda 参数: 表达式

(1)单个参数
```python
square = lambda x: x * xprint(square(4)) # 16
```
(2)多个参数
```python
add = lambda a, b: a + bprint(add(3, 5)) # 8
```
(3)条件表达式
```python
max_num = lambda a, b: a if a > b else bprint(max_num(6, 9)) # 9
# 等价于：
def max_num(a, b):    
        if a > b:
                return a    
        else:
                return b
```


#### 3. Lambda的使用技巧

(1)配合sort()排序
```python
students = [("小明", 85),("小红", 92),("小刚", 78)]
students.sort(key=lambda x: x[1])
print(students)# [('小刚', 78), ('小明', 85), ('小红', 92)]
# x表示列表中的一个元组 x[0]表示姓名 x[1]表示成绩 key=lambda x: x[1]表示按照成绩排序
```


(2)配合sorted()排序
```python
students = [("小明", 85),("小红", 92),("小刚", 78)]
result = sorted(students,key=lambda x: x[1],everse=True)
print(result)# [('小红', 92), ('小明', 85), ('小刚', 78)]
# sorted()返回新列表  reverse=True表示降序
# 原列表不变
```


(3)配合map()处理元素
```python
nums = [1, 2, 3, 4]
result = list(map(lambda x: x * 2, nums))
print(reault)
# map()将函数应用于每个元素  list()将结果转换成列表
```


(4)配合filter()筛选元素
```python
nums = [1, 2, 3, 4, 5, 6]
result = list(filter(lambda x: x % 2 == 0, nums))
print(result)
# [2, 4, 6]
# x % 2 == 0表示判断偶数
# filter()保留条件为True的元素
```


(5)Lambda与列表推导式
```python
nums = [1, 2, 3, 4, 5, 6]
# 使用filter()和Lambdaresult1 = list(filter(lambda x: x % 2 == 0, nums))
# 使用列表推导式result2 = [x for x in nums if x % 2 == 0]print(result1) 
# [2, 4, 6]print(result2) # [2, 4, 6]
```


#### 4. Lambda的注意事项
(1)Lambda不需要return
```python
f = lambda x: x * 2print(f(3)) # 6
```


(2)Lambda只能直接包含一个表达式
```python
# 正确
f = lambda x: x + 1
# 错误 
f = lambda x: return x + 1
```


(3)复杂函数使用def更合适
```python
def calculate(x):
            result = x * 2    
            result += 10    
            return result
```


- 简单函数可以使用Lambda
- 复杂逻辑建议使用def
- Lambda常用于排序、简单计算和筛选





### **Decorator装饰器**
#### 1. 装饰器的基本概念
装饰器可以在不直接修改原函数代码的情况下，为函数增加额外功能

例如，在函数执行前后打印提示信息
```python
def say_hello():
            print("你好！")
```

如果想增加执行前后的提示，可以使用装饰器，而不必修改原函数内部的代码

#### 2. 理解装饰器的基础：函数作为参数
```python
def hello():
            print("你好！")
            def run(func):
                    func()
run(hello)
```
输出：
你好！


注意：
hello   # 表示函数本身hello() # 表示调用函数
- run(hello)：把函数传入run()
- func()：调用传入的函数

#### 3. 实现装饰器
```python
def decorator(func):
            def wrapper():
                        print("开始执行")
                        func()
                        print("执行结束")
                        return wrapperdef 
say_hello():
    print("你好！")
say_hello = decorator(say_hello)
say_hello()


```
输出：
开始执行
你好！
执行结束


执行过程
1. 将say_hello函数传入decorator()
2. 在decorator()内部定义包装函数wrapper()
3. wrapper()包含额外功能以及原函数的调用
4. return wrapper返回包装函数
5. say_hello = decorator(say_hello)让say_hello指向新的包装函数
6. 调用say_hello()时，执行包装函数
注意return wrapper和return wrapper()的区别
return wrapper   # 返回函数本身return wrapper() # 调用函数，再返回它的结果

装饰器中通常使用return wrapper，让调用者以后再执行包装函数

#### 4. 使用@语法简化装饰器
```python
def decorator(func):
        def wrapper():
                print("开始执行")
                func()
                print("执行结束")
        return wrapper
@decorator
def say_hello():
    print("你好！")
say_hello()
```


输出：
开始执行
你好！
执行结束


以下两种写法等价：
```python
@decorator
def say_hello():
    print("你好！")


def say_hello():
            print("你好！")
            say_hello = decorator(say_hello)
```

@decorator是Python提供的装饰器语法，可以简化函数包装操作

#### 5. 带参数的装饰器
如果原函数需要参数，包装函数也必须能够接收参数
```python
def decorator(func):
        def wrapper(*args, **kwargs):
                print("开始执行")
                result = func(*args, **kwargs)
                print("执行结束")
                return result    
        return wrapper
@decorator
def add(a, b):    
        return a + b
print(add(3, 5))
```
输出：
开始执行
执行结束
8


(1)*args
接收任意数量的位置参数
```python
def func(*args):
            print(args)
            func(1, 2, 3)# (1, 2, 3)
```


(2)**kwargs
接收任意数量的关键字参数
```python
def func(**kwargs):
            print(kwargs)
            func(name="Tom", age=18)# {'name': 'Tom', 'age': 18}
```


(3)func(*args, **kwargs)
将接收到的参数传递给原函数，使装饰器可以适用于不同参数形式的函数\


(4)return result
```python
result = func(*args, **kwargs)
return result
```


- 保存原函数的返回值
- 将结果返回给调用者
- 避免装饰器导致原函数的返回值丢失

#### 6. 装饰器的实际应用
##### (1)统计函数运行时间
```python
import time
from functools import wraps

def timer(func):
    @wraps(func)
    def wrapper(*args, **kwargs):
        start = time.perf_counter()

        result = func(*args, **kwargs)

        end = time.perf_counter()
        print("运行时间：", end - start, "秒")

        return result
    return wrapper

@timer
def calculate():
    total = 0
    for i in range(1000000):
        total += i
    return total

print(calculate())
```

1.@wraps(func)：尽可能保留原函数的元信息
2.from functools import wraps：导入 wraps
3.return wrapper：返回包装函数，不能随意写成 return wrapper()

- import time：导入时间模块
- time.perf_counter()：获取适合测量运行时间的计时值
- end - start：计算函数执行耗时
- @timer：给函数增加计时功能

##### (2)记录函数执行信息
```python
def logger(func):
        def wrapper(*args, **kwargs):
                print("正在调用函数：", func.__name__)
                result = func(*args, **kwargs)
                print("函数执行完成")       
                return result    
        return wrapper
@logger
def greet(name):    
        print("你好，", name)           
        greet("Tom")
```


输出：
正在调用函数： greet
你好， Tom
函数执行完成


装饰器还可以用于日志记录、权限检查、缓存等场景


## 面向对象：Class（类）与 Magic Methods（魔法方法），以及 OOP（面向对象编程）的思想

### **class(类)**

#### 类的定义和创建

##### (1) 类的定义

```python
class Student:
    pass
```

- `class`：定义类的关键字
- `Student`：类名，通常采用大驼峰命名法
- `pass`：占位符，表示暂时不编写具体内容

##### (2) 对象的创建

```python
s1 = Student()
s2 = Student()
```

`Student()` 称为实例化，即根据类创建对象

- `Student` 是类，负责描述一类对象的结构和行为
- `s1`、`s2` 是变量，分别引用创建出来的对象
- `s1` 和 `s2` 默认是两个不同的对象

##### (3) 类与对象的关系

可以把类理解为设计图，把对象理解为根据设计图制造出来的具体物品

例如，`Student` 是学生类，小明和小红是两个学生对象它们可以具有相同类型的属性和方法，但属性值可以不同

#### 2. 属性与方法

##### (1) 实例属性

实例属性用于保存具体对象的数据

```python
class Student:
    def __init__(self, name, age):
        self.name = name
        self.age = age

s1 = Student("小明", 18)
s2 = Student("小红", 19)

print(s1.name)  # 小明
print(s2.name)  # 小红
```

- `name`、`age` 是传入的参数
- `self.name`、`self.age` 是保存在当前对象中的属性
- 不同对象可以具有不同的实例属性值
- `s1.name` 表示访问对象 `s1` 的 `name` 属性

##### (2) 实例方法

实例方法是定义在类中的函数，用于描述对象可以执行的行为

```python
class Student:
    def __init__(self, name):
        self.name = name

    def study(self):
        print(f"{self.name}正在学习")

s = Student("小明")
s.study()
```

输出：

```text
小明正在学习
```

实例方法的第一个参数通常是 `self`，用于接收当前实例对象

##### (3) self 的作用

```python
class Student:
    def introduce(self):
        print("我是学生")

s = Student()
s.introduce()
```

调用 `s.introduce()` 时，Python 会自动将实例 `s` 传给 `self`

可以近似理解为：

```python
Student.introduce(s)
```

因此，调用实例方法时通常不需要自己传入 `self`

注意：`self` 不是 Python 关键字，而是约定俗成的参数名称

#### 3. `__init__()` 初始化方法

##### (1) 基本用法

```python
class Student:
    def __init__(self, name, age):
        self.name = name
        self.age = age

s = Student("小明", 18)
```

`__init__()` 是初始化方法创建对象时，Python 会自动调用它，用于设置对象的初始状态

执行 `Student("小明", 18)` 时，可以理解为：

1. Python 创建一个新的 `Student` 对象
2. 自动调用 `__init__()`，将对象传给 `self`
3. 将 `"小明"` 和 `18` 分别传给 `name` 和 `age`
4. 将数据保存到对象的 `self.name` 和 `self.age` 中

##### (2) 为什么需要 `self.name = name`

```python
def __init__(self, name):
    self.name = name
```

这里的两个 `name` 含义不同：
- 右侧 `name`：传入的局部参数
- 左侧 `self.name`：当前对象的属性

`self.name = name` 就是将传入的姓名保存到对象中

##### (3) 注意事项

- `__init__()` 的名称前后各有两个下划线
- 第一个参数通常是 `self`
- 可以定义其他参数，也可以设置默认值
- `__init__()` 必须返回 `None`，不能返回其他值
- 如果没有定义 `__init__()`，在没有其他构造限制的情况下，类仍然可以创建对象

#### 4. 类属性与实例属性

##### (1) 类属性

类属性定义在类内部、方法外部，通常用于保存整个类共享的数据

```python
class Student:
    school = "第一中学"

    def __init__(self, name):
        self.name = name

s1 = Student("小明")
s2 = Student("小红")

print(Student.school)
print(s1.school)
print(s2.school)
```

输出：

```text
第一中学
第一中学
第一中学
```

##### (2) 类属性与实例属性的区别

```python
class Student:
    school = "第一中学"

    def __init__(self, name):
        self.name = name

s1 = Student("小明")
s2 = Student("小红")

s1.school = "第二中学"

print(s1.school)       # 第二中学
print(s2.school)       # 第一中学
print(Student.school)  # 第一中学
```

- 实例属性：属于具体对象，例如 `self.name`
- 类属性：属于类，例如 `school`
- 通过 `s1.school = ...` 赋值时，如果实例原来没有这个属性，就会创建实例属性，而不是修改类属性
- 访问属性时，通常先查找实例自身，再查找类及其继承关系中的属性

#### 5. 属性访问与方法调用

##### (1) 访问和修改属性

```python
s.name          # 读取属性
s.name = "小红"  # 修改或创建实例属性
```

##### (2) 调用方法

```python
s.study()
```

方法调用时，实例方法会自动接收当前对象作为第一个参数

##### (3) `s.name` 与 `s.name()` 的区别

- `s.name`：访问属性
- `s.study()`：调用方法
- 如果属性保存的是一个可调用对象，也可以使用括号调用，但普通属性不一定能这样做

### **Magic Methods（魔法方法）**

#### 1. 魔法方法的概念

魔法方法也叫特殊方法，通常采用 `__方法名__` 的形式，用于规定对象在特定操作下的行为

例如：

```python
__init__
__str__
__repr__
__len__
__add__
__eq__
```

魔法方法一般不需要手动调用，而是由 Python 在执行对应操作时自动调用

#### 2. 常见魔法方法

##### (1) `__init__()`：初始化对象

```python
class Student:
    def __init__(self, name):
        self.name = name

s = Student("小明")
```

创建对象时自动调用，用于初始化对象的属性

##### (2) `__str__()`：控制对象的易读字符串表示

```python
class Student:
    def __init__(self, name):
        self.name = name

    def __str__(self):
        return f"学生姓名：{self.name}"

s = Student("小明")
print(s)
```

输出：

```text
学生姓名：小明
```

`print(s)` 通常会使用 `__str__()`，该方法必须返回字符串

##### (3) `__repr__()`：对象的正式表示

```python
class Student:
    def __init__(self, name):
        self.name = name

    def __repr__(self):
        return f"Student({self.name!r})"

s = Student("小明")
print(repr(s))
```

输出：

```text
Student('小明')
```

- `__str__()`：更注重普通用户阅读
- `__repr__()`：更注重开发者调试和识别对象
- 如果没有定义 `__str__()`，Python 通常会使用 `__repr__()` 作为后备

##### (4) `__len__()`：支持 `len()`

```python
class Team:
    def __init__(self, members):
        self.members = members

    def __len__(self):
        return len(self.members)

team = Team(["小明", "小红", "小刚"])
print(len(team))  # 3
```

定义后，可以使用 `len(obj)` 获取对象的长度返回值应为非负整数

##### (5) `__add__()`：自定义加法

```python
class Number:
    def __init__(self, value):
        self.value = value

    def __add__(self, other):
        return Number(self.value + other.value)

a = Number(10)
b = Number(20)

c = a + b
print(c.value)  # 30
```

执行 `a + b` 时，Python 会尝试使用 `a.__add__(b)`，从而自定义加法行为

##### (6) `__eq__()`：自定义相等比较

```python
class Student:
    def __init__(self, student_id):
        self.student_id = student_id

    def __eq__(self, other):
        if not isinstance(other, Student):
            return NotImplemented
        return self.student_id == other.student_id

s1 = Student(1001)
s2 = Student(1001)

print(s1 == s2)  # True
```

- `==`：比较相等性，可以由 `__eq__()` 定义规则
- `is`：判断是否为同一个对象
- 两个不同对象可以通过自定义规则被判定为相等

##### (7) `__getitem__()`：支持下标访问

```python
class MyList:
    def __init__(self, data):
        self.data = data

    def __getitem__(self, index):
        return self.data[index]

nums = MyList([10, 20, 30])
print(nums[0])  # 10
```

执行 `nums[0]` 时，会调用对应的 `__getitem__()` 方法

##### (8) `__call__()`：让对象可以像函数一样调用

```python
class Greeter:
    def __call__(self, name):
        print(f"你好，{name}")

g = Greeter()
g("小明")
```

输出：

```text
你好，小明
```

定义 `__call__()` 后，可以通过 `对象()` 的形式调用对象

#### 3. 常见魔法方法总结

| 魔法方法 | 对应操作 | 作用 |
|---|---|---|
| `__init__()` | 创建对象时初始化 | 初始化对象 |
| `__str__()` | `str(obj)`、通常包括 `print(obj)` | 易读的字符串表示 |
| `__repr__()` | `repr(obj)` | 对象表示与调试 |
| `__len__()` | `len(obj)` | 获取长度 |
| `__add__()` | `a + b` | 自定义加法 |
| `__eq__()` | `a == b` | 自定义相等比较 |
| `__getitem__()` | `obj[index]` | 下标访问 |
| `__setitem__()` | `obj[index] = value` | 下标赋值 |
| `__contains__()` | `x in obj` | 自定义成员判断 |
| `__call__()` | `obj()` | 让对象可以被调用 |

### **OOP（面向对象编程）**

#### 1. 面向对象编程的基本思想

OOP（Object-Oriented Programming）即面向对象编程

它的核心是将数据和操作数据的方法组织在对象中，通过对象之间的协作完成程序功能

例如，学生对象可以保存姓名、年龄和成绩，也可以提供学习、计算平均成绩等方法

#### 2. 面向过程与面向对象的区别

##### (1) 面向过程

关注解决问题的具体步骤，通常使用变量和函数组织程序

```python
def area(radius):
    return 3.14159 * radius ** 2

print(area(5))
```

##### (2) 面向对象

关注程序中的对象、对象的数据以及对象能够执行的操作

```python
class Circle:
    def __init__(self, radius):
        self.radius = radius

    def area(self):
        return 3.14159 * self.radius ** 2

c = Circle(5)
print(c.area())
```

两种方式都能解决问题程序简单时，面向过程往往更直接；程序复杂时，面向对象通常更有利于组织和维护代码

#### 3. 封装（Encapsulation）

##### (1) 基本概念

封装是将数据与操作数据的方法组织在一起，并通过合理的接口管理数据的访问和修改

##### (2) 基本示例

```python
class BankAccount:
    def __init__(self, balance):
        self.balance = balance

    def deposit(self, amount):
        if amount > 0:
            self.balance += amount

    def get_balance(self):
        return self.balance

account = BankAccount(100)
account.deposit(50)

print(account.get_balance())  # 150
```

存款操作由 `deposit()` 统一处理，可以在方法中加入金额检查等规则

##### (3) Python 中的访问约定

```python
self.name       # 公开属性
self._name      # 约定为内部使用
self.__name     # 触发名称改写
```

Python 没有与部分语言完全相同的严格私有属性机制单下划线表示约定上的内部使用，双下划线主要用于名称改写，并不是安全保护机制

#### 4. 继承（Inheritance）

##### (1) 基本概念

继承允许子类获得父类的属性和方法，并在此基础上增加或修改功能

- 父类：被继承的类
- 子类：继承其他类的类

##### (2) 基本语法

```python
class Animal:
    def eat(self):
        print("正在吃东西")

class Dog(Animal):
    def bark(self):
        print("汪汪汪")

dog = Dog()
dog.eat()
dog.bark()
```

输出：

正在吃东西
汪汪汪


`Dog` 继承了 `Animal`，因此可以直接调用父类提供的 `eat()` 方法

##### (3) 方法重写

```python
class Animal:
    def speak(self):
        print("动物发出声音")

class Dog(Animal):
    def speak(self):
        print("汪汪汪")

dog = Dog()
dog.speak()
```

输出：

汪汪汪


子类定义了与父类同名的方法后，调用该方法时会优先使用子类的实现这称为方法重写

##### (4) `super()`

```python
class Animal:
    def __init__(self, name):
        self.name = name

class Dog(Animal):
    def __init__(self, name, age):
        super().__init__(name)
        self.age = age
```

`super()` 可以按照方法解析顺序调用父类或后续类的方法，常用于复用父类的初始化逻辑

#### 5. 多态（Polymorphism）

##### (1) 基本概念

多态是指不同对象可以通过相同的调用方式，表现出不同的行为

##### (2) 基本示例

```python
class Dog:
    def speak(self):
        print("汪汪汪")

class Cat:
    def speak(self):
        print("喵喵喵")

def make_sound(animal):
    animal.speak()

make_sound(Dog())
make_sound(Cat())
```

输出：

汪汪汪
喵喵喵


`make_sound()` 不需要判断对象究竟是狗还是猫，只要对象提供可调用的 `speak()` 方法，就可以执行对应行为

##### (3) 多态的作用

- 相同的调用方式可以适用于不同对象
- 减少程序对具体类型的依赖
- 更容易扩展新类和新功能





##  文本处理：正则表达式（`re`）

### re正则表达式的定义

正则表达式（Regular Expression，简称 Regex）是一种**用特定规则描述字符串，并对字符串进行匹配、查找、提取和替换**的工具

例如：

```python
import re

text = "我的手机号是13812345678"

result = re.findall(r"\d+", text)
print(result)
```

输出：

```python
['13812345678']
```

这里的 `\d+` 表示：**匹配一个或多个数字**

正则表达式的核心思想是：不必提前知道具体的字符串是什么，只需要规定自己要找的内容有什么特征

### 正则表达式的基本符号

学习正则时，建议按照下面的顺序记忆

#### 1. 普通字符：直接匹配

普通字母和数字通常直接匹配自身

```python
import re

print(re.findall(r"cat", "cat dog cat"))
```

输出：

```python
['cat', 'cat']
```

因为 `cat` 就是要查找的字符串

#### 2. 特殊符号：匹配某一类内容

| 符号   | 含义                | 示例                  |
| ---- | ----------------- | ------------------- |
| `\d` | 一个数字，通常指 `0～9`    | `\d` 匹配 `5`         |
| `\D` | 一个非数字字符           | `\D` 匹配 `a`         |
| `\w` | 一个字母、数字或下划线       | `\w` 匹配 `a`、`5`、`_` |
| `\W` | 一个非 `\w` 字符       | `\W` 匹配 `@`         |
| `\s` | 一个空白字符，如空格、换行、制表符 | `\s` 匹配空格           |
| `\S` | 一个非空白字符           | `\S` 匹配 `a`         |
| `.`  | 除通常的换行符外的任意一个字符   | `.` 匹配 `a`、`7`、`@`  |

注意：这里的 `\w` 不只包括英文字母，Python 的 Unicode 模式下通常也包括汉字

```python
re.findall(r"\d", "a1b23")
# ['1', '2', '3']

re.findall(r"\w", "a_1中!")
# ['a', '_', '1', '中']
```

**重点：** `\d`、`\w`、`\s` 等符号默认都只匹配一个字符要匹配多个字符，需要继续学习后面的数量符号

#### 3. 数量符号：决定匹配多少个字符

这是正则表达式最重要的一部分

| 符号      | 含义               | 示例        |
| ------- | ---------------- | --------- |
| `*`     | 前面的内容出现 0 次或多次   | `a*`      |
| `+`     | 前面的内容出现 1 次或多次   | `a+`      |
| `?`     | 前面的内容出现 0 次或 1 次 | `a?`      |
| `{n}`   | 前面的内容恰好出现 n 次    | `\d{3}`   |
| `{n,}`  | 前面的内容至少出现 n 次    | `\d{2,}`  |
| `{n,m}` | 前面的内容出现 n 到 m 次  | `\d{2,4}` |

用 `a` 举例：

| 正则     | 可以匹配          | 不能匹配        |
| ------ | ------------- | ----------- |
| `a*`   | `""`、`a`、`aa` | `b`         |
| `a+`   | `a`、`aa`      | `""`、`b`    |
| `a?`   | `""`、`a`      | `aa`        |
| `a{3}` | `aaa`         | `aa`、`aaaa` |

这里有一个非常重要的区别：

- `*`：可以没有，也可以有很多个
- `+`：至少要有一个
- `?`：最多只能有一个，也可以没有

例如：

```python
re.findall(r"\d+", "a12b345c6")
# ['12', '345', '6']

re.findall(r"\d{2}", "a12345")
# ['12', '34']
```

`findall()` 会从左到右寻找匹配内容第二个例子中，`\d{2}` 每次匹配两个数字，所以得到 `12` 和 `34`，剩下的 `5` 不满足要求

#### 4. 字符集合 `[]`：规定可以出现哪些字符

方括号 `[]` 表示：**当前位置可以是括号中列出的任意一个字符**

```python
re.findall(r"[abc]", "apple book cat")
# ['a', 'b', 'c', 'a']
```

`[abc]` 只匹配 `a`、`b`、`c` 中的一个字符，不是匹配整个 `abc`

常见写法：

| 写法            | 含义                    |
| ------------- | --------------------- |
| `[abc]`       | `a`、`b`、`c` 中任意一个     |
| `[a-z]`       | 一个小写英文字母              |
| `[A-Z]`       | 一个大写英文字母              |
| `[0-9]`       | 一个数字                  |
| `[a-zA-Z]`    | 一个英文字母                |
| `[a-zA-Z0-9]` | 一个英文字母或数字             |
| `[^abc]`      | 一个不属于 `a`、`b`、`c` 的字符 |

注意：在 `[]` 内部，开头的 `^` 表示取反

例如：

```python
re.findall(r"[a-z]+", "abc123XYZ")
# ['abc']

re.findall(r"[^0-9]+", "abc123def")
# ['abc', 'def']
```

`[^0-9]+` 表示连续匹配一个或多个非数字字符

#### 5. 定位符：规定匹配的位置

定位符不主要描述字符本身，而是限制匹配内容出现在什么位置

| 符号   | 含义    |
| ---- | ----- |
| `^`  | 字符串开头 |
| `$`  | 字符串结尾 |
| `\b` | 单词边界  |

例如：

```python
re.search(r"^abc", "abcdef")
# 匹配成功

re.search(r"^abc", "xabcdef")
# None

re.search(r"abc$", "xxabc")
# 匹配成功
```

`^abc` 要求字符串开头就是 `abc`；`abc$` 要求字符串结尾是 `abc`

`\b` 常用于匹配英文单词边界：

```python
re.findall(r"\bcat\b", "cat scatter cat!")
# ['cat', 'cat']
```

这里不会把 `scatter` 中间的 `cat` 当作独立单词

注意：`^` 和 `$` 在不同位置含义不同：

- `[^abc]` 中的 `^` 表示取反
- `^abc` 中的 `^` 表示开头

#### 6. 分组 `()` 和选择 `|`

**分组 `()`：** 把多个字符组合成一个整体

```python
re.findall(r"(ab)+", "abab ab")
# ['ab', 'ab']
```

`(ab)+` 表示 `ab` 这个整体出现一次或多次

**选择 `|`：** 表示两种规则任选一种

```python
re.findall(r"cat|dog", "cat dog bird")
# ['cat', 'dog']
```

如果需要让选择符作用于一个整体，可以使用括号：

```python
re.findall(r"(cat|dog)s?", "cat cats dog dogs")
# ['cat', 'cat', 'dog', 'dog']
```

这里 `(cat|dog)s?` 表示匹配 `cat` 或 `dog`，后面可以有一个 `s`，也可以没有

注意：上面的结果只保留括号中捕获到的内容，因此不会显示 `s`关于这种结果差异，后面会讲到

#### 7. 转义符 `\`：让特殊符号失去特殊含义

如果想匹配真正的点号 `.`，不能直接写 `.`，因为它在正则中代表任意字符

需要写成 `\.`

| 想匹配的内容  | 正则写法 |
| ------- | ---- |
| 点号 `.`  | `\.` |
| 加号 `+`  | `\+` |
| 星号 `*`  | `\*` |
| 问号 `?`  | `\?` |
| 左括号 `(` | `\(` |
| 反斜杠 `\` | `\\` |

例如：

```python
re.findall(r"\.", "a.b.c")
# ['.', '.']
```

建议在 Python 中写正则时，通常使用 `r"..."`，例如 `r"\d+"`这里的 `r` 表示原始字符串，可以减少反斜杠转义造成的混淆

### 符号组合

学会单个符号后，重点是理解它们组合起来的意思

#### 例 1：匹配连续数字

```python
r"\d+"
```

拆解：

- `\d`：一个数字你
- `+`：前面的数字出现一次或多次

合起来：匹配连续的一段数字

#### 例 2：匹配 3～6 位数字

```python
r"^\d{3,6}$"
```

拆解：

- `^`：从字符串开头开始
- `\d`：数字
- `{3,6}`：数字连续出现 3～6 次
- `$`：匹配到字符串结尾

所以它要求整个字符串都是 3～6 位数字

#### 例 3：匹配简单的英文字母用户名

```python
r"^[a-zA-Z]+$"
```

拆解：

- `^`：开头
- `[a-zA-Z]`：一个英文字母
- `+`：一个或多个字母
- `$`：结尾

因此，整个字符串只能包含英文字母，并且不能为空

#### 例 4：匹配 11 位数字

```python
r"^\d{11}$"
```

它只验证字符串是否由 11 个数字组成

**注意：这不等于验证真实有效的中国手机号** 如果只需要检查格式，这个规则可以作为简单的第一步；如果要校验手机号，还需要进一步限定号段等规则

### 函数

先导入模块：

```python
import re
```

这部分建议重点记住四个函数：`match()`、`search()`、`findall()`、`sub()`

#### 1. `re.match()`：从开头开始匹配

```python
re.match(pattern, string)
```

只从字符串开头尝试匹配

```python
re.match(r"\d+", "123abc")
# 匹配成功

re.match(r"\d+", "abc123")
# None
```

第二个字符串虽然含有数字，但数字不在开头，所以匹配失败

#### 2. `re.search()`：找到第一个匹配位置

```python
re.search(pattern, string)
```

从整个字符串中查找，找到第一个匹配就停止

```python
re.search(r"\d+", "abc123def456")
```

会匹配到 `123`，不会继续寻找 `456`

如果没有找到，返回 `None`

#### 3. `re.findall()`：找出所有匹配结果

```python
re.findall(pattern, string)
```

返回一个列表，包含所有匹配结果

```python
re.findall(r"\d+", "abc123def456")
# ['123', '456']
```

如果没有匹配内容，返回空列表 `[]`

#### 4. `re.sub()`：替换匹配内容

```python
re.sub(pattern, replacement, string)
```

例如，把所有数字替换成 `*`：

```python
re.sub(r"\d+", "*", "abc123def456")
# 'abc*def*'
```

#### 5. `re.split()`：按照匹配内容切割字符串

```python
re.split(pattern, string)
```

例如，按照逗号或分号切割：

```python
re.split(r"[,;]", "apple,banana;orange")
# ['apple', 'banana', 'orange']
```

#### 6. 四个核心函数的区别

| 函数             | 作用      | 返回值          |
| -------------- | ------- | ------------ |
| `re.match()`   | 从开头尝试匹配 | 匹配对象或 `None` |
| `re.search()`  | 查找第一个匹配 | 匹配对象或 `None` |
| `re.findall()` | 查找所有匹配  | 列表           |
| `re.sub()`     | 替换匹配内容  | 替换后的字符串      |
| `re.split()`   | 按规则切割   | 列表           |

如果使用 `match()` 或 `search()`，想要取出匹配到的字符串，通常使用 `.group()`：

```python
result = re.search(r"\d+", "abc123def")

if result:
    print(result.group())
    # 123
```

如果匹配失败，结果就是 `None`，所以不要直接对 `None` 调用 `.group()`

### `findall()` 

这是一个容易忽略的知识点：**正则中有没有捕获分组 `()`，会影响 `findall()` 的返回结果**

#### 没有括号

```python
re.findall(r"\d+", "a12b345")
# ['12', '345']
```

返回完整匹配到的内容

#### 有一个捕获分组

```python
re.findall(r"(\d+)-[a-z]+", "12-ab 345-cd")
# ['12', '345']
```

因为使用了 `(\d+)`，所以只返回括号中的数字部分

#### 有两个捕获分组

```python
re.findall(r"(\d+)-([a-z]+)", "12-ab 345-cd")
# [('12', 'ab'), ('345', 'cd')]
```

每次匹配有两个捕获结果，因此列表中的元素变成了元组

如果只想分组但不想改变 `findall()` 的返回结构，可以使用非捕获分组 `(?:...)`：

```python
re.findall(r"(?:cat|dog)s?", "cats dogs cat")
# ['cats', 'dogs', 'cat']
```

这里 `(?:cat|dog)` 只用于组合规则，不单独捕获内容

### 贪婪匹配与非贪婪匹配

`*`、`+`、`?` 这些数量符号默认通常采用贪婪匹配：在满足整体规则的前提下，尽可能多地匹配

例如：

```python
text = "<a>hello</a><a>world</a>"

print(re.findall(r"<a>.*</a>", text))
# ['<a>hello</a><a>world</a>']
```

`.*` 尽可能多地匹配字符，所以从第一个 `<a>` 一直匹配到了最后一个 `</a>`

如果在数量符号后加 `?`，通常可以让它变成非贪婪匹配：

```python
print(re.findall(r"<a>.*?</a>", text))
# ['<a>hello</a>', '<a>world</a>']
```

这里的 `.*?` 表示尽可能少地匹配字符，同时保证整个正则能够匹配成功

注意：这个例子只是为了理解匹配规则实际解析复杂 HTML 时，通常应该使用专门的 HTML 解析工具，而不是依赖正则

## 代码格式：列表推导式与 Type Hint（类型注释）

### 列表推导式（List Comprehension）

**具体见前面列表部分**



### Type Hint（类型注释）

### 1. 什么是类型注释？

Type Hint，也叫类型提示或类型注释，用来说明变量、函数参数和返回值**预期使用什么类型的数据**

例如：

```python
age: int = 18
name: str = "Tom"
score: float = 95.5
```

其中：

- `int`：整数
- `str`：字符串
- `float`：浮点数

类型注释主要用于提高代码的可读性，帮助编辑器和静态类型检查工具发现潜在问题

**重要：Python 通常不会仅仅因为类型注释不匹配，就自动阻止程序运行**

```python
age: int = "hello"

print(age)
# hello
```

这段代码通常仍然能够运行，但类型检查工具可能会提示错误

#### 2. 常见类型注释

| 类型 | 含义 | 示例 |
|---|---|---|
| `int` | 整数 | `age: int = 18` |
| `float` | 浮点数 | `price: float = 9.9` |
| `str` | 字符串 | `name: str = "Tom"` |
| `bool` | 布尔值 | `is_ok: bool = True` |
| `list[int]` | 整数列表 | `nums: list[int] = [1, 2, 3]` |
| `list[str]` | 字符串列表 | `names: list[str] = ["Tom", "Amy"]` |
| `dict[str, int]` | 键为字符串、值为整数的字典 | `scores: dict[str, int] = {"Tom": 90}` |
| `tuple[int, str]` | 包含整数和字符串的二元组 | `item: tuple[int, str] = (1, "Tom")` |
| `set[int]` | 整数集合 | `nums: set[int] = {1, 2, 3}` |

这些写法适用于 Python 3.9 及以上版本

#### 3. 函数参数的类型注释

在参数名后面加冒号和类型

```python
def add(a: int, b: int):
    return a + b
```

这里的 `a: int` 和 `b: int` 表示预期传入整数

但这段代码还没有标注返回值类型

#### 4. 函数返回值的类型注释

在参数列表后面使用 `->` 标注返回值类型

```python
def add(a: int, b: int) -> int:
    return a + b
```

语法：

```python
def 函数名(参数名: 参数类型) -> 返回值类型:
    函数体
```

例如：

```python
def greet(name: str) -> str:
    return "Hello, " + name
```

其中：

- `name: str`：参数预期是字符串
- `-> str`：返回值预期是字符串

如果函数不返回有意义的值，通常写 `-> None`：

```python
def show_message(message: str) -> None:
    print(message)
```

#### 5. 列表、字典等容器的类型注释

类型注释也可以说明容器内部元素的类型

```python
def sum_nums(nums: list[int]) -> int:
    return sum(nums)
```

这里 `list[int]` 表示整数列表

```python
def get_score(scores: dict[str, int], name: str) -> int:
    return scores[name]
```

这里 `dict[str, int]` 表示字典的键是字符串，值是整数

注意：类型注释是对预期类型的说明，并不自动验证容器中的每个元素

#### 6. 可选类型与多种可能的类型

有时候，变量可能是某个类型，也可能是 `None`

可以使用 `|` 表示多种可能的类型，适用于 Python 3.10 及以上版本

```python
def find_name(user_id: int) -> str | None:
    if user_id == 1:
        return "Tom"
    return None
```

`str | None` 表示返回值可能是字符串，也可能是 `None`

如果返回值可能是整数或字符串：

```python
def process(value: int | str) -> str:
    return str(value)
```

这里 `int | str` 表示参数可以是整数或字符串

#### 7. 类型注释与默认参数

类型注释可以与默认值一起使用

```python
def greet(name: str = "Tom") -> str:
    return "Hello, " + name
```

- `name: str`：参数预期是字符串
- `= "Tom"`：默认值为 `"Tom"`
- `-> str`：返回值预期是字符串

类型注释和默认值是两件不同的事

#### 8. 类型注释的作用

类型注释主要有三个作用：

1. **提高可读性：** 读代码时更容易知道参数和返回值的预期类型
2. **辅助编辑器：** 编辑器可以提供更准确的补全和提示
3. **辅助检查错误：** 静态类型检查工具可以发现部分类型不匹配的问题

它不会自动取代运行时的数据验证

## 进阶技巧：generator 生成器（yield 关键字）

### 什么是生成器

生成器（Generator）是一种特殊的迭代器，可以**每次产生一个值，而不是一次性生成所有结果**。

例如，需要生成 1～5 的数字。

普通列表：

```python
nums = [1, 2, 3, 4, 5]

for num in nums:
    print(num)
```

使用生成器：

```python
def get_nums():
    yield 1
    yield 2
    yield 3
    yield 4
    yield 5

for num in get_nums():
    print(num)
```

两种写法都能依次输出 1～5，但生成器可以在需要时逐个产生数据，不必提前创建一个完整列表。

### `yield` 关键字

#### 1. `yield` 的作用

`yield` 用于生成一个值，并暂停当前函数的执行。下一次继续获取数据时，函数会从暂停的位置继续执行。

```python
def test():
    print("开始")
    yield 10

    print("继续")
    yield 20

    print("结束")

g = test()

print(next(g))
print(next(g))
print(next(g))
```

输出：

```text
开始
10
继续
20
结束
Traceback ...
StopIteration
```

最后一次 `next(g)` 会引发 `StopIteration`，表示生成器已经没有更多数据了。

执行过程：

1. 调用 `test()`：得到生成器对象，函数体还没有开始执行。
2. 第一次 `next(g)`：执行到第一个 `yield`，返回 `10`，并暂停。
3. 第二次 `next(g)`：从暂停处继续，执行到第二个 `yield`，返回 `20`，并暂停。
4. 第三次 `next(g)`：继续执行到函数结束，没有更多值，因此抛出 `StopIteration`。

#### 2. `yield` 与 `return` 的区别

| 对比 | `yield` | `return` |
|---|---|---|
| 作用 | 产生一个值并暂停函数 | 结束函数并返回结果 |
| 执行后能否继续 | 可以通过后续迭代继续 | 不会继续执行该函数 |
| 常见用途 | 生成器、逐个产生数据 | 返回计算结果 |

普通函数：

```python
def test():
    return 10
    return 20

print(test())
# 10
```

遇到第一个 `return` 后，函数就结束了，第二个 `return` 不会执行。

生成器函数：

```python
def test():
    yield 10
    yield 20

g = test()

print(next(g))  # 10
print(next(g))  # 20
```

两个 `yield` 都可以依次产生值。

**记忆：`return` 是结束并返回，`yield` 是产生值并暂停。**

### 创建生成器？

#### 1. 使用生成器函数

只要函数体中包含 `yield`，调用该函数时就会得到一个生成器对象。

```python
def count(n):
    i = 1

    while i <= n:
        yield i
        i += 1

g = count(3)

print(next(g))  # 1
print(next(g))  # 2
print(next(g))  # 3
```

这里每次执行到 `yield i`，都会返回当前的 `i`，并暂停执行。下一次继续时，才执行 `i += 1`。

#### 2. 使用生成器表达式

生成器表达式的写法与列表推导式很相似，只是把方括号 `[]` 改成圆括号 `()`。

```python
# 列表推导式
nums = [i * 2 for i in range(5)]

# 生成器表达式
g = (i * 2 for i in range(5))
```

区别：

```python
print(nums)
# [0, 2, 4, 6, 8]

print(next(g))
# 0

print(next(g))
# 2
```

- 列表推导式会立即创建列表。
- 生成器表达式会创建生成器对象，数据在迭代时逐个产生。

注意：生成器是一次性向前迭代的。已经取出的值不会自动重新提供。

### 生成器与 `for` 循环

实际使用中，通常不需要手动调用 `next()`，直接使用 `for` 循环即可。

```python
def count(n):
    i = 1

    while i <= n:
        yield i
        i += 1

for num in count(3):
    print(num)
```

输出：

```text
1
2
3
```

`for` 循环会自动获取下一个值，并在生成器耗尽时正常结束，不需要自己处理 `StopIteration`。

### 为什么要使用生成器

#### 1. 节省内存

假设需要处理大量数据。

列表方式：

```python
nums = [i for i in range(1000000)]
```

这会创建一个包含一百万个整数的列表。

生成器方式：

```python
nums = (i for i in range(1000000))
```

这会创建一个生成器对象，迭代时才逐个产生数字，而不是提前创建完整列表。

因此，当数据量很大、只需要逐个处理结果时，生成器通常更节省内存。

注意：如果最终还是把全部结果收集到列表中，依然需要相应的内存。

#### 2. 逐步处理数据

例如，依次读取文件中的每一行：

```python
def read_lines(filename):
    with open(filename, "r", encoding="utf-8") as file:
        for line in file:
            yield line.strip()

for line in read_lines("data.txt"):
    print(line)
```

生成器可以逐行提供数据，不必一次性把整个文件的所有内容读入内存。

### 生成器的常见注意事项

#### 1. 生成器不会在创建时立即执行函数体

```python
def test():
    print("执行了")
    yield 1

g = test()
print("创建完成")
```

输出：

```text
创建完成
```

因为调用 `test()` 只是创建生成器对象，函数体要等到开始迭代时才执行。

#### 2. 生成器通常只能遍历一次

```python
g = (i for i in range(3))

print(list(g))
# [0, 1, 2]

print(list(g))
# []
```

第一次遍历已经取完所有数据，第二次没有剩余数据。

如果需要重新遍历，可以重新创建生成器。

#### 3. 生成器结束后不能继续产生数据

```python
def test():
    yield 1

g = test()

print(next(g))  # 1
print(next(g))  # 抛出 StopIteration
```

当生成器执行结束，就没有更多值了。使用 `for` 循环时，Python 会自动处理这个结束信号。

