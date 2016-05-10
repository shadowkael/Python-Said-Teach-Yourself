##字符串

Python中的字符串需要用单引号或者双引号包裹里来，它们的效果是一样的，但一定要配对，比如：`'abc'`，`"吃了没?"`。
 如果字符串中包含引号需要用`\`进行转义，同样如果字符串中包含`\`也需要转义即：`"\\"`
    >>> 'spam eggs'  # 单引号包裹方式
    'spam eggs'
    >>> 'doesn\'t'  # 使用\进行转义
    "doesn't"
    >>> "doesn't"  # 双引号包裹的方式
    >>> '"Yes," he said.'
    '"Yes," he said.'
    >>> "\"Yes,\" he said."
    '"Yes," he said.'
    >>> '"Isn\'t," she said.'
    '"Isn\'t," she said.'

当然这些都是单行字符串，可以打开你的文本编辑器了