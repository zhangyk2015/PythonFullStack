### 一、格式化输出【重点掌握】

> 方式一：占位符          不常用
>
> ```
> %d:可以匹配数字，一般匹配整型【整数】
> %f：可以匹配数字，一般匹配浮点型【小数】
> %s：可以匹配Python中的一切数据类型
> ```
>
> 方式二：f""			常用
>
> 方式三：format(),字符串中讲解
>
> ```Python
> # 1.方式一：占位符          不常用
> """
> %d:可以匹配数字，一般匹配整型【整数】
> %f：可以匹配数字，一般匹配浮点型【小数】
> %s：可以匹配Python中的一切数据类型
> """
> print(34,100,'abc')
> print('学号:',34,',','成绩:',100,',','姓名:','abc',sep='')
>
> # 占位符的语法："指定格式的占位符" % (实际的数据)
> print('学号:%d,成绩:%d,姓名:%s' % (34,100,'abc'))
>
> # 注意1：占位符和实际数据的数量一定要相同
> # print('学号:%d,成绩:%d' % (34,100,'abc'))
> # print('学号:%d,成绩:%d,姓名:%s' % (34,100))
> # 注意2：实际的数据和占位符的类型一定要匹配
> # print('学号:%d,成绩:%d,姓名:%f' % (34,100,'abc'))
> # 注意3:%.nd,n为大于等于1的数字，表示整型的格式化
> print('学号:%s,成绩:%s,姓名:%s' % (34,100,'abc'))
> print('学号:%d,成绩:%s,姓名:%s' % (34,100,'abc'))
> print('学号:%.5d,成绩:%s,姓名:%s' % (34,100,'abc'))
> # 注意4：%.nf,n为大于等于1的数字，表示浮点型的格式化
> print("身高:%f" % (172.864565))
> print("身高:%.3f" % (172.864565))
> print("身高:%.2f" % (172.864565))
>
> # 2.方式二：f""/f-string		常用
> print('学号:%d,成绩:%d,姓名:%s' % (34,100,'abc'))
> print(f"学号:{34},成绩:{100},姓名:{'abc'}")
> # 注意：f"{xx:.nf}"
> print(f"体重:{150.5632:.2f}")
>
> # 练习：从控制台分别输入姓名，年龄和爱好，并按照指定格式输出到控制台上
> """
> 运行效果：
> 请输入姓名：张三
> 请输入年龄：18
> 请输入爱好：吹牛逼
> 我是张三，今年18，爱好吹牛逼
> """
> name = input("请输入姓名：")
> age = input('请输入年龄:')
> hobby = input("请输入爱好：")
> print('我是',name,',','今年',age,',','爱好',hobby,sep='')
> print('我是%s,今年%s,爱好%s' % (name,age,hobby))
> print(f'我是{name},今年{age},爱好{hobby}')    # *******
> ```

### 二、变量【重点掌握】

#### 1.数据类型

> ​	顾名思义，计算机就是用来做数学计算的机器，因此，计算机程序理所当然的可以处理各种数值。但是，计算机能处理的远远不止数值，还可以处理文本，图形，音频，视频，网页等各种各样的数据，而处理不同的数据，需要使用不同的数据类型来进行表示

> 【面试题】Python中常用的数据类型：
>
> - 数字型：整型【int】,浮点型【float】,复数【complex】
> - 布尔型：bool，只有两个值：True和False，True可以被当做1使用，False可以被当做0使用
> - 字符串型：str
> - 列表：list
> - 元组：tuple
> - 字典：dict
> - 集合：set
> - 字节：bytes
> - 空值：NoneType,只有一个值：None    

> ```Python
> # 一、掌握
> # 1. 数字型：整型【int】,浮点型【float】,复数【complex】
> n1 = 34
> n2 = 45.19
> n3 = 4 + 8j
> print(n1,n2,n3)
>
> # 2. 布尔型：bool,只有两个值：True和False
> b1 = True
> b2 = False
> print(b1,b2)
> # 注意：True可以被当做1使用，False可以被当做0使用
> print(True + 1)
> print(False + 1)
>
> # 3. 字符串型：str
> s1 = "3464fahg%$#计算机"
> print(s1)
> s2 = '3464' \
>      'fahg' \
>      '%$#' \
>      '计算机'
> print(s2)
> s3 = """3464
> fahg
> %$#
> 计算机"""
> print(s3)
> s4 = '''3464
> fahg
> %$#
> 计算机'''
> print(s4)
>
> # 二、了解，后期会详细讲解
> # 4.列表：list
> lst1 = [45,67,8,99]
> print(lst1)
>
> # 5.元组：tuple
> t1 = (45,67,8,99)
> print(t1)
>
> # 6.字典：dict
> d1 = {'a':10,'b':20}
> print(d1)
>
> # 7.集合：set
> set1 = {45,67,8,99}
> print(set1)
>
> # 8.字节：bytes
> b3 = b'fhajfh'
> print(b3)
> b3 = b"fhajfh"
> print(b3)
>
> # 9.空值：NoneType,只有一个值：None
> n = None
> print(n)
> ```

#### 2.定义变量

