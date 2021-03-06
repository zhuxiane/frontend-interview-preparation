###链表

**应用场景**：如果要解决的问题里面需要很多快速查询，链表可能并不适合；如果遇到的问题中，数据的元素个数不确定，而且需要经常进行数据的添加和删除，那么链表会比较合适。而如果数据元素大小确定，删除插入的操作并不多，那么数组可能更适合。



###栈

应用场景：在解决某个问题的时候，只要求关心最近一次的操作，并且在操作完成了之后，需要向前查找到更前一次的操作。



###队列

应用场景：直观来看，当我们需要按照一定的顺序来处理数据，而该数据的数据量在不断地变化的时候，则需要队列来帮助解题。在算法面试题当中，广度优先搜索（Breadth-First Search）是运用队列最多的地方，我们将在第 06 课时中详细介绍。



双端队列

应用场景：双端队列最常用的地方就是实现一个长度动态变化的窗口或者连续区间，而动态窗口这种数据结构在很多题目里都有运用。



###树

在面试中常考的树的形状有：普通二叉树、平衡二叉树、完全二叉树、二叉搜索树、四叉树（Quadtree）、多叉树（N-ary Tree）。



树的遍历

掌握递归和非递归写法



### 优先队列

###### 应用场景

从一堆杂乱无章的数据当中按照一定的顺序（或者优先级）逐步地筛选出部分乃至全部的数据。

**举例**：任意一个数组，找出前 k 大的数。

**解法 1**：先对这个数组进行排序，然后依次输出前 k 大的数，复杂度将会是 O(nlogn)，其中，n 是数组的元素个数。这是一种直接的办法。

**解法 2**：使用优先队列，复杂度优化成 O(k + nlogk)。

当数据量很大（即 n 很大），而 k 相对较小的时候，显然，利用优先队列能有效地降低算法复杂度。因为要找出前 k 大的数，并不需要对所有的数进行排序。



优先队列的本质是一个二叉堆结构。堆在英文里叫 Binary Heap，它是利用一个数组结构来实现的完全二叉树。换句话说，优先队列的本质是一个数组，数组里的每个元素既有可能是其他元素的父节点，也有可能是其他元素的子节点，而且，每个父节点只能有两个子节点，很像一棵二叉树的结构。

 

牢记下面优先队列有三个重要的性质。

1. 数组里的第一个元素 array[0] 拥有最高的优先级别。

2. 给定一个下标 i，那么对于元素 array[i] 而言：

- 它的父节点所对应的元素下标是 (i-1)/2
- 它的左孩子所对应的元素下标是 2×i + 1
- 它的右孩子所对应的元素下标是 2×i + 2



无论是添加新的数据还是取出堆顶的元素，都需要 O(logk) 的时间。

初始化堆的时间复杂度是O(n)



### 图

**必会知识点**

- 图的存储和表达方式：邻接矩阵（Adjacency Matrix）、邻接链表（Adjacency List）
- 图的遍历：深度优先、广度优先
- 二部图的检测（Bipartite）、树的检测、环的检测：有向图、无向图
- 拓扑排序
- 联合-查找算法（Union-Find）
- 最短路径：Dijkstra、Bellman-Ford



### 前缀树

###### 应用场景

前缀树被广泛地运用在字典查找当中，也被称为字典树。



###### 实现

前缀树最基本的操作就是两个：创建和搜索。

 

**1. 创建**

- 遍历一遍输入的字符串，对每个字符串的字符进行遍历
- 从前缀树的根节点开始，将每个字符加入到节点的 children 字符集当中。
- 如果字符集已经包含了这个字符，则跳过。
- 如果当前字符是字符串的最后一个，则把当前节点的 isEnd 标记为真。

由上，创建的方法很直观。

 

前缀树真正强大的地方在于，每个节点还能用来保存额外的信息，比如可以用来记录拥有相同前缀的所有字符串。因此，当用户输入某个前缀时，就能在 O(1) 的时间内给出对应的推荐字符串。

 

**2. 搜索**

与创建方法类似，从前缀树的根节点出发，逐个匹配输入的前缀字符，如果遇到了就继续往下一层搜索，如果没遇到，就立即返回。





