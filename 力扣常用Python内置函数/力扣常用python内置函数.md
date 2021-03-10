### String

str.isalpha()：判断字符串是否只由字母组成
str.endswith(word)：判断字符串末尾是否是word
str.upper() ：把所有小写转换成大写
str.lower()：把所有大写转换成小写
str.capitalize()：把第一个字母转化为大写字母，其余小写
str.title()：把每个单词的第一个字母转化为大写，其余小写

### list

多维list初始化

```python
# 只能用👇
l = [[0 for i in range(n)] for j in range(n)]

# 不能用👇，否则改变某行某值时，别的会跟着变！！！
# 比如：l[0][0] = 2, ➡ [[2,0,0],[2,0,0],[2,0,0]]
l = [[0]*n]*n
```

倒叙：list.reverse() / list[::-1]
排序: list.sort()
利用collections.deque([])降低时间复杂度

```python
a = collections.deque([]) # 使list两端都是O(1)
a.popleft()
a.pop()
a.appendleft(x)
a.extend([x,y]) # iteratively
```

### dict

### 字典分别按key和value排序

```python
# 按key排序
d = {1:3, 2:2, 3:1}
sorted(d.keys(), reverse=True) # [3,2,1]
sorted(tryd.items(), key=lambda item:item[1]) # [(3, 1), (2, 2), (1, 3)]
```

### 字典初始化，更新

```python
a = {}
a = collections.defaultdict(list) #在调用a[key]时如果key不在字典中则返回默认值[]而不会报错
# 更新
a.update(b) #把b_dict的值赋给a_dict
```

### set

```python
set.add(item) # 添加元素
set.remove(item) # 删除元素
random.choice(tuple(set)) # 随机取一个元素
```

### heap

```python
heapq.heappop(heap) # pop出最小的元素
heapq.heappush(heap, item) # 插入元素
heapq.heapify([]) # 将list转化为heap（最小堆）
heapq._heapify_max(data) # 最大堆
heap.heapreplace(data, new_item) # pop出最小的元素并插入new_item
```

### 其他常用

range倒叙

```python
# n-1, ..., 1, 0
for i in range(n-1, -1, -1)
```

无穷 ∞ \infty ∞：float(“inf”)
isinstance(l, list)：判断是否是list
all((a,b,c))：如果a,b,c都是True则返回True
random.randint(a, b)：随机返回[a,b]间的整数

### 注意事项

全局变量
可变对象：list dict set
不可变对象：tuple string int float bool
可变对象在函数中可直接当全局变量使用
不可变对象在函数中需要声明"global var"，且不可用于递归recursive中
查询效率：set > dict >> list

### 其他知识点

^异或 1<<5，相当于把第5位从0变到1，从1变到0， 即实现大小写的转换
0 ^ 0=0 ， 0 ^ 1= 1 ， 1 ^ 0= 1 ， 1 ^ 1= 0
ord()返回对应的ASCII码
chr()返回对应的ASCII字符
itertools.product(a,b): 笛卡尔积

bisect(list, target)，二分查找，返回high，即若找到则坐标为high-1，若没找到则前一位是high-1，应插入high位
负数除以整数取余：比如-1%5=4（-1/5=（-1）余4）,-7/3=-3余2

```python
return ["".join(s) for s in itertools.product(*L)]
```

bisect(list, target)，二分查找，返回high，即若找到则坐标为high-1，若没找到则前一位是high-1，应插入high位
负数除以整数取余：比如-1%5=4（-1/5=（-1）余4）,-7/3=-3余2