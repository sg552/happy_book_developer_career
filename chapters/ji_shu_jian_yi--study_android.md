
# 为什么要学会android 开发。

1. 别人会的，我们要会。
2. Titanium的精髓，他的生命力，就在于，能否调用native 代码。

native code 能大幅提升用户体验

为什么H5一直雷声大雨点小？  就因为 用户体验太差。

为什么普通技术写的微信端，都不好。

微信端： 有个一秒钟定律。
某个页面，一秒钟之内必须打开。否则用户就容易把它关掉。

大幅流失客户（客户不会知道是技术原因打开的慢，而是会以为网站挂掉了）

# 为什么优酷会收购土豆？

之前土豆是比优酷早出现1~ 半年。

土豆的用户，比优酷多很多。 但是有一天，土豆的营业拍照，没审批下来（因为它在上海）
所以，网站关掉了。 用户都跑去优酷了。

一个月之后，土豆又活了。但是用户都不来了。

用户很重要
想获得用户，留住用户， 就要提高 用户体验。

所以， 自绝于用户的事儿（5~10秒打开页面），务必避免。

one page app .

不要使用H5的地图。 要使用原生地图。

所以，我们要写 Titanium module .

如何写呢？

1. 会java  ( 基本语法， 编译。 XML， package ... ) 1周。
2. 会android 开发。
3. 会Ti开发。


# java 语法， 略

# Android开发入门

1. 尽量使用 IDE ( android studio)

我之前强调大家：  VIM + 命令行。

vim : 特别快
命令行： 让你了解到IDE 背后的本质。

但是，由于在android开发当中， 废代码太多。 我们不需要像读RUBY代码那样，字字珠玑。

读java代码的感受：

xxxxxxxxxxxxxxxxxx
oooooooooooooo
xxxxxxxxxxxxx
String value = "some value";
ooooooooo
xxxxxxxxxxxx
}}}

借助IDE， 废代码都给折叠了。有用的代码，都能高亮。 没用的废代码，都变灰。。

XML形式的废代码。提高可读性。

使用IDE: 给我们提供设计的预览

# 入门

1. 搭建环境 （JDK, ANDROID SDK，studio ,gradle）

2. 使用 android studio 创建新的 android 项目。

  1. Activity
  2. XML
  3. 一堆乱七八糟的文件（ value.xml,  color.xml, string)

3.


# activity:

可以认为对应了一个视图。 (controller + view )

# R

获取资源文件的 class （ layout,
