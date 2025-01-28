# Python——那些我不知道的

## 字典中的使用方法及作用

在 Python 中，字典 (`dict`) 对象有许多方法和属性。以下是一些常用的字典方法及其作用：

### `dict.clear()`

作用：**移除字典中的所有元素**

```python
d = {'name': 'Alice', 'age': 25}
d.clear()
print(d)  # 输出: {}
```

### `dict.copy()`

作用：**返回字典的浅复制**。

```python
d = {'name': 'Alice', 'age': 25}
d_copy = d.copy()
print(d_copy)  # 输出: {'name': 'Alice', 'age': 25}
```

### `dict.fromkeys(seq,[value])`：

作用：**创建一个新字典，以序列 `seq` 中的元素为键，`value` 为所有键对应的初始值。**

```python
keys = ['a', 'b', 'c']
d = dict.fromkeys(keys, 0)
print(d)  # 输出: {'a': 0, 'b': 0, 'c': 0}
```

### ==`dict.get(key,[default])`==：

作用：**返回指定键的值，如果键不在字典中，返回默认值 `default`。**

```python
d = {'name': 'Alice', 'age': 25}
print(d.get('name'))  # 输出: Alice
print(d.get('city', 'Unknown'))  # 输出: Unknown
```

### `dict.items()`：

作用：**返回一个包含字典键值对的视图对象**。

```python
d = {'name': 'Alice', 'age': 25}
print(d.items())  # 输出: dict_items([('name', 'Alice'), ('age', 25)])
```

### `dict.keys()`：

作用：**返回一个包含字典所有键的视图对象**。

```python
d = {'name': 'Alice', 'age': 25}
print(d.keys())  # 输出: dict_keys(['name', 'age'])
```

### ==`dict.pop(key,[default])`==：

作用：**移除指定键并返回其值，如果键不存在，返回默认值 `default`**。

```python
d = {'name': 'Alice', 'age': 25}
age = d.pop('age')
print(age)  # 输出: 25
print(d)  # 输出: {'name': 'Alice'}
```

### ==`dict.popitem()`==：

作用：**移除并返回字典中的最后一个键值对**。

```python
d = {'name': 'Alice', 'age': 25}
item = d.popitem()
print(item)  # 输出: ('age', 25)
print(d)  # 输出: {'name': 'Alice'}
```

### `dict.setdefault(key,[default])`：

作用：**如果键存在于字典中，返回其值；如果键不存在，则插入键并设置为默认值 `default`。**

```python
d = {'name': 'Alice'}
age = d.setdefault('age', 25)
print(age)  # 输出: 25
print(d)  # 输出: {'name': 'Alice', 'age': 25}
```

### ==`dict.update([other])`：==

作用：**用 `other` 中的键值对更新字典。**

```python
d = {'name': 'Alice'}
d.update({'age': 25, 'city': 'New York'})
print(d)  # 输出: {'name': 'Alice', 'age': 25, 'city': 'New York'}
```

### `dict.values()`：

作用：**返回一个包含字典所有值的视图对象**。

```python
d = {'name': 'Alice', 'age': 25}
print(d.values())  # 输出: dict_values(['Alice', 25])
```

## 集合的使用方法和作用

### ==`set.add(elem)`==

作用：**向集合中添加元素** 
   ```python
   s = {1, 2, 3}
   s.add(4)
   print(s)  # 输出: {1, 2, 3, 4}
   ```

### `set.clear()`

作用：**移除集合中的所有元素**。
   ```python
   s = {1, 2, 3}
   s.clear()
   print(s)  # 输出: set()
   ```

### `set.copy()`

作用：**返回集合的浅复制**。
   ```python
   s = {1, 2, 3}
   s_copy = s.copy()
   print(s_copy)  # 输出: {1, 2, 3}
   ```

### ==`set.difference(others)`==

