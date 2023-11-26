------

# **第1课：Python基础语句**

## **一.print**

print()用于打印输出

### 描述

print()方法用于打印输出，是最常见的一个函数。
注意：print 在 Python3.x 是一个函数，但在 Python2.x 版本不是一个函数，只是一个关键字。

### 语法

```text
print(args)
```

### 参数

objects – 复数，表示可以一次输出多个对象。输出多个对象时，需要用 , 分隔。

sep – 用来间隔多个对象，默认值是一个空格。

end – 用来设定以什么结尾。默认值是换行符 \n，我们可以换成其他字符串。

file – 要写入的文件对象。

flush – 输出是否被缓存通常决定于 file，但如果 flush 关键字参数为 True，流会被强制刷新。

### 实例

**1. 字符串、布尔型和数值类型可以直接输出**

```text
>>> print('Python')
Python
>>> print(True)
True
>>> print(False)
False
>>> print(23)
23
>>> print(-7.2)
-7.2
>>> print(1.0e2)
100.0
```

**2. 输出变量值**

2.1 字符串、布尔型、数值变量

对于字符串变量、布尔型变量和数值变量，print函数会直接打印它们的值。

```text
>>> string = 'C++'
>>> integer = 6
>>> float_number = -7.1
>>> omp = True
>>> print(string)
C++
>>> print(integer)
6
>>> print(float_number)
-7.1
>>> print(omp)
True
```

2.2 列表变量

对于列表变量，print函数会直接将列表全部元素打印出来，并用[]包裹全部元素，表示打印的是一个列表。

```text
>>> print(test_list)
['Nova', 'Cinder', 'Neutron', 'Keystone', 23, 45.2]
```

2.3 元组变量

对于元组变量，print函数会直接将元组全部元素打印出来，并用（）包裹全部元素，表示打印的是一个元组。

```text
>>> test_tuple = ('C9', 'FNC', 'IG', 'G2')
>>> print(test_tuple)
('C9', 'FNC', 'IG', 'G2')
```

2.4 字典变量

对于字典变量，print函数会直接将字典全部键值对打印出来，并用{}包裹全部键值对。字典中的每一个键值对中用：隔开键和值。

```text
>>> test_dict = {'MacBook Pro':'computer', 'IPhone X':'mobile phone', 'FusionSphere':'HuaweiCloud OS'} 
>>> print(test_dict)
{'MacBook Pro': 'computer', 'IPhone X': 'mobile phone', 'FusionSphere': 'HuaweiCloud OS'}
```

2.5 集合变量

对于集合变量，print函数会直接将集合全部元素不规则的打印出来（没有顺序），并用{}包裹全部元素。

```text
>>> test_set = {2, 4, 6, 3.2}
>>> print(test_set)
{2, 3.2, 4, 6}
```

### 3. 格式化输出

Python支持参数格式化。

3.1 格式化字符：%c

```text
>>> print('I love %c' %'S')
I love S
```

3.2 格式化字符串：%s

```text
>>> print('I want to learn %s. How about you?' %'Python')
I want to learn Python. How about you?
```

3.3 格式化整数：%d

```text
>>> print('I like number %d' %23)
I like number 23
```

3.4 格式化无符号整型：%u

```text
>>> print('10 - 23 is %d, not %u' %(-13, 13) )
10 - 23 is -13, not 13
```

3.5 格式化无符号八进制数：%o

print函数将无符号十进制数转换为八进制数。

```text
>>> print('return: %o' %56)
return: 70
```

3.6 格式化无符号十六进制数：%x

print函数将无符号十进制数转换为十六进制数。

```text
>>> print('Return: %x %x' %(123, 257))
Return: 7b 101
```

3.7 格式化无符号十六进制数（大写）：%X

```text
>>> print('Return: %X %X' %(123, 257))
Return: 7B 101
```

3.8 格式化浮点数：%f

```text
>>> print('PI= %f' %(3.1415926))
PI= 3.141593
```

还可以指定浮点数的精度。

```text
>>> print('PI= %f, about %.2f' %(3.1415926, 3.1415926))
PI= 3.141593, about 3.14
```

3.9 用科学计数法格式化浮点数：%e

```text
>>> print('%e' %(1.0e3))
1.000000e+03
3.10 格式化浮点数（简写）：%g
>>> print('%g %g' %(1.0e3, 1.23))
1000 1.23
```

### 4. 格式化操作符

4.1 定义宽度或小数点精度：*

```text
>>> amount = 123
>>> print('%*d' %(5,amount))
  123
```

不过，使用下面的方式也可以替代*，定义宽度：

```text
>>> amount = 123
>>> print('%5d' %amount)
  123
```

4.2 左对齐：-

```text
>>> print('%5d' %amount)    #不采用左对齐输出
  123
>>> print('%-5d' %amount)    #左对齐输出
123
```

4.3 在正数前面显示‘+’号：+

```text
>>> print('%-+5d' %amount)
+123 
```

### 5.自动换行

默认情况下，print函数输出后自动换行：

```text
>>> for i in range(3):
...     print(i)
... 
0
1
2
```

如果不想让print函数执行完换行，可以使用end参数：

```text
>>> for i in range(3):
...     print(i, end='')
... 
012>>>
```

### 6. 指定输出分隔符

默认情况下，print输出是有分隔符的：

```text
>>> address = 'Huawei - Building a Fully Connected, Intelligent World'
>>> print("email: xxx.@", address)
email: xxx.@ Huawei - Building a Fully Connected, Intelligent World
```

要想消去分隔符，可以使用sep参数：

```text
>>> print("email: xxx.@", address)
email: xxx.@ Huawei - Building a Fully Connected, Intelligent World
>>> print("email: xxx.@", address, sep='')
email: xxx.@Huawei.com
```

sep参数还可以指定其他字符作为分隔符：

```text
>>> p1 = 'Asian'
>>> p2 = 'China'
>>> p3 = 'Shannxi'
>>> p4 = "Xi'an"
>>> p5 = 'Yanta'
>>> print(p1, p2, p3, p4, p5, sep='>>> ')
Asian>>> China>>> Shannxi>>> Xi'an>>> Yanta
```

### 注意事项

\1. 输出单/双引号字符串

在输出单/双引号字符串时，print函数可以做到与交互式解释器一样，正确的打印。

?使用两种引号的字符串好处：可以创建本身就包含引号的字符串，而不使用转义符。可以在双引号包裹的字符串中使用单引号，或者在单引号包裹的字符串中使用双引号。

```text
>>> print("I'm a boy.")
I'm a boy.
```

\2. 与交互式解释器响应输出的区别

print函数的输出与交互式解释器的自动响应输出存在一些差异。print( )会把包裹字符串的引号截去，仅输出其实际内容，易于阅读。它还会自动地在各个输出部分之间添加空格，并在所有输出的最后添加换行符。

\3. 当字符串数据与其他数据类型拼接输出时，会报错

```text
>>> print('number ' + 1)
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
TypeError: must be str, not int
```

正确的做法是将非字符串转换为字符串输出，或用%格式化输出。

## **二.if函数**

 Python条件语句是通过一条或多条语句的执行结果（True或者False）来决定执行的代码块。



###  1.if条件语句的基本用法： 

```
if 判断条件：
    执行语句……
else：
    执行语句……
```


​        其中"判断条件"成立时（非零），则执行后面的语句，而执行内容可以多行，以缩进来区分表示同一范围。

else 为可选语句，当需要在条件不成立时执行内容则可以执行相关语句。

if实例：

```
age = 18
if age >= 18:
    print('你已成年！')
else:
    print('你未成年！')
```

结果：![image-20231101100429478](C:\Users\ASUS\AppData\Roaming\Typora\typora-user-images\image-20231101100429478.png)

​                                    

### 2.if条件语句的嵌套方式一：

​        if 语句的判断条件可以用>（大于）、<(小于)、==（等于）、>=（大于等于）、<=（小于等于）来表示其关系。

当**判断条件为多个值时**，可以使用以下形式：

```
if 判断条件1:
    执行语句1……
elif 判断条件2:
    执行语句2……
elif 判断条件3:
    执行语句3……
else:
    执行语句4……
```


实例：

```
holiday_name = '植树节'

if holiday_name == '情人节':
    print('买礼物，买花，买包，买化妆品')
elif holiday_name == '愚人节':
    print('吃饭')
else:
    print('不过节')
```


结果：![image-20231101100548022](C:\Users\ASUS\AppData\Roaming\Typora\typora-user-images\image-20231101100548022.png)

​                              

### 3.if条件语句的嵌套方式二：

```
if 条件1:
    条件1满足执行的动作
    if 满足条件1的基础上的条件2:
        ...
    else:
    条件2不满足的情况下
else:
    条件1不满足时，执行的动作
```


实例： 

```
have_ticket = False
knife_length = 21

if have_ticket:
    print('已有车票，请安检...')
    if knife_length > 20:
        print('长度为 %d:超出限定长度，禁止入内' %knife_length)
    else:
        print('长度为 %d:没有超过限定长度，允许入内'%knife_length)
else:
    print('请先买票')
```


输出结果：![image-20231101100713971](C:\Users\ASUS\AppData\Roaming\Typora\typora-user-images\image-20231101100713971.png)



### 4.if条件语句综合练习：

判断闰年：

用户输入年份year, 判断是否为闰年?
能被4整除但不能被100整除的 或者 能被400整除 那么就是闰年（x%y==z 表示x除y余z）

```
year = int(input('输入年份:'))
if year %4 ==0 and year %100 != 0:
    print('%d是闰年' %year)
elif year %400 ==0:
    print('%d是闰年'%year)
else:
    print('%d不是闰年' %year)
```

​                                 

注意：条件语句的错误基本上都是由于**缩进不正确**导致的，在我们学习生产的过程中，一定要注意语句的缩进搭配，否则，看似正确的代码往往会误导我们。
————————————————
版权声明：本文为CSDN博主「云深丶。」的原创文章，遵循CC 4.0 BY-SA版权协议，转载请附上原文出处链接及本声明。
原文链接：https://blog.csdn.net/weixin_41975471/article/details/89134511

## 三.point

point为标记点，用于指示下一步执行的代码

eg:

```
d = input("选择地点1学校 2家")
if(d=="1"):
    point = 1
else:
    point = 2
if(point==1):
    print("学校")
if(point==2):
    print("家")
```

## 四.引号

数字不加引号就是表示整数，加了引号表示字符串；input收集来的信息默认是字符串

eg

```
a = input("输入数字")
if a == 1:
    print("是一")
```

输入1无法打印“是一”

![image-20231101102903342](C:\Users\ASUS\AppData\Roaming\Typora\typora-user-images\image-20231101102903342.png)

如果把数字1加上引号（把1变成字符串）

```
a = input("输入数字")
if a == '1':
    print("是一")
```

输入1打印“是一”

![image-20231101103042209](C:\Users\ASUS\AppData\Roaming\Typora\typora-user-images\image-20231101103042209.png)

## 五.等号

### 1.一个等号（=）

    $a = 1;表示把1赋值给变量啊
    
    echo $a ; //输出 1

### 2.双等号（==）

    $a = null; $b = ''; $c= 1;
    
    双等号表示等于 
    
         echo  ($a==$b)?1:0; //输出1
    
         echo ($a==$c)?1?0;//输出0

### 3.三等于（===）

     $a = null; $b = ''; $c = 0; $d = false;

  三等于表示恒等于

    echo ($a===$b)?1:0;//输出0
    
    echo ($a===$c)?1:0;//输出0
    
    echo ($a===$d)?1:0;//输出0

注意：== 会先进行类型转换，再进行对比，而===会先比较类型，如果类型不同直接返回不相等
————————————————
版权声明：本文为CSDN博主「爱因斯坦小弟」的原创文章，遵循CC 4.0 BY-SA版权协议，转载请附上原文出处链接及本声明。
原文链接：https://blog.csdn.net/toume/article/details/80915866

## 六.while循环

Python 编程中 while 语句用于循环执行程序，即在某条件下，循环执行某段程序，以处理需要重复处理的相同任务。其基本形式为：

```
while 判断条件(condition)：
    执行语句(statements)……
```

执行语句可以是单个语句或语句块。判断条件可以是任何表达式，任何非零、或非空（null）的值均为true。

当判断条件假 false 时，循环结束。

执行流程图如下：

