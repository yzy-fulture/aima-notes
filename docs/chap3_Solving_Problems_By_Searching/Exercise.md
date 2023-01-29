# 第三章习题

# Exercise 1
> Explain why problem formulation must follow goal formulation.

# Exercise 2
> Give a complete problem formulation for each of the following problems. Choose a formulation that is precise enough to be implemented.
> 1. There are six glass boxes in a row, each with a lock. Each of the first five boxes holds a key unlocking the next box in line; the last box holds a banana. You have the key to the first box, and you want the banana.
> 2. You start with the sequence ABABAECCEC, or in general any sequence made from A, B, C, and E. You can transform this sequence using the following equalities: AC = E, AB = BC, BB = E, and E$x$ = $x$ for any $x$. For example, ABBC can be transformed into AEC, and then AC, and then E. Your goal is to produce the sequence E.
> 3. There is an $n \times n$ grid of squares, each square initially being either unpainted floor or a bottomless pit. You start standing on an unpainted floor square, and can either paint the square under you or move onto an adjacent unpainted floor square. You want the whole floor painted.
> 4. A container ship is in port, loaded high with containers. There 13 rows of containers, each 13 containers wide and 5 containers tall. You control a crane that can move to any location above the ship, pick up the container under it, and move it onto the dock. You want the ship unloaded.


# Exercise 27

>原题目：
>Trace the operation of A search applied to the problem of getting to Bucharest from Lugoj using the straight-line distance heuristic. That is, show the sequence of nodes that the algorithm will consider and the f, g, and h score for each node.

>题目翻译：
>使用直线距离启发式函数，追踪应用于从Lugoj到Bucharest的问题的A * 搜索操作。也就是说，显示算法将考虑的节点序列以及每个节点的f、g和h得分（在第三版习题中为A * 搜索）


>答案参考https://www.csie.ntu.edu.tw/~ai2007s/hw/hw02_s.pdf（图片下等号左边为f， 右边第一个为g，第二个为h


# Exercise 30

>原题目：
>Accurate heuristics don’t necessarily reduce search time in the worst  case. Given any depth d, define a search problem with a goal node at depth d, and write a heuristic function such that $|h(n)−h\*(n)|≤O(logh\*(n))$ but A∗ expands all nodes of depth less than d.

>题目翻译：
>在最坏的情况下，精确的启发式并不一定会减少搜索时间。给定任意深度d，定义一个目标节点位于深度d的搜索问题，并编写一个启发函数，使得$|h(n)−h\*(n)|≤O(logh\*(n))$，但A*扩展所有深度小于d的节点。

>(暂未找到相关参考资料)

# Exercise 31

>原题目：
>The **heuristic path algorithm** [Pohl:1977](https://aimacode.github.io/aima-exercises/search-exercises/#) is a best-first search in which the evaluation function is f(n)=(2−w)g(n)+wh(n). For what values of w is this complete? For what values is it optimal, assuming that ℎ is admissible? What kind of search does this perform for w=0, w=1, and w=2?

>题目翻译：
>启发式路径算法是最佳的第一搜索算法，其中评估函数为$f(n) = (2 - w)g(n) + wh(n)$.对于w的什么值，这是完全的？假设ℎ 是可接受的，对于哪些值是最优的？对于w=0、w=1和w=2，这将执行何种搜索？


>答案：
>1. 对于$ 0 < w < 2 $时，是完全的
>2. $w = 0$得到 $f(n) = 2g(n)$ ，行为完全类似于均匀代价搜索
>3. $w = 1$得到$A^*$搜索
>4. $w = 2$得到$f(n) = 2h(n)$,是贪心最佳优先搜索



