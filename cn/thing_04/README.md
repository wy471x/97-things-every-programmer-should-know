# 自动化您的编码规范

你可能也有过这样的经历。在项目开始时，每个人都有很多良好的意图 - 可以称之为“新项目的决心”。很多时候，这些决心都被写在文件中。关于代码的那些决心最终会被写入项目的编码规范中。在启动会议上，首席开发人员会浏览文件，并且在最好的情况下，每个人都同意尽量遵守这些规范。然而，一旦项目开始进行，这些良好的意图一个接一个地被抛弃。最终交付的代码看起来一团糟，似乎没有人知道它是如何变成这样的。

什么时候出了问题？可能已经在启动会议上。项目成员中有些人没有注意。其他人没有理解其中的要点。更糟糕的是，有些人持不同意见，已经在计划他们的编码规范反抗。最后，有些人理解了其中的要点并同意，但是当项目压力过大时，他们不得不放弃某些规范。对于一个希望获得更多功能的客户来说，格式良好的代码并不能给你带来额外的好处。此外，如果不能自动化执行编码规范，遵循编码规范可能是一项非常乏味的任务。试着手动缩进一个混乱的类，你就会明白这一点。

但是，如果这是一个问题，为什么我们一开始要有编码规范呢？统一格式化代码的一个原因是，没有人可以通过私人的格式化方式来“拥有”一段代码。我们可能希望防止开发人员使用某些反模式，以避免一些常见的错误。总之，编码规范应该使项目中的工作更容易，并从一开始就保持开发速度。因此，每个人都应该对编码规范达成一致——如果一个开发人员使用三个空格缩进代码，而另一个开发人员使用四个空格，这是没有帮助的。

有许多工具可以用于生成代码质量报告，记录和维护编码规范，但这并不是全部解决方案。应该在可能的情况下自动化并强制执行。以下是一些示例：

- 确保代码格式化是构建过程的一部分，以便每个人在编译代码时自动运行它。
- 使用静态代码分析工具扫描代码以查找不希望的反模式。如果发现任何反模式，就中断构建过程。
- 学习配置这些工具，以便可以扫描您自己的项目特定的反模式。
- 不仅要测量测试覆盖率，还要自动检查结果。同样，如果测试覆盖率过低，就中断构建过程。

尝试将您认为重要的每个方面都做到这一点。您将无法自动化您真正关心的一切。对于那些无法自动标记或修复的事情，将它们视为编码规范的补充准则，这些准则是自动化的，但是请接受您和您的同事可能不会如此认真地遵守它们。

最后，编码规范应该是动态的而不是静态的。随着项目的发展，项目的需求会发生变化，一开始可能看起来很聪明的做法，在几个月后可能就不再明智了。

由[Filip van Laenen](http://programmer.97things.oreilly.com/wiki/index.php/Filip_van_Laenen)撰写
