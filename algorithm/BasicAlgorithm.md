# 基本算法思想
### 1.穷举算法思想
穷举算法(ExhaustiveA ttack method)是最简单的一种算法,其依赖于计算机的强大计算能力来穷尽每一种可能的情况从而达到求解问题的目的。穷举算法的效率并不高，它比较适用于处理没有明显特征的问题场合。

穷举算法思想就是在所有会出现的情况中寻找需要的答案,具体思想如下：
```
(1) 对于每一种可能的情况计算其结果
(2) 判断这个结果是否满足要求，如果满足，则表示找到一个正确结果，不过不满足，则继续寻找。
```

注意：使用穷举法最好明确问题答案的范围，这样才能在确定的范围内搜索。指定范围之后，就可以使用循环语句和条件判断语句逐步验证候选答案的正确性，从而得到需要的正确答案。

常见的问题有：`鸡兔同笼问题`

### 2.递推算法思想
递推算法适合有明显公式规律的场合。它主要根据已有的数据和关系，逐步推倒得到结果。

基本算法思想如下：
```
（1）根据已知结果和关系，求解中间结果
（2）判断是否达到要求，如果达到要求，表示找到了一个正确答案，不过没有达到要求，则继续上一步的求解。
```

注意：递推算法需要用户知道答案和问题之间的逻辑关系。在许多数学问题中，都有明确的计算公式可以遵循，因此可以采用递推算法来实现。

常见的问题有：`斐波那契数列`

### 3.递归算法思想
递归算法思想是日常解决问题经常用到的一种算法思想，使用递归思想，往往可以简化代码编写，提高程序的可读性。递归的主要表现形式就是不断调用自身，达到判断条件后跳出。

递归调用是一个函数在它的函数体内调用它自身的函数调用方式，这种函数也称为“递归函数”。在递归函数中，主调函数又是被调函数。执行递归函数将反复调用其自身，每调用一次就进入新的一层。

+ 直接递归：即在函数中调用函数本身。
+ 间接递归：即间接地调用一个函数，如出如func_a调 用 func_b, func_b 又调用func_a。间接递归用得不多。

注意：使用递归，一定要有判断语句使其强制退出，否则递归的调用将永远执行下去。

### 4.分治的算法思想
分治的算法思想属于一种化繁为简的算法思想。它主要将计算步骤比较复杂的问题进行简化而逐步得到结果。

基本算法思想：
分治算法的基本思想是将一个计算复杂的问题分为规模较小，计算简单的小问题求解，然后综合各个小问题，得到最终问题的答案。
```
(1) 对于一个规模为N 的问题，若该问题可以容易地解决（比如说规模>^较小），则直接解决,否则执行下面的步骤。
(2) 将该问题分解为多个规模较小的子问题，这些子问题互相独立，并且原问题形式相同。
(3) 递归地解子问题。
(4) 然后，将各子问题的解合并得到原问题的解。
```
注意：使用分治算法需要待求解问题能够化简为若干个小规模的相同问题，通过逐步划分，达到一个易于求解的阶段而直接进行求解。然后，程序中可以使用递归算法来进行求解。

### 5.概率算法思想
概率算法依照概率统计的思路来求解问题，往往不能得到问题的精确解，但却在数值计算领域得到了广泛的应用。因为很多数学问题，往往没有或者很难计算解析解，这时便需要通过数值计算来求解近似值。

基本算法思想
```
(1) 将问题转化为相应的几何图形S, S 的面积是容易计算的，问题的结果往往对应几何图形中某一部分S1 的面积。
(2) 然后，向几何图形中随机撒点。
(3) 统计几何图形S 和 S1 中的点数。根据S的面积和S1面积的关系以及各图形中的点数来计算得到结果。
(4) 判断上述结果是否在需要的精度之内，如果未达到精度则执行步骤(2)。如果达到精度,则输出近似结果。
```

### 6.贪心算法思想
贪心算法的思想非常简单且算法效率很高，在一些问题的解决上有着明显的优势。

>先来看一个生活中的例子。假设有3种硬币，面值分别为1元、5角、1角。这3种硬币各自的数量不限，现在要找给顾客3元6角钱，请问怎样找才能使得找给顾客的硬币数量最少呢？你也许会不假思索的说出答案：找给顾客3枚1元硬币，1枚5角硬币，1枚1角硬币。其实也可以找给顾客7枚5角硬币，1枚1角硬币。可是在这里不符合题意。在这里，我们下意识地应用了贪心算法解决这个问题。

所谓`贪心算法`，就是总是做出在当前看来是最好的选择的一种方法。以上述的题目为例，为了找给顾客的硬币数量最少，在选择硬币的面值时，当然是尽可能地选择面值大的硬币。因此，下意识地遵循了以下方案：
```
（1）首先找出一个面值不超过3元6角的最大硬币，即1元硬币。
（2）然后从3元6角中减去1元，得到2元6角，再找出一个面值不超过2元6角的最大硬币，即1元硬币。
（3）然后从2元6角中减去1元，得到1元6角，再找出一个面值不超过1元6角的最大硬币，即1元硬币。
（4）然后从1元6角中减去1元，得到6角，再找出一个面值不超过6角的最大硬币，即5角硬币。
（5）然后从6角中减去5角，得到1角，再找出一个面值不超过1角的最大硬币，即1角硬币。
（6）找零钱的过程结束。
```
这个过程就是一个典型的贪心算法思想。

因此，不难看出应用贪心算法求解问题，并不从问题的整体最优上加以考虑，它所作出的每一步选择只是在某种意义上得__局部最优__选择。因此，严格意义上讲，要使用贪心算法求解问题，该问题应当具备以下性质。
```
1. 贪心选择性质。所谓贪心选择性质，就是指所求解的问题的整体最优解可以通过一系列的局部最优解得到。所谓局部最优解，就是指在当前的状态下做出的最好选择。
2. 最优子结构性质。当一个问题的最优解包含着它的子问题的最优解时，就称此问题具有最优子结构性质。
```