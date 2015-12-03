# 看起来的美好

## 屏幕自动适配

自适应的技术，能够提供在不同尺寸的屏幕上显示同样的内容。例如 手机上（600像素宽度以下）
是一种布局，PC显示器上（1024宽度像素)是另外一种布局。

在实现技术上讲，就是一套HTML+CSS代码，让多种设备(横屏，竖屏，大屏，小屏）都可以适配。

目前的实际经验是：

- 要达到最好的效果，必须分别来实现。
- 要让小屏幕跟大屏幕的内容互不影响，否则容易按下葫芦浮起瓢。例如：在PC上明明显示非常正常的页面，放到
移动端就显示不好。等移动端H5页面修改好之后，反观PC端页面又不行了。
- 太多时候，两个端的显示内容是完全不一样的。
- 适配也是有限度的适配。例如：
  * 移动web(wap)屏幕： 一套代码
  * PC 屏幕： 一套代码。 （优酷的移动下载页面）


## I8N 一套代码， 显示多种不同的语言。

i18n(internationalization): 能在不修改代码的前提下针对不同的语言来显示。
下面的例子，是分别使用英文（en.yml) 和 法文（fr.yml)向人问好：

![i18n的例子](/images/i18n例子.png)

- 让代码变得异常臃肿, 难于调试
![让代码变的异常复杂](/images/i18n-复杂的代码.png)
- 很多语言之间是结构完全不同的。你很难把握翻译的粒度（是根据每个字来
翻译？还是根据整个句子来翻译？）
- 无法保证其他语言的代码及时更新。
![不完整的i18n](/images/不完整的i18n.png )，可以看出，作者正在根据英文
来翻译中文。而且其中很多部分都没有及时更新，显示的内容仍然是英文。

参考: [这个著名的ppt](http://de.slideshare.net/HeatherRivers/linguistic-potluck-crowdsourcing-localization-with-rails)
这篇ppt是我见到的把i18n的问题分析的最透彻的文章了。
出现了更加可怕的:
- 语态：
![复杂的语态](/images/i18n-morphemes.png)
- 不同语言的单数、复数问题
![不同语言的单数、复数问题](/images/i18n-复杂的单复数.png)
- 在语言的表现能力上，把语言分成 analytic/synthetic,  no/hella agreement


最要命的是：中国的软件公司不需要做国际化的东西:
- 99%的公司都不卖windows这样的国际化软件。
- 99%的外包公司都不会承接这样的项目。

所以，把精力专心放在做产品上，而不是翻译上。如果遇到一个开源项目，你需要
把它改造成你自己的项目的话，不要保留i18n！

## 数据库的适配：
hibernate , rails Active Record: 都支持数据库的平滑迁 移。 支持多种数据库。

实际的困难：

- 不同的数据库，肯定会用到不同的语法结构
- 就算使用的全都是标准sql，在迁移时也会出现结构不统一的现象，
例如：bool类型的列，在mysql下是boolean 在sqlite3下面是 int(1) ，
需要太久去排错。
- 在国内(无论是软件外包公司还是互联网公司），一个项目开始之后，基本不会更换数据库。

