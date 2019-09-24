## 关键字（keyword）
编程语言中有特定功能、含义的名字,“标识符”，程序中所有变量命名都不可以和关键字重名。可以使用下面的代码在Python的解释交互器上很方便的查看


```
import keyword
keyword.kwlist
```
显示如下：
['False', 'None', 'True', 'and', 'as', 'assert', 'break', 'class', 'continue', 'def', 'del', 'elif', 'else', 'except', 'finally', 'for', 'from', 'global', 'if', 'import', 'in', 'is', 'lambda', 'nonlocal', 'not', 'or', 'pass', 'raise', 'return', 'try', 'while', 'with', 'yield']

在CPython的实现中，源码位置：cpython/Lib/keyword.py 中有两个方法："iskeyword", "kwlist"。

