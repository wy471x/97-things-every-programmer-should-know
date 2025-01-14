# 浮点数不是实数

浮点数并非在数学意义上的"实数"，尽管在某些编程语言（如Pascal和Fortran）中被称为real。实数具有无限精度，因此是连续且无损失的；而浮点数具有有限精度，因此是有限的，并且它们类似于"行为不良"的整数，因为它们不均匀地分布在其范围内。

为了说明这一点，将2147483647（最大的32位有符号整数）赋值给一个32位浮点变量（例如x），然后打印它。你会看到2147483648。现在打印`x - 64`。仍然是2147483648。现在打印`x - 65`，你将得到2147483520！为什么会这样？因为在该范围内相邻浮点数之间的间距是128，而浮点运算会四舍五入到最近的浮点数。

IEEE浮点数是基于二进制科学计数法的定点精确度数字：1.d<sub>1</sub>d<sub>2</sub>...d<sub>p-1</sub> × 2<sup>e</sup>，其中*p*是精度（float为24，double为53）。两个连续数之间的间距是2<sup>1-p+e</sup>，可以安全地近似为ε|x|，其中ε是*机器精度*（2<sup>1-p</sup>）。

了解浮点数周围的间距可以帮助你避免经典的数值错误。例如，如果你正在进行迭代计算（如寻找方程的根），在答案附近要求更高的精度是没有意义的。确保你请求的容差不小于该位置的间距；否则你将陷入无限循环。

由于浮点数是实数的近似值，因此必然存在一些误差。这种误差称为*舍入误差*，可能会导致出人意料的结果。例如，当你相减接近相等的数时，最高位数会相互抵消，因此原本是最低有效位（舍入误差所在的位置）将被提升到浮点结果的最高有效位，从而在任何进一步的相关计算中产生影响（这种现象称为*扩散*）。你需要仔细检查你的算法，以防止此类*灾难性抵消*。为了说明这一点，考虑求解方程 *x<sup>2</sup> - 100000x + 1 = 0* 的情况，使用二次方程公式。由于表达式 *-b + sqrt(b<sup>2</sup> - 4)* 中的操作数在大小上几乎相等，你可以计算根 *r<sub>1</sub> = -b + sqrt(b<sup>2</sup> - 4)* ，然后得到 *r<sub>2</sub> = 1/r<sub>1</sub>* ，因为对于任何二次方程ax2 + bx + c = 0，根满足 *r<sub>1</sub>r<sub>2</sub> = c/a*。

扩散还可以以更微妙的方式发生。假设一个库通过公式 *1 + x + x<sup>2</sup>/2 + x<sup>3</sup>/3! + ...* 来计算 *e<sup>x</sup>*。这对于正数x来说是没有问题的，但是考虑当x是一个很大的负数时会发生什么。偶数次幂的结果是大的正数，减去奇数次幂的幅度甚至不会影响结果。问题在于大的正数项中的舍入误差位于比真正答案要重要得多的数字位置上。答案趋向于正无穷大！解决方法也很简单：对于负数x，计算*e<sup>x</sup> = 1/e<sup>|x|</sup>*。

不用说，你不应该在金融应用中使用浮点数——这就是像Python和C#这样的语言中的十进制类所用的。浮点数旨在进行高效的科学计算。但是，效率如果没有准确性就毫无意义，所以请记住舍入误差的来源，并相应地编写代码！

由[Chuck Allison](http://programmer.97things.oreilly.com/wiki/index.php/Chuck_Allison)撰写