![img](https://www.runoob.com/wp-content/uploads/2013/11/886A6E10-58F1-4A9B-8640-02DBEFF0EF9A.jpg)

### Gif 演示 Python while 语句执行过程

![img](https://www.runoob.com/wp-content/uploads/2014/05/006faQNTgw1f5wnm06h3ug30ci08cake.gif)

复杂一点:

![img](https://www.runoob.com/wp-content/uploads/2013/11/loop-over-python-list-animation.gif)

#### 实例

```
#!/usr/bin/python
 
count = 0
while (count < 9):
   print 'The count is:', count
   count = count + 1
 
print "Good bye!"
```


[运行实例 »](https://www.runoob.com/try/runcode.php?filename=test_while&type=python)

以上代码执行输出结果:

```
The count is: 0
The count is: 1
The count is: 2
The count is: 3
The count is: 4
The count is: 5
The count is: 6
The count is: 7
The count is: 8
Good bye!
```

while 语句时还有另外两个重要的命令 continue，break 来跳过循环，continue 用于跳过该次循环，break 则是用于退出循环，此外"判断条件"还可以是个常值，表示循环必定成立，具体用法如下：

```
# continue 和 break 用法
 
i = 1
while i < 10:   
    i += 1
    if i%2 > 0:     # 非双数时跳过输出
        continue
    print i         # 输出双数2、4、6、8、10
 
i = 1
while 1:            # 循环条件为1必定成立
    print i         # 输出1~10
    i += 1
    if i > 10:     # 当i大于10时跳出循环
        break
```



------

### 无限循环

如果条件判断语句永远为 true，循环将会无限的执行下去，如下实例：

#### 实例

```
#!/usr/bin/python
# -*- coding: UTF-8 -*-
 
var = 1
while var == 1 :  # 该条件永远为true，循环将无限执行下去
   num = raw_input("Enter a number  :")
   print "You entered: ", num
 
print "Good bye!"
```



以上实例输出结果：

```
Enter a number  :20
You entered:  20
Enter a number  :29
You entered:  29
Enter a number  :3
You entered:  3
Enter a number between :Traceback (most recent call last):
  File "test.py", line 5, in <module>
    num = raw_input("Enter a number :")
KeyboardInterrupt
```



**注意：**以上的无限循环你可以使用 CTRL+C 来中断循环。



------

### 循环使用 else 语句

在 python 中，while … else 在循环条件为 false 时执行 else 语句块：

#### 实例

```
#!/usr/bin/python
 
count = 0
while count < 5:
   print count, " is  less than 5"
   count = count + 1
else:
   print count, " is not less than 5"
```

以上实例输出结果为：

```
0 is less than 5
1 is less than 5
2 is less than 5
3 is less than 5
4 is less than 5
5 is not less than 5
```



------

### 简单语句组

类似 if 语句的语法，如果你的 while 循环体中只有一条语句，你可以将该语句与while写在同一行中， 如下所示：

#### 实例

```
#!/usr/bin/python
 
flag = 1
 
while (flag): print 'Given flag is really true!'
 
print "Good bye!"
```

**注意：**以上的无限循环你可以使用 **CTRL+C** 来中断循环。

# **第2课：turtle**

## 一.正确引入turtle画笔 

```
import turtle#单纯引用turtle
import turtle as t#引用turtle,并把turtle简写为t
```

## 二.turtle指令

### 1、设置画布

[turtle](https://so.csdn.net/so/search?q=turtle&spm=1001.2101.3001.7020)为我们展开用于绘图区域，我们可以设置它的大小和初始位置

**turtle.screensize(canvwidth=600,canvheight=800,bg='black')**
\#参数分别代表画布的宽、高、背景色
**turtle.screensize()**#返回默认大小（400,300）

**turtle.setup(width=0.6,height=0.6,startx=100,starty=100)**
\#输入宽和高为整数时, 表示像素; 为小数时, 表示占据电脑屏幕的比例
\#(startx, starty): 这一坐标表示矩形窗口左上角顶点的位置, 如果为空,则窗口位于屏幕中心

### 2、画笔

#### （1）画笔属性

**turtle.pensize(8)**  #画笔粗细

**turtle.color('red')**  #画笔颜色  字符串"green", "red" 或者 RGB 3元组。

**turtle.speed(0）**  #画笔移动速度  画笔绘制的速度范围[0,10]整数，数字越大越快

#### （2）绘图命令

##### ① 画笔运动命令

turtle.forward(8)   #向前移动 **简写为fd**

turtle.[backward](https://so.csdn.net/so/search?q=backward&spm=1001.2101.3001.7020)(8) #向后移动

turtle.right(90) #海龟方向向右转90°

turtle.left(90） #海龟方向向左转90°

turtle.penup()    #提笔  **简写为pu**

turtle.pendown()  #落笔  **简写为pd**

turtle.goto(x,y)   海龟移动到（x,y）位置

turtle.setx(x)     海龟的x坐标移动到指定位置

turtle.sety(y)     海龟的y坐标移动到指定位置

turtle.circle()     画圆  #`具体见3.命令详解`

turtle.dot()      画一个圆点（实心）

turtle.setheading(angle)   #设置当前朝向为angle角度  **简写为seth**

turtle.home()         设置当前画笔位置为原点，朝向东(默认值）

##### ②   画笔控制命令

turtle.fillcolor('red')        设置 填充颜色

turtle.color(color1, color2)  设置 画笔颜色为color1，填充颜色为color2

turtle.begin_fill()          开始填充颜色

turtle.end_fill()           填充完成

turtle.hideturtle()         隐藏海龟图标

turtle.showturtle()        显示海龟图标

##### ③  全局控制命令

turtle.clear()          清空turtle窗口，但是turtle的位置和状态不会改变

turtle.reset()          清空turtle窗口，重置turtle状态为起始状态

turtle.undo()          撤销上一个turtle动作

turtle.isvisible()        返回当前turtle是否可见

t.write("文本" ,align="center",font=("微软雅黑",20,"normal"))      写文本

align(可选）：left,right,center；font(可选)：字体名称，字体大小，字体类型（normal,bold,italic）

##### ④  其他命令

![img](https://img-blog.csdnimg.cn/6e4f444bf6014a2c8f8312b0c46bdd53.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBA5aKo55G2XzE2NQ==,size_20,color_FFFFFF,t_70,g_se,x_16)



### 3. 命令详解

```sql
 turtle.circle(radius, extent=None, steps=None)
```

参数：

​    radius(半径)：半径为正(负)，表示圆心在画笔的左边(右边)画圆；

​    extent(弧度) ；

​    steps ：(做半径为radius的圆的内切正多边形，多边形边数为steps)。

```python
import turtle as t
t.circle(50)#整圆
t.circle(50,steps=3)#内置的三角形
t.penup()
t.goto(100,0)
t.pendown()
t.circle(50,180)#半圆
```

![img](https://img-blog.csdnimg.cn/ea151c3ac9814028bcf3f7047005327a.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBA5aKo55G2XzE2NQ==,size_20,color_FFFFFF,t_70,g_se,x_16)



参考原文链接：https://blog.csdn.net/zengxiantao1994/article/details/76588580

## 三、画五角星

```python
import turtle
turtle.speed(0)
turtle.color("red","red")

turtle.begin_fill()
turtle.forward(200)
turtle.right(180-36)
turtle.forward(200)

turtle.right(180-36)
turtle.forward(200)

turtle.right(180-36)
turtle.forward(200)

turtle.right(180-36)
turtle.forward(200)

turtle.end_fill()
turtle.hideturtle()
```

![image-20231101104830545](C:\Users\ASUS\AppData\Roaming\Typora\typora-user-images\image-20231101104830545.png)

# 第3课:绩点BNI计算器

## 一.float

**float()** 函数用于将整数和字符串转换成浮点数。返回浮点数。(浮点数，是属于[有理数](https://baike.baidu.com/item/有理数/105546?fromModule=lemma_inlink)中某特定[子集](https://baike.baidu.com/item/子集/5017034?fromModule=lemma_inlink)的数的数字表示，在计算机中用以近似表示任意某个[实数](https://baike.baidu.com/item/实数/296419?fromModule=lemma_inlink)。具体的说，这个实数由一个[整数](https://baike.baidu.com/item/整数/1293937?fromModule=lemma_inlink)或[定点数](https://baike.baidu.com/item/定点数/11030127?fromModule=lemma_inlink)（即[尾数](https://baike.baidu.com/item/尾数/6244963?fromModule=lemma_inlink)）乘以某个基数（计算机中通常是2）的整数次幂得到，这种表示方法类似于基数为10的[科学计数法](https://baike.baidu.com/item/科学计数法/756685?fromModule=lemma_inlink)。)

eg:

```
while(1):
   a = float(input("输入字符"))
   print(a)
```

![image-20231101110937952](C:\Users\ASUS\AppData\Roaming\Typora\typora-user-images\image-20231101110937952.png)

如果代码去掉float

```
while(1):
   a = input("输入字符")
   print(a)
```

![image-20231101111129189](C:\Users\ASUS\AppData\Roaming\Typora\typora-user-images\image-20231101111129189.png)

得到字符而不是浮点数

## 二.int

int() 函数用于将一个字符串或数字转换为整型。返回值为整数

### 语法

以下是 int() 方法的语法:

```
class int(x, base=10)
```

### 参数

- x -- 字符串或数字。
- base -- 进制数，默认十进制。

eg

```
>>>int()               # 不传入参数时，得到结果0
0
>>> int(3)
3
>>> int(3.6)
3
>>> int('12',16)        # 如果是带参数base的话，12要以字符串的形式进行输入，12 为 16进制
18
>>> int('0xa',16)  
10  
>>> int('10',8)  
8
```

## 三.一些计算符

### Python算术运算符

以下假设变量： **a=10，b=20**：

| 运算符 | 描述                                            | 实例                                               |
| :----- | :---------------------------------------------- | :------------------------------------------------- |
| +      | 加 - 两个对象相加                               | a + b 输出结果 30                                  |
| -      | 减 - 得到负数或是一个数减去另一个数             | a - b 输出结果 -10                                 |
| *      | 乘 - 两个数相乘或是返回一个被重复若干次的字符串 | a * b 输出结果 200                                 |
| /      | 除 - x除以y                                     | b / a 输出结果 2                                   |
| %      | 取模 - 返回除法的余数                           | b % a 输出结果 0                                   |
| **     | 幂 - 返回x的y次幂                               | a**b 为10的20次方， 输出结果 100000000000000000000 |
| //     | 取整除 - 返回商的整数部分（**向下取整**）       | `>>> 9//2 4 >>> -9//2 -5`                          |

### Python比较运算符

以下假设变量a为10，变量b为20：

| 运算符 | 描述                                                         | 实例                  |
| :----- | :----------------------------------------------------------- | :-------------------- |
| ==     | 等于 - 比较对象是否相等                                      | (a == b) 返回 False。 |
| !=     | 不等于 - 比较两个对象是否不相等                              | (a != b) 返回 True。  |
|        |                                                              |                       |
| >      | 大于 - 返回x是否大于y                                        | (a > b) 返回 False。  |
| <      | 小于 - 返回x是否小于y。所有比较运算符返回1表示真，返回0表示假。这分别与特殊的变量 True 和 False 等价。 | (a < b) 返回 True。   |
| >=     | 大于等于 - 返回x是否大于等于y。                              | (a >= b) 返回 False。 |
| <=     | 小于等于 - 返回x是否小于等于y。                              | (a <= b) 返回 True。  |



# 第4课:定义函数

当某个程序相同或相似部分很多时，可以将相同或相似部分定义为一个函数，从而达到简化代码的目的

比如这是一个画五星红旗的代码

```
import turtle
turtle.speed(6)
turtle.pensize(5)

turtle.penup()#旗面
turtle.goto(-300,-200)
turtle.pendown()
turtle.color("white","red")
turtle.begin_fill()
turtle.forward(600)
turtle.left(90)
turtle.forward(400)
turtle.left(90)
turtle.forward(600)
turtle.left(90)
turtle.forward(400)
turtle.end_fill()

turtle.penup()#大红星
turtle.goto(-260,120)
turtle.pendown()
turtle.color("gold","gold")
turtle.speed(0)
turtle.begin_fill()
turtle.left(90)

turtle.forward(120)
turtle.right(180-36)
turtle.forward(120)

turtle.right(180-36)
turtle.forward(120)

turtle.right(180-36)
turtle.forward(120)

turtle.right(180-36)
turtle.forward(120)

turtle.end_fill()

turtle.penup()#右上角红星1
turtle.goto(-115,150)
turtle.pendown()
turtle.color("gold","gold")
turtle.speed(0)
turtle.begin_fill()
turtle.right(85)

turtle.forward(30)
turtle.right(180-36)
turtle.forward(30)

turtle.right(180-36)
turtle.forward(30)

turtle.right(180-36)
turtle.forward(30)

turtle.right(180-36)
turtle.forward(30)

turtle.end_fill()

turtle.penup()#右上角红星2
turtle.goto(-55,115)
turtle.pendown()
turtle.color("gold","gold")
turtle.speed(0)
turtle.begin_fill()
turtle.right(85)

turtle.forward(30)
turtle.right(180-36)
turtle.forward(30)

turtle.right(180-36)
turtle.forward(30)

turtle.right(180-36)
turtle.forward(30)

turtle.right(180-36)
turtle.forward(30)

turtle.end_fill()

turtle.penup()#右上角红星3
turtle.goto(-65,64)
turtle.pendown()
turtle.color("gold","gold")
turtle.speed(0)
turtle.begin_fill()
turtle.left(100)

turtle.forward(30)
turtle.right(180-36)
turtle.forward(30)

turtle.right(180-36)
turtle.forward(30)

turtle.right(180-36)
turtle.forward(30)

turtle.right(180-36)
turtle.forward(30)

turtle.end_fill()

turtle.penup()#右上角红星4
turtle.goto(-100,7)
turtle.pendown()
turtle.color("gold","gold")
turtle.speed(0)
turtle.begin_fill()
turtle.right(30)

turtle.forward(30)
turtle.right(180-36)
turtle.forward(30)

turtle.right(180-36)
turtle.forward(30)

turtle.right(180-36)
turtle.forward(30)

turtle.right(180-36)
turtle.forward(30)

turtle.end_fill()
turtle.hideturtle()
```

里面画红星部分都是相同的，可以定义为一个函数star

```
def star(x):
    turtle.color("gold","gold")
    turtle.speed(0)
    turtle.begin_fill()
    turtle.forward(x)
    turtle.right(180-36)
    turtle.forward(x)
    turtle.right(180-36)
    turtle.forward(x)
    turtle.right(180-36)
    turtle.forward(x)
    turtle.right(180-36)
    turtle.forward(x)
    turtle.end_fill()

```

程序可以简化为

```
import turtle

turtle.speed(6)#笔
turtle.pensize(5)
def star(x):
    turtle.color("gold","gold")
    turtle.speed(0)
    turtle.begin_fill()
    turtle.forward(x)
    turtle.right(180-36)
    turtle.forward(x)
    turtle.right(180-36)
    turtle.forward(x)
    turtle.right(180-36)
    turtle.forward(x)
    turtle.right(180-36)
    turtle.forward(x)
    turtle.end_fill()
def flag():
     turtle.color("white","red")#旗面
     turtle.begin_fill()
     turtle.forward(600)
     turtle.left(90)
     turtle.forward(400)
     turtle.left(90)
     turtle.forward(600)
     turtle.left(90)
     turtle.forward(400)
     turtle.end_fill()
move(-300,-200)#旗面
flag()
move(-260,120)#大红星
turtle.left(90)
big_star(120)
move(-115,150)#右上角红星1
turtle.right(85)
star(30)
move(-55,115)#右上角红星2
turtle.right(85)
star(30)
move(-65,64)#右上角红星3
turtle.left(100)
star(30)
move(-100,7)#右上角红星4
turtle.right(30)
star(30)

```

# 第5课.for循环

Python for循环可以**遍历**任何序列的项目，如一个列表或者一个字符串。

## 1**语法：**

for循环的语法格式如下：

```
for x in y:#用x遍历y中元素

```

### 实例

```
for i in '123456':
  print(i,end=' ')
```

### 结果

```

1 2 3 4 5 6 
进程已结束，退出代码为 0

```



------

### 通过序列索引

```


```

另一种执行循环的遍历方式是通过索引，如下实例：

### 实例

```
fruits = ['banana', 'apple',  'mango']
for index in range(len(fruits)):
   print ('当前水果 : %s' % fruits[index])
 
print ("Good bye!")
```

以上实例输出结果：

```
当前水果 : banana
当前水果 : apple
当前水果 : mango
Good bye!
```

以上实例我们使用了内置函数 len() 和 range(),函数 len() 返回列表的长度，即元素的个数。 range返回一个序列的数。



------

### 循环使用 else 语句

在 python 中，for … else 表示这样的意思，for 中的语句和普通的没有区别，else 中的语句会在循环正常执行完（即 for 不是通过 break 跳出而中断的）的情况下执行，while … else 也是一样。

### 实例

```
for num in range(10,20):  # 迭代 10 到 20 之间的数字
   for i in range(2,num): # 根据因子迭代
      if num%i == 0:      # 确定第一个因子
         break            # 跳出当前循环
   else:                  # 循环的 else 部分
      print ('%d 是一个质数' % num) 
```

以上实例输出结果：

```
11 是一个质数
13 是一个质数
17 是一个质数
19 是一个质数

进程已结束，退出代码为 0
```

## 2.用for 循环写九九乘法表

代码

```
for i in range(1,10):
 for j in range(1,i+1):
     print("%dx%d=%d"%(i,j,i*j),end='\t')
 print()
```

结果

```
1x1=1	
2x1=2	2x2=4	
3x1=3	3x2=6	3x3=9	
4x1=4	4x2=8	4x3=12	4x4=16	
5x1=5	5x2=10	5x3=15	5x4=20	5x5=25	
6x1=6	6x2=12	6x3=18	6x4=24	6x5=30	6x6=36	
7x1=7	7x2=14	7x3=21	7x4=28	7x5=35	7x6=42	7x7=49	
8x1=8	8x2=16	8x3=24	8x4=32	8x5=40	8x6=48	8x7=56 8x8=64	
9x1=9	9x2=18	9x3=27	9x4=36	9x5=45	9x6=54	9x7=63	9x8=72	9x9=81	
```

### %d的含义

%d，表示按整型输出后面给出的变量的值。

eg

```
print("%d"%3.2)
print("%d"%4)
```

结果

```
3
4

进程已结束，退出代码为 0

```

# 第6课:数据驱动

## Python 列表(List)

序列是Python中最基本的数据结构。序列中的每个元素都分配一个数字 - 它的位置，或索引，第一个索引是0，第二个索引是1，依此类推。

Python有6个序列的内置类型，但最常见的是列表和元组。

序列都可以进行的操作包括索引，切片，加，乘，检查成员。

此外，Python已经内置确定序列的长度以及确定最大和最小的元素的方法。

列表是最常用的Python数据类型，它可以作为一个方括号内的逗号分隔值出现。

列表的数据项不需要具有相同的类型

创建一个列表，只要把逗号分隔的不同的数据项使用方括号括起来即可。如下所示：

```
list1 = ['physics', 'chemistry', 1997, 2000]
list2 = [1, 2, 3, 4, 5 ] 
list3 = ["a", "b", "c", "d"]
```

与字符串的索引一样，列表索引从0开始。列表可以进行截取、组合等。

------

### 1.访问列表中的值

使用下标索引来访问列表中的值，同样你也可以使用方括号的形式截取字符，如下所示：

实例

```
list1 = ['physics', 'chemistry', 1997, 2000]
list2 = [1, 2, 3, 4, 5, 6, 7 ]
 
print "list1[0]: ", list1[0]
print "list2[1:5]: ", list2[1:5]
```

以上实例输出结果：

```
list1[0]:  physics
list2[1:5]:  [2, 3, 4, 5]
```

------

### 2.更新列表

你可以对列表的数据项进行修改或更新，你也可以使用append()方法来添加列表项，如下所示：

实例

```
list = []          ## 空列表
list.append('Google')   ## 使用 append() 添加元素
list.append('Runoob')
print list
```

**注意：**我们会在接下来的章节讨论append()方法的使用

以上实例输出结果：

```
['Google', 'Runoob']
```

------

### 3.删除列表元素

可以使用 del 语句来删除列表的元素，如下实例：

```
list1 = ['physics', 'chemistry', 1997, 2000]
 
print list1
del list1[2]
print "After deleting value at index 2 : "
print list1
```

输出结果：

```
['physics', 'chemistry', 1997, 2000]
After deleting value at index 2 :
['physics', 'chemistry', 2000]
```

------

### 4.Python列表脚本操作符

列表对 + 和 * 的操作符与字符串相似。+ 号用于组合列表，* 号用于重复列表。

如下所示：

| Python 表达式                | 结果                         | 描述                 |
| :--------------------------- | :--------------------------- | :------------------- |
| len([1, 2, 3])               | 3                            | 长度                 |
| [1, 2, 3] + [4, 5, 6]        | [1, 2, 3, 4, 5, 6]           | 组合                 |
| ['Hi!'] * 4                  | ['Hi!', 'Hi!', 'Hi!', 'Hi!'] | 重复                 |
| 3 in [1, 2, 3]               | True                         | 元素是否存在于列表中 |
| for x in [1, 2, 3]: print x, | 1 2 3                        | 迭代                 |

------

### 5.Python列表截取

Python 的列表截取实例如下：

```
>>>L = ['Google', 'Runoob', 'Taobao'] 
>>> L[2] 'Taobao' 
>>> L[-2] 'Runoob' 
>>> L[1:] ['Runoob', 'Taobao'] 
```

描述：

| Python 表达式 | 结果                 | 描述                     |
| :------------ | :------------------- | :----------------------- |
| L[2]          | 'Taobao'             | 读取列表中第三个元素     |
| L[-2]         | 'Runoob'             | 读取列表中倒数第二个元素 |
| L[1:]         | ['Runoob', 'Taobao'] | 从第二个元素开始截取列表 |

------

### 6.Python列表函数&方法

Python包含以下函数:

| 序号 | 函数                                                         |
| :--- | :----------------------------------------------------------- |
| 1    | [cmp(list1, list2)](https://www.runoob.com/python/att-list-cmp.html) 比较两个列表的元素 |
| 2    | [len(list)](https://www.runoob.com/python/att-list-len.html) 列表元素个数 |
| 3    | [max(list)](https://www.runoob.com/python/att-list-max.html) 返回列表元素最大值 |
| 4    | [min(list)](https://www.runoob.com/python/att-list-min.html) 返回列表元素最小值 |
| 5    | [list(seq)](https://www.runoob.com/python/att-list-list.html) 将元组转换为列表 |

Python包含以下方法:

| 序号 | 方法                                                         |
| :--- | :----------------------------------------------------------- |
| 1    | [list.append(obj)](https://www.runoob.com/python/att-list-append.html) 在列表末尾添加新的对象 |
| 2    | [list.count(obj)](https://www.runoob.com/python/att-list-count.html) 统计某个元素在列表中出现的次数 |
| 3    | [list.extend(seq)](https://www.runoob.com/python/att-list-extend.html) 在列表末尾一次性追加另一个序列中的多个值（用新列表扩展原来的列表） |
| 4    | [list.index(obj)](https://www.runoob.com/python/att-list-index.html) 从列表中找出某个值第一个匹配项的索引位置 |
| 5    | [list.insert(index, obj)](https://www.runoob.com/python/att-list-insert.html) 将对象插入列表 |
| 6    | [list.pop([index=-1\])](https://www.runoob.com/python/att-list-pop.html) 移除列表中的一个元素（默认最后一个元素），并且返回该元素的值 |
| 7    | [list.remove(obj)](https://www.runoob.com/python/att-list-remove.html) 移除列表中某个值的第一个匹配项 |
| 8    | [list.reverse()](https://www.runoob.com/python/att-list-reverse.html) 反向列表中元素 |
| 9    | [list.sort(cmp=None, key=None, reverse=False)](https://www.runoob.com/python/att-list-sort.html) 对原列表进行排序 |

# 第7课.利用for循环排序

代码

```
list=[12,40,10,9,8,-1,21,-6]
n=0
#---------原始------------------
for j in range(len(list)-1):
  for i in range(len(list)-(j+1)):
    if(list[j]<list[i+(j+1)]):
       list[j],list[i+(j+1)]=list[i+(j+1)],list[j]
       n+=1
print(list)
print("普通型选择排序交换次数为",n)
#---------改进------------------
list=[12,40,10,9,8,-1,21,-6]
n=0
for j in range(len(list)-1):
    f=j
    for i in range(len(list)-(j+1)):
       if(list[f]<list[i+(j+1)]):
          f=i+(j+1)
    list[j],list[f]=list[f],list[j]
    n+=1
print(list)
print("改进型选择排序交换次数为",n)
#---------最优------------------
list=[12,40,10,9,8,-1,21,-6]
n=0
for j in range(len(list)-1):
    f=j
    for i in range(len(list)-(j+1)):
       if(list[f]<list[i+(j+1)]):
          f=i+(j+1)
    if(f!=j):
        list[j],list[f]=list[f],list[j]
        n+=1
print(list)
print("优化型选择排序交换次数为",n)
```

两个列表内元素交换位置

```
a = [1,2]
print(a)
a[0], a[1] = a[1], a[0]
print(a)
```

结果

```
[1, 2]
[2, 1]

进程已结束，退出代码为 0
```

冒泡排序

```
list=[12,40,10,9,8,-1,21,-6]
n=0
for i in range(len(list)-1):
    for j in range(len(list)-i-1):
        if(list[j]<list[j+1]):
            list[j],list[j+1]=list[j+1],list[j]
            n+=1
print(list)
print(f"排序次数为{n}")
```

把列表中前一个元素与后面所有元素作比较，小于后面就和它换位置

结果

```
[40, 21, 12, 10, 9, 8, -1, -6]
排序次数为6

进程已结束，退出代码为 0
```

# 第8课.发牌（随机数）

在 Python 中，可以使用内置的 random 模块来生成随机数。#类似于turtle

```
import random
```

## 1.radom.random()

**random.random()** 返回一个介于 0.0 和 1.0 之间的随机小数：

实例

```
import random

random_number = random.random()
print(random_number)
```

结果

```
0.7597072251250637
```

## 2.random.randint(a, b)

random.randint(a, b) 用于返回一个介于 a 和 b 之间的整数（包括 a 和 b）。

```
random.randint(a,b)
```

函数返回数字 N ，N 为 a 到 b 之间的数字（a <= N <= b），包含 a 和 b。

实例

```
import random
 
print(random.randint(0,9))
```

结果

```
4
```

## 3random.choice(sequence)

**random.choice(sequence)** 用于从序列中随机选择一个元素：

实例

```
import random

list1 = [1, 2, 3, 4, 5]
random_element = random.choice(list1)
print(random_element)
```

结果

```
4
```

## 4.**random.shuffle(sequence)**

**random.shuffle(sequence)** 用于将序列中的元素进行随机排序：

实例

```
import random

list1 = [1, 2, 3, 4, 5]
random.shuffle(list1)
print(list1)
```

结果

```
[3, 2, 4, 5, 1]
```

# 第9课.数学公式的一些应用

Python **math** 模块提供了许多对浮点数的数学运算函数。

**math** 模块下的函数，返回值均为浮点数，除非另有明确说明。

如果需要计算复数请使用 **cmath** 模块中的同名函数。

要使用 math 函数必须先导入：

```
import math
```

猴子吃桃问题

一只猴子第一天摘下若干个桃子，当即吃了一半，还不过瘾，又多吃了一个；第二天早上又将剩下的桃子吃掉一半，又多吃了一个。以后每天早上都吃了前一天剩下的一半加一个。到第*N*天早上想再吃时，见只剩下一个桃子了。问：第一天共摘了多少个桃子？

代码实现

```
import math
a=1
for i in range(9):
   a=2*a+2
print(a)

```

理解：设猴子昨天剩下x个桃子，今天剩下y个桃子，有 y=x-(x/2+1)  化简得x=2y+2

# 第10课.凯撒法加密解密

## 1.拆分字符串

代码实现（遍历字符串每一个字符）

```
stt = input("请输入字符")
for i in stt:
    print(i)

```

结果

```
请输入字符i love you
i
 
l
o
v
e
 
y
o
u
```

## 2.获取各字符的ASCII序号

代码实现

```
a = input("请输入符号：")
b = ord(a)
print(b)
```

结果

```
请输入符号：q
113

进程已结束，退出代码为 0
```

## 3.ASCII序号转字符

代码实现

```
a = input("请输入序号")
a = int(a)
b = chr(a)
print(b)
```

结果

```
请输入序号113
q

进程已结束，退出代码为 0
```

加密解密器

```
a = input("请选择你要使用的功能1解密器 2加密器：")
while a == "1":
    stt = input("\n\n请输入要解密的字符")
    for i in stt:
        a = ord(i)  # 获得ASCII序号
        b = int(a)
        if 65 <= b <= 90:
            i = b - 3  # 加密前+后移3位
            if i <= 64:
                i = 90 - (64 - i)
        if 48 <= b <= 57:
            i = b - 3  # 加密前+后移3位
            if i <= 47:
                i = 57 - (47 - i)
        if 97 <= b <= 122:
            i = b - 3  # 加密前+后移3位
            if i <= 96:
                i = 122 + (96 - i)
        a = int(i)
        b = chr(a)
        print(b, end='')
    c = input("\n\n请问是否继续1继续 2结束")
    if c == "1":
        a = input("\n\n请选择你要使用的功能1解密器 2加密器：")
    if c == "2":
        print("谢谢使用")

while a == "2":
    stt = input("\n\n请输入要加密的字符")
    for i in stt:
        a = ord(i)  # 获得ASCII序号
        b = int(a)
        if 65 <= b <= 90:
            i = b + 3  # 加密前+后移3位
            if i >= 91:
                i = 65 + (i - 91)
        if 48 <= b <= 57:
            i = b + 3  # 加密前+后移3位
            if i >= 58:
                i = 48 + (i - 58)
        if 97 <= b <= 122:
            i = b + 3  # 加密前+后移3位
            if i >= 123:
                i = 97 + (i - 123)
        a = int(i)
        b = chr(a)
        print(b, end='')
    c = input("\n\n请问是否继续1继续 2结束")
    if c == "1":
        a = input("\n\n请选择你要使用的功能1解密器 2加密器：")
    if c == "2":
        print("谢谢使用")
```

# 第11课.返回值（ruturn)

## 1.return

return可以将所得值返回给定义的函数

```
def a():
    b = 1
    c = 2
    return b+c

print(a())
```

结果

```
3

进程已结束，退出代码为 0
```

## 2.实例。求斐波拉契第n项

```
def Fibonacci(n):
    if n == 1:
        return 1
    elif n == 2:
        return 1
    else:
        return Fibonacci(n - 1) + Fibonacci(n - 2)

n = int(input("求第几项？"))
print(Fibonacci(n))

```

结果

```
求第几项？34
5702887

进程已结束，退出代码为 0
```

# 第12课.求π的近似值

## .取小数点后第n位

```
“{:.nf}”..format(a)
```

表示取a小数点后n位

实例

```
a=float('3.141592653')
print("{:.2f}".format(a))
print("{:.4f}".format(a))
print("{:.6f}".format(a))
```

结果

```
3.14
3.1416
3.141593

进程已结束，退出代码为 0
```

# 第13课.屏幕点击&global&time

## 1.屏幕点击函数

```
import turtle
k = 0
def p(x,y):
    global k#此处K为外部K
    k=1

turtle.onscreenclick(p)#与P函数配套使用
```

解释：当点击屏幕时，运行函数p将外部k赋值为1，可以作为启动下面函数的条件

## 2.global

```
def a():
     t = 8
t=1
a()
print(t)


def a():
    global t#声明全局变量
    t = 8
t = 1
a()
print(t)
```

结果

```
1
8

进程已结束，退出代码为 0
```

# 第14课.str

我们经常需要再消息中使用变量的值。例如，假设我们要祝人生日快乐，可能会编写类似下面的代码：

```
age=20
message="Happy " + age + "th Btrthday!"
print(message)
```

但是如果运行这些代码，会引发错误

```
Traceback (most recent call last):
  File "D:\Python作业\1课\if.py", line 2, in <module>
    message="Happy " + age + "th Btrthday!"
TypeError: can only concatenate str (not "int") to str

进程已结束，退出代码为 1

```

在Python看来，age这个变量表示的可能是数值20，也可能是字符2和0。因为 “+” 运算符两边的数据需要类型一致，因此像上面这样在字符串中使用整数时，需要**显式地将这个整数用作字符串**，让其与两侧的字符串数据类型保持一致。即调用 str() 函数：

```
age=20
message="Happy " + str(age) + "th Birthday!"
print(message)
```

输出结果：

```
Happy 20th Birthday!

进程已结束，退出代码为 0
```

————————————————
版权声明：本文为CSDN博主「SEVLT」的原创文章，遵循CC 4.0 BY-SA版权协议，转载请附上原文出处链接及本声明。
原文链接：https://blog.csdn.net/sunqi568/article/details/81200353

# 第15课.迷宫小游戏

游戏需要键盘控制，则需要一个能识别键盘操作的函数，叫做键盘监听函数

```
def move_up():
 ball.sety(ball.ycor()+5) #设置球的y坐标
def move_down():
 ball.sety(ball.ycor()-5)

game.listen() #开启球的键盘监听功能
game.onkeypress(move_up, 'Up')#长按一直启动move_up()
game.onkey(move_down, 'Down') #按下向上键并松开，立即启动move_down()函数
```

# 第16课.扫码录入系统（字典）

字典是另一种可变容器模型，且可存储任意类型对象。

字典的每个键值 **key=>value** 对用冒号 **:** 分割，每个对之间用逗号(**,**)分割，整个字典包括在花括号 **{}** 中 ,格式如下所示：

```
d = {key1 : value1, key2 : value2, key3 : value3 }
```

**注意：****dict** 作为 Python 的关键字和内置函数，变量名不建议命名为 **dict**。

![img](https://www.runoob.com/wp-content/uploads/2016/04/py-dict-3.png)

键必须是唯一的，但值则不必。

值可以取任何数据类型，但键必须是不可变的，如字符串，数字。

一个简单的字典实例：

```
tinydict = {'name': 'runoob', 'likes': 123, 'url': 'www.runoob.com'}
```

![img](https://www.runoob.com/wp-content/uploads/2016/04/py-dict-2.png)

也可如此创建字典：

```
tinydict1 = { 'abc': 456 }
tinydict2 = { 'abc': 123, 98.6: 37 }
```

------

## 1.创建空字典

使用大括号 **{ }** 创建空字典：

实例

```
# 使用大括号 {} 来创建空字典
emptyDict = {}

#打印字典
print(emptyDict)

# 查看字典的数量
**print**("Length:", len(emptyDict))
 
# 查看类型
**print**(type(emptyDict))
```

以上实例输出结果：

```
{}
Length: 0
<class 'dict'>
```

使用内建函数 **dict()** 创建字典：

```
实例

emptyDict = dict()
 
\# 打印字典
*print(emptyDict)
 
\# 查看字典的数量
print("Length:",len(emptyDict))
 
\# 查看类型
print(type(emptyDict))
```

以上实例输出结果：

```
{}
Length: 0
<class 'dict'>
```

------

## 2.访问字典里的值

把相应的键放入到方括号中，如下实例:

实例

```
a = {'123':['长江','黄河'],'234':'计算机'}
num = input('输入号码')
v = a[num]##键所对应的值部分
print(v)#一个键对应多个元素，对应元素用列表表示
```

以上实例输出结果：

```
输入号码123
['长江', '黄河']

进程已结束，退出代码为 0
```



------

## 3.修改字典

向字典添加新内容的方法是增加新的键/值对，修改或删除已有键/值对如下实例:

实例

```
#!/usr/bin/python3
 
tinydict = {'Name': 'Runoob', 'Age': 7, 'Class': 'First'}
 
tinydict['Age'] = 8               # 更新 Age
tinydict['School'] = "菜鸟教程"  # 添加信息
 
 
print ("tinydict['Age']: ", tinydict['Age'])
print ("tinydict['School']: ", tinydict['School'])
```

以上实例输出结果：

```
tinydict['Age']:  8
tinydict['School']:  菜鸟教程
```



------

删除字典元素

能删单一的元素也能清空字典，清空只需一项操作。

显式删除一个字典用del命令，如下实例：

实例

```
#!/usr/bin/python3
 
tinydict = {'Name': 'Runoob', 'Age': 7, 'Class': 'First'}
 
del tinydict['Name'] # 删除键 'Name'
tinydict.clear()     # 清空字典
del tinydict         # 删除字典
 
print ("tinydict['Age']: ", tinydict['Age'])
print ("tinydict['School']: ", tinydict['School'])
```

但这会引发一个异常，因为用执行 del 操作后字典不再存在：

```
Traceback (most recent call last):
  File "/runoob-test/test.py", line 9, in <module>
    print ("tinydict['Age']: ", tinydict['Age'])
NameError: name 'tinydict' is not defined
```

**注：**del() 方法后面也会讨论。



## 4.字典键的特性

字典值可以是任何的 python 对象，既可以是标准的对象，也可以是用户定义的，但键不行。

两个重要的点需要记住：

1）不允许同一个键出现两次。创建时如果同一个键被赋值两次，后一个值会被记住，如下实例：

实例

```
#!/usr/bin/python3
 
tinydict = {'Name': 'Runoob', 'Age': 7, 'Name': '小菜鸟'}
 
print ("tinydict['Name']: ", tinydict['Name'])
```

以上实例输出结果：

```
tinydict['Name']:  小菜鸟
```

2）键必须不可变，所以可以用数字，字符串或元组充当，而用列表就不行，如下实例：

实例

```
#!/usr/bin/python3
 
tinydict = {['Name']: 'Runoob', 'Age': 7}
 
print ("tinydict['Name']: ", tinydict['Name'])
```

以上实例输出结果：

```
Traceback (most recent call last):
  File "test.py", line 3, in <module>
    tinydict = {['Name']: 'Runoob', 'Age': 7}
TypeError: unhashable type: 'list'
```



------

## 5.字典内置函数&方法

Python字典包含了以下内置函数：

| 序号 | 函数及描述                                                   | 实例                                                         |
| :--- | :----------------------------------------------------------- | :----------------------------------------------------------- |
| 1    | len(dict) 计算字典元素个数，即键的总数。                     | `>>> tinydict = {'Name': 'Runoob', 'Age': 7, 'Class': 'First'} >>> len(tinydict) 3` |
| 2    | str(dict) 输出字典，可以打印的字符串表示。                   | `>>> tinydict = {'Name': 'Runoob', 'Age': 7, 'Class': 'First'} >>> str(tinydict) "{'Name': 'Runoob', 'Class': 'First', 'Age': 7}"` |
| 3    | type(variable) 返回输入的变量类型，如果变量是字典就返回字典类型。 | `>>> tinydict = {'Name': 'Runoob', 'Age': 7, 'Class': 'First'} >>> type(tinydict) <class 'dict'>` |

Python字典包含了以下内置方法：

| 序号 | 函数及描述                                                   |
| :--- | :----------------------------------------------------------- |
| 1    | [dict.clear()](https://www.runoob.com/python3/python3-att-dictionary-clear.html) 删除字典内所有元素 |
| 2    | [dict.copy()](https://www.runoob.com/python3/python3-att-dictionary-copy.html) 返回一个字典的浅复制 |
| 3    | [dict.fromkeys()](https://www.runoob.com/python3/python3-att-dictionary-fromkeys.html) 创建一个新字典，以序列seq中元素做字典的键，val为字典所有键对应的初始值 |
| 4    | [dict.get(key, default=None)](https://www.runoob.com/python3/python3-att-dictionary-get.html) 返回指定键的值，如果键不在字典中返回 default 设置的默认值 |
| 5    | [key in dict](https://www.runoob.com/python3/python3-att-dictionary-in.html) 如果键在字典dict里返回true，否则返回false |
| 6    | [dict.items()](https://www.runoob.com/python3/python3-att-dictionary-items.html) 以列表返回一个视图对象 |
| 7    | [dict.keys()](https://www.runoob.com/python3/python3-att-dictionary-keys.html) 返回一个视图对象 |
| 8    | [dict.setdefault(key, default=None)](https://www.runoob.com/python3/python3-att-dictionary-setdefault.html) 和get()类似, 但如果键不存在于字典中，将会添加键并将值设为default |
| 9    | [dict.update(dict2)](https://www.runoob.com/python3/python3-att-dictionary-update.html) 把字典dict2的键/值对更新到dict里 |
| 10   | [dict.values()](https://www.runoob.com/python3/python3-att-dictionary-values.html) 返回一个视图对象 |
| 11   | [pop(key[,default\])](https://www.runoob.com/python3/python3-att-dictionary-pop.html) 删除字典 key（键）所对应的值，返回被删除的值。 |
| 12   | [popitem()](https://www.runoob.com/python3/python3-att-dictionary-popitem.html) 返回并删除字典中的最后一对键和值。 |

# 第17课.小超市录入查询系统（txt&xlsx）

## 1.读取txt

**read() --------** 一次性读取所有文本

```text
with open("1.txt", "r", encoding='utf-8') as f:  #打开文本
    data = f.read()   #读取文本
    print(data)
```

![img](https://pic2.zhimg.com/80/v2-473a2425d54891c9f40d57b9b4f03cdd_720w.webp)

Ps：在读取文本中含有中文时是gkd，在打开需要定义编码为utf-8。

**readline() -------** 读取第一行的内容

```text
with open('1.txt', 'r', encoding='utf-8') as f:
    data = f.readline()
    print(data)
```

![img](https://pic1.zhimg.com/80/v2-e1c91e96f2a64af8649ee716d9c04ad0_720w.webp)

**readlines() --------** 读取全部内容，以数列的格式返回结果

```text
with open('1.txt', 'r', encoding='utf-8') as f:
    data = f.readlines()
    print(data)
```

![img](https://pic2.zhimg.com/80/v2-43dcdbffdc37e54aca19ae18c31f7a31_720w.webp)

可以配合 for 使用

```text
with open('1.txt', 'r', encoding='utf-8') as f:
    for ann in f.readlines():
        ann = ann.strip('\n')       #去除文本中的换行符
        print(ann)
```

## 2.写入txt

使用 write() 方法：使用 open() 函数打开文件，然后使用 write() 方法将内容写入文件。例如：

```
with open('example.txt', 'w') as f:

    f.write('Hello, world!')
```

open('fire','mode',encoding='') 函数是 Python 内置的用于打开文件的函数，其常用的参数及其含义如下：

1.file: 文件名或文件路径。可以是绝对路径或相对路径。如果是相对路径，则相对于当前工作目录。如果省略了路径，就在当前工作目录中打开文件。

2.mode: 文件打开模式。可以是以下值之一：

'r': 只读模式。默认模式，如果文件不存在，会引发异常

'w': 写模式。如果文件不存在，则创建文件。如果文件已存在，则清空文件并写入新内容。
'x': 独占创建模式。如果文件不存在，则创建文件。如果文件已存在，则引发异常。
'a': 追加模式。如果文件不存在，则创建文件。如果文件已存在，则将新内容添加到文件末尾。
'b': 二进制模式。与其他模式一起使用，例如 'rb' 或 'wb'。
't': 文本模式。与其他模式一起使用，例如 'rt' 或 'wt'
3.buffering: 设置缓冲区的大小。如果省略或为0，则不进行缓冲。如果为1，则行缓冲。如果大于1，则为缓冲区大小。

4.encoding: 用于编码和解码文件内容的编码格式。如果省略，使用默认编码。

## 3.读取xlsx

1.import [openpyxl](https://so.csdn.net/so/search?q=openpyxl&spm=1001.2101.3001.7020) 导入openpyxl模块(没有安装openpyxl模块：win+R 输入cmd 回车，输入pip install openpyxl)

2.获取的文件（×××.xlsx）

```
w = openpyxl.load_workbook('xxx.xlsx') #获取表格文件


```

3.获取所需sheet

(1)

```
import openpyxl #导入模块openpyxl

myExcel = openpyxl.load_workbook('省会表.xlsx') #获取表格文件
sheets = myExcel.sheetnames
print(sheets,type(sheets))
print(sheets[0])
'''
结果：
['Sheet1', 'Sheet2', 'Sheet3'] <class 'list'>
Sheet1
'''

```

(2)

```
import openpyxl #导入模块openpyxl

myExcel = openpyxl.load_workbook('省会表.xlsx') #获取表格文件
#获取指定的表单
mySheet = myExcel.get_sheet_by_name('Sheet1')
print(mySheet.title) #Sheet1

```

(3)

```
import openpyxl #导入模块openpyxl

myExcel = openpyxl.load_workbook('省会表.xlsx') #获取表格文件
mysheet2 = myExcel.active
print(mysheet2.title)  #Sheet1 最好测试一下  不同文件会不同
```

访问excle特定单元格内的数据

```

```

```
from openpyxl import *
b={}
suiy=['A','b','c']
data=load_workbook('商品.xlsx')
sheet=data.active#打开第一个工作表
b2=str(sheet.max_row+1)#获取当前excle表中最后一行数据的行数并加1，来达到继续添加的目的
print(b2)
#--------读取---------
a = sheet.cell(3,3)#sheet.cell(x,y)：x行y列
a = sheet.cell(3,2)
print(a.value)
```

## 4.写入xlsx

```
from openpyxl import *
b={}
suiy=['A','b','c']
data=load_workbook('商品.xlsx')
sheet=data.active#打开第一个工作表
b2=str(sheet.max_row+1)#获取当前excle表中最后一行数据的行数并加1，来达到继续添加的目的
print(b2)
#-----写入-----
sheet[suiy[0]+b2]=input('输入编码')#向sheet工作表中添加数据
sheet[suiy[1]+b2]=input('输入编码')
sheet[suiy[2]+b2]=input('输入编码')
data=data.save('商品.xlsx')#保存
```

# 第18课.综合应用（xlsx&txt）

## 1.index

描述

index() 函数用于从列表中找出某个值第一个匹配项的索引位置。

语法

index()方法语法：

```
list.index(x[, start[, end]])
```

参数

- x-- 查找的对象。
- start-- 可选，查找的起始位置。
- end-- 可选，查找的结束位置。

返回值

该方法返回查找对象的索引位置，如果没有找到对象则抛出异常。

实例

以下实例展示了 index()函数的使用方法：

```
#!/usr/bin/python
# -*- coding: UTF-8 -*-

aList = [123, 'xyz', 'runoob', 'abc']

print "xyz 索引位置: ", aList.index( 'xyz' )
print "runoob 索引位置 : ", aList.index( 'runoob', 1, 3 )
```

以上实例输出结果如下：

```
xyz 索引位置:  1
runoob 索引位置 :  2
```

## 2.Python replace()方法

Python replace() 方法把字符串中的 old（旧字符串） 替换成 new(新字符串)，如果指定第三个参数max，则替换不超过 max 次。

语法

replace()方法语法

```
str.replace(old, new[, max])

```

- old -- 将被替换的子字符串。
- new -- 新字符串，用于替换old子字符串。
- max -- 可选字符串, 替换不超过 max 次

实例

```
#!/usr/bin/python
 
str = "this is string example....wow!!! this is really string";
print str.replace("is", "was");
print str.replace("is", "was", 3);
结果
thwas was string example....wow!!! thwas was really string
thwas was string example....wow!!! thwas is really string

```

## 3.OS

获取指定文件夹内的文件名

```
import os
ls1 = []
ls2 = []
d=input("路径")
a = d[1:-1]
for i in os.listdir(a):
    ls1.append(i)
    
结果
路径"D:\Python作业\18课\作业统计\第15课走迷宫"
['01-黄子扬.py', '02-黄子扬.py', '03-黄子扬.py', '04-黄子扬.py', '05-黄子扬.py', '06-黄子扬.py', '15-06 周子越.py', '15-1-肖香.py', '15-2-肖香.py', '15-3-肖香.py', '15-4-肖香.py', '15-5-肖香.py', '15-6-肖香.py', '15课01-姚文栋 作业1.py', '15课02-姚文栋 作业2.py', '15课03-姚文栋 作业3.py', '15课04-姚文栋 作业4.py', '15课05-姚文栋 作业5.py', '15课06-姚文栋 作业6.py', '15课1马宇腾.py', '15课2马宇腾.py', '15课3马宇腾.py', '15课4马宇腾.py', '15课5马宇腾.py', '15课6马宇腾.py', '15课时作业1运动的球-吴静怡.py', '15课时作业2操纵小球-吴静怡.py', '15课时作业3迷宫小球-吴静怡.py', '15课时作业4迷宫升级-吴静怡.py', '15课时作业5迷宫计时-吴静怡.py', '15课时作业6迷宫-吴静怡.py', '15课郭浩涵01.py', '15课郭浩涵02.py', '15课郭浩涵03.py', '15课郭浩涵04.py', '15课郭浩涵05.py', '15课郭浩涵06.py', '作业6.zip', '增加时间，完成全部程序--武宇涵.py', '增加终点--武宇涵.py', '实现墙对球的阻挡--武宇涵.py', '添加一个迷宫--武宇涵.py', '球在有背景的画布上移动--武宇涵.py', '球的键盘控制--武宇涵.py', '第01课1-程琅.py', '第05课03-向倩py.py', '第13课1-刘锦轩.py', '第15次课01 袁梦齐.py', '第15次课02 袁梦齐.py', '第15次课03 袁梦齐.py', '第15次课1-刘文才.py', '第15次课1-李一钦.py', '第15次课1-续志鹏.py', '第15次课1-魏宇涵.py', '第15次课2-刘文才.py', '第15次课2-李一钦.py', '第15次课2-续志鹏.py', '第15次课2-魏宇涵.py', '第15次课3-刘文才.py', '第15次课3-李一钦.py', '第15次课3-续志鹏.py', '第15次课3-魏宇涵.py', '第15次课4-刘文才.py', '第15次课4-李一钦.py', '第15次课4-续志鹏.py', '第15次课4-魏宇涵.py', '第15次课5-刘文才.py', '第15次课5-李一钦.py', '第15次课5-续志鹏.py', '第15次课5-魏宇涵.py', '第15次课6-刘文才.py', '第15次课6-李一钦.py', '第15次课6-续志鹏.py', '第15次课6-魏宇涵.py', '第15课(1)_周艺程.py', '第15课(2)-周艺程.py', '第15课(3)-周艺程.py', '第15课(4)-周艺程.py', '第15课(5)-周艺程.py', '第15课(6)-周艺程.py', '第15课-1 周尚佑.py', '第15课-1-余祺钰.py', '第15课-1徐祖军.py', '第15课-2 周尚佑.py', '第15课-2-余祺钰.py', '第15课-2徐祖军.py', '第15课-3 周尚佑.py', '第15课-3-余祺钰.py', '第15课-3徐祖军.py', '第15课-4 周尚佑.py', '第15课-4-余祺钰.py', '第15课-4徐祖军.py', '第15课-5 周尚佑.py', '第15课-5-余祺钰.py', '第15课-5徐祖军.py', '第15课-6 周尚佑.py', '第15课-6-余祺钰.py', '第15课-6徐祖军.py', '第15课-邱孜轩.py', '第15课01 郭盛灿.py', '第15课01-向倩.py', '第15课01-方佳伟.py', '第15课01-林子卓.py', '第15课01-洪千.py', '第15课01-胡林.py', '第15课01-赵宇翔.py', '第15课01-马镕相.py', '第15课02 郭盛灿.py', '第15课02-向倩.py', '第15课02-方佳伟.py', '第15课02-林子卓.py', '第15课02-洪千.py', '第15课02-胡林.py', '第15课02-赵宇翔.py', '第15课02-马镕相.py', '第15课03 郭盛灿.py', '第15课03-方佳伟.py', '第15课03-林子卓.py', '第15课03-洪千.py', '第15课03-胡林.py', '第15课03-赵宇翔.py', '第15课04 袁梦齐.py', '第15课04 郭盛灿.py', '第15课04-向倩.py', '第15课04-方佳伟.py', '第15课04-林子卓.py', '第15课04-洪千.py', '第15课04-胡林.py', '第15课04-赵宇翔.py', '第15课04-马镕相.py', '第15课05 袁梦齐.py', '第15课05 郭盛灿.py', '第15课05-向倩.py', '第15课05-方佳伟.py', '第15课05-林子卓.py', '第15课05-洪千.py', '第15课05-胡林.py', '第15课05-赵宇翔.py', '第15课06 袁梦齐.py', '第15课06 郭盛灿.py', '第15课06-向倩.py', '第15课06-方佳伟.py', '第15课06-林子卓(1).py', '第15课06-林子卓.py', '第15课06-洪千.py', '第15课06-胡林.py', '第15课06-赵宇翔.py', '第15课06-马镕相.py', '第15课1 莫铭记.py', '第15课1--许观幸.py', '第15课1-32310胡杨均.py', '第15课1-乔有航.py', '第15课1-何奇.py', '第15课1-何志强.py', '第15课1-余兵权.py', '第15课1-余奥帅.py', '第15课1-余放.py', '第15课1-刘强.py', '第15课1-刘稳.py', '第15课1-卢盛.py', '第15课1-卢鹏飞.py', '第15课1-吴家俊.py', '第15课1-吴师警.py', '第15课1-周子喧.py', '第15课1-周子城.py', '第15课1-周昀鑫.py', '第15课1-唐三越.py', '第15课1-姚烨.py', '第15课1-姜宇.py', '第15课1-姜海洋.py', '第15课1-帅宇浩.py', '第15课1-张为晖.py', '第15课1-张咏仪.py', '第15课1-张琴.py', '第15课1-张苏.py', '第15课1-方茂.py', '第15课1-李昊岽.py', '第15课1-杜荣瑶.py', '第15课1-杨雨薇.py', '第15课1-柯虎.py', '第15课1-熊廷发.py', '第15课1-王光磊.py', '第15课1-王蕊.py', '第15课1-王靖超.py', '第15课1-田羽柯.py', '第15课1-胡锦辉.py', '第15课1-蔡日晗.py', '第15课1-薛宏涛.py', '第15课1-谭皓天.py', '第15课1-邓雅菁.py', '第15课1-郑雨娟.py', '第15课1-郝金潇.py', '第15课1-陈战.py', '第15课1夏天宇.py', '第15课1朱晓春.py', '第15课1肖楠.py', '第15课2 莫铭记.py', '第15课2--许观幸.py', '第15课2-32310胡杨均.py', '第15课2-乔有航.py', '第15课2-何奇.py', '第15课2-何志强.py', '第15课2-余兵权.py', '第15课2-余奥帅.py', '第15课2-余放.py', '第15课2-刘强.py', '第15课2-刘稳.py', '第15课2-刘锦轩.py', '第15课2-卢盛.py', '第15课2-卢鹏飞.py', '第15课2-吴家俊.py', '第15课2-吴师警.py', '第15课2-周子喧.py', '第15课2-周子城.py', '第15课2-周昀鑫.py', '第15课2-唐三越.py', '第15课2-姚烨.py', '第15课2-姜宇.py', '第15课2-姜海洋.py', '第15课2-张为晖.py', '第15课2-张咏仪.py', '第15课2-张琴.py', '第15课2-张苏.py', '第15课2-方茂.py', '第15课2-李昊岽.py', '第15课2-杜荣瑶（键盘控制）.py', '第15课2-杨雨薇.py', '第15课2-柯虎.py', '第15课2-熊廷发.py', '第15课2-王光磊.py', '第15课2-王蕊.py', '第15课2-王靖超.py', '第15课2-田羽柯.py', '第15课2-程琅.py', '第15课2-胡锦辉.py', '第15课2-蔡日晗.py', '第15课2-薛宏涛.py', '第15课2-谭皓天.py', '第15课2-邓雅菁.py', '第15课2-郑雨娟.py', '第15课2-郝金潇.py', '第15课2-陈战.py', '第15课2.1夏天宇.py', '第15课2帅宇浩.py', '第15课2朱晓春.py', '第15课2肖楠.py', '第15课3 莫铭记.py', '第15课3--许观幸.py', '第15课3-32310胡杨均.py', '第15课3-乔有航.py', '第15课3-何奇.py', '第15课3-何志强.py', '第15课3-余兵权.py', '第15课3-余奥帅.py', '第15课3-余放.py', '第15课3-刘强.py', '第15课3-刘稳.py', '第15课3-刘锦轩.py', '第15课3-卢盛.py', '第15课3-卢鹏飞.py', '第15课3-吴家俊.py', '第15课3-吴师警.py', '第15课3-周子喧.py', '第15课3-周子城.py', '第15课3-周昀鑫.py', '第15课3-唐三越.py', '第15课3-姚烨.py', '第15课3-姜宇.py', '第15课3-姜海洋.py', '第15课3-帅宇浩.py', '第15课3-张为晖.py', '第15课3-张咏仪.py', '第15课3-张琴.py', '第15课3-张苏.py', '第15课3-方茂.py', '第15课3-李昊岽.py', '第15课3-杜荣瑶.py', '第15课3-杨雨薇.py', '第15课3-柯虎.py', '第15课3-熊廷发.py', '第15课3-王光磊.py', '第15课3-王蕊.py', '第15课3-王靖超.py', '第15课3-田羽柯.py', '第15课3-程琅.py', '第15课3-胡锦辉.py', '第15课3-蔡日晗.py', '第15课3-薛宏涛.py', '第15课3-谭皓天.py', '第15课3-邓雅菁.py', '第15课3-郑雨娟.py', '第15课3-郝金潇.py', '第15课3-陈战.py', '第15课3-马镕相.py', '第15课3朱晓春.py', '第15课3肖楠.py', '第15课4--许观幸.py', '第15课4-32310胡杨均.py', '第15课4-乔有航.py', '第15课4-何奇.py', '第15课4-何志强.py', '第15课4-余兵权.py', '第15课4-余奥帅.py', '第15课4-余放.py', '第15课4-刘强.py', '第15课4-刘稳.py', '第15课4-刘锦轩.py', '第15课4-卢盛.py', '第15课4-卢鹏飞.py', '第15课4-吴家俊.py', '第15课4-吴师警.py', '第15课4-周子喧.py', '第15课4-周子城.py', '第15课4-周昀鑫.py', '第15课4-唐三越.py', '第15课4-姚烨.py', '第15课4-姜宇.py', '第15课4-姜海洋.py', '第15课4-帅宇浩.py', '第15课4-张为晖.py', '第15课4-张咏仪.py', '第15课4-张琴.py', '第15课4-张苏.py', '第15课4-方茂.py', '第15课4-李昊岽.py', '第15课4-杜荣瑶.py', '第15课4-杨雨薇.py', '第15课4-柯虎.py', '第15课4-熊廷发.py', '第15课4-王光磊.py', '第15课4-王蕊.py', '第15课4-田羽柯.py', '第15课4-程琅.py', '第15课4-胡锦辉.py', '第15课4-蔡日晗.py', '第15课4-薛宏涛.py', '第15课4-谭皓天.py', '第15课4-邓雅菁.py', '第15课4-郑雨娟.py', '第15课4-郝金潇.py', '第15课4-陈战.py', '第15课4朱晓春.py', '第15课4肖楠.py', '第15课5--许观幸.py', '第15课5-32310胡杨均.py', '第15课5-乔有航.py', '第15课5-何奇.py', '第15课5-何志强.py', '第15课5-余兵权.py', '第15课5-余奥帅.py', '第15课5-余放.py', '第15课5-刘强.py', '第15课5-刘稳.py', '第15课5-刘锦轩.py', '第15课5-卢盛.py', '第15课5-卢鹏飞.py', '第15课5-吴家俊.py', '第15课5-吴师警.py', '第15课5-周子喧.py', '第15课5-周子城.py', '第15课5-周昀鑫.py', '第15课5-唐三越.py', '第15课5-姚烨.py', '第15课5-姜宇.py', '第15课5-姜海洋.py', '第15课5-张为晖.py', '第15课5-张咏仪.py', '第15课5-张琴.py', '第15课5-张苏.py', '第15课5-方茂.py', '第15课5-李昊岽.py', '第15课5-杜荣瑶.py', '第15课5-杨雨薇.py', '第15课5-熊廷发.py', '第15课5-王光磊.py', '第15课5-王蕊.py', '第15课5-田羽柯.py', '第15课5-程琅.py', '第15课5-胡锦辉.py', '第15课5-蔡日晗.py', '第15课5-薛宏涛.py', '第15课5-谭皓天.py', '第15课5-邓雅菁.py', '第15课5-郑雨娟.py', '第15课5-郝金潇.py', '第15课5-陈战.py', '第15课5-马镕相.py', '第15课5帅宇浩.py', '第15课5朱晓春.py', '第15课5肖楠.py', '第15课6--许观幸.py', '第15课6-32310胡杨均.py', '第15课6-乔有航.py', '第15课6-何奇.py', '第15课6-何志强.py', '第15课6-余兵权.py', '第15课6-余奥帅.py', '第15课6-余放.py', '第15课6-刘强.py', '第15课6-刘稳.py', '第15课6-刘锦轩.py', '第15课6-卢鹏飞.py', '第15课6-吴家俊.py', '第15课6-吴师警.py', '第15课6-周子喧.py', '第15课6-周子城.py', '第15课6-周昀鑫.py', '第15课6-唐三越.py', '第15课6-姚烨.py', '第15课6-姜宇.py', '第15课6-姜海洋.py', '第15课6-帅宇浩.py', '第15课6-张为晖.py', '第15课6-张咏仪.py', '第15课6-张琴.py', '第15课6-张苏.py', '第15课6-方茂.py', '第15课6-李昊岽.py', '第15课6-杜荣瑶.py', '第15课6-柯虎.py', '第15课6-熊廷发.py', '第15课6-王光磊.py', '第15课6-王蕊.py', '第15课6-田羽柯.py', '第15课6-程琅.py', '第15课6-胡锦辉.py', '第15课6-蔡日晗.py', '第15课6-薛宏涛.py', '第15课6-谭皓天.py', '第15课6-郑雨娟.py', '第15课6-郝金潇.py', '第15课6-陈战.py', '第15课6朱晓春.py', '第15课6肖楠.py', '第15课6迷宫格夏天宇.py', '第15课6邓雅菁.py', '第15课7-32310胡杨均(大量敌对生物,超高难度).zip', '第15课7-32310胡杨均.py', '第15课7-张苏.py', '第15课8-张苏.py', '第15课—李润来1.0.py', '第15课—李润来2.0.py', '第15课—李润来3.0.py', '第15课—李润来4.0.py', '第15课—李润来5.0.py', '第15课—李润来6.0(1).py', '第15课—李润来6.0.py', '第15课任务6-潘余鸿.py', '第15课作业1 杨山峰.py', '第15课作业1-蔡哲.py', '第15课作业2 杨山峰.py', '第15课作业2-蔡哲.py', '第15课作业3 杨山峰.py', '第15课作业3-蔡哲.py', '第15课作业4 杨山峰.py', '第15课作业4-蔡哲.py', '第15课作业5(2) 杨山峰.py', '第15课作业5-蔡哲.py', '第15课作业6(2) 杨山峰.py', '第15课作业6-蔡哲.py', '第15课时01-肖怡冰.py', '第15课时02-曾志杰.py', '第15课时02-肖怡冰.py', '第15课时03-曾志杰.py', '第15课时03-肖怡冰（2）.py', '第15课时04-肖怡冰（2）.py', '第15课时05-曾志杰.py', '第15课时05-肖怡冰.py', '第15课时06-曾志杰.py', '第15课时06-肖怡冰.py', '第15课时1-陈啟煊.py', '第15课时2-陈啟煊.py', '第15课时3-陈啟煊.py', '第15课时4-陈啟煊.py', '第15课时5-陈啟煊.py', '第15课时6-陈啟煊.py', '第15课时·04-曾志杰.py', '第15课是01-曾志杰.py', '第15课（1）-张雨杰.py', '第15课（2）-张雨杰.py', '第15课（3）-张雨杰.py', '第15课（4）-张雨杰.py', '第15课（5）-张雨杰.py', '第15课（6）-张雨杰.py', '第十五课01-康江涛.py', '第十五课01-汪英佳.py', '第十五课02-康江涛.py', '第十五课02-汪英佳.py', '第十五课02改进-康江涛.py', '第十五课03-康江涛.py', '第十五课03-汪英佳.py', '第十五课04-康江涛.py', '第十五课04-汪英佳.py', '第十五课05-康江涛.py', '第十五课05-汪英佳.py', '第十五课06-康江涛.py', '第十五课06-汪英佳.py', '第十五课时01-麦康禹.py', '第十五课时02-麦康禹.py', '第十五课时03-麦康禹.py', '第十五课时04-麦康禹.py', '第十五课时05-麦康禹.py', '第十五课时06-麦康禹.py']

进程已结束，退出代码为 0
```

## 4.正则表达式

```
import re

#[\u4E00-\u9FFF]是所有汉字,通过搜索汉字可以匹配名字,可以记一下
text='12345一二三四五abcde一二三四五12345'
m=re.findall('[\u4E00-\u9FFF]',text)#findall可以查找匹配项,在这里会返回一个列表,也就是m
print(m)#返回['一', '二', '三', '四', '五', '一', '二', '三', '四', '五']

text='12345一二三四五abcde一二三四五12345'
m=re.findall('[\u4E00-\u9FFF]+',text)#+将相邻的汉字组合成一个元素
print(m)#返回['一二三四五', '一二三四五']

text='12345一二三四五abcde一二三四五12345'
m=re.findall('[\u4E00-\u9FFF]+$',text)#$将末尾的汉字组合成一个元素
print(m)#返回[]



'''
#特别的,如果是用search提取的,那么m会是类似<re.Match object; span=(10, 13), match='胡杨均'>的东西,需要n=m.group(),这个n就是字符串了
text=';;;;;;啊啊啊aaaa1111'
print(text)
m=re.search(r'[\u4E00-\u9FFF]+',text)
print(m)
m2=m.group()
print(m2)#这样就不是表格了
'''

'''
a='Cirno99999学编程99999九99999我学废了abcdefg'
name=re.findall('[\u4E00-\u9FFF]{2,3}',a)#加{}是用来限定范围的,这里是2或3的长度
print(name)#会输出什么呢?是'学编程'吗?
'''

'''
a='Cirno99999学编程99999九99999我学废了abcdefg'
name=re.findall('(?<![\u4E00-\u9FFF])[\u4E00-\u9FFF]{2,3}(?![\u4E00-\u9FFF])', a)
print(name)#看着复杂,其实只需要知道?<!是查询前面,?!是查询后面就行了(这里作业可能用不到,不知道也无所谓)
'''

'''
a='123456'
b='234'
if re.search(b,a):#search用于寻找a中是否有b
    print('yes')

a='123456'
b='678'
if re.search(b,a):
    print('no')
'''

'''
#实战--题目:提取目标的学号和姓名
a='18课2023003561---胡杨均01'

num=re.search(r'\d{10}',a)#\d是一个正则表达式特殊字符,代表任何一个数字,等同于[0-9],{10}表示长度
num2=num.group()
name=re.search(r'[\u4E00-\u9FFF]{2,3}',a)
name2=name.group()
print(num2)
print(name2)

b='胡杨均'#假如excle表里的名字是这个,我们需要匹配它们
if re.search(name2,b):
    print(1)
if b==name2:
    print(2)
'''
```

## Python 正则表达式

正则表达式是一个特殊的字符序列，它能帮助你方便的检查一个字符串是否与某种模式匹配。

Python 自1.5版本起增加了re 模块，它提供 Perl 风格的正则表达式模式。

re 模块使 Python 语言拥有全部的正则表达式功能。

compile 函数根据一个模式字符串和可选的标志参数生成一个正则表达式对象。该对象拥有一系列方法用于正则表达式匹配和替换。

re 模块也提供了与这些方法功能完全一致的函数，这些函数使用一个模式字符串做为它们的第一个参数。

本章节主要介绍Python中常用的正则表达式处理函数。

------

### re.match函数

re.match 尝试从字符串的起始位置匹配一个模式，如果不是起始位置匹配成功的话，match() 就返回 none。

**函数语法**：

```
re.match(pattern, string, flags=0)
```

函数参数说明：

| 参数    | 描述                                                         |
| :------ | :----------------------------------------------------------- |
| pattern | 匹配的正则表达式                                             |
| string  | 要匹配的字符串。                                             |
| flags   | 标志位，用于控制正则表达式的匹配方式，如：是否区分大小写，多行匹配等等。参见：[正则表达式修饰符 - 可选标志](https://www.runoob.com/python/python-reg-expressions.html#flags) |

匹配成功 re.match 方法返回一个匹配的对象，否则返回 None。

我们可以使用 group(num) 或 groups() 匹配对象函数来获取匹配表达式。

| 匹配对象方法 | 描述                                                         |
| :----------- | :----------------------------------------------------------- |
| group(num=0) | 匹配的整个表达式的字符串，group() 可以一次输入多个组号，在这种情况下它将返回一个包含那些组所对应值的元组。 |
| groups()     | 返回一个包含所有小组字符串的元组，从 1 到 所含的小组号。     |

实例

```
#!/usr/bin/python
# -*- coding: UTF-8 -*- 
 
import re
print(re.match('www', 'www.runoob.com').span())  # 在起始位置匹配
print(re.match('com', 'www.runoob.com'))         # 不在起始位置匹配
```

以上实例运行输出结果为：

```
(0, 3)
None
```

实例

```
#!/usr/bin/python
import re
 
line = "Cats are smarter than dogs"
 
matchObj = re.match( r'(.*) are (.*?) .*', line, re.M|re.I)
 
if matchObj:
   print "matchObj.group() : ", matchObj.group()
   print "matchObj.group(1) : ", matchObj.group(1)
   print "matchObj.group(2) : ", matchObj.group(2)
else:
   print "No match!!"
```

以上实例执行结果如下：

```
matchObj.group() :  Cats are smarter than dogs
matchObj.group(1) :  Cats
matchObj.group(2) :  smarter
```

------

### re.search方法

re.search 扫描整个字符串并返回第一个成功的匹配。

函数语法：

```
re.search(pattern, string, flags=0)
```

函数参数说明：

| 参数    | 描述                                                         |
| :------ | :----------------------------------------------------------- |
| pattern | 匹配的正则表达式                                             |
| string  | 要匹配的字符串。                                             |
| flags   | 标志位，用于控制正则表达式的匹配方式，如：是否区分大小写，多行匹配等等。 |

匹配成功re.search方法返回一个匹配的对象，否则返回None。

我们可以使用group(num) 或 groups() 匹配对象函数来获取匹配表达式。

| 匹配对象方法 | 描述                                                         |
| :----------- | :----------------------------------------------------------- |
| group(num=0) | 匹配的整个表达式的字符串，group() 可以一次输入多个组号，在这种情况下它将返回一个包含那些组所对应值的元组。 |
| groups()     | 返回一个包含所有小组字符串的元组，从 1 到 所含的小组号。     |

实例

```
#!/usr/bin/python
# -*- coding: UTF-8 -*- 
 
import re
print(re.search('www', 'www.runoob.com').span())  # 在起始位置匹配
print(re.search('com', 'www.runoob.com').span())         # 不在起始位置匹配
```

以上实例运行输出结果为：

```
(0, 3)
(11, 14)
```

实例

```
#!/usr/bin/python
import re
 
line = "Cats are smarter than dogs";
 
searchObj = re.search( r'(.*) are (.*?) .*', line, re.M|re.I)
 
if searchObj:
   print "searchObj.group() : ", searchObj.group()
   print "searchObj.group(1) : ", searchObj.group(1)
   print "searchObj.group(2) : ", searchObj.group(2)
else:
   print "Nothing found!!"
```

以上实例执行结果如下：

```
searchObj.group() :  Cats are smarter than dogs
searchObj.group(1) :  Cats
searchObj.group(2) :  smarter
```

------

### re.match与re.search的区别

re.match只匹配字符串的开始，如果字符串开始不符合正则表达式，则匹配失败，函数返回None；而re.search匹配整个字符串，直到找到一个匹配。

实例



以上

```
#!/usr/bin/python
import re
 
line = "Cats are smarter than dogs";
 
matchObj = re.match( r'dogs', line, re.M|re.I)
if matchObj:
   print "match --> matchObj.group() : ", matchObj.group()
else:
   print "No match!!"
 
matchObj = re.search( r'dogs', line, re.M|re.I)
if matchObj:
   print "search --> searchObj.group() : ", matchObj.group()
else:
   print "No match!!"
```

实例运行结果如下：

```
No match!!
search --> searchObj.group() :  dogs
```

------

## 检索和替换

Python 的 re 模块提供了re.sub用于替换字符串中的匹配项。

语法：

```
re.sub(pattern, repl, string, count=0, flags=0)
```

参数：

- pattern : 正则中的模式字符串。
- repl : 替换的字符串，也可为一个函数。
- string : 要被查找替换的原始字符串。
- count : 模式匹配后替换的最大次数，默认 0 表示替换所有的匹配。

实例

```
#!/usr/bin/python
# -*- coding: UTF-8 -*-
 
import re
 
phone = "2004-959-559 # 这是一个国外电话号码"
 
# 删除字符串中的 Python注释 
num = re.sub(r'#.*$', "", phone)
print "电话号码是: ", num
 
# 删除非数字(-)的字符串 
num = re.sub(r'\D', "", phone)
print "电话号码是 : ", num
```

以上实例执行结果如下：

```
电话号码是:  2004-959-559 
电话号码是 :  2004959559
```

### repl 参数是一个函数

以下实例中将字符串中的匹配的数字乘以 2：

实例

```
#!/usr/bin/python
# -*- coding: UTF-8 -*-
 
import re
 
# 将匹配的数字乘以 2
def double(matched):
    value = int(matched.group('value'))
    return str(value * 2)
 
s = 'A23G4HFD567'
print(re.sub('(?P<value>\d+)', double, s))
```

执行输出结果为：

```
A46G8HFD1134
```

### re.compile 函数

compile 函数用于编译正则表达式，生成一个正则表达式（ Pattern ）对象，供 match() 和 search() 这两个函数使用。

语法格式为：

```
re.compile(pattern[, flags])
```

参数：

- **pattern** : 一个字符串形式的正则表达式
- **flags** : 可选，表示匹配模式，比如忽略大小写，多行模式等，具体参数为：
  1. **re.I** 忽略大小写
  2. **re.L** 表示特殊字符集 \w, \W, \b, \B, \s, \S 依赖于当前环境
  3. **re.M** 多行模式
  4. **re.S** 即为 **.** 并且包括换行符在内的任意字符（**.** 不包括换行符）
  5. **re.U** 表示特殊字符集 \w, \W, \b, \B, \d, \D, \s, \S 依赖于 Unicode 字符属性数据库
  6. **re.X** 为了增加可读性，忽略空格和 **#** 后面的注释

实例

```
>>>import re
>>> pattern = re.compile(r'\d+')                    # 用于匹配至少一个数字
>>> m = pattern.match('one12twothree34four')        # 查找头部，没有匹配
>>> print m
None
>>> m = pattern.match('one12twothree34four', 2, 10) # 从'e'的位置开始匹配，没有匹配
>>> print m
None
>>> m = pattern.match('one12twothree34four', 3, 10) # 从'1'的位置开始匹配，正好匹配
>>> print m                                         # 返回一个 Match 对象
<_sre.SRE_Match object at 0x10a42aac0>
>>> m.group(0)   # 可省略 0
'12'
>>> m.start(0)   # 可省略 0
3
>>> m.end(0)     # 可省略 0
5
>>> m.span(0)    # 可省略 0
(3, 5)
```

在上面，当匹配成功时返回一个 Match 对象，其中：

- `group([group1, …])` 方法用于获得一个或多个分组匹配的字符串，当要获得整个匹配的子串时，可直接使用 `group()` 或 `group(0)`；
- `start([group])` 方法用于获取分组匹配的子串在整个字符串中的起始位置（子串第一个字符的索引），参数默认值为 0；
- `end([group])` 方法用于获取分组匹配的子串在整个字符串中的结束位置（子串最后一个字符的索引+1），参数默认值为 0；
- `span([group])` 方法返回 `(start(group), end(group))`。

再看看一个例子：

实例

```
>>>import re
>>> pattern = re.compile(r'([a-z]+) ([a-z]+)', re.I)   # re.I 表示忽略大小写
>>> m = pattern.match('Hello World Wide Web')
>>> print m                               # 匹配成功，返回一个 Match 对象
<_sre.SRE_Match object at 0x10bea83e8>
>>> m.group(0)                            # 返回匹配成功的整个子串
'Hello World'
>>> m.span(0)                             # 返回匹配成功的整个子串的索引
(0, 11)
>>> m.group(1)                            # 返回第一个分组匹配成功的子串
'Hello'
>>> m.span(1)                             # 返回第一个分组匹配成功的子串的索引
(0, 5)
>>> m.group(2)                            # 返回第二个分组匹配成功的子串
'World'
>>> m.span(2)                             # 返回第二个分组匹配成功的子串
(6, 11)
>>> m.groups()                            # 等价于 (m.group(1), m.group(2), ...)
('Hello', 'World')
>>> m.group(3)                            # 不存在第三个分组
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
IndexError: no such group
```



### findall

在字符串中找到正则表达式所匹配的所有子串，并返回一个列表，如果有多个匹配模式，则返回元组列表，如果没有找到匹配的，则返回空列表。

**注意：** match 和 search 是匹配一次 findall 匹配所有。

语法格式为：

```
findall(string[, pos[, endpos]])
```

参数：

- **string** : 待匹配的字符串。
- **pos** : 可选参数，指定字符串的起始位置，默认为 0。
- **endpos** : 可选参数，指定字符串的结束位置，默认为字符串的长度。

查找字符串中的所有数字：

实例

```
# -*- coding:UTF8 -*-
 
import re
 
pattern = re.compile(r'\d+')   # 查找数字
result1 = pattern.findall('runoob 123 google 456')
result2 = pattern.findall('run88oob123google456', 0, 10)
 
print(result1)
print(result2)
```

输出结果：

```
['123', '456']
['88', '12']
```

多个匹配模式，返回元组列表：

实例

```
import re

result = re.findall(r'(\w+)=(\d+)', 'set width=20 and height=10')
print(result)
```



```
[('width', '20'), ('height', '10')]
```

### re.finditer

和 findall 类似，在字符串中找到正则表达式所匹配的所有子串，并把它们作为一个迭代器返回。

```
re.finditer(pattern, string, flags=0)
```

参数：

| 参数    | 描述                                                         |
| :------ | :----------------------------------------------------------- |
| pattern | 匹配的正则表达式                                             |
| string  | 要匹配的字符串。                                             |
| flags   | 标志位，用于控制正则表达式的匹配方式，如：是否区分大小写，多行匹配等等。参见：[正则表达式修饰符 - 可选标志](https://www.runoob.com/python/python-reg-expressions.html#flags) |

实例

 

```
import re

result = re.findall(r'(\w+)=(\d+)', 'set width=20 and height=10')
print(result)
```

输出结果：

```
12 
32 
43 
3
```

### re.split

split 方法按照能够匹配的子串将字符串分割后返回列表，它的使用形式如下：

```
re.split(pattern, string[, maxsplit=0, flags=0])
```

参数：

| 参数     | 描述                                                         |
| :------- | :----------------------------------------------------------- |
| pattern  | 匹配的正则表达式                                             |
| string   | 要匹配的字符串。                                             |
| maxsplit | 分隔次数，maxsplit=1 分隔一次，默认为 0，不限制次数。        |
| flags    | 标志位，用于控制正则表达式的匹配方式，如：是否区分大小写，多行匹配等等。参见：[正则表达式修饰符 - 可选标志](https://www.runoob.com/python/python-reg-expressions.html#flags) |

实例

```
>>>import re
>>> re.split('\W+', 'runoob, runoob, runoob.')
['runoob', 'runoob', 'runoob', '']
>>> re.split('(\W+)', ' runoob, runoob, runoob.') 
['', ' ', 'runoob', ', ', 'runoob', ', ', 'runoob', '.', '']
>>> re.split('\W+', ' runoob, runoob, runoob.', 1) 
['', 'runoob, runoob, runoob.']
 
>>> re.split('a*', 'hello world')   # 对于一个找不到匹配的字符串而言，split 不会对其作出分割
['hello world']
```



------

## 正则表达式对象

### re.RegexObject

re.compile() 返回 RegexObject 对象。

### re.MatchObject

group() 返回被 RE 匹配的字符串。

- **start()** 返回匹配开始的位置
- **end()** 返回匹配结束的位置
- **span()** 返回一个元组包含匹配 (开始,结束) 的位置

------

## 正则表达式修饰符 - 可选标志

正则表达式可以包含一些可选标志修饰符来控制匹配的模式。修饰符被指定为一个可选的标志。多个标志可以通过按位 OR(|) 它们来指定。如 re.I | re.M 被设置成 I 和 M 标志：

| 修饰符 | 描述                                                         |
| :----- | :----------------------------------------------------------- |
| re.I   | 使匹配对大小写不敏感                                         |
| re.L   | 做本地化识别（locale-aware）匹配                             |
| re.M   | 多行匹配，影响 ^ 和 $                                        |
| re.S   | 使 . 匹配包括换行在内的所有字符                              |
| re.U   | 根据Unicode字符集解析字符。这个标志影响 \w, \W, \b, \B.      |
| re.X   | 该标志通过给予你更灵活的格式以便你将正则表达式写得更易于理解。 |

------

## 正则表达式模式

模式字符串使用特殊的语法来表示一个正则表达式：

字母和数字表示他们自身。一个正则表达式模式中的字母和数字匹配同样的字符串。

多数字母和数字前加一个反斜杠时会拥有不同的含义。

标点符号只有被转义时才匹配自身，否则它们表示特殊的含义。

反斜杠本身需要使用反斜杠转义。

由于正则表达式通常都包含反斜杠，所以你最好使用原始字符串来表示它们。模式元素(如 r'\t'，等价于 '\\t')匹配相应的特殊字符。

下表列出了正则表达式模式语法中的特殊元素。如果你使用模式的同时提供了可选的标志参数，某些模式元素的含义会改变。

| 模式        | 描述                                                         |
| :---------- | :----------------------------------------------------------- |
| ^           | 匹配字符串的开头                                             |
| $           | 匹配字符串的末尾。                                           |
| .           | 匹配任意字符，除了换行符，当re.DOTALL标记被指定时，则可以匹配包括换行符的任意字符。 |
| [...]       | 用来表示一组字符,单独列出：[amk] 匹配 'a'，'m'或'k'          |
| [^...]      | 不在[]中的字符：[^abc] 匹配除了a,b,c之外的字符。             |
| re*         | 匹配0个或多个的表达式。                                      |
| re+         | 匹配1个或多个的表达式。                                      |
| re?         | 匹配0个或1个由前面的正则表达式定义的片段，非贪婪方式         |
| re{ n}      | 精确匹配 n 个前面表达式。例如， **o{2}** 不能匹配 "Bob" 中的 "o"，但是能匹配 "food" 中的两个 o。 |
| re{ n,}     | 匹配 n 个前面表达式。例如， o{2,} 不能匹配"Bob"中的"o"，但能匹配 "foooood"中的所有 o。"o{1,}" 等价于 "o+"。"o{0,}" 则等价于 "o*"。 |
| re{ n, m}   | 匹配 n 到 m 次由前面的正则表达式定义的片段，贪婪方式         |
| a\| b       | 匹配a或b                                                     |
| (re)        | 对正则表达式分组并记住匹配的文本                             |
| (?imx)      | 正则表达式包含三种可选标志：i, m, 或 x 。只影响括号中的区域。 |
| (?-imx)     | 正则表达式关闭 i, m, 或 x 可选标志。只影响括号中的区域。     |
| (?: re)     | 类似 (...), 但是不表示一个组                                 |
| (?imx: re)  | 在括号中使用i, m, 或 x 可选标志                              |
| (?-imx: re) | 在括号中不使用i, m, 或 x 可选标志                            |
| (?#...)     | 注释.                                                        |
| (?= re)     | 前向肯定界定符。如果所含正则表达式，以 ... 表示，在当前位置成功匹配时成功，否则失败。但一旦所含表达式已经尝试，匹配引擎根本没有提高；模式的剩余部分还要尝试界定符的右边。 |
| (?! re)     | 前向否定界定符。与肯定界定符相反；当所含表达式不能在字符串当前位置匹配时成功 |
| (?> re)     | 匹配的独立模式，省去回溯。                                   |
| \w          | 匹配字母数字及下划线                                         |
| \W          | 匹配非字母数字及下划线                                       |
| \s          | 匹配任意空白字符，等价于 **[ \t\n\r\f]**。                   |
| \S          | 匹配任意非空字符                                             |
| \d          | 匹配任意数字，等价于 [0-9].                                  |
| \D          | 匹配任意非数字                                               |
| \A          | 匹配字符串开始                                               |
| \Z          | 匹配字符串结束，如果是存在换行，只匹配到换行前的结束字符串。 |
| \z          | 匹配字符串结束                                               |
| \G          | 匹配最后匹配完成的位置。                                     |
| \b          | 匹配一个单词边界，也就是指单词和空格间的位置。例如， 'er\b' 可以匹配"never" 中的 'er'，但不能匹配 "verb" 中的 'er'。 |
| \B          | 匹配非单词边界。'er\B' 能匹配 "verb" 中的 'er'，但不能匹配 "never" 中的 'er'。 |
| \n, \t, 等. | 匹配一个换行符。匹配一个制表符。等                           |
| \1...\9     | 匹配第n个分组的内容。                                        |
| \10         | 匹配第n个分组的内容，如果它经匹配。否则指的是八进制字符码的表达式。 |

------

## 正则表达式实例

#### 字符匹配

| 实例   | 描述           |
| :----- | :------------- |
| python | 匹配 "python". |

#### 字符类

| 实例        | 描述                              |
| :---------- | :-------------------------------- |
| [Pp]ython   | 匹配 "Python" 或 "python"         |
| rub[ye]     | 匹配 "ruby" 或 "rube"             |
| [aeiou]     | 匹配中括号内的任意一个字母        |
| [0-9]       | 匹配任何数字。类似于 [0123456789] |
| [a-z]       | 匹配任何小写字母                  |
| [A-Z]       | 匹配任何大写字母                  |
| [a-zA-Z0-9] | 匹配任何字母及数字                |
| [^aeiou]    | 除了aeiou字母以外的所有字符       |
| [^0-9]      | 匹配除了数字外的字符              |

#### 特殊字符类

| 实例 | 描述                                                         |
| :--- | :----------------------------------------------------------- |
| .    | 匹配除 "\n" 之外的任何单个字符。要匹配包括 '\n' 在内的任何字符，请使用象 '[.\n]' 的模式。 |
| \d   | 匹配一个数字字符。等价于 [0-9]。                             |
| \D   | 匹配一个非数字字符。等价于 [^0-9]。                          |
| \s   | 匹配任何空白字符，包括空格、制表符、换页符等等。等价于 [ \f\n\r\t\v]。 |
| \S   | 匹配任何非空白字符。等价于 [^ \f\n\r\t\v]。                  |
| \w   | 匹配包括下划线的任何单词字符。等价于'[A-Za-z0-9_]'。         |
| \W   | 匹配任何非单词字符。等价于 '[^A-Za-z0-9_]'。                 |