# git 入门


Git 极速入门

2010-04-23 23:03
分类： 技术
这里非常不错： http://www.lovecloud.info/index.php/2010/02/08/%E6%9C%80%E8%BF%91%E5%AD%A6%E5%88%B0%E7%9A%84%E5%87%A0%E4%B8%AAgit%E7%9A%84%E7%94%A8%E6%B3%95/

查看所有的GIT变量： git var -l
git config -f = ~/.gitconfig 就可以载入变量

提交时需要：（代码review的小要求）
引用
1. 有正确的 用户名和电子邮件( from)

2. comments 中就不要有by Your Name 了。重复。


http://blog.csdn.net/sunrock/archive/2008/06/05/2514204.aspx
引用

  $ git -config user.name "Jike Song"
   $ git -config user.email [email]albcamus@gmail.com[/email]

           注意，这样会在当前repository目录下的. git /config中写入配置信息。 如果 git -config加了--global
        选项，配置信息就会写入到~/. git config文件中。 因为你可能用不同的身份参与不同的项目，而多个
        项目都用 git 管理，所以建议不用global配置。



生成本地修改的所有patch（多少次提交就多少个.path文件）:
引用
git format-patch origin


生成单个patch文件（例子中是将最近5次提交的内容合并到一个文件中）：
引用
git format-patch -5 --stdout  > patch_by_siwei.txt


git push 之前，修改 .git/config 中类似路径为:
git@gitosis.host.com:project_name.git



往远程服务器上提交分支：
引用
git push origin [本地分支名]:[远程分知名(push之后就存在了)]

例如：(理论上)
引用
git push origin added_new_webservice_to_sync_products_and_platforms:lily

提交之后远程就会出现了一个"lily"分支。

apply patch的时候：

最好在linux环境下。如果出现的诡异的 /dev/null问题，十有八九是因为dos文件格式造成的。试试 dos2unix 。如果还不行的话。。。哎，手工吧！
血的教训： 每天时不时的 update 一下，绝对不要等最后push的时候再合并。。。痛苦啊。

每天最好更新一下远程服务器中的代码：

