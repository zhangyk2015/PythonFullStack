### Day3作业讲解

> ```Python
> """
> 1.下列哪个语句在Python中是非法的？（）
> A. x = y = z = 1
> B. x = (y = z + 1)
> C. x, y = y, x
> D. x = y
> """
> y = 2
> z = 0
> # 错误写法，原因：y = z + 1，只是将z+1的结果赋值给y,但是，y = z + 1整体没结果
> # x = (y = z + 1)
> # 正确写法一
> x = (y == z + 1)
> print(x)
> # 正确写法二
> y = z + 1
> x = y
> print(x)
>
> # 扩展：
> y = z + 1
> print(y)
>
> # 已知x = 3 == 3,执行结束后，变量x的值为（）。
> x = 3 == 3
> print(x)   # True
>
> # 从控制台输入一个三位数，分别拆分出个位数，十位数和百位数，将拆分结果输出，
> # 格式为：百位：xx,十位：xx，个位：xx
> # 方式一
> num = int(input('请输入一个三位数：'))  # 153
> bw = num // 100
> sw = num // 10 % 10   # num % 100 // 10
> gw = num % 10
> print(f"百位：{bw},十位：{sw}，个位：{gw}")
>
> # 方式二
> # 扩展：xx[index]表示获取列表，元组或字符串中的第index个数据，index从0开始
> # 如：s = 'abc'---->s[0]获取的是'a',s[1]获取的是'b',s[2]获取的是'c'
> num = input('请输入一个三位数：')   # 153
> bw = num[0]
> sw = num[1]
> gw = num[2]
> print(f"百位：{bw},十位：{sw}，个位：{gw}")
> ```

### 一、分支语句【重点掌握】

> Python 中语句的结构：顺序结构，分支结构【if语句】，循环结构【while语句和for语句】

#### 1.概念

> 在生活中，所谓的判断，指的是如果某些条件满足才能做某件事情；条件不满足时则不能做
>
> ![判断情景](image/判断情景.png)
>
> 在编程中，判断所给定的条件是否满足，根据判断的结果对应执行不同的语句，Python中的分支语句只有if语句
>
> ![if语句](image/if语句.JPG)

#### 2.使用

##### 2.1if单分支

> 语法：
>
> ```
> if 条件：
> 	语句
> ```
>
> 说明：当程序执行到if语句时，首先判断“条件”的值，如果条件的值为“真”，则执行缩进的语句；如果条件的值为“假”，则跳过整个if语句继续向下执行
>
> ```Python
> """
> 总结：
>     a.在Python中，是通过缩进区分代码块的，在编写程序的过程中，要注意缩进对齐问题,
>       一个缩进一般是4个空格或一个tab键
>     b.if语句中的条件是常量，变量或表达式
>     c.Python中表示假的数据：0  0.0   False "" []  ()  {}  None等
>     d.if单分支的工作原理：如果条件成立，则执行代码块中的语句，
>       如果条件不成立，则整个if语句会被跳过，继续执行后面的代码
>     e.总结：代码块要么执行，要么不执行
> """
> # 1.基本语法
> print('11111~~~~~~~')
> if False:
>     print('ok~~~~~~~')
>     print(6262672)
> print('22222~~~~~~~')
>
> # 2.
> # a.用数据直接作为条件
> if 'hello':
>     print('yes~~~~~111')
>
> # b.用变量作为条件         ******
> num = 0
> if num:
>     print('yes~~~~~2222')
>
> # c.用运算符作为条件        ******
> # 主要包括：条件运算符，逻辑运算符，成员运算符
> num1 = 34
> num2 = 89
> if num1 == num2 or num1 < num2:
>     print('yes~~~~3333')
>
> # 3.应用
> # a.需求1：未成年人禁止进入网吧
> # age = int(input('请输入你的年龄：'))
> # if age < 18:
> #     print('未成年人禁止进入网吧')
>
> # b.需求2：从控制台输入一个整数，判断该数是否是偶数
> # 偶数：能被2整除、2的倍数
> # 整除/倍数：num1 % num2 == 0
> num = int(input('请输入一个整数：'))
> # 注意：=和==的区别
> if num % 2 == 0:
>     print(f"{num}是偶数")
>
> # c.从控制台输入一个整数，判断该数是否是7的倍数
> num = int(input('请输入一个整数：'))
> if num % 7 == 0:
>     print(f"{num}是7的倍数")
> ```

##### 2.2if双分支

