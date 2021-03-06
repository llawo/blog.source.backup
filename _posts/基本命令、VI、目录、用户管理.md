---
title: 基本命令、VI、目录、用户管理
date: 2016-07-21 21:07:12
categories:
- 学习笔记
- Linux
tags:
- linux的基本使用
---
此篇是linux的学习笔记：包含linux的基本命令、VI的使用、linux操作系统的目录介绍和系统的用户管理。
<!-- more -->
## 常用命令总结
#### 1、startx —— 进入图形界面
#### 2、shutdown -h now —— 立刻进行关机
#### 3、shutdown -r now —— 现在重新启动计算机
#### 4、reboot  —— 现在重新启动计算机
#### 5、logout —— 注销
#### 6、su - —— 切换成系统管理员身份
#### 7、ls -l —— 列表出文件[详细信息]：加a指列出所有包括隐藏的文件
#### 8、ls/dir —— 查看文件列表

## 常用命令 -指定运行级别
#### 1、0：关机
#### 2、1：单用户（类似安全模式）
#### 3、2：多用户状态没有网络服务
#### 4、==3：多用户状态有网络服务==（服务器常用）
#### 5、4：系统未使用保留给用户
#### 6、==5：图形界面==（常用）
#### 7、6：系统重启
常用运行级别是3和5，要修改默认的运行级别可改文件/etc/inittab的id:5:initdefault:这一行中的数字
##### 注：解决修改错误配置的方法
###### 在进入grub引导界面时，请输入e
###### 在选中第二行 输入e
###### 在最后输入 1 [单用户级别]（因为单用户模式不读取那个配置文件）

---
## Vi编辑器
#### 1、vi Hello.java
#### 2、输入i[进入插入模式]
#### 3、输入ESC[进入命令模式]
#### 4、输入:[wq保存退出 q!退出不保存]
#### 5、编译 javac Hello.java
#### 6、运行 java Hello

---
## Linux目录解析
#### 1、root：存放root用户的相关文件
#### 2、home：存放普通用户的相关文件
#### 3、bin：存放常用命令的目录
#### 4、sbin：存放要具有一定权限才可以使用的命令
#### 5、mnt：默认挂载光驱和软驱的目录
#### 6、boot：存放引导相关的文件
#### 7、etc：存放配置相关文件
#### 8、var：存放经常变化的文件
#### 9、usr：存放软件默认安装的文件夹

---
## Linux用户管理（只有拥有root权限的用户才可操作）
#### 1、useradd：添加用户 eg:useradd xiaoming
创建一个用户则在home目录下创建一个用户名的文件夹，用该用户登录则直接进入该文件夹
#### 2、passwd：设密码 eg:passwd xiaoming (如果不写用户名则给当前用户设密码)
#### 3、userdel：删除用户 userdel+用户名 eg:userdel xiaoming
#### 4、userdel -r：删除用户及用户主目录 eg:userdel -r xiaoming