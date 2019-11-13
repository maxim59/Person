# Github

​			github是一个基于git的代码托管平台

#### 			注册帐户以及创建仓库

#### 			安装Github

#### 			 配置Git

#### 			  检出仓库

​						创建一个本地仓库的克隆版本：

​						

```git clone	/path/to/repository```

如果是远端服务器上的仓库,命令如下：

``git  clone  username@host :/path/to/repository``

#### 工作流

本地仓库由git维护的三棵"树"组成。

​	第一棵树是你的	`工作目录`，它持有实际文件

​	第二棵树是`暂存区（Index）` ，它就像个缓存区域，临时保存你的改动

​	第三棵树是`HEAD`,它指向你最后一次提交的结果

#### 推送改动

将在本地仓库中的结果即`HEAD`提交到远端仓库：

​	git puth prigin master

如果没有克隆现有仓库，并欲将仓库连接到某个远程服务器，可以使用如下命令进行添加：

​	git	remote	add	origin		<server>

#### 分支

​		分支是用来将特性开发绝缘开来的。在你创建仓库的时候，master是“默认的

分支。在其他分支上进行开发，完成后再将它们合并到主分支上

​		创建一个分支，并切换过去：

​				git 	checkout	-b 分支名称

​		切换回主分支：

​				git	checkout	master

​		删除分支：

​				git branch	-d	分支名称

​		将分支推送到远端仓库（如若不然，该分支就是不为他人所见的：）

​				git	push	origin	<branch>

#### 更新与合并

更新本地仓库至最新改动：

​		git pull

#### 标签

​	创建标签：git	tag	标签名	想要标记的提交ID的前10位字符

​	获取提交ID：git log

#### 替换本地改动

​		操作失误，需要替换掉本地改动时：

​			git	checkout	- -	<filename>

​			此命令会使用HEAD中的最新内容替换掉你的工作目录中的文件。已添加到暂存区的改动以及新文件都不会受到影响。

​			如想丢弃在本地的所有改动和提交，可以到服务器上获取最新的版本历史，并将你本地主分支指向它：

​			git	fetch	origin

​			git	reset	- - hard	origin/master

#### 实用小贴士

内建的图形化git：	gitk

彩色的git输出：git	config	color.ui	true

显示历史纪录时，每个提交的信息只显示一行：git	config	format.pretty	oneline

交互式添加文件到暂存区：git	add	-i

