# MyProject2
Test.
第一章 配置github

第二章 利用github管理文档
（1）最近需求一个个人的代码管理工具，之前没有接触过Github，所以想通过这个机会学习一个Github，比较囧的是，刚刚注册就被封了，幸好有国内大牛们的声援，使得Github重新解封。今天下午看了一些Github相关的文档，配置了一下，总结成博客。
          对github的了解还处于入门阶段。希望各路大神指点迷津……

（2）这里直接给出工程性的配置文档，对于github的详细中文讲解，可参考：http://opengit.org/progit/01-introduction 。文档中详细的解释了github常用的命令，以及github的工作原理，强烈推荐观看！
 S1：在github网站上注册成功后，会提示“Create   a   Repository”，创建一个Test的项目。
 S2:   创建完成后，会跳转到这个页面

  Test版本库的位置是  https://github.com/cscmaker/Test.Git 。我们需要在本地创建镜像的时候需要从此处获取，而且我们的代码管理也是在这个地方进行在线管理。

（3）本地安装Github
          系统版本是Ubuntu 11.10
          安装Github有两种方式：
          A：在Github中下载源文件，自己安装
          B：终端中输入  sudo  apt-get install  git-core

（4）按照上图中的“Create a new repository on the command  line”中的命令，创建本体的镜像，并且提交。
           命令分别为：git的文件状态跟集中式的版本管理系统有区别，具体请看上面推荐的文章。
[plain] view plain copy
touch  README.md       #创建一个关于这个代码库的说明文档       
git   init    #初始化git，主要是将当前文件夹初始化为代码库  
git  add README.md    #将README文件加入到本地版本管理中  
git commit -m "first commit" #提交修改  
git remote add origin https://github.com/cscmaker/Test.git  
git push -u origin master#将修改push到版本库中  

（5） 刷新github网站中你的Test库中会出现README.md的文件。
第三章 利用github协作
-----------------------------------------这是分割线！！！！！
