# linux下的常用命令 ( widely used linux commands)

## ls


## mkdir -p
## top
## ps aux --sort rss
## df -kh    查看分区大小
## du . -kh  查看文件夹大小
## ln -s
## kill -9
## crontab -e
## vim /etc/nginx 下面的东东
## tail
## head
## grep *** 重中之重啊。 一定要知道各种形式的参数， 以及各种变种。 比如：   $ grep -F 'fixed string' -R --include=*rb
## zgrep 搜索 压缩文件的内容
## find .
## rsync  传送文件
## sftp
## ssh
## wget
## curl HTTP 请求
## vim ~/.bashrc
## chmod
## chown
## passwd
## netstat
## ifconfig 查看网卡信息
## netrafic 查看流量的（似乎）
## top 命令 （进入之后的各种参数， 按c,1 )
## 各种服务器的命令： nginx -s reload|stop,  rails server...
## tar zxvf
## unzip
## pwd 获知当前目录
## cp -r
## mv

删除大文件： $ echo '' > big_file


知道各个系统文件夹的基本用处。  /var/logs,  /etc/

高级的：
## pipe     find . | grep '.rb'
## logrotate
## split
## awk
## seed
## bash script
## expect

## Linux 的几个好用的命令 ( sweet commands in linux)

这是一个循环，把 /tmp/test.lst 文件中的 每一行都读出来，然后循环运行rsync 命令 . (注意其中的 exclude ) ( a loop that reads all the lines of contents in a file named /tmp/test.lst and then run them one by one)

```bash
for i in `cat /tmp/test.lst`;do
rsync -avzPl --exclude="2013*" --exclude="201404*" --exclude='*.log*' --exclude='*.git' --exclude='*.sql' ./$i 10.103.13.37::cmscode
done
```

在当前目录下，找到所有的文件中包含的 10.103.13.74 ，并且把它替换成： 10.103.13.37 ( find all the '10.103.13.74' and then replace them with '10.103.13.37') 这个功能跟 VIM plugin: Greplace 是一样的。

```bash
$ sed -i "s/10.103.13.74/10.103.13.37/g" `grep "10.103.13.74" -rl ./`
```

## Linux 控制台神器：搜索历史命令 Ctrl + R

(press ctl + r ) 输入任意字符，例如： "mig"  就会出现 $  rake db:migrate    ( press ctrl + r, then input the content you want to search)

如果我想找另一个命令呢？  输入完 'mig' 多按几次 ctrl + r ，就可以继续向前搜索 “mig" 的内容了。  ( if you want to search the last but n result, just press n times 'ctrl + r'.)

如果找到了，按 -> 或者直接回车，就是执行  ( press Enter to execute the command , or 'right arrow (->)' to go to the end of the command.

