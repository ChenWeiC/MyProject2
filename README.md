# MyProject2
Test.
第一章 配置github

第二章 利用github管理文档

第三章 利用github协作

----------------------------------------------分割线
首先在github上创建一个repository项目，当然根据[Git版本控制教程 - Git远程仓库]自己可以随便将本地修改push到github上。
对于其它合作者，只要将其加入到项目合作者中来就可以了：打开repository，点击settings，选择collaborators，在搜索框中搜索合作者账号，然后add，这样项目合作者就可以push代码到项目中来了。

多人协作项目中的分支设置参考[Git分支处理]和[github 多人协作]。
这样之后就可以不用下面介绍的fork+pull request的方式了，省了项目主管的确认这一步。


从远程库克隆
先创建远程库(或者使用别人已有的远程库)，然后从远程库克隆
登陆GitHub > 创建一个新的仓库，名字***_workspace >Initialize this repository with a README可选可不选，选的话GitHub会自动为我们创建一个README.md文件，创建完毕后，可以看到README.md文件：
远程库已经准备好了，用命令Git clone克隆一个本地库：
$ git clone git@github.com:pplove/***_workspace.git
Cloning into '***'...
remote: Counting objects: 3, done.
remote: Total 3 (delta 0), reused 0 (delta 0)
Receiving objects: 100% (3/3), done.
$ cd ***
$ ls
README.md
如果有多个人协作开发，那么每个人各自从远程克隆一份就可以了。
Note:
1. git clone默认会把远程仓库整个给clone下来，但只会在本地默认创建一个master分支，如果远程还有其他的分支，此时用git branch -a查看所有分支
2. GitHub给出的地址不止一个，还可以用https://github.com/pplove/workspace.git这样的地址。实际上，Git支持多种协议，默认的git://使用ssh，但也可以使用https等其他协议。
使用https除了速度慢以外，还有个最大的麻烦是每次推送都必须输入口令，但是在某些只开放http端口的公司内部就无法使用ssh协议而只能用https。
3. clone下来的是一个目录，所以clone时的当前目录可以是根目录
4. colon的项目可以是别人github上的项目，不需要授权、密码等
