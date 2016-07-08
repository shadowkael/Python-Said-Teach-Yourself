##找到第一个匹配元素的位置
###描述

给定一个排序的整数数组（升序）和一个要查找的整数target，用`O(logn)`的时间复杂度找到target第一次出现的下标（从0开始），如果target不存在于数组中，返回-1。

元素的顺序可以改变，并且对新的数组不会有影响。
 
###测试用例：
####用例1：
输入数组A，值为[1, 2, 3, 3, 4, 5, 10]，和target的值:3

返回 2
####用例2：
输入数组A，值为[3, 4, 5, 8, 8, 8, 8, 10, 13, 14]，和target的值:8

返回 3
 
###典故：
 《编程珠玑》里有这么一段话：
 
我想到的一个数在1到100直接，你来猜猜看。50?太小了，75?太大了。如此游戏进行下去，知道你猜中我想的数为止。如果可以猜的范围在1到n之间，那么折半的猜测可以在**log<sub>2</sub>n**次之内猜中，n如果是1000，10次就可以完成，n如果是100万，最多20次就可以完成。
 
对于在有序数组内查找目标数这样的问题，和上面讲的这个例子很相似，具体到这个题二分查找的代码如下：
 
    def binary_search(nums, target):
        # write your code here
        # @param nums: The integer array
        # @param target: Target number to find
        # @return the first position of target in nums, position start from 0
        
        if nums:
            if target > nums[-1]:
                return -1
            elif target < nums[0]:
                return -1
            elif target == nums[0]:
                return 0
            elif target == nums[-1]:
                return len(nums) - 1
            else:
                left_edge = 0
                right_edge = len(nums) - 1
                while left_edge + 1 != right_edge:
                    divide = left_edge + (right_edge - left_edge) // 2
                    if target > nums[divide]:
                        left_edge = divide
                    elif target < nums[divide]:
                        right_edge = divide
                    else:
                        while True:
                            if nums[divide] == nums [divide-1]:
                                divide -= 1
                            else:
                                break
                        return divide
                else:
                    return -1
        else:
            return -1
    
注意刚开始的几个判断，这对于特殊情况而言可以大大缩短搜索过程，而且开销也并不大。