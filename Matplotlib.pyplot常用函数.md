# 示例基础代码

*以下示例都是在如下代码基础上进行的*

```
import numpy as np
import matplotlib.pyplot as plt

x = [0, 1, 3, 5, 7, 9]
y = [0, 1.5, 3.7, 5.2, 7.3, 9.9]

plt.plot(x, y)
# 后面的示例代码插入在下方
# ------
plt.show()
```

# bar(x, height, width=0.8, bottom=None, color, tick_label)

```
import numpy as np
import matplotlib.pyplot as plt

N = 5
menMeans = (20, 35, 30, 35, 27)
womenMeans = (25, 32, 34, 20, 25)
ind = np.arange(N)   

width = 0.35   

plt.bar(ind, menMeans, width, tick_label=['A', 'B', 'C', 'D', 'E'],
 color='r', )
# Tips:plt.bar(tick_label=['A', 'B', 'C', 'D', 'E']) ，会被下一个柱状图覆盖掉
# Tips: plt.bar(color='r'), color也可以用fc替代
plt.bar(ind, womenMeans, width,bottom=menMeans, color='g')

plt.show()
```
# boxplot(x, sym='b+', showmeans=True, patch_artist=True, vert=False, meanline=False)

```
import numpy as np
import matplotlib.pyplot as plt

a = np.array([2, 2.5, 4, 6, 7, 8, 13, 17, 18, 34, 67])

plt.boxplot(a, sym='b+', showmeans=True, patch_artist=True,
 vert=True, meanline=False)
plt.show()
```

# figtext(x, y, s, alpha=0.9, rotation=70, visible=True， size='large')

```
import numpy as np
import matplotlib.pyplot as plt

x = np.array([-3, -2, 1, 2, 3, 5, 9, 12])
y =  x * 1.5
x1 = x/2
y1 = y /2
plt.stem(x, y, linefmt=':', bottom=2, label='test', use_line_collection=True)
plt.figtext(0.5, 0.7, 'bold italic', alpha=0.9, rotation=70, visible=True, size='small')
plt.legend()
plt.show()
```
# grid(axis='both', color='r', linewidth=2)

```
plt.grid(axis='y', color='r', linewidth=1)
```
# hist(x, bins=None, color=None, label=None)

```
import numpy as np
import matplotlib.pyplot as plt

height = np.array([168, 155, 182, 170, 173, 161, 
	155, 173, 176, 181, 166, 172, 170])
bins = np.arange(150, 191, 5)


plt.hist(height, bins, color='g', label='Height')
plt.legend()
plt.show()
```

# legend(title=None, loc='best')

```
import numpy as np
import matplotlib.pyplot as plt

x = np.arange(14)
y = np.sin(x / 2)

plt.step(x, y + 2, label='pre (default)')

plt.legend(title='Parameter where:', loc='upper right')
plt.show()
```

# pie(x, labels=None, colors=None, explode=None, autopct=None, pctdistance=0.6, labeldistance=1.1, startangle=None, radius=None, counterclock=True)

```
import matplotlib.pyplot as plt
import numpy as numpy
import matplotlib as mpl
mpl.rcParams['font.sans-serif'] = ['SimHei']

labels = ['房贷', '饮食', '出行', '教育']
data = [8000, 2000, 2000, 3000]
explode = [0.1, 0, 0, 0]

plt.pie(data, labels=labels, explode=explode, colors=['r', 'b', 'g', 'purple'],
	autopct='%1.2f%%', pctdistance=0.6, labeldistance=0.8,
	radius=1.5, counterclock=True, startangle=90)
plt.show()
```

# plot(x, y, label=None)

```
import numpy as np
import matplotlib.pyplot as plt

x = np.arange(14)
y = np.sin(x / 2)

plt.plot(x, y, label='plot example')
plt.legend()
plt.show()
```

# savefig(fname, dpi=None)

```
import numpy as np
import matplotlib.pyplot as plt
import matplotlib
matplotlib.use('agg')

# 定义数据
x = np.arange(0, 10, 0.1)
y = 0.05 * x ** 2

#绘制图像
plt.plot(x, y)

# 设置坐标轴
plt.xlabel('x data')
plt.ylabel('y data')

# 默认保存为png格式
plt.savefig(r'D:\test2', dpi= 100)
```

# scatter(x, y, s=None, alpha=None, label=None)

