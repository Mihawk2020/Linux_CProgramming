## Start Up

### Git Settings

#### 下载安装

Git下载安装网站：https://git-scm.com/download

安装完成后，在开始菜单里找到Git -> Git Bash，蹦出一个命令行窗口说明Git安装成功。

> Git Bash命令行输入

```shell
git config --global user.name "Your Name"
git config --global user.email email@example.com
```

因为Git是分布式版本控制系统，所以每个机器都必须自报家门：你的名字和Email地址。
注意git config命令的--global参数，用了这个参数，表示你这台机器上所有的Git仓库都会使用这个配置。

#### 相关教程

- Git的官方网站：http://git-scm.com
- 廖雪峰的Git教程：https://www.liaoxuefeng.com/wiki/896043488029600
- Git的cheat sheet：https://gitee.com/liaoxuefeng/learn-java/raw/master/teach/git-cheatsheet.pdf

#### SSH Key

由于你的本地Git仓库和GitHub仓库之间的传输是通过SSH加密的，所以，需要一点设置SSH Key。

1. 打开Git Bash创建SSH Key。`ssh-keygen -t rsa -C "youremail@example.com"`
   替换自己的邮件地址，然后一路回车，无需设置密码。随后显示：

   ```shell
   Your identification has been saved in C:\Users\<用户名>/.ssh/id_rsa.
   Your public key has been saved in C:\Users\<用户名>/.ssh/id_rsa.pub.
   ```

2. 登陆GitHub右上角打开Settings，SSH and GPG keys条目，点击“New SSH Key”，
   填上任意Title，在Key文本框里粘贴id_rsa.pub文件的内容，点击Add SSH key。

为什么GitHub需要SSH Key呢？因为GitHub需要识别出你推送的提交确实是你推送的，而不是别人冒充的。Git支持SSH协议，所以GitHub只要知道了你的公钥，就可以确认只有你自己才能推送。当然，GitHub允许你添加多个Key。假定你有若干电脑，你一会儿在公司提交，一会儿在家里提交，只要把每台电脑的Key都添加到GitHub，就可以在每台电脑上往GitHub推送了。

#### 文件提交

```shell
# clone github repo
https://github.com/Mihawk2020/Linux_CProgramming.git

# change directory
cd Linux_CProgramming

# add changed files
git add --all

# status of working directory
git status

# commit local changes
git commit -m "some text"

# publish local changes (enter username and password)
git push
```

