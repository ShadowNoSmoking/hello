# hello
## github托管静态页面测试
### git测试

***

#### 1. git clone

远程操作的第一步，通常是从远程主机克隆一个版本库，这是就要用**git clone**命令

`$ git clone <版本库地址>`

比如，克隆本人远程主机的hello版本库

`$ git clone https://github.com/tenterrain/hello.git`

该命令会在本机生成一个目录，与远程主机的版本库同名，如果指定不同的目录名，可将目录名作为**git 
clone**的第二个参数

`$ git clone <版本库地址> <本地目录名>`

**git clone**支持多种协议，如: http[s] ssh git ftp[s]等

***

#### 2. git remote

为了便于管理，Git要求每个远程主机必须指定一个主机名。**git remote**命令就用于管理主机名。不带选项的时候，**git remote**命令列出所有远程主机。

	$ git remote
	origin

使用**-v**选项，可以参看远程主机的网址。

	$ git remote -v
	origin  https://github.com/tenterrain/hello.git(fetch)
	origin  https://github.com/tenterrain/hello.git(push)

上面的命令表示，当前只有一台远程主机，叫做origin，以及它的网址。

克隆版本库的时候，所使用的远程主机自动被Git命名为**origin**。如果想用其他的主机名，需要用**git clone**命令的**-o**选项指定

	$ git clone -o hello https://github.com/tenterrain/hello.git
	$ git remote
	hello

上面的命令表示，克隆的时候，指定远程主机名为hello

**git remote show**命令加上主机名，可以查看该主机的详细信息。

`$ git remote show <主机名>`

**git remote add**命令用于添加远程主机。

`$ git remote add <主机名> <网址>`

**git remote rm**用于删除远程主机。

`$ git remote rm <主机名>`

**git remote rename**用于远程主机改名

`$ git remote rename <原主机名> <新主机名>`

***

#### 3. git fetch

一旦远程主机的版本库有了更新(Git术语叫做commit)，余姚将这些更新取回本地，这时就要用到**git fetch**命令。

`$ git fetch origin master`

所有取回的更新，在本地主机上都要用"**远程主机名/分支名**"的形式读取。比如**origin**主机的**master**分支，就要用**origin/master**读取，切换分支命令为**git checkout origin/master**。

**git branch**命令的**-r**选项，可以用来查看远程分支，**-a**选项查看所有分支。

	$ git branch -r
	origin/master
	$ git branch -a
	* master
	  remotes/origin/master

上面的命令表示，本地主机的当前分支是**master**，远程分支是**origin/master**。

取回远程主机的更新后，可以在它的基础上，使用**git checkout**命令创建一个新的分支。

`$ git checkout -b newBranch origin/master`

上面的命令表示，在**origin/master**的基础上，创建一个新分支。

此外，也可以使用**git merge**命令或者**git rebase**命令，在本地分支上合并远程分支。

	$ git merge origin/master
	# 或者
	$ git rebase origin/master

上面的命令表示在当前分支上，合并**origin/master**;
	