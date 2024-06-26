
# 一、首次使用
git为了区分不同用户的提交信息，会要求配置使用者的用户名和邮箱信息。
配置分为全局配置和特定配置。

## 1.1 全局配置
```bash
git config --global user.name "Your Name"
git config --global user.email "your.email@example.com"
```
## 1.2 设置特定仓库用户名和邮箱
```bash
cd /path/to/your/repository  # 进入到仓库所在的目录中
git config user.name "Your Name"
git config user.email "your.email@example.com"
```



# 二、 常用命令

```bash

#创建本地git仓库
git init

# 创建本地分支
git branch <branch>

# 删除本地分支
git branch -d <branch>

# 查看所有分支
git branch -a

# 切换到本地分支
git checkout <branch>

# 创建并切换到本地分支
git checkout -b <branch>

# 查看提交历史
git log

# 合并某个分支的代码到当前分支
git merge <branch>

# 撤销最近的提交
git reset HEAD^

# 撤销提交并删除更改
git reset --hard HEAD^

# 撤销某个提交并保留历史记录（创建一个新的提交来撤销指定提交中的更改，保留历史记录）
git revert <commit-hash>

```
> 切换分支时一定要保证当前仓库的状态不能是修改状态，要么是干净的，要么将当前的修改先暂存，切回该分支的时候再重新修改

# 三、 远程仓库

## 3.1 从远程仓库克隆代码（一般是用于下载代码，远程仓库有代码）
```bash
# 克隆远程仓库（例如 git clone http://192.168.10.6:3000/AMC/NewReposity.git）
git clone <url>
git clone <remote_name> <url>
```
> 远程仓库有多个分支时，克隆后本地只会创建一个默认分支，其它需要的本地分支需要自己创建
```bash
# 创建本地分支并跟随远程分支
git checkout -b <name> origin/<name>
```

## 3.2 已经有本地仓库，与远程仓库建立连接（一般是将本地的代码上传至新的远程仓库，远程仓库没有代码）
```bash
# 查看远程仓库信息
git remote -v

# 添加远程仓库
git remote add <remote_name> <url>

# 设置本地分支跟随远程分支
git branch --set-upstream-to=<origin>/<remote-branch> <local-branch>
```

## 3.3 推送代码到远程仓库
本地分支与远程分支是一一对应的，一般来说最好是同名的，防止混淆。
```bash

# 推动代码到远程（本地分支未跟随远程分支）
git push <remote-reposity> <branch> # 例： git push origin main

# 推动代码到远程，并设置该分支跟随远程分支
git push -u <remote-reposity> <branch> # 例： git push -u origin main

# 强制推送本地代码到远程,会直接覆盖远程仓库，如果没有对应远程分支，则会创建，慎用！一般第一次提交使用
git push -uf <remote-reposity> <branch> # 例： git push -uf origin main

# 推动代码到远程（本地分支已跟随远程分支）
git push  # 例： git push

```


# 四、 开发过程常用命令
```bash
#查看本地仓库状态
git status

# 添加要提交的修改
git add <file>

# 添加所有修改
git add .

# 放弃某个文件修改
git chekcout <file>

# 放弃所有修改(两条都可以)
git checkout .
git reset --hard HEAD

# 提交修改
git commit -m "comment"

# 添加并提交所有修改
git commit -a -m "comment"

# 推送代码到远程仓库（需要先关联远程仓库的分支）
git push

```

# 五、 git 客户端推荐--Fork
[下载地址](https://www.git-fork.com/)

# 六、 参考
[git教程](https://www.runoob.com/git/git-tutorial.html)

[分支管理](https://blog.csdn.net/qq_37974755/article/details/126304583)