git pull . master    (把远程的master更新到当前的本地分支）


windows环境下的Git Bash中注释的换行： 使用单引号。

git commit -m '
balabala
bala
'

# git patch/apply 某一个commit ( apply a patch generated from a specific commit )

2013-11-14 18:57
分类： 技术
如何在另外一个机器上 apply某个 path？

我们遇到一个情况， 在某个机器上，需要一个紧急部署，但是又不希望手工去修改（因为已经有了一个commit 了）。这样的情况下，可以使用git path 专门为某个commit 生成patch, 然后在这个远程机器上apply it.  ( apply a patch generated from a specific commit ?)

$ git format-patch -1 <sha>   # =>  0001__.patch

$ git apply <path_file >

# git cherry-pick. 如何把已经提交的commit, 从一个分支放到另一个分支

2011-12-10 18:13
分类： 技术
实际问题：
  在本地 master 分支上做了一个commit ( 38361a68138140827b31b72f8bbfd88b3705d77a ) ， 如何把它放到 本地 old_cc 分支上？

办法之一： 使用 cherry-pick.  根据git 文档：

Apply the changes introduced by some existing commits
就是对已经存在的commit 进行apply (可以理解为再次提交）

简单用法：

git cherry-pick <commit id>


例如：
$ git checkout old_cc
$ git cherry-pick 38361a68     # 这个 38361a68 号码，位于：


$ git log
commit 38361a68138140827b31b72f8bbfd88b3705d77a
Author: Siwei Shen <siwei.shen@focusbeijing.com>
Date:   Sat Dec 10 00:09:44 2011 +0800

1. 如果顺利，就会正常提交。结果：

Finished one cherry-pick.
# On branch old_cc
# Your branch is ahead of 'origin/old_cc' by 3 commits.

2. 如果在cherry-pick 的过程中出现了冲突

Automatic cherry-pick failed.  After resolving the conflicts,
mark the corrected paths with 'git add <paths>' or 'git rm <paths>'
and commit the result with:

        git commit -c 15a2b6c61927e5aed6718de89ad9dafba939a90b

就跟普通的冲突一样，手工解决：
2.1 $ git status    # 看哪些文件出现冲突

both modified:      app/models/user.rb

2.2 $ vim app/models/user.rb  # 手动解决它。
2.3 $ git add app/models/user.rb
2.4 git commit -c <新的commit号码>

# 一点点git的分支知识（more about git branch )

2013-03-06 09:12
分类： 技术
$ git branch -a 的结果： ( this morning, I ran a GIT command and got its result: )

sg552@youku:/sg552/workspace/m-cms$ git branch -a
  clean_cache
* master
  siwei_branch
  remotes/origin/HEAD -> origin/master
  remotes/origin/master
  remotes/origin/siwei_branch
我很好奇， origin/HEAD 和 origin/master 都是啥，两者有啥关系。搜索了一下，发现： origin/HEAD是默认的checkout 分支。 HEAD-》 master 表示 默认的分支就是origin/master. ( I am curious about what are the HEAD and origin/master, what relationship is between them. after googling around, i found that origin/HEAD is the default cloned branch , and it's pointing to origin/master in my case )

命令： git remote show origin 可以显示本地和远程的origin 上的分支情况 ( command $ git remote show origin lists the branches in local and remotely )

~~~
sg552@youku:/sg552/workspace/m-cms$ git remote show origin
* remote origin
  Fetch URL: ssh://shensiwei@gforge.1verge.net:22022/gitroot/m-cms
  Push  URL: ssh://shensiwei@gforge.1verge.net:22022/gitroot/m-cms
  HEAD branch: master
  Remote branches:
    master       tracked
    siwei_branch tracked
  Local branch configured for 'git pull':
    master merges with remote master
  Local refs configured for 'git push':
    master       pushes to master       (up to date)
    siwei_branch pushes to siwei_branch (fast-forwardable)
~~~

# git tag 基本操作 （ git tagging basic ）

2013-03-14 17:50
分类： 技术
$ git tag -l  查看所有的tag

$ git tag -a 1.1.0 a50fabb -m 'message content .... '
$ git tag -d 1.0   # will remove tag 1.0

$ git tag -n2   # will show the tags with their messages.

1.0.0           CMS 3.0 的抢先版，....
1.0.1           3月14日下午.修改了若干BUG（大部分都是表单验证）...
$ git push --tags  # push local tags to remote server

$ git ls-remote --tags # list all the remote tags

From ssh://....
a70cffc64e73ae4b5ab7329480999305f11d9c76  refs/tags/1.0.0
6d1ad6c601652442d6d32fce5233ba50a1dd9f56  refs/tags/1.0.0^{}
1acf5e9aabbd353ff45b7aa3fe319d3822acad19  refs/tags/1.0.1
5bba7a637e64267ffad38dd48c30df00da6cc91e  refs/tags/1.0.1^{}

# git stash

# git log,

# git show

# git diff

# Git rebase 笔记 ( git rebase introduction)

2013-05-27 10:56
分类： 技术
前几天的一个文章，我提到 自己比较偏好 git-merge. 现在看起来，这个问题不该带有个人偏好。而是需要根据情况，来选择使用 git rebase /merge  ( several days ago, I mentioned that I prefer 'git-merge' to 'git-rebase'.  Now I admit that as a professional programmer, I should not be emotional.  We should choosing the right one according to the real situation )

merge: 会保留时间线。 适合需要保持时间线的场合。  (it would keep the commit order for each branch )

rebase: 不会保留时间线。 适合按照 feature 来查看log的场合。比如，我现在同时在3个分支上工作，但是为了方便代码的提交，我会在一个完成之后再提交另外一个分支/功能模块。所以在这样的情况下使用rebase使得代码更加容易回滚，以及查看log.   ( the origin commit would be removed and a new commit would be generated .  if you are working on 3 branches at the same time, and want to merge the code till the whole module/branch is done, just use this 'rebase' )

简单用法：

$ git rebase master <current_branch>

这样就会把 master上的最后一个commit, 做为当前 分支的commit 的基础。

更多详细，参考 man git-rebase.   ( for more details, please refer to 'man git-rebase' )
