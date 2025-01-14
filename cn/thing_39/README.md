# 通过删除代码来改善代码

有时候，“少即是多”这句陈词滥调确实是正确的。

在过去几周中，我对我们的代码库进行了改进，其中之一就是删除了一些代码块。

我们按照XP原则编写了软件，其中包括YAGNI（即“你现在不需要它”）。人性使然，我们在一些地方不可避免地做得不够好。

我注意到产品执行某些任务花费的时间太长了，这些任务本应该几乎瞬间完成。这是因为它们被过度实现了；添加了一些不必要的花哨功能，尽管当时看起来是个好主意。

因此，我简化了代码，提高了产品的性能，并通过从代码库中删除多余的功能降低了全局代码的熵水平。令人高兴的是，单元测试告诉我在此过程中没有破坏其他任何东西。

这是一个简单而非常令人满意的经历。

那么，为什么不必要的代码首先会出现在那里呢？为什么一个程序员感觉需要写额外的代码，并且它是如何通过代码审查或配对过程的呢？几乎可以肯定是因为以下原因：

- 那是一个有趣的额外功能，程序员想要编写它。*（提示：编写代码是为了增加价值，而不是为了好玩。）*
- 有人认为将来可能需要它，所以最好现在就编写它。*（提示：这不是YAGNI。如果你现在不需要它，请不要现在就编写它。）*
- 它似乎不是那么大的“额外”，所以比起回去询问客户是否真的需要，实现它更容易。*（提示：编写和维护额外的代码总是需要更多时间。而且客户实际上是可以沟通的。一个小小的额外代码随着时间的推移会成为需要维护的大工作。）*
- 程序员发明了额外的要求，但这些要求既没有记录也没有讨论来证明额外功能的合理性。实际上，这个需求是虚假的。*（提示：程序员不确定系统需求，客户确定。）*

你现在正在做什么工作？它们都是必需的吗？

由[Pete Goodliffe](http://programmer.97things.oreilly.com/wiki/index.php/Pete_Goodliffe)撰写
