# 第零部分  学前班
## 学前班
### 0 Python2.X 还是 Python3.X
 这里我假定你是从零开始学习的Python，如果你已经有一些使用经验了，可以跳过这部分内容。关于Python2和Python3版本的讨论网上有一大堆，这里我因为两个原因而选择Python3。一，官网推荐，二，输入语句比Python2短（Python2是raw_input,Python3是input）。更多的原因和利弊在此时讨论还为时过早，所以随便选择2系列或者3系列的最新稳定版就可以开始我们的旅程了。
### 1 安装Python
#### 1.1 Linux和Mac OS
 如果你使用的是Linux操作系统或者Mac OS，那么你的系统中很可能已经装好了Python，你需要做的仅仅是知道自己的Python版本就好了。输入如下命令查看：

    python -V
Python3.X的版本可能需要输入

    python3 -V
比如我这里看到的是：

    userMini:~ user$ python -V 
    Python 2.7.10
如果出现 *-bash: python: command not found* 类似的提示那么你应该访问[www.python.org](http://www.python.org)，官网上有针对各操作系统详细的安装方法。
#### 1.2 Windows
 在Windows中安装Python也很容易访问Python官网[www.python.org](http://www.python.org)，下载对应操作系统的安装包，安装即可，但是注意安装选项中有一个**"Add to path"**要打上勾，安装完成后可以在cmd或者Powershell中输入`python -V`，如果看到打印出了当前Python的版本号，说明安装成功。
### 2 代码编写环境
 选择什么操作系统并不重要，你熟悉哪个就用哪个，刚开始的几天里，我们会一直在Python的交互式解释器中溜达，当代码量超过20行的时候，我们就需要一个更方便的编写环境了。为了能更好的熟悉Python的语法，开始阶段最好选一个没有代码补全的简单文本编辑器，比如Notepad++(Windows)，gedit(Linux)，TextWrangler(OS X)，这里不建议使用Vim，它精简的设计使得熟悉Vim本身就需要时间。先来看一下Python交互式解释器长什么样子，在终端或者cmd中输入`python`，就可以看到类似下面的内容：

    userMini:~ user$ python
    Python 2.7.10 (default, Oct 23 2015, 19:19:21) 
    [GCC 4.2.1 Compatible Apple LLVM 7.0.0 (clang-700.0.59.5)] on darwin
    Type "help", "copyright", "credits" or "license" for more information.
    >>>
注意末尾的'>>>'，这是解释器中默认的提示符。按照惯例此时应该来打印"Hello World!"了

    >>> print('Hello World!')
可以小兴奋一下了，我们完成了每个大牛都要经历的事情。交互环境中的提示符除了'>>>'还有'...'，你可以当它是未完待续的意思，比如编写函数和if语句的时候，再敲一下'回车'就可以结束函数体了。
 在学下面的内容之前，不得不提一下Python的道，试着在'>>>'提示符后输入`import this`，你看到了什么？

"There should be one-- and preferabley only one --obvious way to do it. Although that way may not be obvious at first unless you're Dutch."，可能有同学不明白unless you're Dutch这句话是什么意思，那个……Python之父Guido是荷兰人……膜拜完'The Zen of Python'，如果你想退出交互环境的话，不同的操作系统有些差异一般是'Ctrl + c'，也可能是'Control + d'。另外试试'quit()'和'exit()'也可以退出交互环境。

### 3 学习助力
 学习过程中一定会遇到各式各样的问题，在交互环境里提供了一个有用的文档帮助，可以提供常用方法和关键字的说明比如输入`help(len)`可以得到：
 
    Help on built-in function len in module builtins:
    len(...)
        len(object)
        Return the number of items of a sequence or collection.

此外[官网在线文档](https://docs.python.org/3/)也提供了方便的文档搜索。参考内容中的简明Python教程有些特别，它可以做为一本速查手册。通常交互环境中的Traceback会指明错误比如：输入`gao`然后回车，屏幕上会显示：

    Traceback (most recent call last):
      File "<stdin>", line 1, in <module>
    NameError: name 'gao' is not defined
 
 第二行指名了代码错误的位置，最后一行指出了错误类型是`NameError`，具体情况是`name 'gao' is not defined`，如果你遇到的问题在查阅文档后不能解决，可以试试把错误类型和具体内容粘到搜索引擎中，推荐使用Google或者Bing搜索。
 
 ### 4友情提示
 后面的代码块中可能会出现：
     >>> a = 5    # 给变量 a 赋值为 5
 代码中`#`后面的部分是注释(comments)，范围是从`#`开始，到这一行结束，这里用作解释说明教程中的代码。代码在真正运行时注释是不起作用的，自己编写代码时也应当留有注释，方便日后理解，有这么一句格言：“Code Tells You How, Comments Tell You Why”。