> 语法：
>
> ```
> if 条件：
> 	语句1
> else：
> 	语句2
> ```
>
> 说明：当程序执行到if-else语句时，首先判断“条件”的值，如果条件的值为“真”，则执行语句1；如果条件的值为“假”，则执行语句2
>
> ```Python
> """
> 总结：
>     a.if-else基本使用和if单分支的使用是相同的，条件的表示完全相同
>     b.工作原理：根据条件是否成立，if分支和else分支只会有一个被执行
>     c.else的后面没有条件
>     d.总结：if-else实现了二选一的操作
> """
> # 1.基本语法
> num = 89
> if num < 10:
>     print('小于~~~~~')
> else:
>     print('大于~~~~~')
>
> # 2.应用
> # a.需求1：未成年人禁止进入网吧
> # age = int(input('请输入你的年龄：'))
> # if age < 18:
> #     print('未成年人禁止进入网吧')
> # else:
> #     print('欢迎进入，欢迎充值')
>
> # b.需求2：从控制台输入一个整数，判断该数是否是偶数
> # 偶数：能被2整除、2的倍数
> # 整除/倍数：num1 % num2 == 0
> # num = int(input('请输入一个整数：'))
> # # 注意：=和==的区别
> # if num % 2 == 0:
> #     print(f"{num}是偶数")
> # else:
> #     print(f"{num}是奇数")
>
> # c.从控制台输入一个整数，判断该数是否是7的倍数
> num = int(input('请输入一个整数：'))
> if num % 7 == 0:
>     print(f"{num}是7的倍数")
> else:
>     print(f"{num}不是7的倍数")
> ```
>
> ```Python
> 在Python中产生随机数的方式：
> 方式一：
>      第一步：导入模块/导入库：import  random   
>      第二步：num = random.randint(start,end)，闭区间【包头包尾】,步长默认为1，无法自定义步长
> 方式二：
>      第一步：import  random   
>      第二步：num = random.choice(range(start,end,step))，前闭后开区间【包头不包尾】
>         range(start,end,step):相当于生成了一个容器，容器中的数据是指定的区间，指定的步长
>             start：开始数字，可以省略，默认为0
>             end：结束数字，不可以省略
>             step：步长，可以省略，默认为1，从start~end递增，则步长为正数，从start~end递减，则步长为负数
>             
> 举例：
>     random.randint(0,100):获取0~100之间的任意一个整数随机数
>     random.choice(range(100)):获取0~99之间的任意一个整数随机数
>     random.choice(range(1,100)):获取1~99之间的任意一个整数随机数
>     random.choice(range(1,100,2)):获取1~99之间的任意一个奇数随机数
>     random.choice(range(0,100,2)):获取0~99之间的任意一个偶数随机数
>     
>     random.choice(range(100,2)):错误写法，说明：如果end和step未被省略，则start也不能省略
> ```

> ```Python
> # 1.随机数的简单获取
> """
> 在Python中产生随机数的方式：
> 方式一：
>      第一步：导入模块/导入库：import  random
>      第二步：num = random.randint(start,end)，闭区间【包头包尾】,步长默认为1，无法自定义步长
> 方式二：
>      第一步：import  random
>      第二步：num = random.choice(range(start,end,step))，前闭后开区间【包头不包尾】
>         range(start,end,step):相当于生成了一个容器，容器中的数据是指定的区间，指定的步长
>             start：开始数字，可以省略，默认为0
>             end：结束数字，不可以省略
>             step：步长，可以省略，默认为1，从start~end递增，则步长为正数，从start~end递减，则步长为负数
>
> 举例：
>     random.randint(0,100):获取0~100之间的任意一个整数随机数
>     random.choice(range(100)):获取0~99之间的任意一个整数随机数
>     random.choice(range(1,100)):获取1~99之间的任意一个整数随机数
>     random.choice(range(1,100,2)):获取1~99之间的任意一个奇数随机数
>     random.choice(range(0,100,2)):获取0~99之间的任意一个偶数随机数
>
>     random.choice(range(100,2)):错误写法，说明：如果end和step未被省略，则start也不能省略
> """
> import random   # 注意：在实际使用中，同一个py文件中只需要导入一次
> n1 = random.randint(0,100)
> print(n1)
> n2 = random.choice(range(100))  # 0~99   ******
> print(n2)
> n3 = random.choice(range(1,100)) # 1~99
> print(n3)
> n4 = random.choice(range(1,100,2)) # 1~99之间的奇数
> print(n4)
> n5 = random.choice(range(0,100,2)) # 0~99之间的偶数
> print(n5)
>
> # 错误写法：range(100,2)，此时的100表示start,2表示end，step默认为1
> # n5 = random.choice(range(100,2))  # 等价于range(100,2,1)
> # print(n5)
>
> print(list(range(100,2,1)))   # []
> print(list(range(100,2,-1)))  # [100,99......3]
> """
> range(100,2,1)---->100 101 102....
> range(100,2,-1)----->100 99 98.........3
> """
>
> # 2.应用
> # a.在10~80之间随机获取一个数，判断该数是否是3的倍数
> import random
> num1 = random.randint(10,80)
> if num1 % 3 == 0:
>     print(f"{num1}是3的倍数")
> else:
>     print(f"{num1}不是3的倍数")
>
> # b.模拟彩票中奖
> import random
> random_num = random.choice(range(1000,10000))
> guess_num = int(input("请输入一个4位数："))
> if guess_num == random_num:
>     print('恭喜你，中大奖了！')
> else:
>     print("谢谢参与！")
> ```

##### 2.3if多分支