作用：**返回一个新的集合，包含在当前集合但不在其他集合中的元素**。
   ```python
   s1 = {1, 2, 3}
   s2 = {2, 3, 4}
   diff = s1.difference(s2)
   print(diff)  # 输出: {1}
   ```

### `set.difference_update(others)`

作用：**移除当前集合中存在于其他集合中的元素**。
   ```python
   s1 = {1, 2, 3}
   s2 = {2, 3, 4}
   s1.difference_update(s2)
   print(s1)  # 输出: {1}
   ```

### ==`set.discard(elem)`==

作用：**如果元素 `elem` 在集合中，移除它**。
   ```python
   s = {1, 2, 3}
   s.discard(2)
   print(s)  # 输出: {1, 3}
   ```

### ==`set.intersection(others)`==

作用：**返回一个新的集合，包含当前集合和其他集合的交集**。
   ```python
   s1 = {1, 2, 3}
   s2 = {2, 3, 4}
   inter = s1.intersection(s2)
   print(inter)  # 输出: {2, 3}
   ```

> [!NOTE]
>
> 也可以用 **s1 & s2** 进行取交集的操作

### `set.intersection_update(others)`

作用：更新当前集合，只保留它与其他集合的交集。
   ```python
   s1 = {1, 2, 3}
   s2 = {2, 3, 4}
   s1.intersection_update(s2)
   print(s1)  # 输出: {2, 3}
   ```

### `set.isdisjoint(other)`

作用：如果当前集合与另一个集合没有交集，返回 `True`，否则返回 `False`。
   ```python
   s1 = {1, 2, 3}
   s2 = {4, 5, 6}
   print(s1.isdisjoint(s2))  # 输出: True
   ```

### ==`set.issubset(other)`==

作用：如果当前集合是另一个集合的子集，返回 `True`，否则返回 `False`。
    ```python
    s1 = {1, 2}
    s2 = {1, 2, 3}
    print(s1.issubset(s2))  # 输出: True
    ```

### `set.issuperset(other)`

作用：如果当前集合是另一个集合的超集，返回 `True`，否则返回 `False`。
    ```python
    s1 = {1, 2, 3}
    s2 = {1, 2}
    print(s1.issuperset(s2))  # 输出: True
    ```

### ==`set.pop()`==

作用：移除并返回集合中的一个不确定的元素。如果集合为空，会引发 `KeyError`。
    ```python
    s = {1, 2, 3}
    elem = s.pop()
    print(elem)  # 输出: 1（或其他元素）
    print(s)  # 输出: {2, 3}（或其他剩余元素）
    ```

### ==`set.remove(elem)`==

作用：移除集合中的元素 `elem`。如果 `elem` 不在集合中，会引发 `KeyError`。
    ```python
    s = {1, 2, 3}
    s.remove(2)
    print(s)  # 输出: {1, 3}
    ```

> [!IMPORTANT]
>
> 这里的remove用法是删去**集合中所有的目标元素**，而非第一个

### `set.symmetric_difference(other)`

作用：返回一个新的集合，包含当前集合和另一个集合中不重复的元素。
    ```python
    s1 = {1, 2, 3}
    s2 = {3, 4, 5}
    sym_diff = s1.symmetric_difference(s2)
    print(sym_diff)  # 输出: {1, 2, 4, 5}
    ```

### `set.symmetric_difference_update(other)`

作用：更新当前集合，只保留它与另一个集合中不重复的元素。
    ```python
    s1 = {1, 2, 3}
    s2 = {3, 4, 5}
    s1.symmetric_difference_update(s2)
    print(s1)  # 输出: {1, 2, 4, 5}
    ```

### ==`set.union(others)`==

作用：返回一个新的集合，包含当前集合和其他所有集合的并集。
    ```python
    s1 = {1, 2, 3}
    s2 = {3, 4, 5}
    union = s1.union(s2)
    print(union)  # 输出: {1, 2, 3, 4, 5}
    ```

