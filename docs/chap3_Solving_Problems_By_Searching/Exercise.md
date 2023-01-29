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
>1. 对于 $ 0 < w < 2 $ 时，是完全的
>2. $w = 0$得到 $f(n) = 2g(n)$ ，行为完全类似于均匀代价搜索
>3. $w = 1$得到 $ A^* $ 搜索
>4. $w = 2$得到 $ f(n) = 2h(n) $ ,是贪心最佳优先搜索

# Exercise 32

>原题目：
>Consider the unbounded version of the regular 2D grid shown in . The start state is at the origin, (0,0), and the goal state is at (x,y).
>1. What is the branching factor b in this state space?
>2. How many distinct states are there at depth k(for k>0)？
>3. What is the maximum number of nodes expanded by breadth-first tree search?
>4. What is the maximum number of nodes expanded by breadth-first graph search?
>5. Is h=|u−x|+|v−y| an admissible heuristic for a state at (u,v)? Explain.
>6. How many nodes are expanded by $A$ graph search using h?
>7. Does ℎ remain admissible if some links are removed?
>8. Does ℎ remain admissible if some links are added between nonadjacent states?



>题目翻译：
>考虑所给的常规二维网格的无界版本。开始状态位于原点（0， 0），目标状态位于（x, y）
>1. 这个状态空间中的分支因子b是什么？
>2. 在深度k处有多少不同的状态（对于k＞0)
>3. 广度优先树搜索扩展的最大节点数是多少？
>4. 广度优先图搜索扩展的最大节点数是多少？
>5. $h=|u−x|+|v−y|$是（u，v）处状态的可接受启发式吗？请做出解释
>6. 使用h的$A^*$图搜索可扩展多少个节点(原题目为A搜索，但找的资料上显示为$A^*$)
>7. ℎ 如果删除了某些链接，是否仍然可以接受
>8. ℎ 如果在非相邻状态之间添加了一些链接，是否仍然保持允许


>答案：
>1. 分支因子为4（每个位置的邻居数）
>2. 在深度k处有4k个不同的状态
>3. 
>4.
>5. 可以，这是曼哈顿距离度量方法，并且只能在网格上移动
>6. - （未找到相关资料）
>7. 是的;删除链接可能会导致绕路，这需要更多的步骤，所以h是低估的。
>8. 不是的;非相邻状态的链接可以减少一些实际路径长度，从而导致不在处于低估状态。


# Exercise 33

>原题目：
>n vehicles occupy squares (1,1) through (n,1) (i.e., the bottom row) of an n×n grid. The vehicles must be moved to the top row but in reverse order; so the vehicle ithat starts in (i,1) must end up in (n−i+1,n). On each time step, every one of the n vehicles can move one square up, down, left, or right, or stay put; but if a vehicle stays put, one other adjacent vehicle (but not more than one) can hop over it. Two vehicles cannot occupy the same square.
>1. Calculate the size of the state space as a function of n.
>2. Calculate the branching factor as a function of n.
>3. Suppose that vehicle i is at (xi,yi); write a nontrivial admissible heuristic hi for the number of moves it will require to get to its goal location (n−i+1,n), assuming no other vehicles are on the grid.
>4. Which of the following heuristics are admissible for the problem of moving all n vehicles to their destinations? Explain.
> - $\sum^{n}_{i=1}{h_i}$
> - $max(h_1, ... , h_n)$
> - $min(h_1, ... , h_n)$



>题目翻译：
>n辆车占据n×n网格的正方形（1,1）到（n，1）（即，最下面的一行）。车辆必须移到最上面一排，但顺序相反；因此，在（i，1）开始的车辆必须在（n−i+1，n）结束。在每个时间步长上，n辆车中的每一辆都可以向上、向下、向左或向右移动一个正方形，或保持不变；但如果一辆车停在原地，另一辆相邻的车（但不超过一辆）可以跳过它。两辆车不能占用同一个广场。
>1. 根据n计算状态空间的大小
>2. 计算n作为函数的分支因子
>3. 假设车辆i位于（xi，yi)同时网格上没有其他车辆，为到达目标位置（n−i+1，n）所需的移动次数编写一个非平凡的可接受启发式hi（i为下标）
>4. 对于将所有n辆车移至目的地的问题，以下哪种启发式方法是可接受的？解释
> - $\sum^{n}_{i=1}{h_i}$
> - $max(h_1, ... , h_n)$
> - $min(h_1, ... , h_n)$

>答案：
>1. $n^{2n}$
>2. $5^n$
>3. 曼哈顿距离，即$|(n - i + 1) - x_i| + |n - y_i|$,这对一辆车来说是正确的
>4. 只有第三个是可以接受的。这个解释并不简单，因为它需要两个观察结果。首先，设给定解中的W是所有车辆在其关节轨迹上移动的总距离;也就是说，对于每辆车，将所采取的所有步骤的长度相加。我们有$W \geq \sum^{ }_{h_i }{h_i} \geq n * min{h_1, ... h_n}$.其次，我们每一步可以完成的总量≤n。(注意，对于每一辆跳跃2的车，另一辆车必须保持不变(移动0)，因此每一步的总功以n为界。)因此，完成所有工作至少需要n·min{h1，…，hn}/n = min{h1，…, hn}步骤。

# Exercise 34

>原题目：
>Consider the problem of moving k knights from k starting squares s1,…,sk to k goal squares g1,…,gk on an unbounded chessboard, subject to the rule that no two knights can land on the same square at the same time. Each action consists of moving *up to* k knights simultaneously. We would like to complete the maneuver in the smallest number of actions.
>1. What is the maximum branching factor in this state space, expressed as a function of k?
>2. Suppose hi is an admissible heuristic for the problem of moving knight i to goal gi by itself. Which of the following heuristics are admissible for the k-knight problem? Of those, which is the best?
> - $min(h_1, ... ,h_k)$
> - $max(h_1, ... , h_k)$
> - $\sum^{k}_{i=1}{h_i}$
>3. Repeat (b) for the case where you are allowed to move only one knight at a time.

>题目翻译：
>考虑在无界棋盘上将k个骑士从k个起始方块s1，…，sk移动到k个目标方块g1，…，gk的问题，前提是两个骑士不能同时降落在同一个方块上。每个动作包括同时移动最多k个骑士。我们希望以最少的动作达到目标。
>1. 这个状态空间中的最大分支因子是多少，表示为k的函数
>2. 假设hi是将骑士i单独移动到目标gi的问题的可接受启发式。以下哪种启发式方法可用于k骑士问题？其中，哪一个是最好的？
> - $min(h_1, ... ,h_k)$
> - $max(h_1, ... , h_k)$
> - $\sum^{k}_{i=1}{h_i}$
>3. 对于一次只能移动一名骑士的情况，重复（b）

>答案：
>1. 9k。对于k个骑士，除了完全不移动的可能性，我们还有8种移动中的一种;每个动作为每个骑士执行这9个选择中的一个(除非某些选择因落在同一个方格上而发生冲突)，所以有9k个动作。
>2. 1和2是可以的。如果$h_i$是精确的，那么2对于骑士可以落在同一个方格上的松弛问题是精确的。$h_i$是可容许的，因此不大于确切的值，因此2是可容许的。1不大于2，因此1是可接受的。3不可信。例如，如果每个$g_i$距离$s_i$只有一步，那么(iii)返回k，而最优解的代价是1。2决定了1，所以它必须一样好或者更好。所以2最好
>3. （未找到相关资料）

