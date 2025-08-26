**Git是什么？**

Git是目前世界上最先进的分布式版本控制系统（没有之一）。

版本控制系统：可以记录你过去的文件的版本，同时可以允许多人同时对同一份代码或文件进行修改，他会自动合并

分布式:分布式版本控制系统根本没有“中央服务器”，每个人的电脑上都是一个完整的版本库，这样，你工作的时候，就不需要联网了，因为版本库就在你自己的电脑上。既然每个人电脑上都有一个完整的版本库，那多个人如何协作呢？比方说你在自己电脑上改了文件A，你的同事也在他的电脑上改了文件A，这时，你们俩之间只需把各自的修改推送给对方，就可以互相看到对方的修改了。

分布式版本控制系统通常也有一台充当“中央服务器”的电脑，但这个服务器的作用仅仅是用来方便“交换”大家的修改，没有它大家也一样干活，只是交换修改不方便而已。

**github是什么?**

GitHub 是一个基于 **Git** 的代码托管平台，同时也提供协作开发和版本管理功能。简单来说，它是程序员和团队用来管理、分享和协作开发代码的“社交平台 + 仓库”。



二者简单的使用，适用于小白

首先你需要注册一个github的账号，这里可能需要科技，你可以去网上找找

之后下载git 这里仅有Windows 上的方法：[Git - Downloading Package](https://git-scm.com/downloads/win) 直接进入官方网站下载即可，安装完成后，在开始菜单里找到“Git”->“Git Bash”，蹦出一个类似命令行窗口的东西，就说明Git安装成功。

![image-20250826171847241](%E5%9B%BE%E7%89%87/image-20250826171847241.png)

1.之后新建一个文件夹或者在已有的文件夹中操作，在文件夹中打开命令框（在上面的路径框中输入cmd即可）或者打开命令框后，通过cd 路径，切换到该目录即可

之后在命令框输入

~~~java
git init 
~~~

将该目录设为git可以管理的仓库

2.

之后在目录中创建一个readme.txt文件（其他也可以）

用命令`git add`告诉Git，把文件添加到仓库

~~~java
git add readme.txt
git add . //添加所有的文件到仓库
~~~

执行上面的命令，没有任何显示，这就对了，Unix的哲学是“没有消息就是好消息”，说明添加成功。

第二步，用命令`git commit`告诉Git，把文件提交到仓库：

~~~
$ git commit -m "wrote a readme file"
[master (root-commit) eaadf4e] wrote a readme file
 1 file changed, 2 insertions(+)
 create mode 100644 readme.txt
~~~

git commit -m " 这里面是你写的提交说明''

###  三个区域的角色

1. **工作区（Working Directory）**
   - 你正在编辑的文件所在的位置，就是你电脑上的项目文件夹。
   - 修改文件只是改了工作区的内容，Git 还不知道你要提交哪些修改。
2. **暂存区（Staging Area / Index）**
   - 用来“准备提交”的地方，你告诉 Git：我想把哪些修改放进下一次提交。
   - `git add` 就是把工作区的改动添加到暂存区。
3. **本地仓库（Local Repository）**
   - 真正记录项目历史的地方，每一次提交（commit）都会生成一个快照保存在本地仓库。
   - `git commit` 就是把暂存区的内容保存到本地仓库，形成一个新的版本。



将本地中文件同步到github中

第一步打开你的github 在左上角有一个new repo 点击它

![image-20250826173437251](%E5%9B%BE%E7%89%87/image-20250826173437251.png)

创建一个新的仓库

![image-20250826173548806](%E5%9B%BE%E7%89%87/image-20250826173548806.png)

除了名字其他的不用该

默认创建即可

之后再本地命令框

```plain
git remote add origin git@github.com:michaelliao/learngit.git
```

~~~java
git remote add ssh  //后面是仓库的ssh地址
~~~



请千万注意，把上面的`michaelliao`替换成你自己的GitHub账户名，否则，你在本地关联的就是我的远程库，关联没有问题，但是你以后推送是推不上去的，因为你的SSH Key公钥不在我的账户列表中。

添加后，远程库的名字就是`origin`，这是Git默认的叫法，也可以改成别的，但是`origin`这个名字一看就知道是远程库。

下一步将本地仓库的所有内容推送到远程的仓库：

~~~
git push -u origin master
~~~

把本地库的内容推送到远程，用`git push`命令，实际上是把当前分支`master`推送到远程。

由于远程库是空的，我们第一次推送`master`分支时，加上了`-u`参数，Git不但会把本地的`master`分支内容推送的远程新的`master`分支，还会把本地的`master`分支和远程的`master`分支关联起来，在以后的推送或者拉取时就可以简化命令。

~~~java
master代本地的要推送的分支
如果你在其他分支上工作，比如 dev，就要写成 git push origin dev
~~~

总结

~~~java
git init //创建本地仓库
git add . //将本地文件添加到暂存区
git commit -m " "  //将暂存区的文件加入到本地仓库 形成一个新的版本
    
git remote add  origin（起的远程仓库名）  ssh //给本地仓库关联远程仓库。
git push -u 远程仓库名 推送的分支名
git push -u origin master
    //完成
~~~

遇到的问题ssh密钥进行github身份验（github不允许你访问仓库）：对应的视频：[ssh密钥进行github身份验证，ssh公私密钥使用详解，github密钥配置与使用，git密钥使用详解，git入门教程_哔哩哔哩_bilibili](https://www.bilibili.com/video/BV1dV411G77N/?spm_id_from=333.1007.top_right_bar_window_history.content.click&vd_source=127adf6855a90faec2902ad991db5dd1)

简单说说

右键打开git bash 在里面输入

~~~java
ssh -keygen //之后一直enter即可
    之后在C:\Users\86159\.ssh电脑的这个目录找到 生成的私钥（id_rsa）和公钥（id_rsa.pub），打开公钥复制
        之后将他添加到github中的ssh管理中
~~~

~~~java
//出现这个问题的原因
github身份验证未通过
    通过公钥与私钥的配对实现验
~~~

