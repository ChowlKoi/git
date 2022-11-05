# Git

---

Git是一个开源的分布式版本控制系统，可以有效、高速地处理从很小到非常大的项目版本管理。也是Linus Torvalds为了帮助管理Linux内核开发而开发的一个开放源码的版本控制软件。

[锚点一](#table1)

# Git的发展历史

---

# Git的第一次下载的一些配置

---

1.在官网先下载安装git

2.安装完成后打开git，设置一些基础常用的配置

```
# 添加git的用户名与邮箱
git config --global user.name "chowlkoi"
git config --global user.email "ck@chowlkoi.com"
# 查看配置信息
git config --list -> 查看所有git配置信息
git config --global --list -> 查看本地用户配置信息
```

3.在github上添加ssh公钥

```
# 在指定目录下添加ssh公钥
ssh-keygen -t rsa -> 创建公钥并设置安全密钥类型（rsa）
# 在将生成的.pub的内容上传至github中

# 如遇到一下报错
OpenSSL SSL_read: Connection was reset, errno 10054
# 先检查一下hosts文件是否有问题，没有问题就输入一下代码
git config --global http.sslverify "false"
# 然后再执行git操作测试一下
```



# Git的使用方法

---

## 一.Git使用过程

1.先使用**git init**来初始化本地仓库

```
git init -> 主要用于初始初始化本地仓库，建立一个全新的仓库
```

或者去github克隆一个仓库放到本地

```
git clone [url] -> 获取github库中的仓库下载到主机中
```

2.对文件根据自己需求进行操作

3.将添加/修改后的文件进行本地提交

```
git add . -> 添加所有文件到暂存区
git status -> 查看所有文件状态
git commit -m "第一次更新" -> 提交暂存区中的内容到本地仓库 -m提交信息
git status -> 提交完成后再看看文件状态，如果没有文件要提交就说明提交完成，反之则未提交
```

4.选择需要提交到Github的文件内容（做筛选）

```
在所要提交的项目中创建 .gitignore 文件
# 为注释
*.txt -> 忽略项目中所有.txt结尾的文件
!lib.txt -> lib.txt此文件不被忽略，一定会上传
/temp -> 只忽略temp中的文件，temp中的子文件不会忽略
temp/ -> 会忽略temp中的所有文件
temp/*.txt -> 忽略temp中本目录所有.txt结尾的文件，但不包含子目录.txt结尾的文件
```

```
# 项目中一些常用需要忽略上传的文件
*.class
*.log
*.lock

# Package Files 
*.jar
*.war
*.ear

# idea
.idea/
*.iml
*.ipr
*.iws
.classpath
.project
.settings/
bin/
```

5.将修改后的项目提交到github中

第一种自己手动写代码提交

```
git push -> 将本地提交的项目推送到远程仓库中
```

```
# Git分支
git branch -> 列出所有本地分支
git branch -r -> 列出所有远程分支
git branch [branch-name] -> 新建一个分支，但依然停留在当前分支
git checkout -b [branch] -> 新建一个分支，并切换到该分支
git merge [branch] -> 合并指定分支到当前分支
git branch -d [branch-name] -> 删除分支
git push origin --delete [branch-name] -> 删除远程分支
git branch -dr [remote/branch] -> 删除远程分支
```

第二种如果用的IDEA可在项目中直接提交

​	1.将git内容全部拷贝到项目目录中

​	2.可使用IDEA可视化工具进行提交
