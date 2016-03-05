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