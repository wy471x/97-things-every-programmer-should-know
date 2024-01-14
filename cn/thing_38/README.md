# 如何使用错误跟踪器

无论你将它们称为“错误”，“缺陷”甚至“设计副作用”，都无法逃脱它们的存在。知道如何提交一个好的错误报告，以及如何在报告中寻找问题，是保持项目良好运行的关键技能。

一个好的错误报告需要三个要素：

- 如何尽可能精确地重现Bug，以及重现Bug会导致该Bug出现的频率。
- 在你的观点中，应该发生什么。
- 实际发生了什么，或者至少提供尽可能多的信息。

错误报告中所报告的信息的数量和质量既反映了报告者，也反映了这个错误。愤怒、简洁的错误报告（"这个功能很烂啊！"）只会告诉开发人员你的不良体验，但并没有提供更多的信息。一个提供了足够上下文以便更容易重现的错误报告会赢得大家的尊重，即使它阻止了一个发布。

错误就像一次对话，所有的历史记录都摆在每个人的面前。不要责怪他人或否认B错误的存在。相反，要求更多的信息或考虑你可能忽略了什么。

改变错误的状态，比如从“打开”到“关闭”，是对你对错误评估的公开声明。花时间解释为什么你认为应该关闭该错误，将会节省后来在向沮丧的管理人员和客户证明该决定的繁琐时间。改变错误的优先级也是类似的公开声明，仅仅因为对你来说错误微不足道，并不意味着它不会阻止其他人使用产品。

不要为了自己的目的而过度使用Bug的字段。在Bug的主题字段中添加“VITAL:”可能会使你更容易对某个报告的结果进行排序，但最终会被其他人复制并且不可避免地会输入错误，或者需要在其他报告中删除。使用一个新的值或一个新的字段，并记录该字段的使用方式，这样其他人就不必重复自己。

确保每个人都知道如何找到团队正在处理的错误。通常可以使用一个具有明显名称的公共查询来实现这一点。确保每个人都使用相同的查询，并且在未先通知团队您正在更改每个人正在处理的内容之前不要更新此查询。

最后，记住，Bug不是标准的工作单位，就像一行代码不是精确的工作量衡量一样。

由[Matt Doar](http://programmer.97things.oreilly.com/wiki/index.php/Matt_Doar)撰写