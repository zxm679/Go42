# <center>《Go语言四十二章经》第五章 作用域</center>

作者：李骁

## 5.1 作用域
* 局部变量
在函数体内声明的变量称之为局部变量，它们的作用域只在函数体内，参数和返回值变量也是局部变量。

* 全局变量
作用域都是全局的（在本包范围内）
在函数体外声明的变量称之为全局变量，全局变量可以在整个包甚至外部包（被导出后）使用。
全局变量可以在任何函数中使用。

* 简式变量
使用 := 定义的变量，如果新变量p与那个同名已定义变量 (这里就是那个全局变量p)不在一个作用域中时，那么Go 语言会新定义这个变量p，遮盖住全局变量p。刚开始很容易在此犯错而茫然，解决方法是局部变量尽量不同名。

>注意，简式变量只能在函数内部声明使用，但是它可能会覆盖函数外全局同名变量。而且你不能在一个单独的声明中重复声明一个变量，但在多变量声明中这是允许的，而且其中至少要有一个新的声明变量。重复变量需要在相同的代码块内，否则你将得到一个隐藏变量。
>
>如果你在代码块中犯了这个错误，将不会出现编译错误，但应用运行结果可能不是你所期望。所以尽可能避免和全局变量同名。
