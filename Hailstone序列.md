# Hailstone序列

<img src="F:/gitRepo/algorithm/img/hailstone.png" />

Hailstone序列不是单调的，一会升一会降，像冰雹一样，也叫冰雹序列，到现在为止还未证明出该序列是否为有穷的。

* 若$n$为偶数，则$n$变为原来一半
* 若$n$为奇数，则$n$变原来3倍加1，增大

```c
int hailstone(int n){ //计算序列Hailstone(n)的长度
    int length = 1; //从1开始，以下按定义逐步递推，并累计步数，直至n=1
    while (1<n){
       (n%2)? n=3*n+1: n/=2;
        length++;
    }
    return length; //返回|Hailstone(n)|
}
```

```java
public class Main {
    private static int hailstone(int n){
        System.out.print("Hailstone(" + n + ") = {");
        int length = 1;
        while (n>1){
            System.out.print(n + ", ");
            if((n%2==1)){
                n=n*3+1;
            }else {
                n /= 2;
            }
            length++;
        }
        System.out.println(n+"}\n");
        return length;
    }

    public static void main(String[] args){
        int n = hailstone(27);
        System.out.println("Hailstone序列长度 = " + n);
    }
}
```



* $Hailstone(42) = \{42, 21, 64, 32, ..., 1\}$

* $Hailstone(7) = \{7, 22, 11, 34, 17, 52, 26, 13, 40, 20, 10, 5, 16, ..., 1\}$

* $Hailstone(27) = \{27, 82, 41, 124, 62, 31, 94, 47, 142, 71, 214, 107, ...\}$

* 对于任意的$n$，总有$|Hailstone| < ∞$?

  * 还未证明出该结论成立
  * 也没有找到一个反例

  