> [!IMPORTANT]
>
> 也可以用 **s1 | s2** 进行取并集的操作

### `set.update(others)`

作用：用其他集合的并集更新当前集合。
    ```python
    s1 = {1, 2, 3}
    s2 = {3, 4, 5}
    s1.update(s2)
    print(s1)  # 输出: {1, 2, 3, 4, 5}
    ```

> [!IMPORTANT]
>
> 在update()括号里也可以**直接输入自定义的集合内容**

## 列表的常见用法与作用

在 Python 中，列表 (`list`) 对象有许多方法和属性。以下是一些常用的列表方法及其作用：

### ==`list.append(x)`==：

作用：在列表末尾添加一个元素 `x`。

```python
L = [1, 2, 3]
L.append(4)
print(L)  # 输出: [1, 2, 3, 4]
```

### `list.extend(iterable)`：

作用：用可迭代对象 `iterable` 扩展列表。

```python
L = [1, 2, 3]
L.extend([4, 5])
print(L)  # 输出: [1, 2, 3, 4, 5]
```

### ==`list.insert(i, x)`==：

在指定位置 `i` 插入元素 `x`。

```python
L = [1, 2, 3]
L.insert(1, 4)
print(L)  # 输出: [1, 4, 2, 3]
```

### ==`list.remove(x)`==：

移除列表中**第一个**值为 `x` 的元素。

**如果没有这样的元素，会引发 `ValueError`。**

```python
L = [1, 2, 3, 2]
L.remove(2)
print(L)  # 输出: [1, 3, 2]
```

### ==`list.pop([i])`==：

