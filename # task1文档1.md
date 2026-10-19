# task1文档1

## 基础容器：list 和 dict 的使用技巧

### list

#### 1.list的创建

##### 空列表
        ```python
        a = []
        b = list()
        ```
##### 字面量
        ```python
        nums = [1,2,3]
        ```
##### list的转换
        ```python
        list("abc") #['a','b','c']
        list(d.keys()) #等价于list(d),任何直接传字典等于传键、
        list(d.valus())
        list(d.items())
        list(range(5)) #0,1,2,3,4
        list(range(1,6))#1,2,3,4,5
        ```

#### 2.list的访问

##### list的下标
        ```python
        list[0] #第一个
        list[-1] #最后一个

        ```
##### 切片
        ```python
        #list[起始；结尾；步长] 左闭右开
        list[1:3]
        list[:3]
        list[2:]
        list[:]#全部
        list[::-1]#倒序输出
        ```
#### 3.list的添加

##### append()
        ```python
        s.append() #结尾添加
        ```
##### insert(下标，元素)
        ```python
        s.insert(2,3)
        ```
##### extend()
        ```python
        s.extend([1,2,3])#在结尾插入多个元素
        ```

#### 4.list的删除

##### remove()
        ```python
        s.remove(20) #删除第一个遇到的匹配项
        ```

##### pop(下标)
        ```python
        num = s.pop(1) #删除该下标元素并且返回
        ```

##### del
        ```python
        del nums[0] #删除不返回
        ```

##### clear()
        ```python
        nums.clear() # 全部删除
        ```

#### 5.list的查找

##### in
        ```python
        2 in nums # 返回值是布尔类型
        ```
##### index
        ```python
        nums.index(2) #返回第一次遇见匹配值的下标
        ```
##### count
        ```python
        nums.count(3) #查找3在列表中出现了几次
        ```

#### 6.list的排序

##### sort
        ```python
        nums.sort() #升序
        nums.sort(reverse = True) #降序
        nums.sort(key=abs) #按照绝对值排序
        ```
##### sorted
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



