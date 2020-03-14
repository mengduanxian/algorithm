# Big-O Notation

##### 算法分析

两个主要方面：

* 正确性： 算法功能与问题要求一致？需要数学证明。
* 成本： 运行时间 + 所需存储空间 （时间比空间更重要）

* need to be precise, but not overly detailed. 
* express running time by counting the number of basic computer steps, as a function of the size of the input.

## More precise definition of big-O notation:

* 定义： Let f(n) and g(n) be functions from N^+^ → R^+^. We say that $f=O(g)$ (which means that "f grows no faster than g"), if there is a constant c>0, such that $f(n)≤cg(n)$. 
  * Think of $f(n)$ and $g(n)$ as the running times of two algorithms on input n. 
  * this means that $f$ grows no faster than $g$. 
  * 大O是个渐进上限
* 举个例子：
  * $f_1(n)=n^2$ 
  * $f_2(n)=2n+20$ 
  * $f_2$ is better as $n$ grows ($n>5$ will do)
  * Big-O notation captures this seniority: $f_2=O(f_1)$ because $f_2(n)/f_1(n) = (2n+20)/n^2≤22 \forall n$,
  * But $f_1\ne O(f_2)$, since $f_1(n)/f_2(n)=n^2/(2n+20)<an$, get arbitrarily large, so no constant $c$ will make the definition work. 
* O(·) can be viewed as the analog of the relation "≤".
* we can define the analogs of "≥" and "=" as follows: 
  * $f=\Omega(g)$ means $g=O(f)$ - 大$\Omega$是个渐进下限
  * $f=\Theta(g)$ means $f=O(g)$ and $f=\Omega(g)$.
* Some commonsense rules that help simplify functions by omitting dominated terms: 
  1. Multiplicative constants can be omitted: $14n^2$ becomes $n^2$.
  2. $n^a$ dominates $n^b$ if $a>b$: e.g. $n^2$ dominates $n$.
  3. Any exponential dominates any polynomial: $3^n$ dominates $n^5$ (it even dominates $2^n$).
  4. Likewise, any polynomial dominates any logarithm: n dominates $(log n)^3$. This also means, for example, that $n^2$ dominates $nlogn$.
* 注意：不是说常数就没什么影响。程序员和算法开发人员非常重视常数，甚至通宵熬夜为了使一个算法比以前快2倍。



* $T_A(P) = 算法A求解问题实例P的计算成本$
  * 考察具体实例意义不大，毕竟可能出现的问题实例太多
  * 如何归纳概括？划分等价类
  * 观察：问题实例的*规模*，往往是决定计算成本的主要因素
  * 通常：规模接近，计算成本也接近；规模扩大，计算成本也上升。

* 令$T_A(n) = $ 用算法A求解某一问题规模为n的实例，所需的计算成本。
  * 讨论特定算法A(及其对应的问题)时，简记作$T(n)$.
* 观察：同一问题等规模的不同实例，计算成本不尽相同，甚至有实质差别。
* 例如：在平面上的n个点中，找到所成三角形面积最小的三个点以蛮力算法为例，最坏的情况下需枚举所有C(n,3)种组合，但运气好的话，第一次就能找到在同一直线上的三个点，此时三角形面积为0，而面积无法为负，故此时最小。
* 既然如此，稳妥起见，取T(n) = **max** {T(P) | |P|=n}，即：在规模同为n的所有实例中，只关注最坏（成本最高）者

##### 同一问题通常有多种算法，如何评判其优劣？

* 实验统计是最直接的方法，但足以准确反映算法的真正效率吗？不足够！
  * 不同的算法，可能更适应于不同规模的输入
  * 不同的算法，可能更适应于不同类型的输入
  * 同一算法，可能由不同程序员、用不同程序语言、经不同编译器实现
  * 同一算法，可能实现并运行于不同的体系结构、操作系统
* 为了给出客观的评价，需要抽象出一个理想的平台或模型
  * 不再依赖于上述种种具体的因素
  * 从而直接而准确地描述、测量并评价算法

