`移除并返回列表中指定位置 `i` 的元素。如果没有指定位置，默认移除并返回最后一个元素。

```python
L = [1, 2, 3]
elem = L.pop()
print(elem)  # 输出: 3
print(L)  # 输出: [1, 2]
```

### `list.clear()`：

移除列表中的所有元素。

```python
L = [1, 2, 3]
L.clear()
print(L)  # 输出: []
```

### ==`list.index(x，[start，end])`==：

返回列表中**第一个**值为 `x` 的元素的索引。

**如果没有这样的元素，会引发 `ValueError`。**可以通过 `start` 和 `end` 参数限定搜索范围。

```python
L = [1, 2, 3, 2]
index = L.index(2)
print(index)  # 输出: 1
```

### `list.count(x)`：

返回列表中值为 `x` 的元素的个数。

```python
L = [1, 2, 3, 2]
count = L.count(2)
print(count)  # 输出: 2
```

### `list.sort(key=None, reverse=False)`：

对列表中的元素进行排序。

**`key` 是一个函数，用于指定排序的依据**

`reverse` 是一个布尔值，如果为 `True`，则列表按降序排序。

```python
L = [3, 1, 2]
L.sort()
print(L)  # 输出: [1, 2, 3]
```

### ==`list.reverse()`==：

反转列表中的元素。

```python
L = [1, 2, 3]
L.reverse()
print(L)  # 输出: [3, 2, 1]
```

### `list.copy()`：

返回列表的浅复制。

```python
L = [1, 2, 3]
L_copy = L.copy()
print(L_copy)  # 输出: [1, 2, 3]
```

这些方法和属性可以帮助你有效地操作和管理列表。

## 元组的常见用法与作用

### `tuple.count(x)`：

返回元组中值为 `x` 的元素的个数。

```python
t = (1, 2, 3, 2)
count = t.count(2)
print(count)  # 输出: 2
```

### ==`tuple.index(x，[start,end]])`==：

返回元组中**第一个**值为 `x` 的元素的索引。

如果没有这样的元素，会引发 `ValueError`。可以通过 `start` 和 `end` 参数限定搜索范围。

```python
t = (1, 2, 3, 2)
index = t.index(2)
print(index)  # 输出: 1
```

此外，**元组还支持所有通用的序列操作**，例如索引、切片、连接和重复等。以下是一些示例：

### 序列操作

- 索引：
  ```python
  t = (1, 2, 3)
  print(t[0])  # 输出: 1
  ```

- 切片：
  ```python
  t = (1, 2, 3, 4, 5)
  print(t[1:3])  # 输出: (2, 3)
  ```

- 连接：
  ```python
  t1 = (1, 2)
  t2 = (3, 4)
  t3 = t1 + t2
  print(t3)  # 输出: (1, 2, 3, 4)
  ```

- 重复：
  ```python
  t = (1, 2)
  t2 = t * 3
  print(t2)  # 输出: (1, 2, 1, 2, 1, 2)
  ```

这些操作和方法可以帮助你有效地使用和管理元组。

## 输入输出的其他常见用法

在 Python 中，输入输出函数有多种用法，主要包括 `input()` 和 `print()` 函数。以下是一些常见的用法和示例：

### `input()` 函数

`input()` 函数用于从标准输入读取一行，并返回字符串类型的数据。

#### 基本用法：

```python
name = input("Enter your name: ")
print(f"Hello, {name}!")
```

#### ==将输入转换为其他类型==：

```python
age = int(input("Enter your age: "))
print(f"You are {age} years old.")
```

#### ==读取多个输入值==：

```python
x, y = input("Enter two numbers separated by space: ").split()
x = int(x)
y = int(y)
print(f"The sum of {x} and {y} is {x + y}.")
```

> [!IMPORTANT]
>
> `.split()` 是 Python 字符串方法的一部分。**它用于将字符串拆分为列表，默认情况下按空格分隔。**
>
> ```python
> x, y = input("Enter two numbers separated by space: ").split()
> ```
>
> 这行代码的作用是：
>
> 1. `input("Enter two numbers separated by space: ")`提示用户输入**两个用空格分隔的数字**，并将输入作为字符串返回，且存在一定的==对应关系==。
>
> 2. `.split()` 方法将输入的字符串按空格分隔成一个列表。
>



### `print()` 函数
`print()` 函数用于将输出写到标准输出设备（屏幕）。

#### 基本用法：

```python
print("Hello, World!")
```

#### 使用多个参数：

```python
print("The answer is", 42)
```

#### ==使用格式化字符串（f-string）==：

```python
name = "Alice"
age = 30
print(f"{name} is {age} years old.")
```

#### ==指定分隔符和结束符==：

```python
print("Hello", "World", sep=", ", end="!\n")
```

#### 输出到文件：

```python
with open("output.txt", "w") as f:
    print("Hello, World!", file=f)
```

#### 使用 `str.format()` 方法进行格式化输出：

```python
name = "Alice"
age = 30
print("{} is {} years old.".format(name, age))
```

## Python内置函数收藏

### `isinstance`函数——数据类型检查

`isinstance` 函数用于检查一个对象是否是指定类型或其子类的实例。它的语法如下：

```python
isinstance(object, classinfo)
```

- `object`：要检查的对象。
- `classinfo`：**可以是一个类型或类型的元组。**

==如果 `object` 是 `classinfo` 的实例，或者是其子类的实例，`isinstance` 返回 `True`==，否则返回 `False`。

```python
x = 10
print(isinstance(x, int))  # 输出: True

y = [1, 2, 3]
print(isinstance(y, list))  # 输出: True

z = "hello"
print(isinstance(z, (int, str)))  # 输出: True，因为 z 是 str 类型
```

### `enumerate()`——(index,value)返回

`enumerate` 函数用于==在遍历可迭代对象（如列表、元组或字符串）时，同时获取元素的索引和值。==

它返回一个枚举对象，该对象生成包含**索引和值的元组**。

```python
# ...existing code...
my_list = ['a', 'b', 'c']
for index, value in enumerate(my_list):
    print(index, value)
