# API设计的黄金法则

API设计很困难，尤其是在大型项目中。如果你正在设计一个将有数百或数千个用户的API，你必须考虑将来可能如何修改它以及这些修改是否会破坏客户端代码。除此之外，你还必须考虑API的使用者对你的影响。如果你的API类中使用了自己的某个方法，你必须记住用户可以对你的类进行子类化和方法重写，而这可能会导致灾难性后果。你将无法更改该方法，因为一些用户给它赋予了不同的含义。你未来的内部实现选择受制于用户的影响。

API开发人员用各种方法解决这个问题，但最简单的方法是锁定API。如果你在使用Java，你可能会倾向于将大多数类和方法设置为final。在C#中，你可能会将类和方法设置为sealed。无论您使用哪种语言，您都可能会想通过单例或使用静态工厂方法来呈现您的 API，以便您可以防止有人覆盖行为并以可能限制您以后选择的方式使用您的代码。这一切看起来合理，但真的如此吗？

在过去的十年中，我们逐渐意识到单元测试是实践中非常重要的一部分，但这个教训并没有完全渗透到整个行业中。证据就在我们身边。拿一个使用第三方API的任意未经测试的类，试着为它编写单元测试。大多数情况下，你会遇到麻烦。你会发现使用API的代码与API紧密结合在一起。没有办法模拟API类，以便你可以感知代码与它们的交互，或者为测试提供返回值。

随着时间的推移，情况会变得更好，但前提是我们在设计API时开始将测试视为一个真实的用例。不幸的是，这比仅仅测试我们的代码要复杂一些。这就是**API设计的黄金法则**的所在之处：*为你开发的API编写测试是不够的，你还必须为使用你的API的代码编写单元测试。当你这样做时，你会亲自了解用户在尝试独立测试他们的代码时将要克服的障碍。*

有一种方法可以让开发人员轻松地测试使用你的API的代码。`static`、`final`和`sealed`并不是本质上的不良构造。它们在某些情况下是有用的。但重要的是要意识到测试问题，并且要亲自体验它。一旦你有了这样的经验，你可以像对待其他设计挑战一样来解决它。

由[Michael Feathers](http://programmer.97things.oreilly.com/wiki/index.php/Michael_Feathers)撰写
