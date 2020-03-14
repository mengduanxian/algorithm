# Primality Testing

### Fermat's little theorem

If $p$ is prime, then for every $1≤a<p$, $a^{p-1} \equiv 1$ mod $p$.

```pseudocode
// an algorithm for testing primality
function primality(N)
Input: Positive integer N
Output: yes/no

Pick a positive integer a<N at random
if a^(N-1) ≡ 1 (mod N):
	return yes
else: 
	return no
```

注意：

* The problem is that Fermat's little theorem is not an if-and-only-if condition; it doesn't say what happens when $N$ is not prime.
* In fact, it is possible for a composite number $N$ to pass Fermat's test. 
  * e.g. $341 = 11 ·31$, $2^{341} \equiv 1$ mod $341$ 
* so rather than fixing an arbitrary value of $a$ in advance, we should choose it randomly from $\{1, ..., N-1\}$.
* It turns out that certain extremely rare composite numbers $N$, called **Carmichael numbers**, pass Fermat's test for all $a$ relatively prime to N. But they are rare. 

### Lemma

If $a^{N-1} \not\equiv 1$ mod $N$ for some $a$ relatively prime to $N$, then it must hold for at least half the choices of $a<N$.



Ignoring Carmichael numbers, we can assert: (Pr = Algorithm returns yes when $N$ is prime)

​	If $N$ is prime, then $a^{N-1}\equiv 1$ mod $N$ for all $a<N$. ($Pr = 1$.)

​	If $N$ is not prime, then $a^{N-1}\equiv 1$ mod $N$ for at most half the values of $a<N$. ($Pr≤1/2$)





### Primality Testing with low error probability

```pseudocode
function primality2(N)
Input: Positive integer N
Output: yes / no

Pick positive integers a1, a2, ..., ak < N at random
if (ai)^(N-1)≡1 (mod N) for all i=1,2,...,k:
	return yes
else:
	return no
```

再进一步：

If $a^{N-1}\equiv 1$ mod $N$, we conduct a little follow-up test:

* Write $N-1$ in the form $2^tu$.
* get the sequence: $a^{u}$ mod $N$, $a^{2u}$ mod $N$,...,  $a^{2^tu}$ mod $N$.
* somewhere in the preceding sequence, we ran into a $1$ for the first time. If this happened after the first position (that is, if  $a^{u}$ mod $N \ne 1$), and if the preceding value in the list is not $-1$ mod $N$, then we declare $N$ composite.
* It is a non-trivial square root of $1$ modulo $N$: a number that is not $\pm1$ mod $N$ but that when squared is equal to $1$ mod $N$. Such a number can only exist if $N$ is composite. 