# LV101-assignment-2
In this assignment, you will write a LabVIEW program to calculate Catalan numbers. You need to use your knowledge in for loop, while loop, and array to complete the assignment. The files you need to modify are ```combination.vi```, ```catalan1.vi```, ```catalan2.vi```, and ```main.vi```. You should check your VI step by step because failure in one VI may affect another VI. You can feed in different input numbers and run to testify your work.

## Basic Idea
Catalan number is a sequence of numbers appearing in many different counting problems such as Dyck Paths and Polygon triangulations. The Catalan squence is 1, 1, 2, 5, 14, 42, 132, 429, 1430, 4862, 16796, ... Generally, the Catalan sequence can be calculated by two useful formulas.

The first one is combinatorial definition: $`C_n=\frac{1}{n+1}(^{2n}_{n})`$<br>
Where $(^{2n}_{n})$ means combination you may use as $`C^{2n}_{n}`$ in Taiwanese high school (Note that $`C_{n}`$ which means nth Catalan number is different from $`C^{2n}_{n}`$ which means combination).

Another one is recursive definition:<br>
$`C_{0}=C{1}=1`$<br>
$`C_{n}=\sum ^{n-1}_{i=0} C_{i}C_{n-i-1}`$ for $n \geq 2$


## <code>combination.vi</code>
In this VI, for input integers a and b, you should output $(^{a}_{b})$. Recall what your learn in high school $`(^{a}_{b})=\frac{a \times (a-1) \times ... (a-b+1)}{b!}`$. You should add calculations into the provided for loop to calculate the numerator and denominator separately and divide the two values.

## <code>catalan1.vi</code></h3>
In this VI, for input integer n, you should output $C_{n}$. You should use the combinatorial definition $`C_n=\frac{1}{n+1}(^{2n}_{n})`$ to calculate. You can make use of the combination.vi you just wrote.

## <code>catalan2.vi</code>
In this VI, for input integer n, you should output $`C_{n}`$. However, you should use the recursive definition in this VI. Assume that the input array would be the first (n-1)th Catalan numbers. Thus, you should use the provided for loop and add array function to calculate $`C_{n}`$ from the input array.

For example, the if input n is 5, the input array would be 1, 1, 2, 5 and you should output 14. 

## <code>main.vi</code>
In this VI, you should make the first while loop and  to calculate the first nth Catalan numbers by `catalan1.vi` until $C_{n}>limit$, where the limit is an input integer. You should output the sequence to ans1. Then, you should make the second while loop to do the same calculation, but by `catalan2.vi` this time. The input array of `catalan2.vi` should be the result of the first while loop. Note that because ```catalan2.vi```calculates Catalan number recursively, you do not need to calculate $`C_{0}`$ and $`C_{1}`$, you can just start from $`C_{2}`$ instead. You should output the sequence calculated by ```catalan2.vi``` to ans2. If the two sequences are the same(except that ans2 does not have $`C_{0}`$ and $`C_{1}`$) and agree with the Catalan sequence, then you succeed.

For example, for limit 100, you should output ans1 = 1, 1, 2, 5, 14, 42, 132 and ans2 = 2, 5, 14, 42, 132
