## GIT操作

### git基础

#### 1.git三区

```
工作区:	代表本地开发代码的地方
暂存区:	代表本地仓库暂时保管代码的地址
版本去:	代表代码进入本地版本控制
```

#### 2.git status查看文件状态

```
git status 
	查看文件的状态(查看文件位于哪个区)
红色:说明文件位于工作区
绿色:说明文件位于暂存区
没有体现:说明位于版本区
```

#### 3.将所有文件添加暂存区

```
git add ./*/-A 将所有工作区文件添加到暂存区中
```

#### 4.暂存区添加到版本区

```
git commit -m '注释信息'
	将暂存区中所有文件添加到版本区中
```

### 本地仓库操作

#### 1.初始一个化空的git仓库

```
git init
```

#### 2.linux指令

```
mkdir xx     创建xx文件夹
rm  xx       删除xx文件
rm -r xx     删除xx文件夹
cd  xx       切换目录
clear        清屏
ls           列出当前目录所有的文件
```

```
vi  xx    编辑xx文件(例如:index.js)
	i 		进入插入模式,才能编写代码
	esc		退出插入模式
	: wq  保存并退出文件
```

### 本地没有仓库,远程有仓库

#### 1.克隆远程库到本地

```
git clone 远程仓库地址

注意:克隆的库只有master分支,没有开发分支
git fetch origin  xxx1:xxx2
	xxx1:远程仓库分支名称
	xxx2:本地仓库分支名称
```

#### 2.本地工作区文件,提交到远程仓库保管

```
git add .
git commit -m 'xxxx'
git push -u origin master
	将master分支代码推送到远程仓库保管首次加上-u 后面就不需要了

```

### 本地有一个仓库,远程没有仓库

#### 1.创建本地仓库,进行本地仓库版本控制

#### 2.创建远程仓库

#### 3.关联远程仓库

- ```
  将本地仓库和远程仓库关联起来(只需要做一次)
  git remote add origin xxx
  
  将本地仓库的版本区代码推送到远程仓库保管
  git push -u(第一次需要) origin master
  ```

### 远程仓库有代码,要更新最新代码

#### 1.更新新代码

```
git pull origin master
```

### 分支操作

#### 1.新建一个分支

```
git branch xxx
```

#### 2.切换分支

```
git checkout xxx
```

#### 3.新建并切换分支

```
git checkout -b xxx	
```

#### 4.查看分支

```
git branch
	只要新建分支,就会将当前分支内容克隆到新分支上
```

#### 5.将本地分支代码推送远程仓库保管

```
git push origin xxx(分支名字)
在哪传无所谓,主要看传到哪
```

#### 6.删除分支

```
git branch -d xxx(分支名称)
```

#### 7.合并其他分支内容

```
git merge xxx(分支名称)
```

#### 8.冲突解决

```
$ git merge dev
Auto-merging a.js
CONFLICT (content): Merge conflict in a.js
Automatic merge failed; fix conflicts and then commit the result.
以上代码是实验中冲突出现代码

解决方案,vscode打开冲突的文件,然后手动修改保存
git add .
git commit -m 'feat:解决冲突'
```

### 版本指令

#### 1.查看代码历史版本信息

```
git log
	回车键查看下一页
	不想看了q键退出指令
git reflog
	简略版本
```

#### 2.版本回退

```
git reset --hard HEAD^    
	回退到上一个版本
git reset --hard commitID  
	回退到commitID指定版本

```





## npm操作

### 查看版本

```
npm -v
	任意cmd窗口输入即可查看
```

### 搜索库

```
npm search xxx(要搜索的库)
```

### 更改到国内镜像库

```
npm config set registry https://registry.npm.taobao.org
	只需要做一次
```

### 初始化

```
npm init
	初始化package.json,需要制定配置
```

### 初始化方式2

```
npm init -y
	初始化package.json,使用默认配置
	注意:先要初始化package.json,再开始下载包
```

### 下载xxx包

```
npm install  xxx(包的名字)
npm i		 xxx(包的名字)
	两种方式一个意思
	这个包会下载到 node_modules中
	package-lock.json 下载包的缓存文件
	下载的包会自动添加到 package.json 中的依赖
```

### -S -D -g 版本

```
npm i xxx -S
	下载包并添加到生产依赖 
	"dependencies":{}; 
    运行时依赖
    
npm i xxx -D
	下载包并添加到开发依赖  
	"devDependencies":{};
	构建时依赖
	
npm i xxx@x.y.z 
	下载指定版本
	x 大版本
	y 中版本
	z 小版本
	
npm i 
	下载所有依赖包
	
npm i xxx -g
	全局下载包,作为指令使用
	注意不是通过require使用,而是作为指令使用
```

### 删除xxx包

```
npm remove xxx(包的名字)
npm r      xxx(包的名字)
	删除xxx包
```



## yarn的使用

> fackbook开发的类似npm工具,速度更快

### 下载安装

```
npm i yarn -g
```

### 配置淘宝镜像

```
yarn config set registry https://registry.npm.taobao.org
```

### 初始化package.json

```
yarn init
```

### 下载包

```
yarn add xxx(包名字)
yarn add xxx --dev
yarn 下载所有依赖包
	注意:去哪聚安装不用yarn,用npm
```

### 删除包

```
yarn remove xxx
```

