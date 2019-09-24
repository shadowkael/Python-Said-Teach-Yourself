## 练手小游戏：tutle绘图
### 图形化背景
谈到图形化，就必须要谈到一个人，Ivan Sutherland，计算机图形学之父和虚拟现实之父
- 1963年，MIT博士学位
- 1960年，加州理工大学电气工程硕士学位
- 1959年，卡耐基梅隆大学电气工程学士学位
取得博士学位以后，Ivan离开MIT参加了军队，在安全部门工作，曾参与过雷达和红外跟踪系统的研制。2014年到国内交流，当时做了异步电路方面的研究报告，他有过这样一句名言：

**And so it seems to me the most important thing that adults need to do with young people is not squash their curiosity, but to help them exercise their curiosity and learn how to use it**

### 十行代码
tutle是Python自带的一个绘图包，可以定义画笔的笔触、颜色、方向、步长、绘图速度等
下面的十行代码是个美丽的魔法，尝试为每一行代码增加一句注释。


```
import turtle 
colors = ['red', 'purple', 'blue', 'green', 'yellow', 'orange']
t = turtle.Pen()
t.speed(0)
turtle.bgcolor('black')
for x in range(360):
	t.pencolor(colors[x%6])
	t.width(x/100+1)
	t.forward(x)
	t.left(59)
```

