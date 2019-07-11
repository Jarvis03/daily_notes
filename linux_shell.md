## linux base

### 1. linux shell

#### ubuntu system

- 查看版本：`cat /etc/issue`
- 查看架构：`uname -m`
- 查看内核版本： `uname -r`

#### terminal

- `ctrl + alt + t` : 创建新终端

- `ctrl + shift + n` : 在相同路径下再开启新终端（必须有终端）

- `ctrl + shift + t`: 左右分屏打开同路径终端（必须有终端）

- 关闭终端：`exit` 或 `ctrl + d`

- `linux@ubuntu：～$` :如下表

  | liunx  | @ubuntu:| ~    | $    |
  | ------ | -------- | ---- | ---- |
  | 用户名 | 主机名   | 路径：`～`表示`home/`，`/`表示`root/` | 用户权限:`$`普通用户，`#`管理员 |



#### pack  manager

ubuntu 支持Ded包管理工具，常用工具包括`dpkg`，`apt`

##### dpkg

本地离线安装

- `-i`: 安装debian软件包
- `-r`: 移除已安装软件包
- `-P`: 移除已安装软件包和配置文件
- `-L`: 列出安装的软件包清单

##### apt

1. `etc/apt/source.list`是apt镜像的地址文件

2.  `var/lib/apt/lists`存放apt本地软件包的索引文件

3. `var/cache/apt/archives` 是apt本地缓存目录

- `update`:下载更新软件包列表信息

- `upgrade`:系统中所有的软件包升级到最新

- `install`: 下载所需软件包并进行安装

- `remove`: 卸载

- `clean`：清楚下载的软件包

  
  
* `apt-get --reinstall install`:重新安装

* `apt-get --purge remove`:完全卸载
  
* `apt-get -f install`: 修复软件包的依赖关系
  
#### base command

多个命令一行书写使用`：`

一条命令多行书写使用`\`

#####  cd

- `cd -`: 回到上次工作目录

##### mkdir

- `-p`:可以一次建立多个目录

##### cp  rm

- `-r`:递归删除
- `rm -rf`:删除目录名


##### ln

- `-s`:建立连接符号

##### tar

- `-c` : 打包
- `-x`：解包
- `-f`: 普通文件

##### grep

`grep "string" * -nR`:当前目录下递归搜索

- `-I`：不区分大小写
- `-n`：显示匹配行以及行号
- `grep "h" ./ -r | less`:配合管道将其转到less（分页器）

##### find

`find 路径 -name filename`:从当前目录开始寻找指定文件

- `-name`: 支持通配符`*`和`？`  如`find ./ -name test*.c`

##### head 与tail

显示文件指定行：`head -line file | tail -1`

##### more 与 less

`q`:退出，less 支持字符查找：`/str`

##### wc

对文件内容进行统计

- `-c`: 字符数
- `-w`:单词数
- `-l`: 行数

##### cut

对字符串进行分割

- `-d`:指定分隔符
- `-f`:指定需要的区域

如截取`/etc/passwd`文件内的用户名：

`cat  /etc/passwd | cut -d ":" -f 1`

##### alias

定义别名

`alias listsoft = 'ls /var/cache/apt/archives'`

取消别名使用`unalias`

**配置文件**: `.bashrc` 、`.profile`

#### shell 基本配置

##### History

使用`history`命令可以将历史命令打印到终端，linux默认保存1000条历史记录，可以设置`HISTSIZE`来修改条数

 **永久修改** : 修改`、home/.bashrc` 的 HISTSIZE 并使用`source`命令使其生效

##### 环境变量

添加环境变量： `/etc/profile`中添加 `export PATH=/home/guo:$PATH`,然后使用`source`使其生效

##### 查看磁盘

如使用 `df -h` 查看各个磁盘，找到优盘，将其挂载到`/mnt`

如 `mount -t  vfat /dev/sdb4 /mnt`

##### 用户与组

- `/etc/passwd`可以识别用户清单，当用户登录时系统会查询这个文件

  `root: x: 1: 1:root,,,:/root:/bin/bash`

  | root   | x        | 1    | 1    | root,,,  | /root  | /binbash |
  | ------ | -------- | ---- | ---- | -------- | ------ | -------- |
  | 登录名 | 密码口令 | UID  | GID  | 个人信息 | 主目录 | shell    |

  

- `/etc/shadow`:加密的用户清单

- `/etc/group`:组名称和成员

  包含：组名，加密口令， GID，成员列表
  
  
  
  **常用命令**:
  
  `adduser`,`userdel`,`usermod`,`groupadd`,`groupdel`
  
##### 网络配置

`/etc/network/interfaces`文件可以进行配置，配置完成后使用`sudo /etc/init.d/networking restart`命令使其生效

  




