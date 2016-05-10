##字符串

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