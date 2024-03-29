## Linux的简介与作用

### 		LAMP:Apache + MySQL + PHP

​		LAMP是指一组通常一起使用来运行动态网站或者服务器的自由软件

​		Linux，是一类Unix计算机操作系统的统称，是目前最流行的免费操作系统。代表版本有：debian,centos,ubuntu,fedora,gentoo等

​		Apache：网页服务器

​		MariaDB或MySQL,数据库管理系统（或者数据库服务器）

​		PHP，Perl或Python,脚本语言

		1. Apache 是LAMP架构最核心的Web Server，开源、稳定、模块丰富是Apache的优势。但Apache的缺点是有些臃肿，内存和CPU开销大，性能上有损耗，不如一些轻量级的Web服务器高效，轻量级的Web服务器对于静态文件的响应能力来说远高于Apace服务器。
  		2. Apache做为Web Server是负载PHP 的最佳选择，如果流量很大的话，可以采用Nginx来负载非PHP的Web请求

###        LNMP：Nginx + MySQL + PHP

​				Nginx一个高性能的HTTP和反向代理服务器，也是一个IMAP/POP3/SMTP代理服务器。

​				Nginx性能稳定、功能丰富、运维简单、处理静态文件速度快且消耗资源系统极少。

1. 相比Apache，Nginx使用更少的资源，支持更多的并发连接，体现更高的效率。
2. 作为邮件代理服务器：Nginx同时也是一款非常优秀的邮件代理服务器（最早开发这个产品的目的之一，就是作为邮件代理服务器）。
3. 反响代理可以根据url将请求转向于不同用途的集群，比如图片请求，转向图片服务器集群；视频请求，转向视频服务器集群。

### 	  Windows : IIS + SQLServer+ASP

​					图形界面，简单以上手，非开源，不免费，使用量比较少，多用于小型快速网站开发以及本地测试使用。

​					数据查询网站：<a>www.netcrraft.com ------>该网站数据是官方通过获取数据包数据踩点技术获得，准确性极高。	  </a>

总结：

Linxu特点：开源、稳定、安全、可靠

​				Windows：简单、易用、用户友好

## Linux界面

​		[root@localhost ~]#

​		 [当前登陆用户@主机名 当前所在目录]$

​		 当前用户：

​					Linux 管理员： root

​					Windows 管理员：adminstrator

​			主机名：

​						创建服务器时i起的名字，可以进行修改

​			当前目录：

​						～ 代表刚进入系统时的家目录，pwd命令显当前所在目录，如果出现目录了，表示当前的目录路径

​						管理员 /root

​						普通用户 /home/用户名

​			#号：

​						#  表示管理员用户

​						$  表示普通用户

## 目录操作命令

### 		命令基本格式

​						`命令[选项][参数]`

​						命令：根据不同命令实现不同的功能，必填

​						选项：适用于调整命令的功能，选填

​						参数：参数是命令的操作对象，如果可以省略参数，那是由于幽认参数

`ls`  list的缩写，显示目录下的的内容

`ls -l` longlist的缩写长格式显示的意思（缩略选项用一个减号，完整选项用两个减号）

​	`-rw-r--r--r. 1 root root 20734 11月 8 08:00 install.log` 

​	第一列：权限

​	第二列：引用次数

​	第三列：所有者

​	第四列：所属组

​	第五列：大小，默认单位是Byte

​	第六列：文件最后一次修改或是访问时间

​	第七列：文件名



`ls -hl` 人性化显示。文件大小显示为常见大小单位 K M G

`ls -a`  显示所有文件( 包含隐藏文件)

`ls -d`  显示目录本身，而不是里面的子文件

#### cd命令和tab快捷键

​		cd 切换所在目录

​		命令名称：cd

​				**`cd /home`**

​				**`cd /boot`**

​				`相对路径` ：参照当前所在目录，进行查找。先确定当前所在目录。

​				`绝对路径` ：从根目录开始指定，一级一级递归查找

#### Tab键：文件和命令补全

​				Linux可以进行命令补缺，自动填充后面的文件夹名称，如果有重复的名字，无法补缺，就按两下tab键，会告诉你到底需要补缺哪一个，同理，命令也是会补缺的

`推荐使用绝对路径是为了减少错误` 

​		扩展：

​					cd： 回到登录用户的家目录

​					cd -：进入上次操作的目录

​					cd .. ：进入上一级目录

​					pwd ：显示当所在目录

​					ctrl + l 	清屏

​					ctrl + c	强制终止

#### 常见目录

​			/			根目录

​			/root    管理员用户的家目录

​			/home  普通用户的家目录