> 语法：
>
> ```python
> if 条件1：
> 	语句1
> elif 条件2：
> 	语句2
> elif 条件3：
> 	语句3
> ….
> elif 条件n：
> 	语句n
> else：
> 	语句m
>     
> else if  ---->elif
> ```
>
> 说明：当程序执行到if-elif语句时，首先计算条件1的值，如果条件1的值为真，那么执行语句1，执行完语句1则直接跳出整个if-elif语句，代码继续向下执行；
>
> ```Python
> """
> 注意：
>     a.如果需要操作的情况在3种及3种以上，则使用if多分支
>     b.if-elif...-else实现的是多选一的操作
>     c.不管多分支中有多少个条件成立，都只会执行其中的一个分支,哪个分支在最前面则执行哪个分支
>     d.else分支可以省略，但是，一般情况下，如果if和elif对应的所有的条件都不满足，则会执行else分支
>     e.if和elif的后面都需要添加条件，else的后面一定不要添加条件
> """
> # 1.基本语法
> # a.if-elif-elif......
> # num = int(input('请输入一个数字：'))
> # print('start~~~~~')
> # if num == 1:
> #     print('a')
> # elif num == 2:
> #     print('b')
> # elif num == 3:
> #     print('c')
> # elif num == 4:
> #     print('d')
> # elif num == 5:
> #     print('e')
> # elif num == 6:
> #     print('f')
> print('end~~~~~')
>
> # b.if-elif-elif......else
> num = int(input('请输入一个数字：'))
> if num == 1:
>     print('a')
> elif num == 1:
>     print('b')
> elif num == 1:
>     print('c')
> elif num == 4:
>     print('d')
> elif num == 5:
>     print('e')
> elif num == 6:
>     print('f')
> else:
>     print('xyz')
>
> # 2.应用
> # 需求:从控制台输入两个数，比较这两个数的大小
> # 方式一
> # num1 = int(input('请输入第一个数：'))
> # num2 = int(input('请输入第二个数：'))
> # if num1 > num2:
> #     print('大于')
> # elif num1 < num2:
> #     print('小于')
> # else:
> #     print('等于')
>
> # 方式二：扩展：eval(xx):识别xx字符串中的python代码并执行
> # r = eval(input("请输入两个数，用逗号隔开:"))
> # print(r,type(r))
> num1,num2 = eval(input("请输入两个数，用逗号隔开:"))  # 拆包
> # print(type(num1),type(num2))
> if num1 > num2:
>     print('大于')
> elif num1 < num2:
>     print('小于')
> else:
>     print('等于')
> ```

##### 2.4三者的区别

> ```
> 【面试题】if语句的单分支，双分支和多分支的区别
> 单分支：只能处理一种情况，特点：要么执行，要么不执行
> 双分支：处理两种情况，特点：实现二选一的操作
> 多分支：处理3种及3种以上的情况，特点：实现多选一的操作
> ```

##### 2.5嵌套if语句

> 语法：
>
> ```
> if 表达式1：
> 	语句1
> 	if 表达式2：
> 		语句2
> ```
>
> 说明：当表达式1和表达式2的值都为真时，才会执行语句2
>
> 注意：单分支，双分支和多分支两两之间可以互相嵌套
>
> ```Python
> # 1.基本使用
> n1 = 34
> n2 = 90
> if n1 != n2:
>     print('yes~~~~~~1111111')
>     if n1 < n2:
>         print('yes~~~~~22222')
>     else:
>         print('no~~~~~22222')
> else:
>     print('no~~~~~1111')
>
> # 2.应用
> """
> 扩展：
> x.isdigit():判断x字符串是否非空且全部由数字组成，如果是则结果为True,反之为False
> len(x):获取x字符串的长度
> """
> num = input('请输入一个三位数：')  # 153
> if num.isdigit():
>     if len(num) == 3:
>         num = int(num)
>         bw = num // 100
>         sw = num // 10 % 10  # num % 100 // 10
>         gw = num % 10
>         print(f"百位：{bw},十位：{sw}，个位：{gw}")
>     else:
>         print('不是三位数')
> else:
>     print("输入有误")
> ```

##### 2.6三目运算符

> Python中本身没有三目运算符，我们可以通过if-else模拟三目运算符
> 优点：实现二选一的操作，可以简化if-else语句
> 缺点：三目运算符只有一行代码，所以只能实现简单的逻辑
>
> ```Python
> # 语法：a if 条件 else b
> # 工作原理：如果条件成立，则整个表达式的结果为a；如果条件不成立，则整个表达式的结果为b
>
> # 1.代码块的实现：逻辑复杂
> num = int(input('请输入一个整数：'))
> # 注意：=和==的区别
> if num % 2 == 0:
>     print(f"{num}是偶数")
> else:
>     print(f"{num}是奇数")
>
> # 2.三目运算符实现：逻辑简单
> num = int(input('请输入一个整数：'))
> r1 = '偶数' if num % 2 == 0 else '奇数'
> print(r1)
> r1 = True if num % 2 == 0 else False
> print(r1)
> ```



### 