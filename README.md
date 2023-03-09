**寻路算法 位于path_basic.py文件 第30行,第74行，分别为获取最短与最长路径。** 
**自动寻路 位于pathfinding.py文件 第22行**  

# 贪吃蛇项目解析

## 文件介绍
- config.json
> 存储配置文件，可以按需求更改参数，必须与main.py位于同一目录下
- drawer.py
> 定义了Drawer, SnakeDrawer, FruitDrawer三个类，用于绘画图形。
- food.py
> 读取了config的信息，在食物被吃掉后生成新的水果。
- main.py
> 主程序，运行即为贪吃蛇自动寻路版本。
- path_basic.py
> 本项目的寻路算法实现相关代码。
- snake.py
> 构建Snake类，实现蛇的功能。
- pathfinding.py
> 本项目的自动寻路算法实现相关代码。

## 执行方法
- 配置需要的环境之后运行main.py

## 算法介绍

### 寻路算法
在path_basic.py中采用了广度优先搜索算法得到最短路径，其中
- shortest_path为采用广度优先搜索算法实现的最短路径
- longest_path为最长路径，通过无限拓展最短路径得到



### 自动寻路
实现自动寻路功能时，采用了改良的贪心算法，具体实现过程如下
- 搜索蛇头到食物的最短路径，称之为决策A
- 假设蛇按此路径达到了食物后，查看蛇是否有路径到达蛇尾，如有即可认为处于安全状态，便可以执行决策A
- 假设蛇假设蛇按此路径达到了食物后，没有路径到达蛇尾，认为蛇吃了食物后无法存活，便不执行决策A  
实现自动寻路的循环在main.py中，pathfinding.py中实现了如何确定从当前位置到下一食物位置的路径。