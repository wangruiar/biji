# Day03

- 在Git社区创建自己的账号并创建一个仓库

- 安装使用Git仓库

1. 打开终端  输入命令：sudo apt-get install git
2. 验证git是否安装成功：git version
3. 创建目录：mkdir  目录名 
4. 打开目录：cd 
5. 初始化：git init 
6. 查询：ls 
7. 创建文件：touch 文件名
8. git config --global user.name"wangruiar" （git社区的账号）
9. git config --global user.email "1309029519@qq.com"（邮箱）
10. 查看是否配置成功，输入命令：git config --list 
11. 配置Git的私钥和公钥.密码为空.  输入命令：ssh-keygen -t rsa  -C "1309029519@qq.com"
12. 证书已经生成成功，进入指定路径下，输入命令：cd ~/.ssh/
13. vim打开Git社区的公钥证书：vim id_rsa.pub
14. 验证Git是否配置成功：ssh git@github.com
15. 退出：ssh:cd
16. 进入仓库：cd 库名
17. 创建一个叫做"feature_x"的分支，并切换过去：
    `git checkout -b feature_x`
    切换回主分支：
    `git checkout master`
    再把新建的分支删掉：
    `git branch -d feature_x`
    除非你将分支推送到远端仓库，不然该分支就是 *不为他人所见的*：
    `git push origin `

- 公共的仓库

1. 创建库:  mkdir 库名
2. 打开库：cd 库名
3. 设置为git仓库： git init
4. 创建文件：touch 文件名
5. 添加文件：git add 文件名（git add . 是添加全部文件）
6. 提交+注释： git commit -m "注释"
7. git remoteadd origin ...
8. git push -u origin master
9. 查看本地所以分支： git branch
10. 在Git社区给组员发科隆连接并发送邮箱邀请
11. 切换到新分支： git  checkout  -b 分支名
12. 查看本地所以分支： git branch
13. 创建库:  mkdir 库名
14. 打开库：cd 库名
15. 创建文件：touch 文件名
16. 添加文件：git add 文件名（git add . 是添加全部文件）
17. 提交+注释： git commit -m "注释"
18. 推送自己的分支：git push origin 支名：支名
19. 查看本地所以分支： git branch
20. 将远程最新内容拉到本地：git fetch -a
21. 一个一个合并：git merge origin/组员分支名
22. 查看：ls
23. 查看当前状态：git  status
24. 切换到master分支：git checkout master
25. 查看本地所以分支： git branch
26. 在自己master中合并自己支名：git merge 支名
27. 查看本地所以分支： git branch
28. 添加全部文件：git add .
29. 提交+注释： git commit -m "注释"
30. 推送的远程仓库：git push origin master:master