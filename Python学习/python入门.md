## 列表

## 一.删除和添加

列表可以把它比做成c语言的数组，与数组不同的地方我认为 列表更加的灵活。

1.修改元素，在python中修改元素直接定义新的值即可 **对于 [-1] 总是索引到列表的最后一个元素**

```python
moto = ['li','zi','hao']
print(moto)
['li', 'zi', 'hao']

moto[0]= 'akali'
print(moto)
['akali', 'zi', 'hao']
```

2.添加元素

**append**附加，给列表附加元素时，他将添加到列表末尾

```python
#在末尾添加元素 append

moto.append('lisin')
print(moto） 
['akali', 'zi', 'hao', 'lisin']
```

**insert**插入，使用insert可以在列表各个位置添加新的元素，但是使用insert，需要指定添加元素的索引和值

```python
moto.insert(0,'otto')#添加到0位置处
print(moto)
['otto', 'akali', 'zi', 'hao', 'lisin']
```

3.插入元素

**del语句** 如果知道欲删除的元素的位置，可以使用del语句

```python
del moto[0]
print(moto)
['akali', 'zi', 'hao', 'lisin']
```

**pop** 用pop()删除元素 **可以接着使用它的值** 

```python
poped_moto = moto.pop()#弹出元素  根据索引
print(moto)
print(poped_moto)
['akali', 'zi', 'hao']
```

**remove** 根据值删除   只知道元素的值时就可以根据值删除元素

```python
#删除元素 通过值删除
moto.remove('zi')
print(moto)
['akali', 'hao']

```

## 二.组织列表

**sort** sort可以永久性的改变列表里的元素排列顺序

```python
cars =['bmw','audo','benzi']
print(cars)
['bmw', 'audo', 'benzi']
cars.sort()
print(cars)
['audo', 'benzi', 'bmw']
```

现在元素是按照字母顺序排列，同时可以向sort()传递 reverse=Ture  来反向排序。

```python
cars.sort(reverse=True)
print(cars)
['bmw', 'benzi', 'audo']
```

**对列表元素排列顺序的修改是永久性的**

**使用sorted()对列表进行临时修改** sorted函数可以按照特定的顺序修改列表元素，同时不影响他们在列表中的原始排列顺序。

```python
furt=['apple','water','strawberry','peech']
print(furt)
print(sorted(furt))
print(furt)


['apple', 'water', 'strawberry', 'peech']
['apple', 'peech', 'strawberry', 'water']#临时修改  没有改变原来的排列顺序
['apple', 'water', 'strawberry', 'peech']
```

**reverse** 倒着排列顺序 **reverse不是按与字母顺序相反的顺序排列，而是反转列表的元素排列顺序**、

reverse可以永久性的改变元素的排列顺序。

**使用函数len可以获得列表的长度**

## 三.操作列表

1.遍历整个列表，可以通过for循环实现

```python
humans =['alice','tom','jack','ada']
for i in range(4):
    print(humans[i])

alice
tom
jack
ada
```

```python
for human in humans:
    print(human)
  这样也可以实现
```

2.创建数值列表

**使用range创建数字列表**  可以使用list()将range的结果直接转化为列表

```python
numbers = list(range(1,10))
print(numbers)
[1, 2, 3, 4, 5, 6, 7, 8, 9]

```

由于差一原则 只返回1-9的数字

**同时range也可以指定插值类似于等差数列？**  

```python
numbers = list(range(1,10,3))后末尾的数字代表差值
print(numbers)
[1, 4, 7]

```

平方也可以实现

```python
sauqres=[]
for value in range(1,11):
    square=value**2
    sauqres.append(square)
print(sauqres)
--》[1, 4, 9, 16, 25, 36, 49, 64, 81, 100]
```

统计计算函数：**min()  max() sum()**

### 列表解析 --------

将for循环和创建新元素的代码合并成一行，并自动附加新元素，这种方法可以更加高效的创建列表。

```python
saqure01=[i**2 for i in range(1,11)]
print(saqure01)
[1, 4, 9, 16, 25, 36, 49, 64, 81, 100]
```

**使用列表的一部分**

**切片**通过设置一个范围可以索引处范围内的元素

例如指定索引0，3  返回索引为0，1，2的元素

```python
player =['jack','tom','aic','zoom']
print(player)
print(player[0:3])

['jack', 'tom', 'aic', 'zoom']
['jack', 'tom', 'aic']
```

