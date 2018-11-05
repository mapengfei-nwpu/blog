

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



* git仓库的使用

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

* 基本的本地操作

```bash
# add  暂存操作
# commit 提交修改。已经暂存了的文件才能被修改。

```