# ...existing code...
```

输出将是：
```
0 a
1 b
2 c
```

这样，你可以在遍历时同时访问元素的索引和元素本身。

### `range()`——整数序列生成

`range` 函数用于**生成一个整数序列**，通常用于在 `for` 循环中迭代特定次数。

它有三种主要用法：

1. **`range(stop)`**: 生成从 `0` 到 `stop-1` 的整数序列。
2. **`range(start, stop)`**: 生成从 `start` 到 `stop-1` 的整数序列。
3. **`range(start, stop, step)`**: 生成从 `start` 到 `stop-1` 的整数序列，步长为 `step`。

示例代码：

```python
# ...existing code...
# 使用 range(stop)
for i in range(5):
    print(i)  # 输出 0, 1, 2, 3, 4

# 使用 range(start, stop)
for i in range(2, 5):
    print(i)  # 输出 2, 3, 4

# 使用 range(start, stop, step)
for i in range(1, 10, 2):
    print(i)  # 输出 1, 3, 5, 7, 9
# ...existing code...
```

这些用法可以帮助你生成所需的整数序列，并在循环中使用。

### 字符串变换函数集合

以下是 Python 中常用的字符串变换函数及其作用：

1. **`str.upper()`**: 将字符串中的所有字符转换为大写。
   
   ```python
   s = "hello"
   print(s.upper())  # 输出: "HELLO"
   ```
   
2. **`str.lower()`**: 将字符串中的所有字符转换为小写。
   ```python
   s = "HELLO"
   print(s.lower())  # 输出: "hello"
   ```

3. **`str.capitalize()`**: 将字符串的第一个字符转换为大写，其余字符转换为小写。
   ```python
   s = "hello world"
   print(s.capitalize())  # 输出: "Hello world"
   ```

4. **`str.title()`**: 将字符串中的每个单词的首字母转换为大写。
   ```python
   s = "hello world"
   print(s.title())  # 输出: "Hello World"
   ```

5. **`str.swapcase()`**: 将字符串中的大写字符转换为小写，小写字符转换为大写。
   ```python
   s = "Hello World"
   print(s.swapcase())  # 输出: "hELLO wORLD"
   ```

6. **`str.strip([chars])`**: 去除字符串两端的指定字符（默认为空格）。
   ```python
   s = "  hello  "
   print(s.strip())  # 输出: "hello"
   ```

7. **`str.lstrip([chars])`**: 去除字符串左端的指定字符（默认为空格）。
   ```python
   s = "  hello  "
   print(s.lstrip())  # 输出: "hello  "
   ```

8. **`str.rstrip([chars])`**: 去除字符串右端的指定字符（默认为空格）。
   ```python
   s = "  hello  "
   print(s.rstrip())  # 输出: "  hello"
   ```

9. **`str.replace(old, new[, count])`**: 将字符串中的 `old` 子字符串替换为 `new` 子字符串，可以指定替换的次数 `count`。
   ```python
   s = "hello world"
   print(s.replace("world", "Python"))  # 输出: "hello Python"
   ```

10. **`str.split(sep=None, maxsplit=-1)`**: 将字符串按照指定的分隔符 `sep` 分割为列表，可以指定最大分割次数 `maxsplit`。
    ```python
    s = "hello world"
    print(s.split())  # 输出: ["hello", "world"]
    ```

11. **`str.join(iterable)`**: 将可迭代对象中的元素连接成一个字符串，元素之间用字符串 `str` 作为分隔符。
    ```python
    l = ["hello", "world"]
    print(" ".join(l))  # 输出: "hello world"
    ```

12. **`str.find(sub[, start[, end]])`**: 返回子字符串 `sub` 在字符串中的最低索引，如果没有找到则返回 -1。
    ```python
    s = "hello world"
    print(s.find("world"))  # 输出: 6
    ```

13. **`str.index(sub[, start[, end]])`**: 返回子字符串 `sub` 在字符串中的最低索引，如果没有找到则抛出 ValueError。
    ```python
    s = "hello world"
    print(s.index("world"))  # 输出: 6
    ```

14. **`str.startswith(prefix[, start[, end]])`**: 判断字符串是否以指定的前缀 `prefix` 开头。
    ```python
    s = "hello world"
    print(s.startswith("hello"))  # 输出: True
    ```

15. **`str.endswith(suffix[, start[, end]])`**: 判断字符串是否以指定的后缀 `suffix` 结尾。
    ```python
    s = "hello world"
    print(s.endswith("world"))  # 输出: True
    ```

这些函数可以帮助你在处理字符串时进行各种变换和操作。

### `list()`——列表替换与更新

`list()` 函数用于将一个可迭代对象（如字符串、元组、集合、字典、生成器等）转换为列表。

它的作用是==创建一个新的列表，其中包含了可迭代对象中的所有元素==。

以下是一些常见的用法示例：

1. **将字符串转换为列表**：
   ```python
   s = "hello"
   lst = list(s)
   print(lst)  # 输出: ['h', 'e', 'l', 'l', 'o']
   ```

2. **将元组转换为列表**：
   ```python
   t = (1, 2, 3)
   lst = list(t)
   print(lst)  # 输出: [1, 2, 3]
   ```

3. **将集合转换为列表**：
   ```python
   s = {1, 2, 3}
   lst = list(s)
   print(lst)  # 输出: [1, 2, 3]
   ```

4. **将字典的键转换为列表**：
   ```python
   d = {'a': 1, 'b': 2, 'c': 3}
   lst = list(d)
   print(lst)  # 输出: ['a', 'b', 'c']
   ```

5. **将生成器转换为列表**：
   ```python
   def fib(max):
       n, a, b = 0, 0, 1
       while n < max:
           yield b
           a, b = b, a + b
           n = n + 1
   
   m = fib(6)
   lst = list(m)
   print(lst)  # 输出: [1, 1, 2, 3, 5, 8]
   ```

### python内置函数总结整理

####  **常用基础函数**

- **`print()`**: 输出内容到控制台。
  
  ```python
  print("Hello, World!")  # 输出: Hello, World!
  ```
  
- **`len()`**: 返回对象的长度（如字符串、列表、元组等）。
  ```python
  len("Python")  # 输出: 6
  ```

- **`type()`**: 返回对象的类型。
  ```python
  type(42)  # 输出: <class 'int'>
  ```

- **`id()`**: 返回对象的内存地址。
  ```python
  id("Python")  # 输出: 内存地址（整数）
  ```

- **`input()`**: 从用户输入中读取数据，返回字符串。
  ```python
  name = input("Enter your name: ")
  ```

#### **类型转换函数**

- **`int()`**: 将对象转换为整数。
  ```python
  int("42")  # 输出: 42
  ```

- **`float()`**: 将对象转换为浮点数。
  ```python
  float("3.14")  # 输出: 3.14
  ```

- **`str()`**: 将对象转换为字符串。
  ```python
  str(42)  # 输出: "42"
  ```

- **`bool()`**: 将对象转换为布尔值。
  ```python
  bool(0)  # 输出: False
  ```

- **`list()`**: 将可迭代对象转换为列表。
  ```python
  list("Python")  # 输出: ['P', 'y', 't', 'h', 'o', 'n']
  ```

- **`tuple()`**: 将可迭代对象转换为元组。
  ```python
  tuple([1, 2, 3])  # 输出: (1, 2, 3)
  ```

- **`set()`**: 将可迭代对象转换为集合。
  ```python
  set([1, 2, 2, 3])  # 输出: {1, 2, 3}
  ```

- **`dict()`**: 创建字典。
  ```python
  dict(name="Alice", age=30)  # 输出: {'name': 'Alice', 'age': 30}
  ```

####  **数学运算函数**

- **`abs()`**: 返回绝对值。
  ```python
  abs(-10)  # 输出: 10
  ```

- **`round()`**: 四舍五入。
  ```python
  round(3.14159, 2)  # 输出: 3.14
  ```

- **`min()`**: 返回最小值。
  
  ```python
  min(1, 2, 3)  # 输出: 1
  ```
  
- **`max()`**: 返回最大值。
  ```python
  max(1, 2, 3)  # 输出: 3
  ```

- **`sum()`**: 求和。
  ```python
  sum([1, 2, 3])  # 输出: 6
  ```

- **`pow()`**: 计算幂。
  
  ```python
  pow(2, 3)  # 输出: 8
  ```
  
- **`divmod()`**: 返回商和余数。
  
  ```python
  divmod(10, 3)  # 输出: (3, 1)
  ```

####  **迭代与序列操作**

- **`range()`**: 生成一个整数序列。
  ```python
  list(range(5))  # 输出: [0, 1, 2, 3, 4]
  ```

- **`enumerate()`**: 返回枚举对象，生成索引和值的对。
  ```python
  list(enumerate(["a", "b", "c"]))  # 输出: [(0, 'a'), (1, 'b'), (2, 'c')]
  ```

- **`zip()`**: 将多个可迭代对象打包成元组。
  ```python
  list(zip([1, 2], ["a", "b"]))  # 输出: [(1, 'a'), (2, 'b')]
  ```

- **`sorted()`**: 返回排序后的列表。
  ```python
  sorted([3, 1, 2])  # 输出: [1, 2, 3]
  ```

- **`reversed()`**: 返回反转的迭代器。
  ```python
  list(reversed([1, 2, 3]))  # 输出: [3, 2, 1]
  ```

#### **逻辑与判断**

- **`all()`**: 如果所有元素为真，返回 `True`。
  ```python
  all([True, 1, "hello"])  # 输出: True
  ```

- **`any()`**: 如果任一元素为真，返回 `True`。
  ```python
  any([False, 0, "hello"])  # 输出: True
  ```

- **`isinstance()`**: 检查对象是否是某个类的实例。
  ```python
  isinstance(42, int)  # 输出: True
  ```

- **`issubclass()`**: 检查一个类是否是另一个类的子类。
  ```python
  issubclass(bool, int)  # 输出: True
  ```

#### **文件与输入输出**

- **`open()`**: 打开文件并返回文件对象。
  ```python
  file = open("example.txt", "r")
  ```

- **`eval()`**: 执行字符串形式的 Python 表达式。
  ```python
  eval("2 + 3")  # 输出: 5
  ```

- **`exec()`**: 执行字符串形式的 Python 代码。
  ```python
  exec("x = 10")
  ```

#### **其他实用函数**

- **`help()`**: 查看对象的帮助信息。
  ```python
  help(print)  # 显示 print 函数的帮助信息
  ```

- **`dir()`**: 返回对象的属性和方法列表。
  ```python
  dir("hello")  # 返回字符串对象的所有方法
  ```

- **`globals()`**: 返回全局变量的字典。
- **`locals()`**: 返回局部变量的字典。

---

## 字符串的操作总结

在 Python 中，字符串（`str`）是一种不可变序列类型，支持丰富的操作。以下是 Python 中对字符串可以实现的主要操作：

### **字符串创建与基本操作**
- **创建字符串**：
  ```python
  s = "Hello, World!"
  ```

- **字符串拼接**：
  ```python
  s1 = "Hello"
  s2 = "World"
  s = s1 + " " + s2  # 输出: "Hello World"
  ```

- **字符串重复**：
  ```python
  s = "Hi" * 3  # 输出: "HiHiHi"
  ```

- **字符串长度**：
  ```python
  len("Python")  # 输出: 6
  ```

### **字符串索引与切片**
- **索引**：
  ```python
  s = "Python"
  print(s[0])  # 输出: 'P'
  print(s[-1]) # 输出: 'n'（负索引表示从末尾开始）
  ```

- **切片**：
  ```python
  s = "Python"
  print(s[1:4])  # 输出: 'yth'（从索引 1 到 3）
  print(s[:3])   # 输出: 'Pyt'（从开头到索引 2）
  print(s[3:])   # 输出: 'hon'（从索引 3 到末尾）
  print(s[::2])  # 输出: 'Pto'（步长为 2）
  ```

### **字符串查找与替换**
- **查找子字符串**：
  ```python
  s = "Hello, World!"
  print(s.find("World"))  # 输出: 7（返回第一次出现的索引）
  print(s.find("Python")) # 输出: -1（未找到）
  ```

- **替换子字符串**：
  ```python
  s = "Hello, World!"
  s_new = s.replace("World", "Python")  # 输出: "Hello, Python!"
  ```

- **检查前缀或后缀**：
  ```python
  s = "Hello, World!"
  print(s.startswith("Hello"))  # 输出: True
  print(s.endswith("!"))        # 输出: True
  ```

### 字符串分割与连接
- **分割字符串**：
  ```python
  s = "apple,banana,cherry"
  parts = s.split(",")  # 输出: ['apple', 'banana', 'cherry']
  ```

- **连接字符串**：
  ```python
  parts = ["apple", "banana", "cherry"]
  s = ",".join(parts)  # 输出: "apple,banana,cherry"
  ```

### **字符串格式化**
- **`f-string`（推荐）**：
  ```python
  name = "Alice"
  age = 30
  s = f"My name is {name} and I am {age} years old."
  ```

- **`format()` 方法**：
  ```python
  s = "My name is {} and I am {} years old.".format("Alice", 30)
  ```

- **`%` 格式化**（旧式）：
  ```python
  s = "My name is %s and I am %d years old." % ("Alice", 30)
  ```

### 字符串大小写转换
- **转换为大写**：
  ```python
  s = "hello"
  s_upper = s.upper()  # 输出: "HELLO"
  ```

- **转换为小写**：
  ```python
  s = "HELLO"
  s_lower = s.lower()  # 输出: "hello"
  ```

- **首字母大写**：
  ```python
  s = "hello world"
  s_title = s.title()  # 输出: "Hello World"
  ```

- **大小写互换**：
  ```python
  s = "Hello World"
  s_swap = s.swapcase()  # 输出: "hELLO wORLD"
  ```

### 字符串修剪与填充
- **去除空白字符**：
  ```python
  s = "  Hello, World!  "
  s_strip = s.strip()  # 输出: "Hello, World!"
  ```

- **填充字符串**：
  ```python
  s = "Hello"
  s_padded = s.center(10, "*")  # 输出: "**Hello***"
  ```

### **字符串检查**
- **是否为字母或数字**：
  ```python
  s = "Hello123"
  print(s.isalnum())  # 输出: True
  ```

- **是否为字母**：
  ```python
  s = "Hello"
  print(s.isalpha())  # 输出: True
  ```

- **是否为数字**：
  ```python
  s = "123"
  print(s.isdigit())  # 输出: True
  ```

- **是否为空白字符**：
  ```python
  s = "  "
  print(s.isspace())  # 输出: True
  ```

### **字符串编码与解码**
- **编码为字节**：
  ```python
  s = "Hello"
  b = s.encode("utf-8")  # 输出: b'Hello'
  ```

- **解码为字符串**：
  ```python
  b = b'Hello'
  s = b.decode("utf-8")  # 输出: "Hello"
  ```

### **其他操作**
- **统计子字符串出现次数**：
  ```python
  s = "Hello, Hello, World!"
  count = s.count("Hello")  # 输出: 2
  ```

- **反转字符串**：
  ```python
  s = "Python"
  s_reversed = s[::-1]  # 输出: "nohtyP"
  ```

- **检查字符串是否包含子字符串**：
  ```python
  s = "Hello, World!"
  print("World" in s)  # 输出: True
  ```