如果没有指定第一个索引，那么将会自动从列表开头开始

**可以在切片中设置第三个值，这个值将会告诉python每隔几个单位提取一个元素**

**遍历切片 可以在for循环中使用切片**

```python
for i in player[0:3]:
    print(i)
```

### 复制列表

```python
my_foods =['pizza','falafel','carrot cake']
f_food = my_foods[:] #没有索引的切片
my_foods.append('cannoli')、#添加元素
f_food.append('ice cream') #添加元素
print(my_foods)
print(f_food)
#不使用切片无法复制 pl： my_foods=f_food 不可行
['pizza', 'falafel', 'carrot cake', 'cannoli']
['pizza', 'falafel', 'carrot cake', 'ice cream']
```

### 元组：不可变的列表

元组很像列表，但是用圆括号而非中括号表示。元组也可以通过索引来访问。**元组内的元素禁止被修改** 

虽然不能修改元组的元素，但是可以给储存元素的变量重新赋值。

## 四.if语句

基本结构和c语言差不多。

**if elif else**语句   elif代码行执行另一个if ，仅在前面的测试未通过的情况下才会发生。

**if语句处理列表**         

## 五.字典

**字典是一系列的键值对，每个键都与一个值相连**

```python
alien ={'color':'green','points':5}
#键值对之间用都逗号隔开
print(alien['color'])
```

**字典是一种动态结构，可随时在其中添加键值对**

```python
alien = {'color':'green','name':'jack'}
print(alien)
alien['age']=18
alien['len']=50
print(alien)

{'color': 'green', 'name': 'jack'}
{'color': 'green', 'name': 'jack', 'age': 18, 'len': 50}

```

**删除键值对，对于字典中不再需要的信息，可使用del语句将其相应的键值对彻底删除。 使用del语句时，必须指定字典名和要删除的键。**

```python
alien = {'color':'green','name':'jack'}
print(alien)
alien['age']=18
alien['len']=50
print(alien)

del alien['color']
print(alien

{'color': 'green', 'name': 'jack'}
{'color': 'green', 'name': 'jack', 'age': 18, 'len': 50}
{'name': 'jack', 'age': 18, 'len': 50}#删除后键'color'已经消失
```

**删除的键值对会永远消失**

**使用get()来访问值**  如果指定的值不存在时，使用方括号来访问值会发生问题。

```python
alien = {'color':'green','name':'jack'}
point_value = alien.get('point','5')#第一个参数用于指定键，（必不可少），第二个参数为指定键不存在时返回的值。
print(point_value)

5#指定键不存在，返回值为5
```

**通过for循环遍历字典**  

*编写遍历字典的for循环时，可以定义两个变量，用于储存键值对中的键和值， 第二部分包括字典名和函数items（），它返回一个键值对列表*

```python
girlfriend={
    'name':'xiaohua',
    'age' :'18',
    'height':'170cm',
    'city':'wuhan',
}
#定义两个变量，来分别传递键和值，通过items函数返回列表
for key,value in girlfriend.items():
    print(f"\nkey:{key}")
    print(f"\nvalue:{value}")
    
    key:name

value:xiaohua

key:age

value:18

key:height

value:170cm

key:city

value:wuhan

```

**通过keys 来遍历字典中所有的键**

```python
for massage in girlfriend.keys():#keys可加可不加
    print(massage)
name
age
height
city
```

**按照特定顺序遍历字典中所有的键**

```python
for massage01 in sorted(girlfriend.keys()):
    print(massage01)
#对字典调用sort参数，会在遍历之前 先对字典排序。
age
city
height
name
```

**遍历字典的所有值 ，可以使用values来返回一个值列表**

```python
for massage in girlfriend.values():
    print(massage)
```

**可以使用set来保证遍历出的集合中的元素时独一无二的**

**嵌套**

```python
aliens =[]#创建一个空字典

for alien_number in range(30):#创建循环向空字典中添加元素
    new_alien ={'color':'green','points':'5','speed':'slow'}
    aliens.append(new_alien)

for alien in aliens[:5]:#打印前五个
    print(alien)
```

**在字典中储存列表**

**在字典中储存字典**

