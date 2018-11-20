###1.以容易理解的格式列出/home 目录中所有以”d”开头的文件目录的大小



###2.列出/home 目录中所有以”s”开头的目录。
find -name "s*"


###3.删除后缀名为.log 的所有，删除前逐一询问
rm -i *.log



###4.cp 命令 —n 和 -u的区别

-n, --no-clobber：不覆盖既有文件；
-u,--update：使用这项参数后只会在源文件的更改时间较目标文件新时或是名称相互对应的目标文件并不存在时，才复制文件

###5.找你的用户目录下面的所有py文件,ls -l 查看他们的属性,然后把这些结果输入到一个文件之中
ls -l *.py >test1 


###6.使用ls查看根目录 并且每行显示3个信息


###7.查看所有进程信息,只查看前3行
ps  |head -n 4


###8.分析以下问题,并给出解决方案

###Mount is denied because the NTFS volume is already exclusively opened.
###The volume may be already mounted, or another software may use it which could be identified for example by the help of the 'fuser' command.


###9.ssh 服务端口是多少,ssh免密登录方式的原理是什么

###10.权限755代表什么权限,如果我想把所有的w权限去除应该使用什么命令
chmod -w 文件


