# Big-O Notation

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