> 程序在运行的过程中，表示的值可以随时发生改变的标识符
>
> 在程序设计中，变量是一种存储数据的载体【容器】
>
> 语法：变量名  =   值
>
> 说明：变量名其实就是一个标识符
>
> ```Python
> # 1.基本定义
> # name是变量名/引用/标识符，'zhangsan'是数据，用于给name赋值
> # 注意：定义一个变量，相当于在计算机的内存中开辟了一份空间，该空间中存储了一个指定的数据
> name = 'zhangsan'
> print(name)
>
> # 2.在定义变量的同时可以声明类型，后期才会使用到
> num:int = 10
>
> # 3.定义多个变量
> # a
> a1 = a2 = a3 = 66
> print(a1,a2,a3)
>
> # b
> b1,b2,b3 = 10,20,30
> print(b1,b2,b3)
>
> # 注意：默认情况下，当同时定义多个变量时，变量和数据的数量需要保持一致
> # b1,b2,b3 = 10,20,30,40  # ValueError: too many values to unpack (expected 3)
> # b1,b2,b3,b4 = 10,20,30 # ValueError: not enough values to unpack (expected 4, got 3)
> ```

#### 3.变量的使用

> ```Python
> # 1.可以给变量重新赋值
> name = 'zhangsan'    # 初始值
> print(name)
> name = '李四'        # 重新赋的值
> print(name)
>
> # 2.id(x)：获取数据x在计算机内存中的地址
> # 注意：获取一个变量的地址，实际获取的是变量中存储的数据的地址
> a1 = 19
> print(id(a1))
> print(id(19))
>
> # 3.type(x):获取数据x的数据类型
> r1 = 66
> r2 = '66'
> print(r1,r2)
> print(type(r1))   # <class 'int'>
> print(type(r2))   # <class 'str'>
> lst = [34,6,7,8]
> print(type(lst))   # <class 'list'>
>
> # 注意：但凡是通过input从控制台输入的数据，都是字符串类型
> age = input("请输入你的年龄：")
> print(age,type(age))  # 18 <class 'str'>
>
> # 4.常量
> # 注意：在程序中，如果希望一个变量表示的值不需要被修改，则将该变量定义为常量
> # 变量命名法：所有字母全部小写，不同单词之间使用下划线连接
> # 常量命名法：所有字母全部大写，不同单词之间使用下划线连接
> PI = 3.1415
> print(PI)
>
> # PI = 'gagag'
> # print(PI)
> ```

#### 4.变量的应用

> ```Python
> # 1.交换两个变量的值【面试题】
> # a.方式一：增减一个中间变量
> num1 = 23
> num2 = 88
> temp = num1
> num1 = num2
> num2 = temp
> print(num1,num2)
>
> # b.方式二：Python中特有的语法            ********
> num1 = 23
> num2 = 88
> num1,num2 = num2,num1
> print(num1,num2)
>
> # c.方式三：加减法
> num1 = 23
> num2 = 88
> num1 = num1 + num2  # num1 = 23 + 88
> num2 = num1 - num2  # num2 = 23 + 88 - 88
> num1 = num1 - num2  # num1 = 23 + 88 - 23
> print(num1,num2)
>
> # d.方式四：异或【自学】
>
> # 2.打包pack和拆包unpack【面试题】
> # b1,b2,b3 = 10,20,30,40  # ValueError: too many values to unpack (expected 3)
>
> # *:所有
> # a.打包
> b1,b2,*b3 = 10,20,30,40,24,56,7,89
> print(b1,b2,b3)
> b1,*b2,b3 = 10,20,30,40,24,56,7,89
> print(b1,b2,b3)
> *b1,b2,b3 = 10,20,30,40,24,56,7,89
> print(b1,b2,b3)
>
> # b.拆包
> a,b,c = [34,56,6]
> print(a,b,c)
> a,b,c = (34,56,6)
> print(a,b,c)
> a,b,*c = (34,56,6,56,78)
> print(a,b,c)
> ```

#### 5.删除变量

> 定义变量：从无到有，语法：变量名  = 值，是在计算机的内存中开辟空间的过程
> 删除变量：从有到无,语法：del  变量名，该变量在计算机内存中占用的空间被销毁的过程
>
> ```Python
> # 1.定义变量
> name = 'jack'
> print(name)
>
> # 2.删除变量
> del name
> # print(name)  # NameError: name 'name' is not defined
>
> # print(num)   # NameError: name 'num' is not defined
> ```

#### 6.变量的类型转换

> int(x):将x转换为整型 
>
> float(x):将x转换为浮点型
>
> str(x):将x转换为字符串,x可以是任意类型
>
> bool(x):将x转换为布尔型
>
> ```Python
> # 1.需求：假设人的最长寿命为130，计算剩余寿命
> # 写法一：
> # age = input('请输入你的年龄：')
> # print(f"剩余寿命:{130 - int(age)}")
>
> # 写法二：
> # age = input('请输入你的年龄：')
> # age = int(age)  # 重新赋值
> # print(f"剩余寿命:{130 - age}")
>
> # 写法三：
> age = int(input('请输入你的年龄：'))
> print(f"剩余寿命:{130 - age}")
> ```



