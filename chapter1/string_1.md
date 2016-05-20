##字符串
### 字符串是什么鬼

Python中的字符串需要用单引号或者双引号包裹里来，它们的效果是一样的，但一定要配对，比如：`'abc'`，`"吃了没?"`。
 如果字符串中包含引号需要用`\`进行转义，同样如果字符串中包含`\`也需要转义即：`"\\"`
    >>> 'spam eggs'    # 单引号包裹方式
    'spam eggs'
    >>> 'doesn\'t'    # 使用\进行转义
    "doesn't"
    >>> "doesn't"    # 双引号包裹的方式
    >>> '"Yes," he said.'
    '"Yes," he said.'
    >>> "\"Yes,\" he said."
    '"Yes," he said.'
    >>> '"Isn\'t," she said.'
    '"Isn\'t," she said.'

这些都是单行字符串，当然还有多行的写法。多行字符串需要用三个单号或者三个双引号包裹起来，比如：
    >>> abc = '''My name is Kael    # 敲回车换行，进行多行编写
    ... I like play Dota'''
    >>> abc

然后敲下回车，交互环境返回:'My name is Kael**\n**I like play Dota'，注意看我们的多行字符串里多出一个"\n"来，它表示换行，再输入`print(abc)`就可以看到字符串abc的打印效果了。
#### 什么情况？
看下面这段代码：
    >>> abc = "Try to modified "
    >>> abc[0] = "J"
    TypeError: object does not support item assignment
交互环境告诉我们不能对字符串abc进行修改
    >>> abc
    'Try to modified'
    >>> abc = "What?"
    >>> abc
    'What?'
又可以“修改”了，怎么回事？第一种情况是因为我们试图修改一个immutable（不可变）的值，在Python中值其实都是不能修改的，比如我们不能把2改变成3，但是看下面一个，我们可以对变量名再次赋值，变量abc的值变为'What?'，而之前的'Try to modified'这个值会被自动回收掉。

### 使用方法
#### 字符串连接
Python中可以进行多重赋值，比如下面代码中的三个变量，然后对其进行连接
    >>> a, b, c = '高', '成', '龙'
    >>> name = a + b + c
    >>> name
    '高成龙'
    
有没有很方便？但是大规模的使用上面的字符串连接方法并不高效，高效的方式是使用字符串的格式化比如：
    >>> birthday = 'Oct 20th'
    >>> name = 'dear'
    >>> sentence = 'My {}\'s birthday is {}.'.format(name, birthday)
    >>> sentence
    'My dear's birthday is Oct 20th.'

注意第三行我们在字符串内又使用了单引号，需要加入`\`，对它进行转义，此外`{}`内可以加上数字来表示使用后面`format`中的第几个参数，比如：
    >>> print('I like {1} than {0}'.format('apple', 'pear'))
    I like pear than apple
#### 大写 and 小写
upper()和lower()是一组功能相反的方法，upper()方法返回字符串的全部大写结果，lower()返回全部小写结果。还有一个更炫酷的方法title()，比如：
    >>> sentence = 'My dear's birthday is Oct 20th.'
    >>> sentence.title()
    "My Dear's Birthday Is Oct 20th.
如果你刚好需要显示一个英文际题，That is.

#### 替换 or 转换
replace()方法返回某字符串中所有匹配内容被替换之后得到的字符串：
    >>> 'I like swim and sketch'.replace('e','ed')
    'I liked swim and skedtch'

translate()方法只处理单个字符，它的优势在于可以同时进行多个替换，比如我们想要把一个字符串中的所有`'a'->'c'`，所有`'b'->'X'`，这样场景就可以使用translate()转换。具体使用如下：
    >>> table = str.maketrans('gao', 'GOD')
    >>> 'gao like eating grape'.translate(table)
    'GOD like GrOpe'
#### 脱衣和她的姐妹们
strip()方法返回去除字符串两侧的指定参数(好像脱去了衣服一样)，你也可以用lstrip()或者rstrip()来指定只脱一边的，不加参数，默认脱掉空格比如：
    >>> '   I love Ven Gogh\'s painting     '.strip()
    "I love Ven Gogh's painting"
    >>> '--No-module-named-str!--'.strip('*!')
    '--No-module-named-str!--'    # 第一个要脱的没找到，第二个也不会去找
    >>> '--No-module-named-str!--'.strip('-!')
    'No-module-named-str'    # 两个参数都会脱去
    
#### 合并 and 分割
字符串的内建方法：join()（合并）和split()（分割）也是一组相反的方法，同时它们的使用频率相当高。

##### join()
    >>> a = [1,2,7,8,4,3,6,10]    # 定义一个列表，简单理解就是由[]括起来的内容
    >>> sep = '+'
    >>> sep.join(a)
    Traceback (most recent call last):
      File "<stdin>", line 1, in <module>
    TypeError: sequence item 0: expected str instance, int found
    
最后一行，交互环境给了我们一个`TypeError`注意使用join()方法合并的必须是`str`，继续输入下面的代码：
    >>> a = [str(i) for i in a]    # 等号右侧的叫做列表解析
    >>> print(sep.join(a))
    1+2+7+8+4+3+6+10
    >>> eval(sep.join(a))    # eval()方法可以计算一个str表达式的值
    41
在这里我们的代码中出现了一些新的内容，比如列表，列表解析以及eval()函数，这里不用深究，下一节中我们会进一步学习。
##### split()
如果我们有一句话，想取出其中的每一个单词就可以用：
    >>> sentence = "My name is Chanlone Gogh"
    >>> sentence.split()
    ['My', 'name', 'is', 'Chanlone', 'Gogh']    # 结果得到了一个由每个单词组成的列表
split()函数接受一个str类的参数，如果像上例一样不指定会以'空格'进行分割，并返回一个列表。再看下面这个URL的处理：
    >>> 'gaosir.com/python/index'.split('/')
    ['gaosir.com', 'python', 'index']