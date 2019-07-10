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

#### base command

#####  cd

- `cd -`: 回到上次工作目录

##### mkdir

- `-p`:可以一次建立多个目录

##### cp  rm

- `-r`:递归删除
- `rm -rf`:删除目录名

##### grep

- `-I`：不区分大小写
- `-n`：显示匹配行以及行号
- `grep "h" ./ -r | less`:配合管道将其转到less（分页器）

##### find

- `-name`: 支持通配符`*`和`？`  如`find ./ -name test*.c`

##### ln

- `-s`:建立连接符号

##### tar

- `-c` : 打包
- `-x`：解包
- `-f`: 普通文件



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
  
   





