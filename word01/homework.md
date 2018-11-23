##1.以容易理解的格式列出/home 目录中所有以”d”开头的文件目录的大小
 ls -lh d*


2.列出/home 目录中所有以”s”开头的目录。
ls -F |grep "^s" | grep "/$"



3.删除后缀名为.log 的所有，删除前逐一询问
rm -i *.log



4.cp 命令 —n 和 -u的区别

-n, --no-clobber：不覆盖既有文件；
-u,--update：使用这项参数后只会在源文件的更改时间较目标文件新时或是名称相互对应的目标文件并不存在时，才复制文件

5.找你的用户目录下面的所有py文件,ls -l 查看他们的属性,然后把这些结果输入到一个文件之中
ls -l *.py >test1 


6.使用ls查看根目录 并且每行显示3个信息


7.查看所有进程信息,只查看前3行
ps -a |head -n 4


8.分析以下问题,并给出解决方案

Mount is denied because the NTFS volume is already exclusively opened.
The volume may be already mounted, or another software may use it which could be identified for example by the help of the 'fuser' command.


NTFS卷被拒绝是因为已经执行打开，可能已经被挂载或者有应用程序正在使用它，
可以使用fuser命令显示正在使用指定的file，file system或者socket的进程信息。


如#fuser -m -u /dev/sdb1 使用-m -u显示正在使用/dev/sdb1的进程PID以及用户名称，
如我输入上述命令后显示的情况



表明是PID为31301的进程正在使用它，如果命令为fuser -m -u /deev/sdb1，
那么显示为/dev/sdb1: ?31301(root)表示root用户的31301进程正在使用/dev/sdb1，
可以使用kill命令杀死该进程,kill 31301，此时在使用mount命令就不会出错了



9.ssh 服务端口是多少,ssh免密登录方式的原理是什么
交换公钥  端口：22

10.权限755代表什么权限,如果我想把所有的w权限去除应该使用什么命令
用户权限：读写执行  用户组：读执行  其他用户：读执行
chmod -w 文件





1.git add和git stage的区别是什么
向索引中添加文件内容    
2.git rm --cached 和git rm -f的区别是什么
只从索引中删除     覆盖最新的检查

3.git和svn的区别是什么
区别1、GIT是分布式的，SVN不是
这是GIT和其它非分布式的版本控制系统，最核心的区别；
GIT跟SVN一样有自己的集中式版本库或服务器。
但，GIT更倾向于被使用于分布式模式，
也就是每个开发人员从中心版本库/服务器上chectout代码后会在自己的机器上克隆一个自己的版本库。

区别2、Git直接记录快照，而非差异比较
Git和其他版本控制系统的主要差别在于，
Git 只关心文件数据的整体是否发生变化，
而大多数其他系统则只关心文件内容的具体差异。
Git 并不保存这些前后变化的差异数据。实际上，
Git 更像是把变化的文件作快照后，记录在一个微型的文件系统中。
每次提交更新时，它会纵览一遍所有文件的指纹信息并对文件作一快照，
然后保存一个指向这次快照 的索引。为提高性能，若文件没有变化，
Git不会再次保存，而只对上次保存的快照作一链接。

区别3、近乎所有操作都是本地执行
在 Git 中的绝大多数操作都只需要访问本地文件和资源，不用连网。
但如果用 CVCS 的话，差不多所有操作都需要连接网络。
因为 Git 在本地磁盘上就保存着所有当前项目的历史更新，所以处理起来速度飞快。

4.筛选出 2018.10.1 到 2018.10.20之间的日志,并且输出为地理图,并且没有做过合并
 git log --after="2018-11-1" --before="2018-11-20" --no-merges --graph




5.git init和git clone的区别
git init # 初始化本地的仓库，会生成.git文件，此时不会加入任何文件的快照
git clone remote_path #克隆远程仓库到当前文件夹，会一起克隆远程的文件夹

6.每次提交都忽略.idea文件夹里面的东西怎么办

7.如果编辑一个文件之后并且加入了暂存区,但是你后悔了,想把文件恢复到没有修改之前的样子,怎么办

8.如何检出标签?

9.git fetch 和 git pull的区别
git fetch 拉取不会和本地合并
git pull  拉取会和本地合并   
10.如何添加远程仓库
git rmote add origin 地址