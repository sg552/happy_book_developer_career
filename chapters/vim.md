## 选择什么编辑器?

<<Pragmatic Programmer>>:
> 世界上只有三种编辑器：　Vim, Emacs　和其他.

其他的编辑器包括: Eclipse (设计模式的作者之一,在IBM主持的项目), Textmate (最初流传于Mac上),JBuilder, Visual Studio, Sublime 等.

这些编辑器的最大问题,是使用时需要用鼠标来导航. 试想你的眼睛, 先看低头找一下鼠标， 再移动指针到某个位置，再敲击键盘， 再摸到鼠标，重复上面的步骤。。。会很累。

考虑到几乎每个Linux的版本都会默认安装Vim, 我建议大家学习。

源代码教程  https://github.com/sg552/my_vim

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

更多的操作，我为大家录制了的视频, 一小时内可以学完： http://edu.51cto.com/course/11219.html