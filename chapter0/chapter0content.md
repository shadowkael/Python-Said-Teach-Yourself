# 第零部分  学前班的迷惑和术语
## 学前班
### 0 Python2.X 还是 Python3.X
这里我假定你是从零开始学习的Python，如果你已经有一些使用经验了，可以跳过这部分内容。关于Python2和Python3版本的讨论网上有一大堆，这里我因为两个原因而选择Python3。一，官网推荐，二，输入语句比Python2短（Python2是raw_input,Python3是input）。更多的原因和利弊在此时讨论还为时过早，所以随便选择2系列或者3系列的最新稳定版就可以开始我们的旅程了。
### 1 安装Python
#### 1.1 Linux和Mac OS
如果你使用的是Linux操作系统或者Mac OS，那么你的系统中很可能已经装好了Python，你需要做的仅仅是知道自己的Python版本就好了。输入如下命令查看：

    python -V

比如我这里看到的是：

    userMini:~ user$ python -V 
    Python 2.7.10
如果出现*-bash: python: command not found*类似的提示那么你应该访问[www.python.org](http://www.python.org)，官网上有针对各操作系统详细的安装方法。
#### 1.2 Windows
在Windows中安装Python也很容易访问Python官网[www.python.org](http://www.python.org)，下载对应操作系统的安装包，安装即可，但是注意安装选项中有一个**"Add to path"**要打上勾，安装完成后可以在cmd或者Powershell中输入`python -V`，如果看到打印出了当前Python的版本号，说明安装成功。
### 2 代码编写环境
刚开始的几天里，我们会一直在Python的交互式解释器中溜达，当代码量超过20行的时候，我们就需要一个更方便的编写环境了。为了能更好的熟悉Python的语法，开始阶段最好选一个简单的文本编辑器，比如Notepad++，Gedit，TextWrangler。先来看一下Python交互式解释器长什么样子，在终端或者cmd中输入`python`，就可以看到类似下面的内容：

    userMini:~ user$ python
    Python 2.7.10 (default, Oct 23 2015, 19:19:21) 
    [GCC 4.2.1 Compatible Apple LLVM 7.0.0 (clang-700.0.59.5)] on darwin
    Type "help", "copyright", "credits" or "license" for more information.
    >>>
注意末尾的'>>>'，这是解释器中默认的提示符。按照惯例此时应该打印"Hello World!"了

    >>>print('Hello World!')
可以小兴奋一下了，我们完成了每个大牛都要经历的事情。在学下面的内容之前，不得不提一下Python的道，试着在'>>>'提示符后输入`import this`，你看到了什么？