```
import matplotlib.pyplot as plt
import matplotlib as mpl

x = [1, 5, 3, 8, 6]
y = [7, 4, 2, 9, 10]
s = [20, 80, 30, 90, 150]
print(s)
plt.scatter(x, y, s, alpha=0.9, label='test')
plt.legend()
plt.show()
```


# show()

```
plt.show()
```

# stem([x,] y, linefmt=None, bottom=0, label=None, use_line_collection=False)

```
import numpy as np
import matplotlib.pyplot as plt

x = np.array([-3, -2, 1, 2, 3, 5, 9, 12])
y =  x * 1.5
x1 = x/2
y1 = y /2
plt.stem(x, y, linefmt=':', bottom=2, label='test', use_line_collection=True)
plt.legend()
plt.show()
```
# step(x, y, label=None)

```
import matplotlib.pyplot as plt

x = [0, 1, 2]
y = [3, 5, 7]

plt.step(x, y, label='plot1')
plt.legend()
plt.show()
```


# suptitle(t)

```
import numpy as np
import matplotlib.pyplot as plt

names = ['group_a', 'group_b', 'group_c']
values = [1, 10, 100]

plt.figure(figsize=(9, 3))

plt.subplot(131)
plt.bar(names, values)
plt.title('xxx')
plt.subplot(132)
plt.scatter(names, values)
plt.subplot(133)
plt.plot(names, values)
plt.suptitle('Categorical Plotting')
plt.show()
```
# text(x, y, s, bbox=dict(facecolor='r', alpha=0.9), fontsize=10)

```
import numpy as np
import matplotlib.pyplot as plt

N = 5
menMeans = (20, 35, 30, 35, 27)
womenMeans = (25, 32, 34, 20, 25)
ind = np.arange(N)   

width = 0.35   

plt.bar(ind, menMeans, width, tick_label=['A', 'B', 'C', 'D', 'E'],
 color='r', )

plt.text(2 + 0.35/2, 20, 'test for text',bbox=dict(facecolor='g', alpha=0.9),fontsize=10)

plt.show()
```

# title(label)

```
plt.title('Example for title()')
```

# xlabel(xlabel)

```
plt.xlabel('xlabel')
```

# ylim((bottom, top))

```
import numpy as np
import matplotlib.pyplot as plt

x = np.arange(14)
y = np.sin(x / 2)

plt.plot(x, y, label='plot example')
plt.xlim((-2, 20))
plt.legend()
plt.show()
```

# xticks(ticks, [labels])

```
import matplotlib.pyplot as plt
import matplotlib as matplotlib
import numpy as np

name = ['Languages', 'Mathematics', 'English']
c1 = np.array([81.3, 83, 87.1])
c2 = np.array([85.6, 87.4, 90])
c3 = np.array([78, 81.2, 86.1])

width = 0.4
x1 = [1, 3, 5]
x2 = [x1[i] + 0.4 for i in range(3)]
x3 = [x2[i] + 0.4 for i in range(3)]

plt.bar(x1, c1, label='class1', color='r', width=width)
plt.bar(x2, c2, label='class2', color='g', width=width)
plt.bar(x3, c3, label='class3', color='purple', width=width)
plt.xticks(x1, ['A', 'B', 'C'])
plt.xticks(x2, name, rotation=20)
plt.legend()
plt.show()
```
# ylabel(ylabel)

```
plt.ylabel('ylabel')
```

# ylim((bottom, top))

```
import numpy as np
import matplotlib.pyplot as plt

x = np.arange(14)
y = np.sin(x / 2)

plt.plot(x, y, label='plot example')
plt.ylim((-2, 20))
plt.legend()
plt.show()
```

# yticks(ticks, [labels]）

```
import matplotlib.pyplot as plt
import matplotlib as matplotlib
import numpy as np

name = ['Languages', 'Mathematics', 'English']
yname = ['Pass', 'Good', 'Excellent']
c1 = np.array([81.3, 83, 87.1])
c2 = np.array([85.6, 87.4, 90])
c3 = np.array([78, 81.2, 86.1])

width = 0.4
x1 = [1, 3, 5]
x2 = [x1[i] + 0.4 for i in range(3)]
x3 = [x2[i] + 0.4 for i in range(3)]
y1 = np.array([60, 80, 90])

plt.bar(x1, c1, label='class1', color='r', width=width)
plt.bar(x2, c2, label='class2', color='g', width=width)
plt.bar(x3, c3, label='class3', color='purple', width=width)

plt.xticks(x2, name)
plt.yticks(y1, yname)

plt.legend()
plt.show()
```