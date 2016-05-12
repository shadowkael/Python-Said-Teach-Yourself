##数组剔除元素后的乘积
###描述

给定一个整数数组A。

定义B[i] = A[0] * ... * A[i-1] * A[i+1] * ... * A[n-1]， 计算B的时候请**不要使用除法**。
 
 PS：说实话这个题目不是很看得懂，英文题目要更好理解一些：Product of Array Exclude Itself，意思就是B[i]的值是A中除去A[i]后，其它所有值的积。"Itself"这个词很重要……
 
 ###测试用例：
 输入 A = [1, 2, 3]， 返回 [6, 3, 2]
 
 ###思路：
 
 1、两层for循环，时间复杂度O(n<sup>2</sup>)，核心如下：
 
     B = list()
     for outer_index in range(len(A)):
         num = 1
         for inner_index, inner_value in enumerate(A):
             if inner_index == outer_index :
                 continue
             num *= inner_value
         B.append(num)
     retrun B
 
 2、想这样一个场景，我们要求的B中的每个数都是，原列表中去除它本身后，左右两部分相乘得来的。于是我们可以做这样的分治：
 
 + 计算所有可用的左右因子
 + 取相应左右因子的乘积
 + 存入列表B中
 
计算所有左右因子，这里使用并行遍历zip(A, reversed(A))，然后我们就得到了一个时间复杂度为O(n)的算法，空间上使用了两个额外的列表进行存储：

    B = list()
    length_A = len(A)
    left_case_list = list()
    right_case_list = list()
    # 并行遍历求出所有左右因子并存入对应列表（其实这里的多求了一个列表中全部数的乘积）
    for (left_item, right_item) in zip(A[:-1], reversed(A)):    # reversed(A)也可以用 A[::-1]代替
        if left_case_list and right_case_list:
            left_case_list.append(left_case_list[-1] * left_item)
            right_case_list.append(right_case_list[-1] * right_item)
        else:
            left_case_list.append(left_item)
            right_case_list.append(right_item)
    # 求出对应的左右因子乘积，并存入列表B
    for i in range(length_A):
        left_window = i - 1
        right_window = length_A - i - 2
        if left_window < 0:
            left_num = 1
        else:
            left_num = left_case_list[left_window]
        if right_window < 0:
            right_num = 1
        else:
            right_num = right_case_list[right_window]
        B.append(left_num * right_num)
    return B

注意，我们对列表A进行reverse操作的时候，可以用三种方法实现：

第一种，`A.reverse()`会改变A本身，返回值为None，也就是说它是操作A的一个动作

第二种，`reversed(A)`不会改变A，返回了一个列表反向迭代器(listreverseliterator)

第三种，`A[::-1]`，不会改变A，返回了一个步长为'-1'（逆序）A的切片，如果需要对原列表切片取逆的话，这是最省事的方案了，但是要注意A[start:to:step]，默认情况下step如果不写，值为1，也可以简化成A[start:to]这种。此外切片操作中start是包含的，to是不包含的，而且因为我们的step是'-1'所以，start要大于to。