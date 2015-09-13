# 常量参数，变量参数和inout参数

下面主要介绍下常量参数，变量参数，和inout参数，正确的理解这几种参数方式对于我们后续的swift开发会有很大的帮助，排除掉很多理解上的偏差。

## 常量参数

swift中我们默认的参数定义都是常量参数，即在方法内部我们只能对参数进行读操作。

## 变量参数

如果开发者需要在方法内部改变参数的值，我们可以把参数定义为变量参数。

``` swift
func swapInt(var a:Int, var b:Int) {
    let tmp = a;
    a = b;
    b = tmp;
}

var a = 1, b = 5
swap(a, b)
a
b
```

在上面的例子中，虽然在方法内部改变了num的值，当时在方法外部，num的值还是6。这个很明显是我们大学中学习C++时的值传递和引用传递的概念。我们可以这样理解在swift语言中，变量参数实质上是值传递，在方法内部对参数的改变，不会对方法外部的内容造成影响。

## inout参数

``` swift
func swapInt2(inout a:Int, inout b:Int) {
    let tmp = a;
    a = b;
    b = tmp;
}

var c = 1, d = 5
swapInt2(&c, &d)
c
d
```

在swift中，我们可以使用inout参数来达到在方法中可以改变参数。

需要注意两点：

1. 定义inout参数在参数前加入关键字inout
2. 在使用方法传递参数时，需要在参数前添加&。