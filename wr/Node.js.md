# Node.js

简单的说 Node.js 就是运行在服务端的 JavaScript。

Node.js 是一个基于Chrome JavaScript 运行时建立的一个平台。

### 安装步骤：

1. 安装curl  ->  sudo apt install curl
2. 切换到主目录 -> cd ~
3. 使用`curl`为你的首选版本安装脚本，确保使用首选版本字符串`，我用的是Node.js v10.x，`如果你用的版本是Node.js v6.x，则将10.x替换为6.x， 如果你用的版本是Node.js v8.x，则将10.x替换为8.x。（下面命令中的斜体内容即10.x根据自己的首选版本进行修改）-> curl -sL https://deb.nodesource.com/setup_\*10.x\* -o nodesource_setup.sh
4. 使用gedit查看脚本 -> gedit nodesource_setup.sh
5. 在sudo下运行脚本 -> sudo bash nodesource_setup.sh
6. 再次重新安装Node.js  -> sudo apt install nodejs
7. 查看Node.js版本 ->  nodejs -v
8. 查看npm版本 -> npm -v
9. 为了使一些`npm`包能够工作（例如那些需要从源代码编译代码的包），你需要安装`build-essential`包 -> sudo apt install build-essential

### 第一个Node.js程序：Hello World!

1. 打开终端 -> vim helloworld.js -> console.log("Hello World"); ->wq(保存退出)

2. node helloworld.js(运行)

3. ```
   $ node
   > console.log('Hello World!');
   Hello World!
   ```