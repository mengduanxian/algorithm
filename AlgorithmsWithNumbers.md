# Algorithms with Numbers

* The sum of any three single-digit numbers is at most two digits long. 
* This rule holds not just in decimal but in any base $b≥2$. 
* How many digits are needed to represent the number N>0 in base b?
* With k digits in base b we can express numbers up to $b^k-1$.
  * By solving for k, we find that $\lceil log_{b}(N+1)\rceil$ digits are needed to write $N$ in base $b$.
* e.g. $999=10^3 -1$
* How much does the size of a number change when we change bases?
  * Recall the rule for converting logarithms from base a to base b: $log_{b}{N} = log_{a}{N}/log_{a}{b}$.
  * So the size of integer $N$ in base $a$ is the same as its size in base $b$, times a constant factor $log_{a}{b}$. 
  * In big-O notation, therefore, the base is irrelevant, and we write the size simply as $O(logN)$. 
* Running time for the addition algorithm
  * Suppose $x$ and $y$ are each $n$ bits long; 
  * Then the sum of $x$ and $y$ is $n+1$ bits at most, and each individual bit of this sum gets computed in a fixed amount of time. 
  * The total running time for the addition algorithm is therefore of the form $c_0+c_1n$, where $c_0$ and $c_1$ are some constants; in other words, it is *linear*. 
  * Instead of worrying about the precise values of $c_0$ and $c_1$, we will focus on the big picture and denote the running time as $O(n)$.
  * Is there a faster algorithm? For addition, in order to add two $n$-bit numbers we must at least read them and write down the answer, and even that requires $n$ operations. 
* 
