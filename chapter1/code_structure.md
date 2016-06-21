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
    
注意代码块开始的那一行行尾有个`:`，下一行属于这个块所以有四个空格用来缩进，然后是else，即条件不满足时执行该区块的内容，然后继续`:`和缩进。
    


