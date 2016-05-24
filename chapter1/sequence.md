## 序列家族
序列可以理解为一系列有序的元素(item)，比如上一节中我们讲的字符串，通过序号我们可以找到字符串中的每一个字符，序号是字符的位置官方的说法是索引(index)，序列的开始索引是0，看下面这个例子：
    >>> nums = [1,5,10,6,8,3,20,9]
    >>> nums[0], nums[2]
    (1, 10)
    >>> nums[-1]
    95
    >>> nums[8]
    ...
    IndexError: list index out of range
    >>> nums[-9]
    ...
    IndexError: list index out of range
看下图中这条蛇找元素的时候我们可以从蛇头（0）开始向右正数，或者向左负数，比如“6”的索引可以是`3`也可以是`-5`。

![](image/sequence_nums.png)


注意代码中最后的那两个`IndexError`，不要让索引值超过蛇的长度，那样会咬到尾巴。

### 列表
列表(list)是值的序列，在字符串中，这些值是字符，在列表中，值可以是任何类型，而且可以不必类型完全相同。创建列表最简单的方法是用方括号“[]”将元素括起来，比如：
    >>> ex_list0 = ['abc', 10, 20]
    >>> ex_list1 = [ex_list0, 'nested']
    >>> ex_list2 = list()
    >>> ex_list3 = []
    >>> print(ex_list0, ex_list1, ex_list2, ex_list3)
    ['abc', 10, 20] [['abc', 10, 20], 'nested'] [] []
第三行和第四行中的`[]`和`list()`可以建立一个空的列表。
#### 列表方法——修改
###### append()
append()方法会在原来的列表尾追加一个元素，方法和函数不同，通常需要以合适的“对象.方法名”来调用，比如：
    >>> list_1 = [9,8,0,5]
    >>> print(list_1.append(7))
    None
print()的结果是None，因为append()方法本身并没有返回值，只是追加了一个元素到列表尾。

##### pop()
pop的意思是“砰”功能和名字一样，pop()方法和append()的基本相反，不加参数的时候pop()方法“砰”掉列表尾的元素，如果加了参数（瞄准），就定向的“砰”。比如：
    >>> list_7 = ['a','c','v','z','t','y']
    >>> list_7.pop()
    'y'
    >>> list_7
    ['a', 'c', 'v', 'z', 't']
    >>> list_7.pop(2)
    'v'

##### insert()
当然我们也有可以定向追加元素的方法，比如：
    >>> nums = [0,1,2,3,4,5]
    >>> nums.insert(3, 'here')
    >>> nums
    [0, 1, 2, 'here', 3, 4, 5]
它接收两个参数，第一个是插入位置，第二个是插入内容。

##### remove()
我们除了可以用以用pop()方法做定向删除，还可以使用remove()做匹配删除，比如：
    >>> ex_list5 = ['I', 'love', 'dear', 'and', 'love', 'my', 'sketch']
    >>> ex_list5.remove('love')
    >>> ex_list5
    ['I', 'dear', 'and', 'love', 'my', 'sketch']
    >>> ex_list5.remove('heart')
    ...
    ValueError: list.remove(x): x not in list

它只会移除第一个匹配项，如果在列表中没有匹配内容会引发一个ValueError。

#### 列表方法——顺序
顺序中的方法其实也是对列表进行了修改，当然我们也有不改变原列表的办法，后面用到的时候再提
##### reverse()
reverse()方法会让原列表变成反向（好像从尾到头一样），比如：
    >>> nums = [1,5,10,6,8,3,20,9]
    >>> nums.reverse()
    >>> nums
    [9, 20, 3, 8, 6, 10, 5, 1]
    
####
    