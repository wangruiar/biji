# **day 03**

## git

### 验证git是否安装成功：

#####         `git version`

### 查看是否配置成功：

##### 		`git config --list`

### 初始化当前文件夹为Git本地仓库：

##### 		`git init`  

### 跟踪所有改动过的文件:

#####    	`git add .`

### 传输文件

### 	1.暂存需要提交的文件：

##### 		**`git add a.txt`**

### 	2.查看目前代码的修改状态:

##### 		`git status`

### 	3.提交已暂存的文件

### 		`git commit -m“首次提交”`

##### 		`git remote add origin https://github.com/sun3155003246/-.git`

**git clone -b 分支名 网站;**

### 	4.同步到服务器

###  	  `git push -u origin master`

#### 创建切换分支

### 	`git checkout -b 分支名`    

#### 查看当前所在分支

##### 	`git branch`   

####  切换分支

### 	`git checkout 分知名`  

#### 合并指定分支到当前分支

##### 	`git merge <branch>`

### 合并远程分支

**git merge origin/**

### 从远程获取最新版本到本地

### `git fetch -a` 

####   删除本地分支：

### `git branch -d 分支名（remotes/origin/分支名）`

####   强制删本地：

#### `git branch -D 分支名`

####   删除远程分支：

#### `git push origin --delete 分支名（remotes/origin/分支名）`

