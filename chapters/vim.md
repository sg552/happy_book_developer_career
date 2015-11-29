# 如何使用键盘.

敲键盘是很重要的事情。键盘瞧不好，会直接影响到工作效率。

我见过不少候选人, 虽然是计算机专业毕业,但是却不会用标准的键盘指法. 这样根本不行.
无法在计算机这个领域走远.

试想,当你需要输入一个字母, 却没有使用标准的键盘指法的话,几乎所有人都不能准确的按到目标键.
所以只好低头看一眼键盘, 把手移动上去, 再抬头看一眼屏幕, 敲击个字, 再抬头, 再低头...

这样的问题是:

1. 效率极其低下.
2. 眼睛容易疲劳.
3. 被其他同仁嘲笑.

(当然好处可能是颈椎得到了充分的活动.)

所以, 使用键盘的方式是:

1. 必须符合标准键盘指法: 左手食指放在F, 右手食指放在J上. 具体的方法见:
2. 编程时尽量不要靠鼠标。 因为每一次你摸向鼠标的时候，你的目光都会离开屏幕，看到鼠标，再移动回来。

（所以个人认为 ios 的xcode 开发效率不会太高）

## 好键盘很重要, 它是我们的武器.

市面上几十块的键盘就算了吧。起码要买入门的机械键盘。 这个不到200块的狼蛛键盘就不错：
http://item.jd.com/1118133.html

基本上我们公司人手一个。

## 合适的键盘的布局

`\` 这个键 很诡异。它的位置一般在 Enter的左侧（ 单引号 `'` 的右侧），
或者在 `backspace`  的左侧，`+`的右侧，跟 `[`和 `]` 一样，是最难以摸正确的按键。

`Enter`是我们按的最多的，所以它的面积要大。

左右两个`shift` ，以及 `enter`上方的 `backspace`，也都最好是大键。

F1，F2，...F12， 也都最好是可以一键按到的。

所以，这个是比较合适的布局：

![比较合适的键盘图](http://siwei.me/system/images/W1siZiIsIjIwMTUvMDEvMDMvMjJfNDBfMDZfNDE1X18uanBnIl0sWyJwIiwidGh1bWIiLCIyMjV4MjU1PiJdXQ/%E5%90%88%E9%80%82%E7%9A%84%E9%94%AE%E7%9B%98%E5%B8%83%E5%B1%80.jpg)

所以，不要购买 87键的小键盘。 例如下面这个：

![不好的87键键盘](http://siwei.me/system/images/W1siZiIsIjIwMTUvMDEvMDMvMjJfNDNfMzRfNTM2X18uanBnIl0sWyJwIiwidGh1bWIiLCI0NTB4NDUwPiJdXQ/%E4%B8%8D%E5%90%88%E9%80%82%E7%9A%84%E9%94%AE%E7%9B%98.jpg)

`因为这种小键盘的很多键是难以按到的。你需要用多个组合键才能按到。比如说 `F1`， `F2`，
这些都需要使用莫名其妙`fn + key` 的组合键。问题就来了，你能做到不看键盘，就能准确的摸到你的
`fn` 键吗？

另外, 如何按`ctrl`? 你要比别人多一根手指。

记得使用小指的掌根去按`ctrl`. 小指掌根是你的第11,12个手指。当你按`ctrl + f` 时(vim中的翻页
操作）, 这个`ctrl`应该是用右手掌的小指掌根按的。 同理，`ctrl + n` 时，这个`ctrl`应该是左手
的小指掌根来按。

绝对不是看一眼键盘，然后用食指去按ctrl.

总之,快捷键的按法, 是两个手同时按,才会高效,方便.

如何按alt? 我一般是用大拇指。

## 如何使用快捷键。

用好快捷键可以让你的开发速度再次提高一个台阶。

这里：http://siwei.me/blog/posts/shortcuts-should-be-short和 http://siwei.me/blog/posts/shortcuts-should-be-short 是之前的两篇文章。

快捷键的原则，是越短越好。越通用越好。比如 ctrl + page_down 就是很短（2个组合键），很通用（在terminal, browser中都用来切换tab ) .

按组合键的方法，是左手和右手同时按。例如： `ctrl + f` 的

错误方式：看一眼键盘，然后左手小指按`ctrl` , 左手食指按`f`.
正确的方式应该是 右手小指掌根按`ctrl`. 左手食指按 `f`

最难按到的几个按键：

`\`,  `]` , `fn`,

所以不建议使用 苹果键盘

## 选择什么编辑器?

<<Pragmatic Programmer>>:
> 世界上只有三种编辑器：　Vim, Emacs　和其他.

其他的编辑器包括: Eclipse (设计模式的作者之一,在IBM主持的项目), Textmate (最初流传于Mac上),
JBuilder, Visual Studio, Sublime 等.

这些编辑器的最大问题,是使用时需要用鼠标来导航. 试想你的眼睛, 先看一眼键盘, 两个


我们就用Vim吧.

## Vim的基本操作

- 上下左右：  jkhl
- 下一个单词：  w
- 前一个单词：  b
- 下一屏： ctrl + f
- 上一屏 :  ctrl + b
- 搜索some_string：    /some_string
- 把全局的some_string 替换成 new_string :   %s/some_string/new_string/g
- 继续搜索下一个：  n
- 继续搜索前一个 :   N (shift + n)
- 补全：    ctrl + n ,  ctrl + p  (next, previous的缩写)
- 删掉一个字母：  x
- 删掉一个单词：  dw
- 删掉一行：   dd
- 删掉3行：    3d
- 复制一个单词：  yw
- 复制当前行： yy
- 粘贴： p
- 选中N行：   shift + v , 再 jk
- 快速打开一个文件：  ctrl + t
- 快速打开前一个文件：  ctrl + e
- 跳到文件头： gg
- 跳到文件末尾： shift + g
- 在光标前新增内容： i  (insert的缩写)
- 在光标后新增内容： a (add的缩写）
- 快速的跳到该行最后：  shift + 4
- 快速的跳到该行最前：  0
- 上一次编辑的地方：  g;
- 下一次编辑的地方：  g,
