## Git常用代码速查

>**Git的配置**

$~~$**命令代码**

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

- **进行用户全局配置**

  ```bash
  git config --global user.name [名字]
  git config --global user.email [邮箱]
  ```
$~~$**Git的相关配置文件**
$~~~~$(1) system系统类$~$Git\etc\gitconfig 
$~~~~$(2) global用户类$~~~$C:\user\administrator\.gitconfig
  
>**项目创建**

- 项目初始化

  ```bash
  git init
  ```

- 克隆自远程仓库

  ```bash
  git clone [url地址]
  ```

>**文件的状态及查看**

- 查看所有文件状态

  ```bash
  git status
  ```

- 查看指定文件状态

  ```bash
  git status [文件名]
  ```

>**忽略文件**


>**Git的分支说明**
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