​			/bin		命令保存目录（普通用户可以读取的命令）

​			/sbin	  命令保存目录（管理用户才能使用的目录）

​			/usr/bin/

​			/usr/sbin/



​			/boot		启动目录，启动相关文件

​			/dev			设备文件保存目录

​			/etc			配置文件保存目录

​			/lib			函数库的保存位置

​			/mnt			系统挂载目录，U盘

​			/media		挂载目录，光盘

​			/misc			网络存储盘



​			/tmp			临时目录

​			/proc			直接写入内存

​			/sys

​			/usr			系统软件资源目录，系统的重要目录

​			/var			系统相关文档内容，系统的可变内容，比如日志，随时变化

​			/var/log/  系统日志位置

#### 创建和删除目录

​	创建目录

​			`mkdir`	目录名

​			`mkdir test`	创建一个test目录

​			`mkdir -p admin/include/upload/` 递归建立目录

​	删除目录

​			rm	本身是删除文件用的，不加参数会报错，加 -r 以后就没问题

​			`rm` -rf 	文件或者目录

​					-r 	目录，删除目录

​					-f	  目录，强制

#### 文件操作命令

   1. 增：

      ​		`touch`	触摸  新建文件，修改文件的最后一次访问时间

      ​		touch 文件名

      ​	`注意：就算重复建立同样的文件名，它也不会报错，会给你修改最后一次的访问时间`

      `不允许同名的目录和文件同时存在`

      2.删：

      ​		rm -rf 文件名

      3.查：

      ​	`cat` 文件名  查看文件内容，不太适合太大的文件

      ​	`cat` -n	查看文件，同时显示行号

      ​		shift + PaUp		向上翻页

      ​		shift + Down		向下翻页

      ​	`more` 	文件名	分屏显示文件内容，就像分页

      ​	注意：空格也是向下翻页  b是向上翻页  q 退出

      

      #### 文件和目录均可操作的命令

        1. rm	删除

        2. cp     复制

           ​	cp	源文件	目标目录

           ​	例：`cp index.php /tmp/`	复制文件到目录

      		3.	-r   复制目录

              例：`cp -r www	/tmp/`		复制目录到目录

      		4.	mv  剪切或者改名   不论文件还是目录，都不需要加`-r` 选项

           ​    mv	源文件	目录位置

           ​	mv	index.php	admin.html		改名，同目录

              mv	admin.php	/tmp/	剪切



## 权限管理

​			命令：`alias` 	查看别名

​			1.权限位

​					第一位： 代表文件类型

​										`-`     普通文件

​										`d` 	目录文件

​										`l` 	  链接文件（快捷方式）

​					第二到第九位：权限标识

​								属主权限 u = user

​								属组权限 g = group

​								其他人权限 o = other

​								r		读 		4

​								w	  写		 2

​								x		执行	 1

​					2.修改权限

​								chomd	修改权限

​								`chomd  u + x  index.php`	给index.php的所有值 u加上x执行权限

​								`chomd u - x index.php`		给index.php的所有值u去掉 x 执行权限

​								`chomd g + w , o + w index.php` 	给index.php的所属组和其他人都加入写权限

​								`chomd  u=rwx 	index.php`	给index.php加入读、写、执行的权限

​								`chomd	755			index.php` 		---->	一般代表标准执行权限

​								`chomd	644		index.php` 		----->	一般表示标准只读权限

​								`chomd	777		index.php` 	----->	表示所有权限，注意：不可以给目录赋予777权限  

## 常用其他命令

#### 	查找命令  

​			whereis   命令名		查找命令的命令

​			find			搜索命令			

​				`按照文件名查找  	-name`

​						find	查找位置	-name	文件名

​						`按文件名查找`		find / -name	index

​						`按文件名查找，不区分大小写`		find / -iname index

​				`按照文件大小查找`	  

​						find	.	-size	27k		--->	表示正好是27k文件

​						find	.	-size	-27k		--->	表示小于27k文件

​						find	.	-size	+27k		--->	表示大于27k文件

​					`按照大小查找支持的单位有：b,	c,	w,	k,	M,	G(注意大小写)`  

​				`按照类型查找		-type`  	

​					f：普通		d:	目录			l:	链接

​					find	.	-type	d	按照文件大小查找

​					find	.	-type	f		搜索当前目录下所有的普通文件

#### 	文件内容查找命令

​			grep	"字符串"		文件名

​			-v	反响选择

​			-i	忽略大小写

​			例：		grep	-i	"root"	index.php	不区分大小写

​							grep	-p	"root"	index.php	取反，不含有