# git是什么
Git是分布式版本控制软件

仓库存放所有的版本，本地也存放所有的版本，提高系统的健壮性。集中式版本控制软件是一个服务端仓库存放所有版本，本地只存放一个版本


# Git安装

Windows：
1. 下载安装包，默认安装
2. git --version：查看git版本

linux：
yum install git

# Git配置
如果没有配置，commit时会报错

配置命令：配置用户名和邮箱
```git
git config --global user.email "邮箱"
git config --global user.name "名字"
```

# Git知识
## Git三大区域
+ 工作区：
    两种文件状态：已管理文件（生成了版本）和新增/修改文件（红色）
+ 暂存区：
    通过`git add`添加的文件都在暂存区（绿色），可回滚、可提交版本
+ 版本库：
    通过`git commit`提交的版本

# Git使用
## 基础
版本控制（Git管理文件夹）步骤：
1. 进入要管理的文件夹
2. 初始化：`git init`
3. 管理：
    + `git status`：检测文件状态
    + `git add 文件/.` ：管理文件或全部文件，管理起来的文件会变绿
    
    三种状态的变化：
    + 红色：新增的文件/修改了原老文件
    + 绿色：通过`git add`命令之后被git管理起来的文件
    + 查询不到：通过`git commit`生成了版本
4. 生成版本：`git commit -m "描述信息"`：生成一个版本
5. 查看版本：`git log`

## 回滚
回滚到以前的版本到工作区(本地-管理状态)：`git reset --hard 版本号`。版本号为每次commit时生成的，通过`git log`命令查看

向前滚动版本(将版本库的某个版本替换成工作区)：`git reset --hard 版本号`。版本号通过`git reflog`命令查看

将版本库某个版本回滚到暂存区：`git reset --soft 版本号`

从暂存区回滚到工作区（绿色→未管理红色）：`git reset HEAD`

从版本库回滚到工作区(未管理状态红色)：`git reset --mix 版本号`

将改动的文件改回被管理时状态（未管理状态红色→干净状态）：`git checkout -- 文件`

## 分支

开发新功能时可以另开新分支开发

紧急修复线上bug的思路：另开一个新分支去修复主线上的bug，不影响别的分支上的开发功能，完成修复之后合并到主分支(master)。合并新功能时会有冲突，新功能分支上的bug没有被修复，需要去修改文件，之后再add和commit

+ 查看所处分支：`git branch`
+ 创建分支：`git branch 分支名`
+ 切换分支：`git checkout 分支名`
+ 合并分支：先切换会主分支，使用命令`git merge 分支名`合并分支
+ 删除分支：`git branch -d 分支名`

