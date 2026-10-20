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

装饰器中通常使用return wrapper，让调用者以后再执行包装函数。

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
将接收到的参数传递给原函数，使装饰器可以适用于不同参数形式的函数。\


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


装饰器还可以用于日志记录、权限检查、缓存等场景。
