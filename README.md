# MyProject2
Test.
第一章 配置github
github是程序猿的代码托管平台，也是基于git的开源分布式版本控制系统。然而，当你登陆github官网时，它并没有为你准备一个很好的代码上传的系统，这是因为它是基于git的分布式版本管理系。那么，如何更快更有效的将本地代码上传到github呢？首先，我们需要在本地安装git，这样才能在本地环境中使用git命令行，（例如：$ git add index.html）其次是要连接到你的github账户上，这样才能把你的代码文件上传上去，而每一次的更改都会形成一个版本记录，这样对团队协作是很有帮助的。

安装 Git

这里主要讲的是mac系统，windows也是一样的，只不过mac是在终端下进行，而windows是在cmd下进行的。安装git，这里推荐安装Apple公司的Xcode，Xcode集成了Git，最新版的Xcode已经默认安装好了git。完成安装之后，就可以使用 git 的命令行工具。

当然，首先你需要注册一个github账户。

配置帐号信息

在cmd或者终端下输入以下命令行：

git config --global user.name trigkit4git config --global user.email 345823102@qq.com

当然，这是我的账户信息，你需要将他们换成你自己的。

创建本地ssh

这是一种传输代码的方法，速度快又安全。SSH 是目前较可靠，专为远程登录会话和其他网络服务提供安全性的协议。

在终端或cmd输入以下命令行：

ssh-keygen -t rsa -C "1134431822@qq.com"

当然，邮箱依然换成你注册github时所用的邮箱。
路径选择 : 使用该命令之后, 会出现提示选择ssh-key生成路径, 这里直接点回车默认即可, 生成的ssh-key在默认路径中;密码确认 : 这里我们不使用密码进行登录, 用密码太麻烦;就一路回车下去

将ssh配置到GitHub中

在mac os X 下前往文件夹，/Users/自己电脑用户名/.ssh。

windows应该是（C:\Documents and Settings\Administrator\.ssh （或者 C:\Users\自己电脑用户名\.ssh）中）。

然后用记事本打开id_rsa.pub，将里面的全部代码复制到github的SSH中。

id_rsa.pub 文件内容 :

ssh-rsa AAAAB3NzaC1yc2EAAAADAQABAAABAQDS0qLtpontavr43AQntX4oBOsg2R3QlWubMYvfgJsIDX6NWd5RaIDLBLEMwIFLDcpvpQKvk5S/bTy4vTuWqeY6fkQ/tZBKksQn1WuYDcSfjLF8BuPMfdkboTh9NaKESKnsiWdranEVbmB5vOAHm8T+HFGdzG7Tz4ygzCnTwvdpBYrd/4jgeazws2d7CuMeuyb+FxdDTQy9YmJJm+82ypfR//bLyzRJo3SYadnPO3VdOAZCO1Isky+p/0nNN/obC4t2y2+oHBAqJV9h37f9S8UShgDmZoVLicRi4poni0i70xj+t/hnOsT8fmEc+vM9USyN+ndawz2oWjikKgln1jOB 1134431822@qq.com

登陆github网站，点击Settings——SSH keys——点击右侧的Add SSH key ，接下去你懂得。



验证是否配置成功 :复制如下代码:

ssh -T git@github.com

然后出现如下信息：

Warning: Permanently added the RSA host key for IP address '192.30.252.131' to the list of known hosts.Hi hawx1993! You've successfully authenticated, but GitHub does not provide shell access.

验证时可能让你输入YES，当出现以上信息时，说明配置成功，可以连接上GitHub;

创建版本库

第一步，在本地创建一个版本库，代码如下：

$ mkdir test   #test是你的文件夹的名字$ cd test     #进入test所在目录$ pwd        #pwd命令用于显示当前目录    /Users/trigkit4/test #这是在我的Mac上的目录

第二步，通过git init命令把这个目录变成Git可以管理的仓库：

$ git init

然后会输出以下信息：

Initialized empty Git repository in /Users/trigkit4/banner/.git/

这里的.git目录是Git用来跟踪管理版本库的，默认是隐藏的。

第三部，接着，在github上创建一个你自己的new repository，然后下一步，

mkdir test  cd test   git init    # initialize your git repository  touch README  # create a file named README  git add README    # add README to cache  git commit -m 'first commit'  # commit your files to local repository  

然后我们将本地的文件传送至github中，使用如下命令：

git remote add origin https://github.com/yourname/test.git  git push -u origin master  

从现有仓库克隆

git clone git://github.com/yourname/test.gitgit clone git://github.com/yourname/grit.git mypro#克隆到自定义文件夹

本地

git add *#跟踪新文件rm *&git rm *#移除文件git rm -f *#移除文件git rm --cached *#取消跟踪git mv file_from file_to#重命名跟踪文件git log#查看提交记录git commit#提交更新git commit -m 'message'git commit -a#跳过使用暂存区域，把所有已经跟踪过的文件暂存起来一并提交git commit --amend#修改最后一次提交git reset HEAD *#取消已经暂存的文件git checkout -- file#取消对文件的修改（从暂存区去除file）git checkout branch|tag|commit -- file_name#从仓库取出file覆盖当前分支git checkout -- .#从暂存区去除文件覆盖工作区

分支

git branch#列出本地分支git branch -r#列出远端分支git branch -a#列出所有分支git branch -v#查看各个分支最后一个提交对象的信息git branch --merge#查看已经合并到当前分支的分支git branch --no-merge#查看为合并到当前分支的分支git branch test#新建test分支git checkout test#切换到test分支git checkout -b test#新建+切换到test分支git checkout -b test dev#基于dev新建test分支，并切换git branch -d test#删除test分支git branch -D test#强制删除test分支git merge test#将test分支合并到当前分支git rebase master#将master分之上超前的提交，变基到当前分支
第二章 利用github管理文档

第三章 利用github协作
-----------------------------------------这是分割线！！！！！
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
