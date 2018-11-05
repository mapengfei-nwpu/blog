

### 学习如何使用git

* git的初始设置

```bash
#设置用户名和密码
git config --global user.name "pengfei"
git config --global user.email "merrily@live.com"
#查看所有设置
git config --list
#查看某项参数
git config user.name
git config user.email

```

* git仓库的ssh密钥

```bash
#生成密钥。还不知道这些参数什么意思
ssh-keygen -t rsa -C "merrily@live.com"
#会生成两个文件id_rsa和id_rsa.pub。前者不动，后者复制到GitHub上。
```



* 远程仓库的设置

```bash
#创建一个git仓库，会出现 .git 文件夹
git init
#设置远程仓库，remote信息不是全局的，而是存储在仓库里
#格式为 git remote add 远程仓库名 远程仓库地址(GitHub中的下载地址)
git remote add github git@github.com:mapengfei-nwpu/bubblepoint.git
#列出远程仓库的信息。有两种方法
git remote
git remote -v
#移除远程仓库
git remove github
#与远程同步有三个指令，clone，push，fetch，pull
#我还不知道怎么用
```

* 远程仓库与本地仓库的同步(参考了这篇[博客](https://blog.csdn.net/u012575819/article/details/50553501))

```bash
#为了使本地仓库与远程仓库不矛盾，要么使用分支，要么每次本地修改后都提交到远程。
#远程仓库刚创建时，是与本地仓库毫无联系的仓库，必须进行关联
#远程仓库创建后，首先fetch远程仓库的信息到本地
git fetch github master
#然后远程分支remotes/github/master和本地的master合并。合并在当前的master分支。
#如果远程仓库创建时不是空的 则合并可能会失败。因为远程文件和本地文件矛盾。
#首次合并需要加后面的参数 因为这两个仓库原本是独立的
git merge remotes/github/master --allow-unrelated-histories
#合并以后再推送到服务器
git push github master:master
#以后只要拉取远程仓库就行了。相当于fetch+merge 与当前支合并。
git pull github master
```

* 基本的本地操作

```bash
# 提交所有修改到暂存区 包括删除、创建、修改 
git add .
# commit 提交修改. 已经暂存了的文件才能被修改
git commit -m "修改说明"

```

* 打标签

```bash
#打标签其实就是给id加了一个别名。
#查看标签所有标签
git tag
#打标签默认是打在当前分支最近一次commit上的。
git tag v1.0 -m "第一个版本"
```



