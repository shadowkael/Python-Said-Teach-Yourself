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
    

    


