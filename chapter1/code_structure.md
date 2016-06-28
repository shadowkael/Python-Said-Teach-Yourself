## 代码骨架

从前面的内容中，我们已经看到Python的一行代码写完之后，不需要额外加一个的`;`进行说明。在Guido设计语言时，为了避免输入太多的括号或者关键字，Python中使用缩进来区分代码块，建议使用四个空格进行缩进（不要使用Tab和空格混排）。就像我们在“练手小游戏”一节里看到的那样。

这样做无疑强制增加了代码的可读性，同时一行代码的建议长度是80个字符，如果超过80个字符可以在第一行的末尾使用连接符`\`，这样解释器会把下一行解释为同一行。

    >>> scan = 'I could see no valley'+ \
    ... 'no farms' + \
    ... 'no cottages' + \
    ... 'and no church spire--' + \
    ... 'only a lake.'
    >>> scan
    'I could see no valleyno farmsno cottagesand no church spire--only a lake.'

### 使用if、elif、else进行比较
前面我们讨论了基本运算和Python中常见的数据类型，下面我们探讨Python的代码结构:

    >>> flag = 5 < 3
    >>> if flag:
    ...     print("True condition block")
    ... else:
    ...     print("Flase condition block")
    ...
    Flase condition block
    
注意代码块开始的那一行行尾有个`:`，下一行属于这个块所以有四个空格用来缩进，然后是else，即条件不满足时，执行该区块的内容，然后继续`:`和缩进。

注意Python中不像C语言中使用swich语句控制多分支而是使用elif（此外如果……）
    >>> color = 'purple'
    >>> if color == 'red':
    ...     print("Apple")
    ... elif color == 'yellow':
    ...     print("Rock band")
    ... elif color == "purple":
    ...     print("A vestiges of the thought")
    ... else:
    ...     print("what is ", color")
    ...
    A vestiges of the thought
    
if、elif、else也被称作条件语句
    
#### Python中的False

除了逻辑运算得到的明确False外，下面的情况也会被认为是False:

  + null 类型    None
  + 整形         0
  + 浮点         0.0
  + 空字符串     ""
  + 空列表       []
  + 空元组       ()
  + 空字典       {}
  + 空集合       set()

除此之外，全都被认为是True，基于这样的定义，我们可以很方便的判定收到的参数或者列表是不是为空比如：`if ex_list:`就可以判定ex_list这个变量是不是有值，且值是不是为空。

##### 注意，None是个很特别是值

看下面这个例子，把`None`直接放到判定条件中：

    >>> if None:
    ...     print("True")
    ... else:
    ...     print("False")
    ...
    False
    
虽然结果输出了False但是None并不等同于False：
    
    >>> if None is False:
    ...     print("None is False")
    ... else:
    ...     print("None is just None")
    ...
    None is just None
    
### 循环
#### while:定义循环区块
目前为止我们的代码都是自顶向下执行的，有时候需要对某些代码块进行重复操作，这就用到了循环。Python中最简单的循环机制是while。比如打印0－9，可以写为：

    >>> count  = 0
    >>> while count < 10:
    ...     print(count)
    ...     count += 1
    ...
    0
    1
    .
    .
    .

#### break:跳出循环
如果想让循环在某一条件下停止，但不确定在哪次循环中跳出，可以在无限循环中使用`break`语句。比如我们通过Python的input()函数从键盘输入名字，进行问候。当输入数字`0`的时候跳出循环。

    1   >>> import string
    2   >>> while True:
    3   ...     name = input("Name to greeting [type 0 to quit]:")
    4   ...     if name == 0:
    5   ...         break
    6   ...     print(string.capwords(name), ", greeting!")
    7   ...
    8   Name to greeting [type 0 to quit]: leonardo
    9   Leonardo, greeting!
    10  Name to greeting [type 0 to quit]: van gogh
    11  Van Gogh, greeting!
    12  Name to greeting [type 0 to quit]: 0
    13  >>>

我们在第1行引入了string包，第6行中调用了string包中的一个函数`capwords()`，该函数接收一个字符串，并把每个单词的首字母大写。

#### continue:回到循环开始
有时候我们不想一下子结束整个循环，仅仅是不执行后面的代码回到循环开始的位置，那么就需要用到continue关键字，比如下面这个例子输出1－5的平方，如果可以被3整除则跳过:

    >>> for num in range(1,6):
    ...     if num%3 == 0:
    ...         continue
    ...     print(num * num)
    ...
    1
    4
    16
    25

#### for:迭代
上面的代码中我们看到了循环的另一种实现方式：`for`。其实`for`完成的是迭代，`range(1,6)`产生了一个可迭代的对象，Python中字符串、元组、字典、集合等都是可迭代的。`range()`的用法和序列一节中提到的分片类似，也是三个参数`range(start,stop,step)`。Python文档中写到："Return a sequence of numbers from start to stop by step." 看下面一个例子：

    >>> couple_num = [(1, 2), (2, 3), (3, 4)]
    >>> for (a, b) in couple_num:
    ...     print(a, b)
    ...
    1 2
    2 3
    3 4
    >>> 
    
#### else:循环结束的尾巴
无论是使用`while`还是`for`都允许加上一个`else`语句，可以用作循环正常结束(不是由break跳出)后的扫尾。下面是一个稍微复杂一点的代码，用心敲一遍，并读懂它的意思：

    >>> from pprint import pprint
    >>> a_list = list(range(10))
    >>> matrix_list = []
    >>> line = 0
    >>> while line < 5:
    ...     matrix_list.append(a_list)
    ...     flag = input("type 'q' to quit loop, else continue. line:%s" % line)
    ...     if flag == 'q':
    ...         break
    ...     line += 1
    ... else:
    ...     print(matrix_list)
    ...     pprint(matrix_list)
    ...
    
自己尝试解决所有的Error并正确运行它，如果一切顺利，并且没有打断会输出一个5\*10的矩阵。

好了研究一下代码中新出现的东西，`from pprint import pprint`的意思是从标准库的pprint模块中引入pprint函数，该函数在输出时会尽量排列输出元素增加人类可读性。
