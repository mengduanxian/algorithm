# Algorithms with Numbers - addition algorithm

### How many digits are needed to represent the number N>0 in base b?

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

### Running time for the addition algorithm

* Suppose $x$ and $y$ are each $n$ bits long; 
* Then the sum of $x$ and $y$ is $n+1$ bits at most, and each individual bit of this sum gets computed in a fixed amount of time. 
* The total running time for the addition algorithm is therefore of the form $c_0+c_1n$, where $c_0$ and $c_1$ are some constants; in other words, it is *linear*. 
* Instead of worrying about the precise values of $c_0$ and $c_1$, we will focus on the big picture and denote the running time as $O(n)$.
* Is there a faster algorithm? For addition, in order to add two $n$-bit numbers we must at least read them and write down the answer, and even that requires $n$ operations. 
* Why $O(n)$ operation? Isn't binary addition something that computers today perform by just one instruction?
  * It is certainly true that in a single instruction we can add integers whose size in bits is within the *word length* of today's computer - 32 perhaps. But, it is often useful and necessary to handle numbers much larger than this, perhaps several thousand bits long. Adding and multiplying such large numbers on real computers is very much like performing the operations bit by bit. 
  * When we want to understand algorithms, it makes sense to study even the basic algorithms that are encoded in the hardware of today's computers. In doing so, we shall focus on the *bit complexity* of the algorithm, the number of elementary operations on individual bits - because this accounting reflects the amount of hardware, transistors and wires, necessary for implementing the algorithm. 

### Multiplication and division

