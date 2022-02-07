# 废代码

[boilerplate code](https://en.wikipedia.org/wiki/Boilerplate_code)
烧水壶(架子）  代码

有它，没啥意义。  没它，没法编译，运行的代码。

html:

```html
<html>
  <head>
  </head>
  <body>
  </body>
</html>
```

java:

```java
package ...

import ...
import ..
import ..

class {
  public void setXX () {

  }
}
```


javascript:





# 为什么要自己搭建博客。


## 学会分享和开放

- 聪明的人，永远能学会你藏着掖着的东西
- 不开窍的人，你把东西放到他面前，他都不要。

## 博客是自己的名片。

- 你是专业的。
- 你的技术轨迹，能被人看到。
- 是自己最好的备忘。  （ 例如，今天我想给出几个废代码的例子，直接搜 ：  siwei.me rubymotion,
siwei.me boilderplate )  我可以把非常复杂的东西，记在里面。

因为技术，他在我们第一次弄的时候，最难。 （难度系数 95 （满分100））
第二次以后，每次用， 难度系数只有5.

## 锻炼你的口才。

我们自己写文章，肯定自己看。

我写个句子：   我今天吃了早饭。 有主语，谓语，宾语。


```
最近在学习用 Elixir 的 MVC 框架 Phoenix 写一个 Chatroom 。
有一个问题是 在 channel 中渲染模板，虽然我用 Phoenix.View.render 方法顺利解决了。
但这让我开始思考另外几个问题：
```

有一个问题是：  后面应该接上一个完整的句子。


我的前期可能有语病， 后期就绝对越来越少了。
```
2016-02-20 rails 项目增加日志功能(log) (31)

2016-02-18 wwdr 过期的问题解决办法 (27)

2016-02-18 IOS下获取UDID 等各种信息。 (24)

2016-02-10 截屏并制作gif的工具：licecap (57)

2016-02-07 appcelerator titanium的几本英文书 (68)

...

2008-03-12 Jalopy在Eclipse下的使用 (332)

2008-03-05 《Checkstyle4.3中文手册》草稿版，请大家多给意见！想加入OpenDoc. (323)

2007-06-12 应用开源项目时，你会大肆封装，修改它吗？ (349)
```

英语谚语：  [吃自己的狗粮](https://en.wikipedia.org/wiki/Eating_your_own_dog_food)。

你是作者。 谁是第一个读者？  自己么！

XX问题解析。

XX问题答疑


# 吐槽OC

为什么要加上NSString,   AFNetworking

如果我那天声明个变量：  “绿色”，  刚好前缀是RED，  REDgreen?

green = 'red'
banana = 'apple'


# 臭名昭著的 匈牙利命名法。

sName = 'DASHI'
iSum = '100'
aApples = [apple1, apple2]

这个臭名昭著，大部分时候，不是由别人提出来的。而是由这个语言的熟手提出来的。
因为，只有自己，（代码作者本身） ，才是这个命名法的最大受害者。

java:

DatabaseManager   dbMysqlMng  = ...;

为什么是 dbMysqlMng 这个命名？

- 只有最新的新手  和 最老的老手， 才会提出这个问题
： 为什么要加前缀？
为什么要 缩写？

## 起源

微软，OFFICE （类似的办公软件） ， 做WORD 文档中，会对  行，和列 做变量的命名和区分。

rowXXX,   columnYYY

由于早期 C 编译器的限制，一个变量最多8位。  MyBanana1 和 MyBanana2 在编译器看来是一个东西。

所以，出现了各种各样的缩写：

- manager ->  mng
- implement  -> impl
- array  ->  arr

现在，永远不要这样做。

- nite   -> night
- height -> h8
- a1b2c3

代码的可读性，永远排在第一位。


- rowXXX,  columnYYY  ->  rXXX, cYYY

这个是可以接受的。

但是，它的重点，在于 前缀能很好的分辨出这个 变量的 作用。（它是自解释的

后来，大家就把它用错了。  前缀就简单的用 类型来做了）。


# 最好的注释，是清晰的方法名。

很复杂的注释，是不如 清晰明了的方法名的。


```
# 该方法，实现了： 向用户的手机端发送 验证码。
public void func1(){
}

# 该方法，实现了： 想用户发送 重置密码的链接。
public void func2(){
}

# 卖出咖啡
public void buy_coffee(){
}

# 颜色设置成红色
public void set_green(){

}
```


改正方法：

1. 修改方法名。 方法名就是自己能说明问题的( self-explaination. )
```
# 该方法，实现了： 向用户的手机端发送 验证码。
public void send_validation_code_to_user_mobile(){
}
```

2. 删掉注释。
```
public void send_validation_code_to_user_mobile(){
}
```

## 为什么不要注释？

90% 是不需要的。因为注释会过期。


```
# 发送验证码到用户手机
send_validation_code_to_user_mobile(){
   send_validation_code()
   # 过两天, 要记录日志了。
   save_log()
   # 在发送验证码的同时， 向用户发送邮件提醒

   # 过两天， 再给用户发送站内短信。
   ...
}
```

第一次，第二次修改这个方法时，作者可能会更新注释。
之后，就慢慢就荒废注释了。 到后期，你会发现，注释跟 原方法 差了十万八千里。