```python
users = {#储存姓名和姓氏和地址
    'aeinstein':{
    'first':'albert',
    'last':'einstein',
    'location':'princetion',},

    'mcurie':{
        'first':'marie',
        'last':'curie',
        'location':'paris',
    },

}

for username, user_info in users.items():
    print(f"\nusername:{username}")
    full_name = f"{user_info['first']}{user_info['last']}"#可以看为类似于多维数组的形式
    location = user_info['location']

    print(f"\tFullname:{full_name.title()}")
    print(f"\tLocation: {location.title()}")
```

## 六.用户输入与while循环

**input** 能让程序停止工作，等待用户输入一些文本。使用input输入时 python将其解读为字符串，

**int** 能让python将输入内容解读为数值，将数的字符串转化为数值表示。

```python
currunt_number = 1;
while currunt_number <= 5:
    print(currunt_number)
    currunt_number += 1
```

**设置让while循环能够退出**

```python
prompt ="\n tell me something,and i will reapt it back to you"
prompt += "\nEnter 'quit' to end the program "
message ="" #创建变量用于记录用户输入的值
while message != 'quit':#进入循环时 python将会比较message的值
    message = input(prompt)
    print(message)
 ----》   
 tell me something,and i will reapt it back to you
Enter 'quit' to end the program 123
123

 tell me something,and i will reapt it back to you
Enter 'quit' to end the program 11
11

 tell me something,and i will reapt it back to you#输入quit程序自动结束
Enter 'quit' to end the program quit
quit
```

**使用while循环处理列表和字典**

*优点*：**通过while循环同列表和字典结合起来使用，可收集，储存并组织大量输入，供以后查看和显示**

案例模拟：假设一个列表包含新注册还未验证的用户。验证这些用户后，如何让将他们移到另一个已验证的用户列表中。

通过使用while循环来实现

```python
# 首先创建一个待验证的用户列表
# 和一个用于储存已验证用户的空列表
unconfirmed_users = ['lihua','tom','jack','otto']
confirm_users = []
#验证每一个用户，直到没有未验证的用户。
# 将每一个验证的用户移入已验证用户的列表中。
while unconfirmed_users:
    currunt_user = unconfirmed_users.pop()#弹出元素

    print(f"verifying user:{currunt_user.title()}")
    confirm_users.append(currunt_user)#通过append添加元素进入列表
#显示所有已验证的用户
print("\n the users have been confirmed")
for confirm_users in confirm_users:
    print(confirm_users.title())

```

```python
-----》verifying user:Otto
verifying user:Jack
verifying user:Tom
verifying user:Lihua

 the users have been confirmed
Otto
Jack
Tom
Lihua
```

##   七.函数和模块的使用

### 函数的作用

不知道大家是否注意到，在上面的代码中，我们做了3次求阶乘，这样的代码实际上就是重复代码。编程大师*Martin Fowler*先生曾经说过：“**代码有很多种坏味道，重复是最坏的一种！**”，要写出高质量的代码首先要解决的就是重复代码的问题。对于上面的代码来说，我们可以将计算阶乘的功能封装到一个称之为“函数”的功能模块中，在需要计算阶乘的地方，我们只需要“调用”这个“函数”就可以了。

### 定义函数

在Python中可以使用`def`关键字来定义函数，和变量一样每个函数也有一个响亮的名字，而且命名规则跟变量的命名规则是一致的。在函数名后面的圆括号中可以放置传递给函数的参数，这一点和数学上的函数非常相似，程序中函数的参数就相当于是数学上说的函数的自变量，而函数执行完成后我们可以通过`return`关键字来返回一个值，这相当于数学上说的函数的因变量。

```python
"""
输入M和N计算C(M,N)

Version: 0.1
Author: lzh
"""
def fac(num):
    """求阶乘"""
    result = 1
    for n in range(1, num + 1):
        result *= n
    return result


m = int(input('m = '))
n = int(input('n = '))
# 当需要计算阶乘的时候不用再写循环求阶乘而是直接调用已经定义好的函数
print(fac(m) // fac(n) // fac(m - n))
```

**说明：** Python的`math`模块中其实已经有一个名为`factorial`函数实现了阶乘运算，事实上求阶乘并不用自己定义函数。下面的例子中，我们讲的函数在Python标准库已经实现过了，我们这里是为了讲解函数的定义和使用才把它们又实现了一遍，**实际开发中并不建议做这种低级的重复劳动**。



