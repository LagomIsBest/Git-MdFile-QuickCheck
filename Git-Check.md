## Git常用代码速查
>**索引**
- [Git的基本配置](#config)
  -  [命令代码](#config.1)
  -  [Git的相关配置文件](#config.2)
- [Git项目创建](#init)
- [远程仓库的增删查看](#remote)
- [各区域文件传输命令](#trans)
- [文件的状态及查看](#status)
- [Git的分支命令](#branch)
- [忽略文件的语法](#ignore)
  
>**<div id = "config">Git的基本配置<div>**

**<div id = "config.1">命令代码<div>**

- 查看配置(-l list)

  ```bash
  git config -l
  ```

- 查看系统自带配置

  ```bash
  git config --system --list
  ```

- 查看用户全局配置

  ```bash
  git config --global --list
  ```

- **<div id = "config.2">进行用户全局配置<div>**

  ```bash
  git config --global user.name [名字]
  git config --global user.email [邮箱]
  ```
$~~$**Git的相关配置文件**
$~~~~$(1) system系统类$~$Git\etc\gitconfig 
$~~~~$(2) global用户类$~~~$C:\user\administrator\.gitconfig
  
>**<div id = "init">Git项目创建<div>**

- 项目初始化

  ```bash
  git init
  ```

- 克隆自远程仓库

  ```bash
  git clone [url地址]
  ```
>**<div id = "remote">远程仓库的增删查看<div>**
- 查看远程库
  ```bash
  git remote -v
  ```

- 添加远程库
  ```bash
  git remote add [远程库简称] [url地址]
  #第一个远程库一般命名为origin
  ```

- 将指定的远程仓库从本地配置中移除
  ```bash
  git remote rm [远程库简称]
  #rm即remove
  ```

>**<div id = "trans">各区域文件传输命令<div>**
- [Git相关的区域说明，点击跳转](Git-WorkingPrinciple.md)
- 将工作区的文件添加到暂存区：
  ```bash
  git add [文件名/路径] #添加指定文件
  git add . #添加当前目录所有文件(除忽略文件)
  ```
- 将暂存区的文件提交到版本库：
  ```bash
  git commit -m "Commit message"
  #-m 表示附加一个提交信息
  ```
- 将本地仓库的文件提交到远程仓库：
  ```bash
  git push [远程库简称] [当前分支名称]
  #如 git push origin main
  ```
- 从远程仓库拉取更新到本地仓库：
  ```bash
  git pull [远程库简称] [分支名称]
  ```
- 版本库中的文件还原到工作区和暂存区
  ```bash
  git checkout [文件名/路径/分支名称]
  #该命令将版本库中的最新文件覆盖当前的工作区和暂存区
  ```
- 撤销对文件的修改：
  ```bash
  git restore [文件名/路径]
  #该命令将撤销文件的修改，使其恢复为最近一次提交时的状态。
  ```

- 将暂存区的文件回退到工作区
  ```bash
  git reset HEAD [文件名/路径]
  ```
- 查看文件修改的具体内容
  ```bash
  git diff [文件名/路径]
  ```

>**<div id = "status">文件的状态及查看<div>**
- [文件状态解释，点击跳转](Git-WorkingPrinciple.md)
  

- 查看所有文件状态

  ```bash
  git status
  ```

- 查看指定文件状态

  ```bash
  git status [文件名]
  ```

>**<div id = "branch">Git的分支命令<div>**
- 查看当前分支名称
  ```bash
  git branch -v
  git branch --show-current
  ```
- 列出所有本地分支

  ```bash
  git branch
  ```

- 列出所有远程分支

  ```bash
  git branch -r
  ```

- 新建一个分支，但仍然留在当前分支

  ```bash
  git branch [分支名称]
  ```

- 新建一个分支，并且切换到该分支

  ```bash
  git checkout -b [分支名称] #-b即branch
  git switch -c [分支名称]  #-c即create
  #两行代码2选1
  ```

- 删除分支

  ```bash
  git branch -d [分支名称]
  ```

- 删除远程分支

  ```bash
  git push [远程仓库的简称] --delete [分支名称]
  git branch -dr [remote/branch]
  #两行代码2选1
  ```

>**<div id = "ignore">忽略文件的语法<div>**

即.gitignore文件
- 空格不匹配任意文件，可作为分隔符，可用反斜杠转义
开头的文件标识注释，可以使用反斜杠进行转义
- ! 开头的模式标识否定，该文件将会再次被包含，如果排除了该文件的父级目录，则使用 ! 也不会再次被包含。可以使用反斜杠进行转义
- / 结束的模式只匹配文件夹以及在该文件夹路径下的内容，但是不匹配该文件
- / 开始的模式匹配项目跟目录
如果一个模式不包含斜杠，则它匹配相对于当前 .gitignore 文件路径的内容，如果该模式不在 .gitignore 文件中，则相对于项目根目录
** 匹配多级目录，可在开始，中间，结束
- ? 通用匹配单个字符
- *通用匹配零个或多个字符
- [] 通用匹配单个字符列表

