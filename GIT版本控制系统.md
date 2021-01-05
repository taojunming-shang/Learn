## GIT版本控制系统
> 版本控制系统：
> 1.记录历史版本信息（记录每一次修改的记录）
> 2.方便团队相互之间协作的开发
### 常用的版本控制系统
- cvs/svn：集中式版本控制系统
- git：分布式版本控制系统
  1.GIT工作原理
+ 工作区：我们能看到的，并且用来写代码
+ 暂存区：临时存储用的
+ 历史区：生成历史版本
  工作区——>暂存区——>历史区
  1.GIT的全局配置
> 第一次安装后，我们在全局环境下配置基本信息
```
$ git config --global -l   查看全局配置信息
$ git config -l   查看配置信息
配置全局信息 用户名和邮箱
$ git config --global user.name 'xxx'
$ git config --global user.eamil 'xxx@xx.xxx'
```
2.创建仓库完成版本控制
> 创建本地仓库git 
```
$ git init  创建仓库
//=>会生成一个隐藏文件夹“ .git”（这个文件夹不能删除，因为暂存区和离市区还有一些其他文件信息都在这里，删除以后就不是一个完整的git仓库
```
> 在本地编写完代码后（再工作区），把一些文件提交到暂存区
```
$ git add xxx 把某一个文件或者文件夹提交到暂存区
$ git add .   把当前仓库中所有最新修改的文件都提交到暂存区
$ git add -A
$ git status 查看当前文件的状态（红色代表在工作区，绿色代表在暂存区，看不见东西证明所有修改的信息都已经提交到历史区）
```
> 把暂存区内容提交到历史区
```
$ git commit -m'描述信息：本次提交内容的一个描述信息'
查看历史版本信息
$ git log
$ git reflog 包含回滚信息
```

### GIT和GIT-HUB

> GIT和GIT-HUB：https://www.github.com
>
> 一个网站（一个开源的源代码管理平台），用户注册后，可以在自己账户下创建仓库，用来管理项目的源代码（源代码基于git传到仓库中）
>
> 我们所熟知的插件、类库、框架等都是在这个平台上有托管，我们可以下载观看和研究研究源码等

1.Settings 用户设置

+ Profile 修改个人信息
+ Account 修改用户名
+ Security 修改密码
+ Emails 邮箱

2.创建仓库

new repository ->填写信息 ->Creat repository 

- public 公共仓库作为开源的项目
- private 私有仓库作为内部团队协作管理项目

Settings   ->删除仓库Delete this repository 

​               ->Collaborators 设置协作开发者

Code 可以查看历史版本信息和分支信息

3.把本地信息提交到远程仓库

```shell
//建立连接
查看本地仓库和那些远程仓库保持连接
$ git remote -v
让本地仓库和远程仓库穿件一个新的链接，origin是随意取的一个链接名（可以改成自己想要的）
$ git remote add origin [GIT仓库地址]
删除相关联信息
$ git remote rm origin
```

```
提交前最好先拉取
$ git pull origin master
把本地代码提交到远程仓库（需要输入GitHub用户密码）
$ git push origin master
```

```
$ git clone [远程仓库git地址] [别名：可以不设置。默认仓库名]
/*
   真实项目开发流程：
      1.组长或负责人先建立中央仓库
      2.小组成员基于：$ git clone 把远程仓库及默认的内容克隆到本地一份（解决了三个事情：初始化一个本地仓库 git init 、和对应的远程仓库保持关联 git remote add 、吧远程仓库默认内容拉取到本地 git pull
      3.每个小组成员写完自己的程序后，基于 git add /git commit'' 把自己修改的内容放到历史区，然后 git pull/ git push 把本地信息和远程仓库信息同步即可（可能涉及冲突的处理）
*/
```

### NPM

> node package manger： node模块管理工具，根据NPM我们可以快速安装。卸载所需要的资源文件（例如：jQuery，Vue，Vue-router...）
>
> 去NODE官网下载https://nodejs.org/en/ 下载node，安装以后NPM也跟着安装了
>
> $ node -v
>
> $ npm - v  出现版本好证明安装成功

#### 基于npm进行模块管理

> https://www.npmjs.com/ 基于npm是从npmjs.com平台下载安装

```
$ npm install xxx   把模块安装到当前项目下（node_modules)
$ npm install xxx -g  把模块安装到全局环境中
$ npm i xxx@1.00 安装指定版本号的模板
# npm view xxx versions > xxx.version.json  查看某个模块的版本信息（输出到指定的JSON文件中）
$ npm init -y 初始化当前项目的配置依赖清单
$ npm i xxx --save  把模块保存在清单生产依赖中
$ npm i xxx --save-dev  把模块保存在清单开发依赖中
$ npm install 跑环境，按照清单安装所需的模板

$ npm root -g 查看全局安装模板的目录
$ npm uninstall xxx
$ npm uninstall xxx -g 卸载安装过的模板


```

