# day01

命令行

- ![image-20200518231345799](C:\Users\zengxiaolong\AppData\Roaming\Typora\typora-user-images\image-20200518231345799.png)

命令行有很多的名字：命令行、CMD窗口、Terminal、终端、shell（壳）

### 命令行的使用

- 常用的命令
  - dir当前目录下的内容
  - cd，调整到指定的目录，相当于双击文件夹一样
    - 在路径中，.表示当前目录，..表示上一级目录，跟css是一样的
  - mkdir，创建新的文件夹
  - rmdir，删除一个文件夹
  - del，删除一个文件（慎用），删除之后回收站都没有了

## 版本控制（version Control）

- 版本控制是指对软件开发过程中各种代码，配置文件及说明文档等文件变更的管理。
- 类似单击游戏里面就有这种功能，存储进度，通过
- ![image-20200518235011589](C:\Users\zengxiaolong\AppData\Roaming\Typora\typora-user-images\image-20200518235011589.png)
- 版本控制工具有很多种，今天讲的一种工具叫做Git，只要是开发就会用到版本控制软件

- git的使用

  - 基本的配置，（通常只需配置一次，

    - 配置用户名

      - ```html
        git config --global user.name'用户名' 要改的就是用户名，用来识别用户的身份
        ```

      - 配置电子邮件

      - ```
        git config --global user.email"电子邮件"
        ```

      - 记录代码保存的时候标识身份的

  - 使用

    - 初始化项目，将项目交给git维护

      - 进入到项目目录

      - 初始化项目，使git对代码进行管理

        - ```
          git init	这时候表示项目已经初始化完毕了
          ```

        - 查看代码的状态

          - ```javascript
            git status(状态)
            ```

          - ![image-20200519003206206](C:\Users\zengxiaolong\AppData\Roaming\Typora\typora-user-images\image-20200519003206206.png)

          - 

.git是隐藏文件，一般不动它

git是主程序，后面的是子程序，只要文件夹里面有一个.git文件夹就是git项目

代码就存在这个文件夹里

- 使git对文件进行追踪

  ```javascript
  git add 增加到git监听名单里
  ```

- changes：改变

- add 理解为暂存，就是告诉git在监听这个文件，文件名必须写完整

- 重复输入指令的时候按上下方向键可以切换之前用过的指令
- 

这里的a已经追踪到了，b和c还没有被追踪

![image-20200519213435200](C:\Users\zengxiaolong\AppData\Roaming\Typora\typora-user-images\image-20200519213435200.png)

**要git add b.txt，不过这样太麻烦了，可以直接add. 表示追踪当前目录下所有文件**

这里b和c都被追踪了

![image-20200519213550078](C:\Users\zengxiaolong\AppData\Roaming\Typora\typora-user-images\image-20200519213550078.png)

- 将代码存储到仓库中（存储进度）
- 调命令`git commit`表示提交，把已经追踪的代码还没提交的提交出来，这时候弹出这个窗口
- ![image-20200519213802649](C:\Users\zengxiaolong\AppData\Roaming\Typora\typora-user-images\image-20200519213802649.png)
- 这里是写描述信息的，介绍这次做了哪些操作，如果选的编辑器是vscode，就会弹出vscode
- 这里带#的就是注释，没用
- 这里面相当于写的日志
- ![image-20200519214017621](C:\Users\zengxiaolong\AppData\Roaming\Typora\typora-user-images\image-20200519214017621.png)
- 这样表示代码提交成功
- ![image-20200519213956490](C:\Users\zengxiaolong\AppData\Roaming\Typora\typora-user-images\image-20200519213956490.png)
- 这样文件就存起来了，commit 是最终存到仓库里

步骤

- 在文件夹新建一个txt文件
- 先调add，把txt交给git管理
- git add d.txt
- 调git commit永久存储

将代码存储到仓库，并直接设置描述信息

`git commit -m'设置描述信息'`-m 这样就不会弹出编辑器了，直接在git里面写，这样写省事，就不用在编辑器里面写了，直接就提交了

<img src="C:\Users\zengxiaolong\AppData\Roaming\Typora\typora-user-images\image-20200519214534371.png" alt="image-20200519214534371" style="zoom:150%;" />

- 查看提交的日志`git log`
- ![image-20200519214754773](C:\Users\zengxiaolong\AppData\Roaming\Typora\typora-user-images\image-20200519214754773.png)
- 提交了两次
- ![image-20200519214846629](C:\Users\zengxiaolong\AppData\Roaming\Typora\typora-user-images\image-20200519214846629.png)
- 刚安装完配置的用户名和邮箱就会在这里显示
- ![image-20200519215020320](C:\Users\zengxiaolong\AppData\Roaming\Typora\typora-user-images\image-20200519215020320.png)
- 在某一个阶段存一下，在关键位置存



如果用vim文本编辑器，提交之后会弹出这样

![image-20200519221053009](C:\Users\zengxiaolong\AppData\Roaming\Typora\typora-user-images\image-20200519221053009.png)

对于前端用的比较少

先在里面输入描述内容

![image-20200519221201994](C:\Users\zengxiaolong\AppData\Roaming\Typora\typora-user-images\image-20200519221201994.png)

再按esc，按：，按回车，就存起来了

![image-20200519221248571](C:\Users\zengxiaolong\AppData\Roaming\Typora\typora-user-images\image-20200519221248571.png)

**changed：更改**

**insertions：插入**

**init：初始化**

.git就是文件仓库，这个不能动

新建一个txt不归git管

`git add .`单词跟**.**也要有空格，这时候就把文件交给git管理了

`git commit -m`创建了一个`g.txt`这时候`g.txt`就提交过去了，这个文件就存到仓库了

这个表示没有东西提交，工作树是干净的

![image-20200519231153900](C:\Users\zengxiaolong\AppData\Roaming\Typora\typora-user-images\image-20200519231153900.png)

这个表示在主要的分支，就是主代码上

![image-20200519231222815](C:\Users\zengxiaolong\AppData\Roaming\Typora\typora-user-images\image-20200519231222815.png)

现在改一个txt显示这样，没有存储，想提交就`git add a.txt`为什么追踪过了还要再追踪，因为add它是多功能的，如果没有被追踪就表示设置，如果被追踪了，现在表示暂存，还没有最终提交，

![image-20200519232008041](C:\Users\zengxiaolong\AppData\Roaming\Typora\typora-user-images\image-20200519232008041.png)

要提交就用`git commit -m'对文本修改后的描述'`，如果修改了文件也要调用add，再commit

![image-20200519233247680](C:\Users\zengxiaolong\AppData\Roaming\Typora\typora-user-images\image-20200519233247680.png)

现在改一下b.txt

每次提交之前都要add，这样太麻烦了

直接`git commit -a -m`回车，所有的文件都修改了，-a就是commit的一个参数

提交所有被追踪的文件，适用已被追踪的文件

![image-20200519233636846](C:\Users\zengxiaolong\AppData\Roaming\Typora\typora-user-images\image-20200519233636846.png)

删除文件，调用status也会提示被删了

**如果误删了文件，加载指定版本的代码**

`git checkout`表示检出，取出来，写id前面就四五位就可以了，恢复之前的状态

- 也可以用在修改文件里面内容的状态，通过日志查看想恢复到哪里就复制哪个版本的id

这个是id![image-20200519234031410](C:\Users\zengxiaolong\AppData\Roaming\Typora\typora-user-images\image-20200519234031410.png)

这个id能保证它的唯一性

master表示最新的位置，`git checkout master`恢复到代码不同的状态，回到代码的任意版本，就好像时光倒流

`git log`查看日志



**q是退出**

**clear清屏**

**modified 修改**

**restore 恢复**

**file 文件**

**branch 分支**

**master 主干**

## Head和Master

这是树状结构，只有主干

![image-20200520010855440](C:\Users\zengxiaolong\AppData\Roaming\Typora\typora-user-images\image-20200520010855440.png)



![image-20200520011044023](C:\Users\zengxiaolong\AppData\Roaming\Typora\typora-user-images\image-20200520011044023.png)

master是最新位置

head表示当前所在的位置

checkout实际上是在改变head的位置

## 创建远程仓库

- 在真正开发项目时，git仓库一定不是仅仅存在于本地计算机中，一定有一个公共的服务器用来存储代码，公共服务器可以满足多人开发的需求

- 在公司时，一般公司都会有自己的git服务器，用来存储代码，但是现在是学习阶段，所以我们可以直接使用公共的git仓库来学习git操作

- 这几天我们使用国内的代码托管平台，来学习git的操作 http://gitee.com

- **add .**追踪所有的文件

- **git push**推送

- **git pull**拉取代码

- 

- ```javascript
  记住用户名全选信息
  git config --global credential.helper wincred
  取消记录用户的权限信息
  git credential-manager uninstall
  ```

- 推送之前先拉取下来，先确定本地和服务器版本一致，用get pull拉取下来，再git push推送

- **如果忘记用户名和密码在控制面板-用户账号-凭据管理器-普通凭据-编辑**

# day02

看视频位置引入远程仓库，这是版本控制系统

![image-20200521060932840](C:\Users\zengxiaolong\AppData\Roaming\Typora\typora-user-images\image-20200521060932840.png)

获取到远程仓库的代码

![image-20200521060958460](C:\Users\zengxiaolong\AppData\Roaming\Typora\typora-user-images\image-20200521060958460.png)

输入地址和保存的位置

![image-20200521061216215](C:\Users\zengxiaolong\AppData\Roaming\Typora\typora-user-images\image-20200521061216215.png)

open project表示在哪里打开，this是当前窗口，new是新窗口

![image-20200521061235924](C:\Users\zengxiaolong\AppData\Roaming\Typora\typora-user-images\image-20200521061235924.png)

可以直接在webstorm里面git命令

![image-20200521061512990](C:\Users\zengxiaolong\AppData\Roaming\Typora\typora-user-images\image-20200521061512990.png)

下面可以写描述信息

![image-20200521061532212](C:\Users\zengxiaolong\AppData\Roaming\Typora\typora-user-images\image-20200521061532212.png)

# day 02

webstorm浏览器设置

![image-20200521080820298](C:\Users\zengxiaolong\AppData\Roaming\Typora\typora-user-images\image-20200521080820298.png)

引入外部js文件，在script标签中写src属性引入

![image-20200521081335299](C:\Users\zengxiaolong\AppData\Roaming\Typora\typora-user-images\image-20200521081335299.png)

如果引入了外部文件，就不能在内部编写代码，想写就再写一个新的script标签，这个是内部的

可以把js代码在超链接的href属性中，也可以写在一些标签的属性中

![image-20200521082052969](C:\Users\zengxiaolong\AppData\Roaming\Typora\typora-user-images\image-20200521082052969.png)



## js基本语法

- 多行注释/* */

- 单行注释//
- 严格区分大小写
- js中每一个指令被称为一个语句，每一个语句以分号结尾，如果不写，浏览器会自动添加
  - 有些情况下浏览器可能加错了
- js中会忽略多个空格和换行

## 变量和字面量

- 字面量(值)
  - 1,2,3,4，'hello'，true，就是它本身的意义，没有别的含义
  - 通常在代码中不会直接使用字面量，因为不容易记忆，不方便后期维护
- 变量
  - 可以用来存储字面量
- 声明变量var a，可以同时声明多个，用逗号隔开，声明和赋值同时进行
- 标识符
  - 在js中，所有的可以自己命名的内容，都被称为标识符
    - 变量名、函数名、类名
  - 标识符的规范
    - 字母，数字，下划线，$
      - 不能是数字开头
        - 不能是js中的关键字和保留字，比如var， 

帕斯卡命名法单词与单词直接用下划线隔开，全小写

中文也可以作为变量用，但是最好别用，会被打死

## 数据类型

数据类型是指js中的字面量类型

- 数值(number)
  - 数值就是数字，包括整数(int)和浮点数(float)
  - 创建数字的都是10进制的数字
  - 0b二进制
  - 0o八进制
  - 0x十六进制
- 当超过一定范围数字会以科学计数法来显示，数字再大的时候，会显示infinity，比如e+100表示 10的100次方
- 在JS中，小数可以确保小数点后的15位的值，超过就会显示近似值
- 如果计算要求的精度比较高，千万不要在JS中直接计算
- 特殊数字
  - infinity正无穷
  - -infinity负无穷
  - NaN非法数字
- 为了解决不能存储大整数的问题，在ES2020版本中，定义了一种新的数据类型，专门用来表示大整数，是以n结尾的，目前还没有正式推出，实际应用还要等个一两年



# day03 字符串 基本数据类型 类型转换 运算符

可以给一个变量反复多次赋值

不要重复声明变量

### 字符串

- 在JS中使用字符串来表示语言，文字这些内容，用引号引起来，单引号双引号都可以
- 同类型的引号不能嵌套，可以单引号嵌套双引号，或者双引号嵌套单引号，\表示转义字符

### 类型检查

蓝色是数字，灰色是字符串

typeof：检查数据类型

### 布尔值

- Boolean，主要用来进行逻辑判断
  - 两个值true和false

### null和undefined

空值（null），一个空对象

未定义(undefined)

- 声明了变量，不赋值，它的值就是undefined
- 一般不会主动为一个变量赋值为undefined

type的类型是一个bug，设计缺陷，历史遗留问题

### 基本数据类型

- 数字、字符串、布尔值、空值、未定义
- 基本数据类型是构建程序的基石，所有数据都是以上几种数据组合而成
- 所有的基本数据类型都是不能改变的
- 数据存到内存当中
- ![image-20200521102549806](C:\Users\zengxiaolong\AppData\Roaming\Typora\typora-user-images\image-20200521102549806.png)
- 变量也会存到内存里
- 每个值都有一个内存地址
- ![image-20200521102757437](C:\Users\zengxiaolong\AppData\Roaming\Typora\typora-user-images\image-20200521102757437.png)



### 类型转换

- 指将其他的数据类型转换为字符串，数字，布尔值

- 调用xxx的yyy方法==>xxx.yyy()

- 转换的原理：根据原来的值创建一个新值

- toString()只是根据原来的值创建一个新的字符串并返回，不会改变原来的值，所以需要声明一个变量接收这个结果，比如

- ```javascript
  var b = a.toString()
  //如果要对a进行改变，要对变量重新赋值
  var a = a.toString()
  ```

- null和undefined中，不存在toString方法，如果对null和undefined调用tostring()会报错

- 可以通过String()函数，来将其他类型的值转换为字符串

- String功能比toString功能强大一些，可以将null和undefined转成字符串

- String

  - 对于有toString()方法的值来说，String()会直接调用它们的toString()来将其转换为字符串
  - 对于没有toString()方法的null和undefined来说，null会转成'null'，undefined会直接转成'undefined'

- **一般用的String**

内存空间是有限的，存的是值的地址，每个值占用的内存大小不一样，如果直接在变量里存值，内存大小就不固定了，这样性能更好一些

### 类型转换

空格和空串转数字是0

布尔值转数字

- true转为1
- false转为0
- null转为0
- undefined转为NaN

### 字符串转数字

parseInt提取整数

parsefloat提取小数

**这两个专门用来对付字符串的**

## 转换成布尔值

使用Boolean()函数 

除了0和NaN是false，其他都转换为true

字符串转布尔值

- 除了空串是false，其他都是true

  - ```javascript
            var result = Boolean('');//false
    ```

  - 

null和undefined都会转为false

 **转布尔值总结，所有表示没有的都会转成false，大部分对象都会转成true**

## 运算符

- 可以对一个或者多个进行各种运算
- 加、减、乘、除、取余、次方(**)、开方

## 算数运算符

在js中，可以对非数字类型的进行算数运算，会转换成数字再运算，true+false=1

任何值跟字符串做加法都是拼串操作

### 字符串拼接

模板字符串

- 可以使用反单引号来创建模板字符串

- ```
  a=`今天天气真好
  明天也好
  后天也好`
  ```

- 这是新的语法，可以多行使用，ie老版本不支持

- console.log可以打印多个值

- 在模板字符串中可以直接使用变量

- ![image-20200521150532013](C:\Users\zengxiaolong\AppData\Roaming\Typora\typora-user-images\image-20200521150532013.png)

### 隐式类型转换

可以通过为任意值加空串的形式转换成一个字符串

![image-20200521150908646](C:\Users\zengxiaolong\AppData\Roaming\Typora\typora-user-images\image-20200521150908646.png)

可以通过为人一直-0  *1  /1这些方式转换为数字，这些方式比较麻烦，了解一下，原理和Number()一样，操作简便一些

### 一元运算符

只会影响一个值

**+ 是正号，不会对数字产生影响**

**- 是负号，会对数字进行取反**

**可以用一元的 + 将任意值转换为数字，以后主要是用这种方式**

这种会直接把字符串转成数字运算

![image-20200521151725324](C:\Users\zengxiaolong\AppData\Roaming\Typora\typora-user-images\image-20200521151725324.png)

​	 typeof也是运算符，用来检查一个值的类型

### 总结

多看文档，js技术更新很快，了解最新的东西

转义字符

![image-20200521152701759](C:\Users\zengxiaolong\AppData\Roaming\Typora\typora-user-images\image-20200521152701759.png)

类型转换(其他类型转String)，一般都是用的拼串

![image-20200521152834239](C:\Users\zengxiaolong\AppData\Roaming\Typora\typora-user-images\image-20200521152834239.png)



# day04 运算符 条件控制语句

![image-20200519085725887](C:\Users\zengxiaolong\AppData\Roaming\Typora\typora-user-images\image-20200519085725887.png)

![image-20200519092318545](C:\Users\zengxiaolong\AppData\Roaming\Typora\typora-user-images\image-20200519092318545.png)



## 逻辑运算符

!	如果对一个非布尔值进行非运算，会先将其转换成布尔值再取反，利用非运算，可以将一个任意类型的值转换为布尔值

隐式转换：为一个值进行两次取反，即可转换为布尔值

&&

- 可以对符号两次的值进行与运算
- 如果与运算两侧的值都为true，则返回true，否则返回false

||

null转布尔值为false

## 非布尔值的与或运算

对于非布尔值进行与或运算时，先转换成布尔值，然后进行运算，最终返回的是原值

hello转布尔值是true，0转布尔值是false

与运算规则

- 如果第一个是true，则返回第二个值，否则返回第一个

或运算规则

- 如果第一个是true，返回第一个值，否则返回第二个

在js中，与、或都是短路的

- 对于与运算，如果第一个是false，不会去看第二个
- 对于或运算，如果第一个是true，不会看第二个

## 关系运算符

- 用来比较两个值之间的关系是否成立，成立返回true，不成立返回false1
- 如果对于非数值进行关系运算，通常js解析器会将非数字的值转换为数值，然后再比较
- 当比较两个字符串大小是，解析器不会讲字符串转换为数字比较，比较字符串时，解析器会逐位比较Unicode编码
- 如果比较的是两个字符串类型数字时，依然会比较编码，可能是错误的结果

## 相等运算符

- 主要用来比较两个值是否相等，相等返回true，否则返回false

- == 

  - 如果比较两个不同类型的，先转成同类型再比较
  - 通常情况，不同类型都会被转成数值再比较
  - null和其他类型比较时不会转换成数字
  - null和undefined比较是true

- ！=

  - ！=  检查两个值是否不等，如果不等返回true，否则返回false
  - 不相等会做自动类型转换，只有两个值转换为相同类型后依然不等才会返回true

  

  ===

  - 比较两个值是否全等，不会做自动类型转换
  - NaN不和任何值相等，包括它自身
  - 检查一个值是否是NAN，需要使用函数isNaN
  - null和undefined做全等比较，返回false

- ！==  不全等

  - 检查两个值是否不全等，如果不全等返回true，否则返回false
  - 不会做自动类型转换，如果两个值的类型不一样，直接返回true

- 特殊情况

  - NaN不和任何值相等，包括自己，所有的值跟NaN比较都返回false
  - 可以通过isNaN()函数，来检查一个值是不是NaN

## 赋值运算符

用于将一个值赋值给一个变量

**=**

- 用来将右侧的值赋给左侧的变量

![image-20200519140439854](C:\Users\zengxiaolong\AppData\Roaming\Typora\typora-user-images\image-20200519140439854.png)

- 使用这些赋值运算符都会导致变量的改变
- 可能会导致变量改变的情况
  - 使用赋值运算符
  - 使用自增或者自减

## 条件运算符（三元运算符）

- 条件运算符，可以根据条件选择要执行的语句

  - 语法：条件表达式？语句1：语句2

  - 执行顺序：

    - 在执行时，先对条件表达式进行求值判断

      - true就执行：前面的
      - false就执行：后面的
      - 这种方式可以用，但是强烈不建议使用，容易挨打
      - ![image-20200519142500091](C:\Users\zengxiaolong\AppData\Roaming\Typora\typora-user-images\image-20200519142500091.png)

      - 要写也要这样写，结构清晰一些
      - ![image-20200519142536826](C:\Users\zengxiaolong\AppData\Roaming\Typora\typora-user-images\image-20200519142536826.png)
      - a=1 || 2 && 3，如果或的优先级高就是从左往右算结果应该是3
      - ![image-20200519143941388](C:\Users\zengxiaolong\AppData\Roaming\Typora\typora-user-images\image-20200519143941388.png)
      - 如果与的优先级高先算2&&3，结果应该是1
      - 证明与的优先级比或的优先级高一些
      - 有一个传说中的运算符优先级的表格
        - 在表格中越靠前优先级越高，优先级越高越有限计算
        - 优先级一样，从左往右计算，如果遇到优先级不清除的可以通过这个表格查询
        - 优先级的表格不需要记，如果遇到优先级不清除的，可以通过（）来改变运算优先级
      - **多个运算用逻辑运算符连接**

    ## 代码块

    在js中，可以通过代码块来为代码进行分组

    - 在同一个代码块中的代码就属于同一组代码，这一组代码要么全都执行，要么都不执行，把功能相关的放到一起，比如css声明块要花括号包起来，这里也是一样，这三个就属于一组了
    - ![image-20200519150640462](C:\Users\zengxiaolong\AppData\Roaming\Typora\typora-user-images\image-20200519150640462.png)
    - 都是从上到下执行，就是把这三个分成一组，可以写很多代码块，分很多组

    - js的代码块，通常情况下，代码块对于外部来说应该是隔离的，代码块外部是不能看到代码块内部的，在js里一样可以访问

    - 在js中，使用var声明的变量，是没有块级作用域的

      - 在{}中声明的变量，在{}外部依然可以访问，这是js的一个问题

      - 为了解决这个问题，在后来的js版本中，引入了新的声明变量方式let

      - let a=10；这个也是在声明变量，let就是“让”的意思，让a=10

        - 使用let声明的变量，就具有块级作用域，如果a写到{}外边就不能访问了。let就是解决var的问题

        - ![image-20200519151217235](C:\Users\zengxiaolong\AppData\Roaming\Typora\typora-user-images\image-20200519151217235.png)

        - 除了let，在js中还提供了一种声明常量的方式const，常量一旦声明就不能重新赋值

        - let用来创建变量，const用来创建常量，有些浏览器对这些支持度不是很好，所以现在很多情况还是用var

          

## 流程控制语句

![image-20200519152033203](C:\Users\zengxiaolong\AppData\Roaming\Typora\typora-user-images\image-20200519152033203.png)

代码是从上往下执行的，这样就不能满足我们的需求，说明这是个笨程序，需要一个判断

通过流程控制语句，可以改变代码执行顺序，或者可以让指定的代码反复执行多次

分类

- 条件判断语句
- 条件分支语句
- 循环语句，可以把某一段代码执行多次

条件判断语句

- if语句
  - if(条件表达式)
    - 语句
  - 执行流程
    - 在执行时先对if后的条件表达式进行求值判断，看是true还是false
      - 如果是true就执行if后的语句
      - 如果是false就不执行
    - if只会影响到它后面的那条语句，如果希望if语句可以控制多条语句，可以统一放到一个代码块中
    - 一般情况下，为了结构清晰，即使if后只有一条语句，也应该放到一个代码块中，这样更清晰，也不麻烦，不用在代码块后边加分号

## if else语句

prompt：弹出提示

if-else语句

- 语法
  - if(条件表达式){语句
  - }else{语句
  - }
  - 执行流程：
    - if-else语句在执行时，会先对if后的条件表达式求值判断
    - 如果为true执行if后的语句
    - 如果为false，执行else后语句

**if-else if-else**，就是把多个if-else进行拼接

执行流程

- if-else if-else执行时，会自上向下一次对if后的条件表达式进行求值判断
  - 如果条件表达式结果为true，则执行if后语句，执行完毕语句结束
  - 如果条件表达式为false，则继续向下判断，以此类推，直到找到为true的为止，如果所有的条件表达式都为false，则执行else后的语句

随便建个文件夹，在Git里面输入`git clone地址`就保存到文件夹里面了，下载代码

![image-20200519184921009](C:\Users\zengxiaolong\AppData\Roaming\Typora\typora-user-images\image-20200519184921009.png)

把服务器代码拉到本地，拉取代码

![image-20200519185216673](C:\Users\zengxiaolong\AppData\Roaming\Typora\typora-user-images\image-20200519185216673.png)

如何自己创建代码仓库

先注册账号

![image-20200519190925180](C:\Users\zengxiaolong\AppData\Roaming\Typora\typora-user-images\image-20200519190925180.png)

新建仓库



# day05 if for循环

这样写可读性不高

![image-20200520092427605](C:\Users\zengxiaolong\AppData\Roaming\Typora\typora-user-images\image-20200520092427605.png)

把顺序调整一下就可以了

![image-20200520092444602](C:\Users\zengxiaolong\AppData\Roaming\Typora\typora-user-images\image-20200520092444602.png)

## if练习

判断奇数偶数，除了判断奇数和偶数之外，还要加一个除了偶数和奇数之外还要判断除了这两种情况之外的

加一个条件用或运算

![image-20200520094015488](C:\Users\zengxiaolong\AppData\Roaming\Typora\typora-user-images\image-20200520094015488.png)

通过狗狗年龄算出自己的年龄

![image-20200520101213037](C:\Users\zengxiaolong\AppData\Roaming\Typora\typora-user-images\image-20200520101213037.png)



isNaN返回true表示是非法数字

![image-20200520101551817](C:\Users\zengxiaolong\AppData\Roaming\Typora\typora-user-images\image-20200520101551817.png)

Java编程全解适合入门新手看，比较细致

prompt什么都不输就输空串，转成数字就是0

var换行，该加空格加空格



练习3： 我家的狗5岁了，5岁的狗相当于多大年龄的人呢？

   	 其实非常简单，狗的前两年每一年相当于人类的10.5岁，然后每增加一年就增加四岁。

​    	那么5岁的狗相等于人类的年龄就应该是10.5+10.5+4+4+4 = 33岁

  	  编写一个程序，获取用户输入的狗的年龄，然后通过程序显示其相当于人类的年龄。 如果用户输入负数，请显示一个提示信息

思路：

- 定义狗的名字
- 检查输入是否合法，alert和console
- if判断是不是数字类型（isNaN(变量名) 或者小于0）
  - 满足其中任意调节弹出(输入有误)；
  - 如果输入正确就进入else
    - 声明一个人名的变量
    - 判断如果够的年龄<=2
      - 人的年龄=狗的年龄*10.5
      - 否则
        - 人的年龄=狗的年龄*10.5+(狗的年龄-2)乘以4
      - alert(狗的年龄+'岁的狗相当于'+人的年龄+'岁的人')

## 条件分支语句

- 根据不同的数字显示不同的中文

  - 1显示壹，2显示贰
  - 创建变量num表示数字
  - 判断如果是1就打印壹，以此类推打印2,3,4
  - 这样写太麻烦了
  - ![image-20200520135342442](C:\Users\zengxiaolong\AppData\Roaming\Typora\typora-user-images\image-20200520135342442.png)

- 用条件分支语句(switch-case)

  - switch(表达式){ 

  - case 表达式:

  - }

  - ![image-20200520135552103](C:\Users\zengxiaolong\AppData\Roaming\Typora\typora-user-images\image-20200520135552103.png)

  - 执行流程

    - switch在执行时从上到下执行，将case后的表达式和switch后()中的表达式进行全等比较

    - 如果比较结果为true则从当前case处开始执行代码

    - 如果比较结果为false就继续向下比较，直到找到true为止

    - 字符串跟数字全等比较，相等但不全等

    - **注意：当case后的表达式和switch后的表达式全等比较结果为true时，会从当前case处开始向下执行代码，此时它下边的所有代码都会执行，哪怕是其他case后的代码都会执行，如果不希望执行其他case后的代码，可以在语句的最后使用break，避免重复执行其他后面的代码，如果所有的比较结构都为false，就从default处开始执行**

    - ![image-20200520140730256](C:\Users\zengxiaolong\AppData\Roaming\Typora\typora-user-images\image-20200520140730256.png)

    - 全等比较不仅做数值比较，还要做类型比较

      - num=+prompt()转数字

    - 要么都是数字，要么都是字符串

    - 写字母不能比较，可以在判断里面case写‘你输错了’，这样全部列举出来很不现实
  
    - ```javascript
      default
      当上面的条件都不满足就执行default，相当于if else里面的else
    这个可以写任意位置，不是必须写最后，但是是最后判断，这个比ifelse结构清晰
      ```

    - ![image-20200520141635996](C:\Users\zengxiaolong\AppData\Roaming\Typora\typora-user-images\image-20200520141635996.png)

    - 在开发中主要还是if-else为主，当判断的条件都是xxx===xxx的时候，比较适合使用switch-case

    - ![image-20200520142003502](C:\Users\zengxiaolong\AppData\Roaming\Typora\typora-user-images\image-20200520142003502.png)
  
    - ![image-20200520142324148](C:\Users\zengxiaolong\AppData\Roaming\Typora\typora-user-images\image-20200520142324148.png)
    
    - ```javascript
      //作业
       //获取用户输入的信息
              var num = prompt('请输入数字');
              switch(num){
                  case '1':
                  alert('周一');
                  break;
                  case '2':
                  alert('周二');
                  break;
                  case '3':
                  alert('周三 ');
                  break;
                  case '4':
                  alert('周四');
                  break;
                  case '5':
                  alert('周五');
                  break;
                  case '6':
                  alert('周六');
                  break;
                  case '7':
                  alert('周日');
                  break;
                  default:
                  alert('输入有误');
              }
      ```
    
    - 

## 循环语句

在网页中打印一行❤

![image-20200520143723495](C:\Users\zengxiaolong\AppData\Roaming\Typora\typora-user-images\image-20200520143723495.png)

```javascript
loop	循环语句
//语法
while (){
}
```

- while语句
  - 语法while(条件表达式){语句。。}
  - if只判断一次，while判断很多次，当条件表达式为false就停止

条件表达式一直为true就会形成死循环

![image-20200520144916433](C:\Users\zengxiaolong\AppData\Roaming\Typora\typora-user-images\image-20200520144916433.png)

所以条件表达式不能写死

每一个循环至少由三个表达式组成

- 初始化表达式，初始化一个变量	

- ```javascript
  var i=0 
  while(i<10){
      //更新表达式，修改初始化变量的值,执行10次，直到i到10的时候就停止
      i++;
  }
  ```

- ![image-20200520145536846](C:\Users\zengxiaolong\AppData\Roaming\Typora\typora-user-images\image-20200520145536846.png)

- 

- 获取用户输入狗的年龄

- ```javascript
  var dagAge=promt('请输入狗的年龄')
  //可能用户输入的不符合规范
  if(isNaN(dogAge))
  ```

- 满足任意一个都不是一个合法的值

- ![image-20200520151727006](C:\Users\zengxiaolong\AppData\Roaming\Typora\typora-user-images\image-20200520151727006.png)

- 如果输入不对就一直输，直到对了为止

- ![image-20200520151952495](C:\Users\zengxiaolong\AppData\Roaming\Typora\typora-user-images\image-20200520151952495.png)

- 把if改成while就可以了

- ![image-20200520153222172](C:\Users\zengxiaolong\AppData\Roaming\Typora\typora-user-images\image-20200520153222172.png)

- //假设存款的年利率为5%，1000元存几年能变成5000元

  - 循环执行一次代表一年
  - ![image-20200520153936212](C:\Users\zengxiaolong\AppData\Roaming\Typora\typora-user-images\image-20200520153936212.png)

- 值需要直到循环执行了多少次，就知道钱存了多少年

- 需要一个计数器year=0；

- 每循环一次，就自增一年

- ![image-20200520154124024](C:\Users\zengxiaolong\AppData\Roaming\Typora\typora-user-images\image-20200520154124024.png)

```javascript
//假设存款的年利率为5%，1000元存几年能变成5000元
        // 创建一个变量，用来存储钱数
        var money = 1000;

        // money *= 1.05; //一年后的钱数
        // money *= 1.05; //两年后的钱数

        // 创建一个计数器
        var year = 0;

        // 创建一个循环，来模拟存钱的状态
        while (money <= 5000){
            money *= 1.05;

            //使计数器增加
            year++;
        }

        alert('从1000到5000需要'+year+'年！');
```



**do while循环**

语法

![image-20200520154422912](C:\Users\zengxiaolong\AppData\Roaming\Typora\typora-user-images\image-20200520154422912.png)

执行流程

- do-while循环在执行时，会先执行do后边的代码块(循环体)，然后对while后的条件表达式进行求值判断，如果为false，退出语句，如果为true，继续执行循环体
- do-while和while的区别
  - while语句是先判断再执行
  - do-while语句是先执行再判断
  - 大部分情况下两种语句是一样的，主要区别在于do-while语句可以确保循环体至少执行一次，循环一次的时候可以用do-while，和switch差不多，用的很少

## for循环

循环是可以互相代替的，至少语法有不一样的地方

初始化表达式

条件表达式

更新表达式

while循环把这三个表达式分开写的

![image-20200520160646483](C:\Users\zengxiaolong\AppData\Roaming\Typora\typora-user-images\image-20200520160646483.png)

for循环是把这三个放一起，结构清晰一些

执行流程

- 1.for循环执行时，首先执行初始化表达式，来初始化变量
- 2.执行条件表达式，判断循环是否执行
  - 如果判断结构为false，则语句结束
  - 如果判断结果为true，则执行循环体
- 执行更新表达式对值进行更新
- 重复第二步
- ![image-20200520161202069](C:\Users\zengxiaolong\AppData\Roaming\Typora\typora-user-images\image-20200520161202069.png)
- 有一个东西自始至终就执行了一次，就是初始化表达式
- for循环的功能跟while循环功能一样，但是结构更加清晰，一般开发中使用for循环的几率比较高
- for循环中的三个表达式都可以省略不写，也可以写在for循环的其他位置，但是分号不能省略
- ![image-20200520161534037](C:\Users\zengxiaolong\AppData\Roaming\Typora\typora-user-images\image-20200520161534037.png)
- 如果省略for循环所有表达式，就会变成死循环
- ![image-20200520161643452](C:\Users\zengxiaolong\AppData\Roaming\Typora\typora-user-images\image-20200520161643452.png)
- 

## 总结

### 代码块

- 代码块用来为代码进行分组，在js中，同一个代码块中的代码要么都执行，要么都不执行

- 使用{}来创建代码块，里面写什么都行

- 例子

- ```javascript
  {
      var a = 10;
      var b = 20;
  	console.log('hello');
  	console.log('你好');
  }
  ```

- 在js中使用var声明的变量是没有块作用域的，在代码块内部声明的变量，在外部也能访问

- 使用let和const声明的变量具有块作用域，只能在代码块内部访问，外部无法访问

- let声明的是普通变量，const声明的是常量（只能赋值一次）

### 流程控制语句

- 通过流程控制语句，可以改变代码的执行顺序，或者可以使某段代码反复执行多次，就是条件判断和条件分支之类的

- #### 条件判断（❤）

  - if语句

    - 语法

    - ```javascript
      if(条件表达式){
          
      }
      ```

    - 执行流程：

      - if语句执行时先对条件表达式判断，如果结果为true，执行if后面的代码块，如果为false不执行

  - if-else语句（❤）

    - 语法

      - ```javascript
        if(){
           
           }else{
            
        }
        ```

      - 执行流程

        - if-else执行时，先对if后的条件表达式求值判断，如果结果为true，执行if后的代码块，如果结果为false执行else后的代码块

    - **条件表达式不是一定要布尔值，也可以是其他类型的值，其他类型的值会被转化为布尔值，然后判断**

  - if-else if-else语句（❤）

    - 语法

      - ```javascript
        if(){
           语句。。
           }else if{
            
        }else{
            
        }
        ```

      - 执行流程

        - if-else if-else在执行时，自上向下一次进行条件表达式进行求值判断，如果条件为true，则执行当前if后的代码块，执行完毕语句结束。如果为false就继续向下判断，直到找到true为止；如果所有的条件表达式都是false，执行else后的语句
        - 注意：一个if语句中只会有一个代码块被执行
        - if语句可以嵌套，js里啥都能套，基本没有限制

### 条件分支(switch)

语法

- ```javascript
  switch(){
         case 表达式：
         语句。。
         break
          case 表达式：
         语句。。
         break
          case 表达式：
         语句。。
         default:
         语句。。
         break
         }
  ```

- **自己擅长什么，哪些是必须掌握的，这些要知道**

- 执行流程

  - switch在执行时，先自上向下一次将case后的表达式和switch后的表达式进行全等比较，结果为true，从当前case处向下执行代码，如果结果为false，继续向下判断，直到找到true位置；如果所有的比较结果都是false，就从default处行下执行代码。注意每一个写完之后都加一个break

### 循环语句

- 循环语句可以让某段代码反复执行多次，在js中一共有三种循环语句while、do-while、for

- while

  - 语法

    - ```javascript
      while(){
      语句。。。
            }
      ```

    - 执行流程

      - while执行时，先对while后的条件表达式进行判断，如果结果为false，语句结束。如果结果为true，执行循环体，循环体执行完毕继续对条件表达式进行判断，以此类推，**执行流程搞懂了就没啥大问题了**

    - do-while

      - 语法

        ​	![image-20200520164348826](C:\Users\zengxiaolong\AppData\Roaming\Typora\typora-user-images\image-20200520164348826.png)

        - 执行流程
          - do-while语句执行时，先执行do后的代码块，执行完毕对while后的条件表达式进行判断，如果为false语句结束，如果为true继续执行
          - 和while语句，do-while可以确保循环体至少执行一次，其他和while语句没有区别

    - for

      - 语法

        - ```javascript
          for(初始化表达式；条件表达式；更新表达式){
              
          }
          ```

        - 执行流程

          - for循环执行步骤：

            1.执行初始化表达式，初始化变量（只执行一次）

            2.执行条件表达式判断是否执行循环体

            3.判断为true，执行循环体

            4.循环体执行完毕，执行更新表达式

            5.更新表达式执行完毕，重复2，直到为false，循环就结束了

        - 死循环(慎用，会一直执行)

          1.![image-20200520165012766](C:\Users\zengxiaolong\AppData\Roaming\Typora\typora-user-images\image-20200520165012766.png)

          2.![image-20200520165019692](C:\Users\zengxiaolong\AppData\Roaming\Typora\typora-user-images\image-20200520165019692.png)

          这两个是一样的，1会转成true

          3.![image-20200520165055660](C:\Users\zengxiaolong\AppData\Roaming\Typora\typora-user-images\image-20200520165055660.png)

          **死循在程序当中环用的挺多的，有些程序是需要一直运行的，就比如我们用的软件，一直开着，确保程序一直都在开着，很多东西都需要慢慢体会的**

  **作业**

  ![image-20200520165725410](C:\Users\zengxiaolong\AppData\Roaming\Typora\typora-user-images\image-20200520165725410.png)

  ![image-20200521193040165](C:\Users\zengxiaolong\AppData\Roaming\Typora\typora-user-images\image-20200521193040165.png)

  ![image-20200521193120111](C:\Users\zengxiaolong\AppData\Roaming\Typora\typora-user-images\image-20200521193120111.png)

  

  

  

  

  水仙花思路

  for循环百位的所有数

  - for循环十位的数
  - for循环个位的数
      - 判断，如果百位的三次方+十位的三次方+个位的三次方==

  

```javascript

```

**预习：**

循环的嵌套

break continue

对象

函数

数组

# day 06 预习-对象 函数，返回值 匿名函数 枚举对象 

### 知识点积累

- break：结束当前整个循环

- continue结束当次循环，继续下一次循环

- outer：可以给for循环起名，在循环体里面对这个变量名直接操作

- Math.sqrt()，对一个数进行开方

- **计时器**console.time('test') 计时器开始，test是起的名字， console.timeEnd('test')，计时器结束



在JS中来表示一个人的信息(name gender age)

如果使用基本数据类型的数据，我们所创建的变量都是独立的，不能成为一个整体

对象属于一种复合的数据类型，在对象中可以保存多个不同数据类型的属性

对象的分类

- 内建对象
  - 由ES标准中定义的对象，在任何的ES的实现中都可以使用
  - 比如Math，String，Number，Boolean，Function，Object
- 宿主对象
  - 由JS的运行环境提供的对象，目前来讲，主要指由浏览器提供的对象	
    - 比如BOM DOM
      - console.log，console就是一个对象，document.writ，document也是一个对象，这两个对象都是浏览器提供的

- 自定义对象

  - 由开发人员创建的对象，这个是最难的

- 创建对象 

  ```javascript
  var obj =new Object() 这是调了一个Object函数
  ```

- 使用new调用的函数，是构造函数constructor

- 构造函数是专门来创建对象的函数

- 使用typeof检查一个对象时，会返回object

- 在对象中保存的值称为属性

- 向对象添加属性

  - **语法：对象.属性名=属性值**

  - 向obj中添加一个name属性 ,gender属性，age属性

  - ```javascript
    obj.name='孙悟空'
    obj.gender='男'
    obj.age='18'
    ```

- **读取对象中的属性**

  - **语法：对象.属性名或者对象['']**
    - []里面传的是字符串，这种方式灵活一些，把字符串赋值给变量，在[]里面就可以直接写变量

读取对象中没有的属性，不会报错而是会返回undefined

**修改对象的属性值**

- **语法：对象.属性名=新值**
- 读取对象中没有的属性会返回undefined

**删除对象的属性**

- **语法：delete 对象.属性名**
- delete也可以删变量

## 属性名和属性值

向对象中添加属性

```javascript
obj.name='孙悟空'
```

属性名

- 对象的属性名不强制要求遵守标识符规范
- 但是我们使用时尽量按照标识符的规范去做：不能数字开头，不能是关键字保留字，小驼峰命名
- 如果要使用特殊的属性名，不用 **.** 的方式来操作，要使用另一种方式
  - 语法：对象['属性名']=属性值
  - 读取时也采用这种方式
  - 其实属性名就是一个字符串
  - **. [ ] new**优先级最高
  - 在[]中可以直接传递一个变量，这样变量值是多少就会读取哪个属性
  - JS对象的属性值，可以是任意的数据类型，甚至也可以是一个对象

检查对象里是否有某个属性

- in运算符
  - 通过这个运算符可以检查一个对象中是否有指定的属性，如果有则返回true，没有则返回false
  - 语法
    - **'属性名'in对象**

属性值

属性值可以是任意类型，布尔值，空值，undefined，对象

对象中也可以存储对象

## 基本和引用数据类型

![image-20200522051013612](C:\Users\zengxiaolong\AppData\Roaming\Typora\typora-user-images\image-20200522051013612.png)

对象是保存到堆内存中的，每创建一个新的对象，就会在堆内存中开辟一个新的空间，而变量保存的是对象的内存地址（对象引用），如果两个变量保存的是同一个对象引用，当一个通过一个变量修改属性时，另一个也会受到影响

当我们比较两个基本数据类型的值时，就是比较的值

而比较两个引用数据类型时，它是比较的对象的内存地址，如果两个对象一样，但是地址不一样，也会返回false

## 对象字面量

使用对象字面量创建一个对象

```javascript
var obj={} 	和	var obj=new Object()  本质上是一样的
```

使用对象字面量，可以在创建对象时，直接指定对象中的属性

语法

- {属性名：属性值，属性名：属性值。。}，

- ```javascript
  var obj2={name:"猪八戒"，age:28,gender:"男"}
  ```

- 这种结构不是很清楚，可以加个换行

- ```javascript
  var obj2={
  name:"猪八戒"，
  age:28,
  gender:"男"
  }
  ```

- 对象的属性名的引号可加可不加

- 如果使用一些特殊名字，则必须加

- 属性名和属性值是一组一组的名值对结构

  - 名和值之间用：连接，多个名值对之间用，隔开
  - 最后一个就不用写逗号了，如果写逗号了浏览器默认会删除

## 函数

- 函数也是一个对象

- 普通对象就像一个容器，只能装东西

- 函数对象能封装一些功能（代码），在需要时可以执行这些功能（代码）

- 函数中可以保存一些代码在需要的时候调用

- ```javascript
  创建一个函数对象
  var fun=new function()
  ```

- 使用typeof检查一个函数对象时，返回是一个function

- 可以将要封装的代码以字符串的形式传递给构造函数

- 封装到函数中的代码不会立即执行，仅仅只是存起来了

- 函数中的代码会在函数调用的时候执行、

- 调用函数语法：函数对象()

- fun()

- 调用函数时，函数中封装的代码会按照顺序执行

- 函数对象具有普通函数的功能，但比普通函数强大

我们在实际开发中很少使用构造函数创建一个函数对象，基本上不用

使用函数声明来创建一个函数

语法：function 函数名（形参1，形参2.。。形参N）{}

可以在函数体里写大量的代码，调用的时候只需要一行代码fun()

匿名函数

- 语法：

- ```javascript
   function(){}
  ```

## 函数的参数

定义一个用来求两个数和的函数

```javascript
function sum(){
函数体
}
sum();
```

可以在函数的()中来指定一个或多个形参，多个形参之间用逗号隔开，相当于在函数内部声明了对应的变量，没有赋值

在调用函数中可以传实参，实参将会赋值给对应的形参

所以要注意是否接受到非法参数

调用函数时，解析器不会检查实参数量

如果实参的数量少于形参数量，则没有实参的形参将是undefined

函数的实参是任意的数据类型

如果实参的数量多于形参，则多余的实参将不会被使用

如果实参的数量小于形参，则没有实参对应的形参将会赋值为undefined

## 返回值

```javascript
function sum(a,b,c){
	alert(a+b+c);
}
sum(1,2,3)
```

返回的结果不一定要输出，可以把结果return返回

语法：return 值

return后的值会作为执行结果返回

可以定义一个变量接收这个结果

var result = sum(1,2,3)

函数返回什么，result的值就是什么

在函数中，return后的语句都不会执行 

return后面不写值，就相当于return了一个undefined

如果函数中不写return，也会返回一个undefined

**使用return可以结束整个函数**

返回值可以是任意的数据类型

也可以是一个对象和函数

在函数里面可以无限声明函数

## 立即执行函数（IIFE)

调用匿名函数

````javascript
(function(){
    alert('我是匿名函数');
})()
````

立即执行函数往往只会执行一次，创建后立即执行

```javascript
function(a,b){
console.log('a='+a);
console.log('b='+b);
}(12,34)
```

## 对象

对象的属性值可以是任何的数据类型，也可以是个函数

```javascript
		 //创建对象
        var obj = new Object();
        obj.name = '孙悟空';
        obj.age = 18;

        obj.sayName = function(){
            console.log(obj.name);
        }
        console.log(obj.sayName);
        obj.sayName();//函数也可以作为对象的属性的
//如果一个函数作为一个对象的属性保存
//那么我们称这个函数是这个对象的方法，调用函数就是调用对象的方法(method)
//但是它只是名称上的区别，没有其他区别
//这个是调方法
obj.sayName();
//这个是调函数
fun();
```

## 枚举对象中的属性

就是把对象中的属性一个一个取出来

使用for in语句，跟for循环有点像

语法：

```javascript
for(var 变量 in 对象){

}
```

for in语句对象中有几个属性，循环就会执行几次

每次执行时，会将对象中的一个属性的名字赋值给变量

```javascript
var obj={
            name:'周杰伦',
            age:'50',
            gender:'男'
        }
        //for..in语句
        for(var n in obj){//n就是属性名
            // console.log(n);
            console.log("属性名:"+n)
            console.log("属性值:"+obj[n]);//[]可以传变量
        }
```



通过for..in语句，对象里面有什么全都取出来了

## 优化质数

```javascript
 console.time('test')
        for (var i = 2; i < 100; i++) {
            //定义一个标志位，默认是质数
            var flag = true;
            //获取可能整除i的数
            for (var j = 2; j < i**0.5; j++) {//**0.5表示根号，对i开方
                if (i % j == 0) {
                    //不是质数，标志位false
                    flag = false;
                    break;
                }
            }
            // if (flag) {
            //     console.log(i);
            // }
        }
        console.timeEnd('test');
```

优化的前提是先确保能实现效果，再一步一步优化

## git补充

版本控制工具导入

![image-20200522213029903](C:\Users\zengxiaolong\AppData\Roaming\Typora\typora-user-images\image-20200522213029903.png)

这是跟git关联的版本信息

![image-20200522220757332](C:\Users\zengxiaolong\AppData\Roaming\Typora\typora-user-images\image-20200522220757332.png)

文件创建完了还没有存储，要点这个

![image-20200522221001540](C:\Users\zengxiaolong\AppData\Roaming\Typora\typora-user-images\image-20200522221001540.png)

现在保存到本地了

要把代码存到远程仓库，还要推送

每个人的库都是独立的，如果哪天把远程库删了，对于本地库没有影响

origin就是远程库的名字

master是分支的名字

点击master，这是本地的记录

![image-20200522221722513](C:\Users\zengxiaolong\AppData\Roaming\Typora\typora-user-images\image-20200522221722513.png)

这相当于两个节点

![image-20200522221907203](C:\Users\zengxiaolong\AppData\Roaming\Typora\typora-user-images\image-20200522221907203.png)

本地的修改没有推送到远程，现在Ctrl+k，提交一下，然后推送，这时候远程的master也有记录了

![image-20200522222149829](C:\Users\zengxiaolong\AppData\Roaming\Typora\typora-user-images\image-20200522222149829.png)

默认所有的操作都是在本地，commit只是在本地，push才推送到远程服务器上

master是主分支，如果所有的代码都往主分支上推，一旦一个代码也会造成其他代码出问题，主分支相当于程序的主干

​	开发的过程中，主分支一般没有权限，如果一个代码有bug也会对其他代码造成影响，影响整个程序的体验，可能就会被用户看到

一般会创建一个新的分支，这样不会影响到主干程序

如何创建分支

- ![image-20200522163652497](C:\Users\zengxiaolong\AppData\Roaming\Typora\typora-user-images\image-20200522163652497.png)
- ![image-20200522163838250](C:\Users\zengxiaolong\AppData\Roaming\Typora\typora-user-images\image-20200522163838250.png)

在新的分支添加分支跟主分支是没有关系的

让分支回到主干上，就是分支合并

合并到当前分支上

![image-20200522224847780](C:\Users\zengxiaolong\AppData\Roaming\Typora\typora-user-images\image-20200522224847780.png)

代码合并完成之后把创建的远程分支都删除，这样开发就完成了

![image-20200522225512459](C:\Users\zengxiaolong\AppData\Roaming\Typora\typora-user-images\image-20200522225512459.png)

真实开发中会有很多分支

合并分支的时候代码发生了冲突

![image-20200522230210636](C:\Users\zengxiaolong\AppData\Roaming\Typora\typora-user-images\image-20200522230210636.png)

证明git处理不了，才让你处理，手动处理到底用哪个代码选merge，会出现这样的窗口，红色表示发生冲突的部分

![image-20200522230437639](C:\Users\zengxiaolong\AppData\Roaming\Typora\typora-user-images\image-20200522230437639.png)

通常情况下不要删别人代码，点×就把代码删了，从礼貌角度讲，把别人的放前面，自己放后面

这就是最终合并的代码，点击Apply应用

![image-20200522230656707](C:\Users\zengxiaolong\AppData\Roaming\Typora\typora-user-images\image-20200522230656707.png)





- **作业 **

- 把这两天的练习重新敲敲

  - **day05**

    - 根据用户输入的数字，打印星期几(switch-case)
    - 求100以内所有7的倍数之和，以及个数，用两个方法，同学的方法更简便一些(day05)
    - 求1000以内的水仙花数(day05)
    - 获取用户输入的任意数，判断是否是质数(day05)

    ​    //如何判断是质数，只能被1和自身整除的数，从2开始，除到比自身小于1的数

    - 编写一个程序，获取一个用户输入的整数。然后通过程序显示这个数是奇数还是偶数。

    - 编写一个程序，检查任意一个年份是否是闰年。  如果一个年份可以被4整除不能被100整除，或者可以被400整除，这个年份就是闰年

    - 我家的狗5岁了，5岁的狗相当于多大年龄的人呢？

      ​    其实非常简单，狗的前两年每一年相当于人类的10.5岁，然后每增加一年就增加四岁。

      ​    那么5岁的狗相等于人类的年龄就应该是10.5+10.5+4+4+4 = 33岁

      

      ​    编写一个程序，获取用户输入的狗的年龄，然后通过程序显示其相当于人类的年龄。 

      ​    如果用户输入负数，请显示一个提示信息

    - 从键盘输入小明的期末成绩:

      ​      当成绩为100时，'奖励一辆BMW'

      ​      当成绩为[80-99]时，'奖励一台iphone'

      ​      当成绩为[60-79]时，'奖励一本参考书'

      ​      其他时，什么奖励也没有

    - 大家都知道，男大当婚，女大当嫁。

      ​      那么女方家长要嫁女儿，当然要提出一定的条件：

      ​        高：180cm以上;

      ​        富:1000万以上;

      ​        帅:500以上;

      ​      如果这三个条件同时满足，则:'我一定要嫁给他'

      ​      如果三个条件有为真的情况，则:'嫁吧，比上不足，比下有余。'

      ​      如果三个条件都不满足，则:'不嫁！'

    - 根据不同的数字显示不同的中文

      ​    //1 --> 壹  2 --> 贰（switch-case）

    - 获取到用户输入的狗的年龄

      ​    // 如果用户输入的内容不合法，则重复的显示出输入的对话框，

      ​    // 让用户重新输入，直到用户输入正确位置

    - 假设存款的年利率为5%，1000元存几年能变成5000元

    - 

    - 

  - **day06**

    - 打印矩形，每次只能打印一颗*(day06)
    - 打印三角形(day06)
    - 打印倒三角(day06)
    - 打印乘法口诀表(day06)
    - 求100以内所有奇数之和(day06)

- 把git的分支的创建、合并、解决冲突、删除



# day07 对象 可变类型 函数

数值，字符串，字符串，布尔值，空值，未定义

所有的基本数据类型都是独立的，当我们去表示一个复杂的数据时，无法体现出多个数据描述的是一个整体

对象Object，变量之间是相互独立的，对象就像一个容器一样，在对象的内部可以存储多个类型不同的变量

当我们需要表示一些复杂数据，值需要将相关的值统一存储到一个对象

对象可以将变量分组

## 可变类型

Number，String、Boolean、Null、Undefined这些数据类型都属于不可变类型

数据的值是没办法修改的，可以修改变量，只能通过为变量来重新赋值

修改一个变量的值时，不会影响其他变量

![image-20200523094833026](C:\Users\zengxiaolong\AppData\Roaming\Typora\typora-user-images\image-20200523094833026.png)



![image-20200523100515293](C:\Users\zengxiaolong\AppData\Roaming\Typora\typora-user-images\image-20200523100515293.png)

var o2 = o1;多一个变量o2，o2也是0x123

对象是可变类型

o1.name='zbj'，这一步改变的是对象

![image-20200523100655704](C:\Users\zengxiaolong\AppData\Roaming\Typora\typora-user-images\image-20200523100655704.png)

在修改对象时，会影响到所有的指向这个对象的变量，因为自始至终就是一个对象

改变量不会影响别人，只会影响自己

改对象会影响所有指向该对象的变量

会导致变量发生变化的情况

- 使用赋值运算符为变量重新赋值
  - a=10;
  - b += 10;
  - b *=10;
  - 自增，自减
  - a++
  - ++a
  - a--
  - --a
- 除此之外都可以认为是在修改对象

在实际开发中，如果想改变一个变量的值，可以放心改，因为它不会影响到别人，比如

```javascript
        var c = 10;
        c--;    //会影响到d
        var d = c;
        // c--; // 不会影响到d
        console.log(d);//10

```



如果要改变一个对象的值，要小心了，因为它会影响到其他的指向该对象的变量，比如

```javascript
        var a1={};
        a1.name='swk';
        var a2 =a1;
        a2.name='zbj';
        //a2会影响a1
        console.log('a1=',a1);//a1= {name: "zbj"}

		//如果没有指向同一个对象，就不会影响到其他对象
        var f = {};
        var g = {};
        g.gender = '18';
        console.log('f.gender=',f.gender)//f.gender= undefined
        console.log('g.gender=',g.gender)//g.gender= 18
```



每次使用{}、Object()、new Object()都会创建出一个新的对象

使用相等或全等比较两个对象时，比较的是对象的内存地址

如果内存地址相同，比较返回true，内存地址不同返回false

## const补充

const声明的变量是常量，常量只能进行一次赋值

常量只是禁止了变量的重新赋值，如果变量指向的是一个对象，这个对象可以正常修改，不会被const影响

```javascript
        const a=10;
        a=20;//报错，const定义的变量是常量，只能赋值一次
        console.log(a);
```





## 函数

对象的本质就是存储数据的，函数也是对象

```javascript
console.log('你好');
console.log('你好');
console.log('口你急哇');//日语
//放到代码块中
{
console.log('你好');
console.log('你好');
console.log('口你急哇');//日语
}
```

现有的技术手段只能复制粘贴，非常麻烦，也很难维护

和object不同，函数是专门存储代码的对象，可以将一组代码存储到一个函数对象中，并且在需要时对函数进行调用

语法

```javascript
function(){
语句。。。
}
//比如创建一个fn函数
function fn(){
    console.log('你好');
	console.log('你好');
	console.log('口你急哇');
}
```

打印fn的时候就是在打印整个函数对象

存储到函数中的代码不会自动执行，需要对函数进行调用，代码才会执行，调用的语法:函数对象()，表示调用函数当中存储的代码，函数还可以反复调用

**函数体内不能直接给变量赋值，这样就没有意义了**

在定义形参时，可以在参数后为其指定默认值

```javascript
function fn(a=1,b=2){}
```



## 总结

广义上说，对象就是一种数据结构，所有的数据在程序中都可以通过对象存储。

js是面向对象的语言，换句话说，所有的东西到了计算机中都是对象（一切皆对象）

狭义上说，对象是JS中一种数据类型(Object)

对象属于一种复合数据类型，在对象可以存储多个不同类型的值，这些值在对象被称为属性。

对象实际上就是一个存储属性的容器。

![image-20200523162002786](C:\Users\zengxiaolong\AppData\Roaming\Typora\typora-user-images\image-20200523162002786.png)

向对象添加属性

```javascript
o1.属性名=属性值；
o2['属性名']=属性值；
```

读取属性

```javascript
o1.属性名;
o2['属性名'];
var a='属性名';
o2['a'];
```



属性

- 属性名：

  - 属性名没有强制格式要求，可以使用任意字符串作为属性名
  - 但是在实际开发中强烈建议遵循标识符的规范
  - 如果属性名太奇怪了，主要是指不符合标识符规范，必须使用['']形式来设置

- 属性值

  - 属性值是对象中真实存储的数据
  - 属性值可以是任意的数据类型，可以是对象，也可以是一个函数

- 对象的字面量

- ```
  var obj = {属性名:属性值，属性名:属性值};
  ```

- 使用typeof检查一个对象时，会返回'object'

- 可以使用delete关键词来删除一个对象中的属性

- ```javascript
  delete obj.name;
  ```

- 对象 属于可变类型，对象中存储的数据是可以被改变的

  - 改变量时，不会影响其他的变量（给变量重新赋值不会影响其他变量）

  - ```javascript
    var a=10;
    var b =a;
    a++;//改变量
    a=11;//改变量
    a+=5;//改变量
    ```

  - 改对象时，会影响到所有指向该对象的变量

  - ```javascript
    		var o1 = {};
            var o2 = {};
            o1.name = '周杰伦';//改对象
            o2.age = '18';//改对象
            delete o1.name;//改对象
            console.log(o1.name);//undefined
    ```

## 函数

函数也是一个对象

函数用来存储代码，并且在需要时对这些代码进行反复调用

函数的创建

- 函数声明

- ```javascript
  function 函数名([形参1,形参2。。]){
      语句
  }
  ```

- 函数表达式

- ![image-20200523163338135](C:\Users\zengxiaolong\AppData\Roaming\Typora\typora-user-images\image-20200523163338135.png)

- 函数的调用

  - ```
    函数对象([实参1，实参2，实参3。。。]){
    
    }
    ```

- 

- 使用typeof检查一个函数时会返回function

- ![image-20200523163423241](C:\Users\zengxiaolong\AppData\Roaming\Typora\typora-user-images\image-20200523163423241.png)

- 函数的参数

  - 形参
    - 在定义函数时，可以在函数的()中制定形参
    - 定义形参就相当于在函数中定义了变量，但是没有赋值
    - 形参的值最终由实参来决定的
  - 实参
    - 在调用函数时，可以在函数的()中指定实参
    - JS不会检查实参的类型和数量，可以传递任意类型的参数
    - 如果实参数量等于形参，则实参形参一一对应
    - 如果实参数量多于形参，多于的不会使用
    - 如果实参数量少于形参，没有实参的形参将会是undefined，前提是没有指定默认值，如果指定了默认值就是默认值

- 函数的返回值

  - 可以通过return来指定函数的返回值

  - 语法

    ```javascript
    return 值；
    ```

  - 返回值将会作为函数的执行结果返回，可以定义变量来接收返回值。

  - return后可以跟任意的值，如果没有值，相当于return undefined

  - **return执行后，函数会立即终止，后面的代码都不会执行，有点像break和continue，这个多练练**

  - ![image-20200523164315818](C:\Users\zengxiaolong\AppData\Roaming\Typora\typora-user-images\image-20200523164315818.png)

- 立即执行函数（IIFE)

  - 立即执行函数会在定义完成后立即执行，只会执行一次

  - 语法

    - ```javascript
      (function(){
      
      })()
      ```

    - 

- 连着写两个IIFE时必须以分号结尾

- ![image-20200523165037593](C:\Users\zengxiaolong\AppData\Roaming\Typora\typora-user-images\image-20200523165037593.png)

- 



# day08 预习 作用域 预解析 this 原型 原型 数组 

## 作用域

作用域是指变量的作用范围

在JS中一共有两种作用域

- 全局作用域

  - 直接编写在script标志中的JS代码

  - 全局作用域在页面打开时创建，在页面关闭时销毁

  - 在全局作用域中有一个 全局对象window，对象都是对现实世界的抽象，它代表的是一个浏览器的窗口，它由浏览器创建，我们可以直接使用

  - ```javascript
    console.log(window)
    ```

  - 在全局作用域中创建的变量都会作为window对象的属性保存

  - ```javascript
    var a=10;
    console.log(a)//也可以写成
    console.log(window.a);
    ```

  - 在全局作用域中创建的函数都会作为window对象的方法保存

    ```javascript
    function fun(){
    	console.log('我是fun函数')
    }
    fun()写成window.fun()是一样的
    window.alert('哈喽')
    ```

  - 我们所谓的函数就是window对象的方法

## 变量的声明提前（预解析）

![image-20200523221839731](C:\Users\zengxiaolong\AppData\Roaming\Typora\typora-user-images\image-20200523221839731.png)

如果声明变量时不使用var关键字，则变量不会被声明提前

函数的声明提前

- 使用函数声明创建的函数function 函数(){}
  - 它会在代码执行之前就被创建，所以我们可以在函数声明前调用函数
- 使用函数表达式创建的函数，不会被声明提前，所以不能在声明前调用
- 全局作用域中的变量都是全局变量，在页面任意部分都可以访问到

## 函数作用域

调用函数时创建函数作用域，函数执行完毕以后，函数作用域销毁

每调用一次函数就会创建一个新的函数作用域，他们之间是互相独立的

在函数作用域中可以访问到全局的变量

![image-20200523223138551](C:\Users\zengxiaolong\AppData\Roaming\Typora\typora-user-images\image-20200523223138551.png)

在全局作用域无法访问到函数作用域的变量

当在函数作用域中操作一个变量时，先在自身作用域中寻找，如果没有向上一级作用域寻找，一直找到全局作用域，如果全局作用域中也没有，就报错

在函数中访问全局变量可以使用window对象

在函数作用域中也有声明提前的特性，使用var关键字声明的变量，会在函数中所有的代码之前被声明

函数声明也会在函数中所有的代码之前执行

在函数中，不使用var声明的变量都会成为全局变量 

```javascript
function fun(){
    d=100;//这里相当于写的window.d=100;d没有使用var关键字，就会设置为全局变量
}
fun();
console.log(d);
```

## this

解析器在调用函数时，每次都会向函数内部传递一个隐含的参数，这个隐含参数就是this

this实际上是个参数，只不过是浏览器传进来的，this指向的是一个对象，这个对象我们称为函数执行的上下文对象

根据函数的调用方式的不同，我们的this会指向不同的对象

以函数形式调用，this永远指向window

以方法调用时，this就是调用方法的那个对象

```javascript
        var name='全局';

        function fun() {
            console.log(this);//这里写this就很灵活，当obj.sayName调用的时候就指向obj，当obj2.sayName调用的时候就指向obj2
        }
        var obj = {
            name: 'swk',
            sayName: fun
        }
        var obj2 = {
            name: 'shs',
            sayName: fun
        }
        // fun();
        obj2.sayName();
```



## 使用工程方法创建对象

```javascript
        var obj={
            name:'swk',
            age:18,
            gender:'男',
            sayName:function(){
                alert(this.name);
            }
        }
        //使用工程方法创建对象
        function createPerson(name,age,gender){
            var obj=new Object();

            //将对象中添加属性
            obj.name=name;
            obj.age=age;
            obj.gender=gender;
            obj.sayName=function(){
                alert(this.name);
            }
            //将新对象返回
            return obj;
        }
        var obj2 = createPerson('zjl',30,'人妖');
        var obj3 = createPerson();
        var obj4 = createPerson();

        console.log(obj2);
```

这种方式更简单，更方便批量创建对象

对象字面量里面两个属性之间用'，'隔开，而两个语句之间用'；'隔开，

使用工厂方法创建的对象，使用的构造函数都是Object，所以创建的对象都是Object这个类型，就导致我们无法区分出多种不同的对象

## 构造函数

创建一个构造函数，专门用来创建Person对象

构造函数就是一个普通函数，创建方式和普通函数没有区别，不同的是构造函数习惯上首字母大写

```javascript
function Person(){

}
```

构造函数和普通函数的区别就是调用方式的不同

普通函数就是直接调用，而构造函数需要使用new关键字调用

构造函数执行流程

- 当调用构造函数的时候，立刻创建一个新的对象，以出现new， 就会在堆内存开辟一个新空间创建对象 

- 将新建的对象设置为函数中的this，在构造函数中可以使用this来引用新建的对象，this会作为返回值赋值给新创建的函数

- 逐行执行函数中的代码

- 将新建的对象作为返回值返回

- ```javascript
  function Person(){
  	alert(this);//就是新建的对象per
  }
  var per = new Person;
  console.log(per);
  ```

- 



使用同一个构造函数创建的对象，我们称为一类对象，也将一个构造函数成为一个类 

我们将通过一个构造函数创建的对象，成为该对类的实例

```javascript
var obj=new Object()//obj就是Object的实例
```



使用instanceof可以检查一个对象是否是一个类的实例

- ```javascript
  function Person(){}
  console.log(per instanceof Person)
  ```

- 语法：对象 instanceof 构造函数

- 如果是，则返回true，否则返回false

- 所有对象都是Object的对象，所以任何对象和Object做instanceof检查都会返回true

this的情况

- 当以函数的形式调用时，this是window
- 当以方法的形式调用时，谁调用方法this就是谁
- 当以构造函数调用时，this就是新创建的那个对象

```javascript
//在Person构造函数中，为每一个对象都添加了一个sayName方法
//目前我们的方法是在构造函数内部创建的，构造函数每执行一次就会创建一个新的sayName方法
//所有实例的sayName都是唯一的
//执行一万次就会创建一万次新的方法，而且一万个方法都是一模一样的，这完全没必要，完全可以使所有的对象共享同一个方法
//将sayName方法在全局作用域定义，这样很大程度上提升了程序的性能
function fun(){
        alert('哈喽大家好，我是：'+ this.name);
    }
function Person(name,age,gender){
    this.name=name;
    this.age=age;
    this.gender=gender;
    //向对象中添加一个方法
    this.sayName = fun
}
	//创建一个Person实例
	var per = new Person('孙悟空',18,'男')；
    var per2 = new Person('猪八戒',20,'男')；
    per2.sayName();

//这里有个问题，将函数定义在全局，污染了全局作用域的命名空间，这样也很不安全，比如开发一个项目多人开发，可能另一个人也用fun这个名字，那么我这个fun就被覆盖了，下面讲到原型
```

## 原型	 prototype

我们所创建的每一个函数，解析器都会向函数中添加一个属性**prototype**，这个属性对应一个对象，这个对象就是我们所谓的**原型对象**

将函数定义在全局作用域，污染了全局作用域的命名空间，而且定义在全局作用域中也很不安全，

这个属性对应着一个对象，这个对象就是我们所谓的原型对象，如果函数作为普通函数调用，prototype没有任何作用

当函数通过构造函数的形式调用时，它所创建的对象中都会有一个隐含的属性指向该构造函数的原型对象，我们可以通过__ proto __来访问该属性 

**原型对象就相当于一个公共的区域，所有同一个类的实例都可以访问到这个原型对象**

我们可以将对象中共有的内容，统一设置到原型对象中

当我们访问对象的一个属性或者方法时，它会先在对象自身中寻找，如果有就直接使用，如果没有就会去原型对象中寻找，如果找到就直接使用

以后我们创建构造函数时，可以将这些对象共有的属性和方法统一添加到构造函数的原型对象中，这样不用分别为每一个对象添加，也不会影响到全局作用域，就可以使每个对象都具有这些属性和方法了

 检查对象里面是否有某个属性，如果对象中没有但是原型中有，也会返回true

```js
console.log('属性名' in 对象名);
```

可以使用对象的`hasOwnProperty()`来检查对象自身中是否有该属性，这个方法只有当对象自身中含有属性时，才会返回true

```
对象.hasOwnProperty('属性名')
```

原型对象也是对象，它也有原型

当我们在使用一个对象的属性或方法时，会先在自身中寻找，自身中如果有就直接使用，如果没有就取原型对象中寻找，如果原型对象中有，则使用，如果没有就去原型的原型中寻找

获取原型的原型

```javascript
console.log(对象.__proto__.__proto__);
```

Object对象的原型没有原型，如果在Object中依然没有找到，就返回undefined

## 数组

1.从前往后遍历，数组里面5个元素，打印出来

  var arr=[10,20,30,23,43]

```js
		var arr=[10,20,30,23,43];
        for(var i=0;i<arr.length; i++){
            document.write(arr[i]+'&nbsp;&nbsp;');
        }
        document.write('<br/>');
        document.write('<br/>');
```



2.从后往前遍历数组

 var arr=[10,20,30,23,43]

```js
		 var arr=[10,20,30,23,43];
        for(var i=arr.length-1; i>=0; i--){
            document.write(arr[i]+'&nbsp;&nbsp;');
        }
```





3.数组求和

  var arr=[10,20,30,23,43]

```js
 		//定义一个求和的变量
        var sum = 0;
        //获取数组当中所有的数
        for (var i = 0; i < arr.length; i++) {
            sum += arr[i];
        }
        console.log(sum);

```



4.求数组最大值，最小值，平均值

- 随便定义一个数组

- 定义一个的变量表示最大值的数组

- 定义一个变量表示最小值的数组

- 定义一个变量表示总和的数组，目的是为了算平均值

- ```js
  		 var arr = [23, 21, 1, 33, 85];
          //定义最大值
          var max = arr[0];
          //定义最小值
          var min = arr[0];
          //定义求和的变量，为了最后求平均值
          var sum = 0;
          //获取arr所有的数
          for (var i = 0; i < arr.length; i++) {
            //拿原数组所有的数跟max数组的第一个数对比，找到最大值，找到了就放进max数组里面
              if(max<arr[i]){
                  max = arr[i];
              }else if(max>arr[i]){//对比找到最小值之后放进min数组里面
                  min = arr[i];
              }
              sum += arr[i];
          }
          //
          console.log('最大值='+max);
          console.log('最小值='+min);
  ```

- 

5.合并数组（在新数组当中合并/在原数组当中合并）

```js
		//方法1：在新数组中合并
        var arr1 = [1,3,5,7,9];
        var arr2 = [2,4,6,8,10];
        //创建一个空的新数组
        var newArr=[];
        //遍历第一个数组
        for(var i = 0; i < arr1.length; i++){
            newArr[newArr.length]=arr1[i];
        }
        //遍历第二个数组
        for(var i = 0; i < arr2.length; i++){
            newArr[newArr.length]=arr2[i];
        }
        console.log(newArr)

        //方法2：在原数组中合并
        var arr1 = [1,3,5,7,9];
        var arr2 = [2,4,6,8,10];
        //遍历第一个数组
        for(var i =0; i<arr1.length; i++){
            arr2[arr2.length]=arr1[i];
        }
        console.log(arr2);
```

6.找出数组中的所有偶数打印，奇数生成新数组

var arr = [1,2,3,4,5,6,8,10];

```js
 		var arr = [1,2,3,4,5,6,8,10];
        //声明一个变量表示新数组
        var newArr=[];
        //遍历数组里面所有的数
        for(var i = 0; i<arr.length; i++){
            //判断偶数
            if(arr[i] % 2 ==0){
                console.log(arr[i]);
            }else{
                newArr[newArr.length]=arr[i];
            }
        }
        console.log(newArr);
```

数组的增删改查

```js
        var arr=[2,34,5,6,6,7,3];
        //增
        arr[arr.length]=23;
        console.log(arr);
        //删
        arr.length -= 2;
        console.log(arr);

        //改
        arr[2]=2;
        console.log(arr);

        console.log(arr[3]);

         //末尾增一个：
         arr[arr.length]=23;

        console.log(arr);

          // 头部增加一个
          for(var i = arr.length -1; i >=0; i--){
            arr[i + 1]= arr[i];
        }
        console.log(arr);

        // 构造函数定义数组
        // 创建一个新数组，并打印
        var arr2=new Array(3,3,4,);//如果里面只写一个数字代表的是数组的长度
        console.log(arr2);
```



## 数组去重

```js
数组去重(都是不动原来的数组，去重后是一个新数组)
		//创建一个原数组
        var arr = [2,3,4,5,2,3,4,6,7,4]
        //创建一个空的新数组，用来放去重后的数
        var newArr = [];

        //遍历原数组
        for(var i = 0; i<arr.length; i++){
            //遍历新数组
            for(var j =0 ; j<=newArr.length; j++){
                if(arr[i]===newArr[j]){
                    break;
                }else if(j===newArr.length){
                    newArr[j]=arr[i];
                    break;
                }
            }
        }
        console.log(newArr);
```

## for循环强化练习

计算100的阶乘 1*2....*100  100!



求1!+2!+3!+...+20!的值

打印三位数位上有3或者7的数字





# day08 作用域==>day08预习

如果一个对象的属性是函数，则该函数是这对象的一个方法（method），这里表示调用obj的g方法

![image-20200525084235380](C:\Users\zengxiaolong\AppData\Roaming\Typora\typora-user-images\image-20200525084235380.png)

在JS中，函数和方法主要就是称呼不同，本质是一样的，都是用来存代码的

比如

```js
alert()是函数直接调了
console.log()是方法//console代表的是一个对象，log是console对象的一个属性，也是方法
```

## 局部作用域

- 函数作用域
- 块作用域

## 全局作用域

- 直接写在script标签内部的变量都位于全局作用域里

- var声明的变量没有块作用域，所有在代码块中使用var声明的变量依然是全局变量

- 在代码块中（if switch while for)使用var声明的变量也在全局作用域中
- 在全局作用域中创建的变量，被称为全局变量，全局变量能在任意位置被访问
- 在全局创建的函数成为全局函数，在任意位置都能调用
- 全局作用域在网页加载时创建，在网页关闭时销毁

## 变量提升(预解析)

 在JS中，所有使用var关键字声明的变量，会在所有的代码执行前完成

- 这个特点我们成为变量提升，只有声明会被提前，而赋值不会被提前
- 这个表示不能在c被初始化之前访问
- ![image-20200525093625522](C:\Users\zengxiaolong\AppData\Roaming\Typora\typora-user-images\image-20200525093625522.png)
- 使用let声明的变量无法在初始化前被访问
- 使用函数声明的函数，它会在所有代码执行前被创建，调函数就不用考虑函数的位置了
- 只有var和function开头的代码会被提升
- 立即执行函数不会被提升，这个是创建执行同时完成

## 全局对象

变量实际上也是存储在对象当中`var a=10;`

在全局作用域中，有一个对象叫做全局对象

- 在全局创建的所有变量，都会作为全局对象的属性保存
- 在全局作用域中创建的所有函数，都会作为全局对象的方法保存
- 在浏览器中，全局对象叫做window
- 在全局作用域中所有的变量和函数都存储在window对象中
- 全局函数是window对象的方法，可以通过window.xxx()来调用
- 声明变量不使用var关键帧，相当于直接向window对象添加属性

## 函数作用域

函数作用域在函数调用时产生，在函数调用结束时销毁

每调用一次函数就会产生新的函数作用域

在函数作用域中定义的变量是局部变量，只能在函数内部访问

全局作用域无法访问局部变量

在函数中定义的函数是局部函数，只能在函数内部调用

变量和函数的提升同样适用于函数作用域

使用var声明的变量和function开头的函数，会在函数内部所有代码执行前声明和创建

一个作用域对于它外部的作用域是完全封闭的

## 作用域链

当我们去访问一个变量时，会优先在当前作用域中寻找是否有该变量，如果没有就取上一层作用域中寻找，如果全局都没找到就报错，`Uncaught ReferenceError:xxx is not defined`

![image-20200525114938280](C:\Users\zengxiaolong\AppData\Roaming\Typora\typora-user-images\image-20200525114938280.png)

作用域链就是查找变量的方向

**在作用域中找变量，找到全局还是没有就报错**

这里的c.name会被影响 

![image-20200525141739915](C:\Users\zengxiaolong\AppData\Roaming\Typora\typora-user-images\image-20200525141739915.png)

**scope 作用域**

## this

在每个函数中，都有一个隐含的参数叫this

this代表的是当前调用函数的对象，简单来说，谁调用的函数，this就是谁

this是谁，主要是由函数的调用方式来决定

- 如果以函数的形式调用，this就是window
- 如果以方法的形式调用，this就是调用方法的对象



## 总结

### 方法

- 一个对象的属性也可以是一个函数，如果对象的属性是函数，则称为这个函数是该对象的方法，调用函数就称为调用方法
- 函数和方法没有本质区别，函数实际上就是window对象的方法

### 作用域

- 作用域指的就是一个变量的作用范围，变量在何处可见
- 作用域主要分为两种：
  - 全局作用域
    - 全局作用域在网页加载时创建，在网页关闭时销毁
    - 所有的**直接**写在script标签中的变量都在全局作用域中
    - 全局作用域中的变量叫做全局变量，函数叫做函全局函数
    - 全局函数可和变量可以在任意位置被访问
    - 全局作用域中存在一个全局对象window，所有全局变量都会作为window对象的属性保存，所有的全局函数都会作为window对象的方法保存（只针对var的情况，没考虑let）
      - 使用let声明的变量不会存储在全局里面
  - 局部作用域
    - 块作用域
    - 函数作用域
      - 函数作用域在调用时创建，调用结束时销毁，每调用一次函数就会创建一个新的函数作用域。
      - 在函数中声明的变量（或参数）都属于局部变量
      - 局部变量对于外部是隐藏的，不能获取
      - 在函数作用域中，可以访问全局变量
      - 在函数中声明变量时，如果不使用var，变量会成为全局变量
  - 变量和函数的提升
    - 使用var声明的变量，使用function开头的函数，会在所有代码执行前执行（在预解析阶段执行）
    - 变量会被提前声明但不赋值，function会直接创建
    - 在全局作用域和函数作用域都会出现提升情况
  - 作用域链
    - 当访问一个变量时，浏览器会先在作用域中寻找该变量，如果找到了就直接使用，如果没找到继续向上一层作用域中寻找，如果找到全局还没找到就报错

### this

this是函数中的隐含的参数

this的值只跟函数的调用方式有关

根据调用方式的不同

- 以函数形式调用，this是window
  - 例子
    - xxx()
- 以方法形式调用，this是调用方法的对象
  - 例子
    - xxx.yyy()
- 

# 构造函数

构造函数(constructor)

- 构造函数是专门用来创建对象的函数
- 构造函数其实就是普通函数
- 构造函数和普通函数的区别在于调用方式
  - 如果函数直接调用，那么它就是一个普通函数
  - 如果通过new关键字来调用，那么它就是一个构造函数

构造函数的作用就是返回新对象

为了和普通函数区分，构造函数通常会大写字母开头，比如String，Number

构造函数的执行流程

​	1.调用构造函数，它会创建一个新的对象

​	2.将新 对象设置为函数中的this，构造函数中，this表示新创建的对象

​	3.执行函数中的代码

​	4.将新的对象作为返回值返回

在构造函数中，可以通过this向新对象中添加属性

```js
function Person(name,age,gender){
    this.name='孙悟空';
	this.age=18;
	this.gender='男'
	this.sayHello=function(){
    console.log('我是'+this.name)
	}

}
	var p1 = new Person('孙悟空',18,'男');
	var p2 = new Person('猪八戒',20,'男');

```

省略了创建和返回的步骤

**构造函数一定要用new去调用**

Person实际上是对象类型

字面量创建的对象都是Object

工厂方法创建的对象没办法区分出类型，因为返回的都是Object

一个构造函数也被称为一个类（class）

- 通过一个类创建的对象，我们称这个对象是这个类的实例
- 通过同一个类创建的对象，我们称其为一类对象

`instanceof`运算符，可以用来检查一个对象是否是一个类的实例

```js
function Person(){}
console.log(per instanceof Person)
```

目前，我们讲sayHello()方法定义在构造函数内部，这就意味着，构造函数每执行一次就会创建一个新的函数对象，这就导致了每一个对象的sayHello方法都是不同的函数对象

但是本质上每个对象的sayHello()结构是一模一样的，创建多个对象完全是浪费内存空间

创建这么多相同的函数对象是没有必要的，我们完全可以让所有的对象都使用同一个sayHello()方法

问题：如何能做到这样？》》原型

### //调用的时候new干了4件事

​      //1、首先会在堆当中开辟一个新的空间（准备实例化出来的对象）

​      //2、把函数调用的this指向指向新开辟的空间

​      //3、老老实实执行函数里面的代码，就是把相应的属性和值塞到新的空间当中（实例化过程）

​      //4、把实例化的丰满的有内容的这个空间地址给返回

## 原型

类型是对象的模板，比如上帝就是类，人就是实例

JS又增加了一个缺陷，可以通过实例去修改原型，但是千万不要这么做

不一样的属性写到构造函数里面，比如name，age，一样的写到显示原型里面添加一个属性

怎么检查属性在对象里面还是在原型里面

In运算符，用来检查一个对象中是否含有某个属性，比如检查p1里面有没有name属性



![image-20200526135858059](C:\Users\zengxiaolong\AppData\Roaming\Typora\typora-user-images\image-20200526135858059.png)

name是在原型里的，p1本身是没有name属性的，这就是in的特点

使用in检查一个属性时，无论属性是在原型中还是在对象本身中都会返回true



可以使用对象的`hasOwnProperty()`来检查对象自身中是否有该属性，这个方法只有当对象自身中含有属性时，才会返回true

```js
对象.hasOwnProperty('属性名')
```

当打印一个对象时，方法必须要将对象转化为字符串然后再输出

比如var mc = new 构造函数()

打印mc 就是[object Object]

mc被转成字符串，实际上就是调用了mc的toString()方法

Object的原型是所有对象的原型，如果依然没找到返回undefined

找原型的原型的原型，如果找不到就返回null

Object的原型Object.prototype是所有对象的原型

检查某个对象是否是某个类的实例

```js
对象 instanceof 类（构造函数）
```

推荐使用第二种，一般用的第一个

![image-20200526145420778](C:\Users\zengxiaolong\AppData\Roaming\Typora\typora-user-images\image-20200526145420778.png)

这三个指的是同一个对象

![image-20200526145557387](C:\Users\zengxiaolong\AppData\Roaming\Typora\typora-user-images\image-20200526145557387.png)

prototype只对类有用

_ _ proto _ _是给自己用的

prototype是给别人用的

打印一个对象时，显示的实际上是对象的toString()方法返回值

如果不希望打印[object Object]，可以重新为对象设置一个toString（）方法

![image-20200526150508273](C:\Users\zengxiaolong\AppData\Roaming\Typora\typora-user-images\image-20200526150508273.png)

直接改原型的toString，可以直接把相关的实例都改了

静态方法，不需要创建实例就可以调用

![image-20200526152042506](C:\Users\zengxiaolong\AppData\Roaming\Typora\typora-user-images\image-20200526152042506.png)

![image-20200526152053607](C:\Users\zengxiaolong\AppData\Roaming\Typora\typora-user-images\image-20200526152053607.png)



实例的属性

![image-20200526152109144](C:\Users\zengxiaolong\AppData\Roaming\Typora\typora-user-images\image-20200526152109144.png)

属性在构造函数的原型里，都是可以通过实例去调

![image-20200526152146007](C:\Users\zengxiaolong\AppData\Roaming\Typora\typora-user-images\image-20200526152146007.png)

## 垃圾回收机制

垃圾回收（GC Garbage collect）

- 程序在运行的过程中，会产生大量的垃圾，这些垃圾如果长期存在内存中，会严重影响到程序的运行速度
- 程序中的垃圾必须被及时清理，以确保运行不会被影响到程序的运行
- 所有访问不到的对象都是垃圾对象
- 如果一个对象没有任何的变量对其引用，则该对象就是一个垃圾对象
- 像这种垃圾对象，在程序存在过多，会导致程序运行变慢，必须清理，那么如何清理？
- 在JS中有自动垃圾回收机制，我们只需要将不使用的变量设置为null就可以了

## 数组

数组也是一个对象，也是用来存储数据的，和object不同，数组中可以存储一组有序的数据，而object是按照名字存储的

数组中存储的数据称为元素

数组中的每一个元素都有一个唯一的索引，通过索引可以对其进行各种操作

索引（index），从0开始的整数

创建一个数组对象

```js
var arr = new Array()
```

向数组中添加元素

语法

```js
数组[索引]=值；
arr[0]=33;//往数组第一个位置添加了一个值是33
arr[1]=22;
```

数组和对象没有本质的区别，不同点在于对象中使用属性名来操作数据

数组中通过索引来操作数据

对于存储大量数据就用数组

语法

```js
数组[索引]
```

如果读取数组中没有的属性，会返回undefined

获取数组的长度

arr.length

对于连续数组，length获取到的就是元素的数组

对于非连续数组，length获取到的就是元素的最大索引+1，在实际开发中，尽量避免使用非连续数组，性能差

length属性也可以直接修改，比如arr.length=20，就把长度改成20，可以增加长度，也可以缩短长度

向最后一位增加元素

```js
arr[arr.length]
```

for-of和for-in类似，for-of直接返回元素，for-in返回的是索引，这两种循环对老版本的浏览器支持度不高

**练习**

创建一个Person类，创建一个数组，向数组中添加几个Person对象

要求创建一个函数，可以获取到数组中所有的成年人，并将其保存到一个新的数组中返回，

## 总结

### 构造函数

构造函数（类）是专门用来创建对象的函数，更像是一个匆忙上线的产品

构造函数就是一个普通函数，一个函数如果直接调用那么就是一个普通函数，如果通过new调用，就是一个构造函数

一个构造函数也称为一个类，通过该构造函数创建的对象，称对象为该类实例。通过同一个构造函数创建的对象为同一类对象

构造函数执行流程

- 先创建一个新的对象
- 将新的对象设置为函数的this
- 逐行执行代码
- 将新的对象作为返回值返回

this到底是谁

- 以函数形式调用时，this是window
- 以方法形式调用时，this是调用方法的对象
- 以构造函数形式调用时，this就是实例对象
- 未完待续。。。



### 数组的方法

- 类方法

  - Array.isArray()

    - 用来检查一个值（对象）是否是数组，是数组返回true，不是返回false

  - 实例方法（通过实例对象调用）

    - push()

    - pop()

    - unshift()

    - shift()

    - concat()

      - 用来连接两个或多个数组
      - 该方法不会影响到原数组，而是返回一个新的数组

    - join()

      - 将数组中所有的元素拼接为一个字符串
      - 参数
        - 第一个参数：字符串，该字符串会成为连接符来连接每一个元素
          - 如果不指定，默认使用，作为连接符
        - 不会影响原数组

    - slice()

      - 用来抽取数组中部分元素，生成新数组（不会影响到原数组）
      - 参数
        - 第一个参数，抽取的起始位置索引，包含起始位置
        - 第二个参数，抽取结束位置的索引，不包含结束位置
        - 如果省略第二个参数，默认会抽取到最后
        - 索引可以是负值，负值表示倒数第几个

    - splice()

      - 用来删除、添加、替换数组中的元素（会影响到原来的数组）

      - 参数

        - 第一个参数：删除的起始位置索引
        - 第二个参数：删除的数量
        - 第三个后的参数：要添加的元素

      - 返回值

        - 返回的是被删除的元素

      - 例子

        - 删除元素

          - ```javascript
            arr.splice(2,3)//从索引2开始向后删除3个元素
            var result = arr.splice(2,3)//result接收到的是被删除的素
            ```

        - 替换元素

          - ```javascript
            var result = arr.splice(2,3,xxx,yyy,zzz)
            ```

        - 在指定位置插入元素

          - ```javascript
            arr.splice(2,0,xxxx,yyy)
            ```

          - 

    - IndexOf()

      - 用来查询元素在数组中第一次出现的位置
      - 参数
        - 第一个：被查询的元素
        - 第二个：查询的起始位置（默认是0）
      - 返回值
        - 找到元素，返回元素第一次出现的索引
        - 没找到返回-1
      - 区别
        - indexOf()从前往后找
        - lastIndexOf()从后往前找

    - lastIndextOf() 查询元素第二次出现的位置

    - forEach()

      - 为数组中的每一个元素调用函数

      - 只适用于数组

      - forEach()需要一个回调函数作为参数，回调函数会调用多次()，数组中有几个元素就调用几次，每次调用时会将元素的信息作为参数传递进回调函数

      - 可以通过定义参数来获取信息
      
      - 三个参数

        - value，当前的元素
  - index，当前元素的索引
        - array ，当前被遍历的数组

      - 可以在编辑器里面写出来，按住Ctrl单击forEach
      
      - ![image-20200529093315810](C:\Users\zengxiaolong\AppData\Roaming\Typora\typora-user-images\image-20200529093315810.png)
      
      - ```javascript
        var arr = ['孙悟空', '猪八戒', '沙和尚', '唐僧'];
                arr.forEach(function(index,arr){
                    console.log(index,arr);
                })
                //箭头函数写法
                // arr.forEach(((value,index,array) => console.log(array)));
                
               
                 var arr = ['彭于晏','孙悟空','周杰伦','猪八戒'];
                //  arr.forEach(function(a){
                //      console.log(a);
                //  })
                 //箭头函数写法
                 arr.forEach((value)=>console.log(value));
        
                    //用箭头函数编写两个数的和
                 var a= 10 , b=20;
                 fn=(a,b) => console.log(a+b);
                 fn(a,b);
        
                 var fn6 = () => console.log(this);
                fn6();
        
                var fn3 =()=>30+10;
                console.log(fn3());
        
                var fn4 = () =>{
                    var a=10,b=20;
                    return a+b;
                }
                console.log(fn4());
                
                var fn5 = () => ({a:10, b:33});
                console.log(fn5());
        
                var fn6 = () => console.log(this);
                fn6();
        ```
      
      - 



原型（prototype）

- JS是一门面向对象的高级语言，它的面向对象是基于原型的

- 在函数对象都存在一个属性prototype，该属性指向了一个对象，这个对象就是原型对象

- 如果函数作为普通函数调用，这个prototype没有任何作用

- 如果函数作为一个构造函数调用时，则它所创建的所有实例中都会有一个隐含的属性（_ _proto _ _ )指向该对象（实例的隐式原型指向构造函数的显示原型）

- 所以原型对象就相当于所有实例的一个公共区域，可以将对象中共有属性统一设置在原型对象中，这样我们只需要设置一次即可让所有的实例都具有这些方法

- 创建构造函数（类）时，将独有的属性在函数内部通过this来设置，将共有的属性在函数外部通过原型设置

  - ```javascript
    function Myclass(name,age){
        this.name=name;
        this.age=age;
    }
    Myclass.prototype.xxx=xxx;
    Myclass.prototype.yyy=functiong(){};
    ```

- 原型链

  - 在访问一个对象的属性时，JS解析器会先在先在对象本身中寻找，如果找到了，则直接使用。如果没找到就到对象的原型中寻找，找到了就使用，没找到就到原型的原型中寻找，以此类推，直到找到object的原型，它是所有对象的原型，如果依然没有找到，就返回undefined
  - 访问属性时，会沿着对象的原型链查找，找不到返回undefined
  - 访问变量时，会沿着作用域链查找，找不到会报错

- in运算符和方法：

  - in 运算

    - 检查一个对象是否含有某个属性（原型中含有该属性也会返回true）

    - ```javascript
      '属性名' in 对象
      ```

  - instanceof运算符

    - 检查一个对象是否是某个类的实例（原型链上有该类的实例就会放返回true）

    - ```javascript
      obj instanceof object //对象 instanceof 构造函数
      ```

    - hasOwnProperty（）

      - 检查一个对象自身是否含有某个属性

      - ```javascript
        obj.hasownproperty('name')//对象.hasownproperty
        ```

  - toString（）

    - 当打印一个对象时，浏览器会自动调用对象的toString()将对象转为字符串，然后再打印
    - 所有当打印一个对象时，实际上是打印对象的toString()方法的返回值
    - 可以通过重写toString()来改变打印对象输出的结果

### 垃圾回收

在变成语言中，不被任何变量或属性引用的对象（不可达对象）被称为垃圾对象。垃圾对象我们无法访问，但依然会占据内存空间。所以有必须对垃圾对象进行及时的清理，才能确保程序运行速度不会变慢

JS中有自动的垃圾回收机制，我们不需要手动回收，只需要将不再使用的变量设置为null即可

垃圾回收的常见方式：

- 引用计数，对象被引用的次数，记录对象被引用的次数

- ```javascript
  var a = {};
  b = a;
  c= a;//{}被引用了三次
  a = null//少了一次
  b = null //又少一次
  c = null //引用计数为0
  这时候就出现了垃圾回收机制
  
  ```

  - 会导致带来循环引用的问题，垃圾不能正确回收

- 标记清除，从根上开始，JS顶级对象是window，从window开始倒，倒出一个数来，只要是在这个树上的都不删，有些对象不在这棵树上就删除，这种性能就很差

- ![image-20200527092041334](C:\Users\zengxiaolong\AppData\Roaming\Typora\typora-user-images\image-20200527092041334.png)

- 分代收集，等于把上面两种综合，在系统底层把所有的对象分成了两代或者三代，一代青年，一代中年，一代老年，青年代表示刚刚生成的对象，老年代表示创建很长时间了，青年代容易死

- ### 数组（Array）

- 数组也是一个对象，用来存储一组有序的数据

- 数组中存储的数据被称为元素，在数组中通过索引来操作元素

- 索引指的是一组从0开始的整数

- 数组的使用

  - ```javascript
    var arr new Array()//通过构造函数创建
    arr = []//通过字面量创建数组
    arr = [3,3,4,5,]//创建数组时直接指定数组中的元素
    arr = new Array(3)//创建指定长度为3的数组
    ```

  - 

  - ```javascript
    向数组中添加元素
    arr[0]=33//向所有为0的位置添加一个元素 语法：数组[所有]=值；
    
    删除数组中的元素
    delete arr[0]//删除所有为0的元素
    
    读取元素
    arr[1];//读取索引为1的元素 ，读取一个不存在的元素会返回undefined
    
    获取数组的长度（元素的个数）
    arr.length//获取数组长度（最大索引+1）
    
    修改数组长度
    arr.length=3;
    //length可读可写，有的只是只读的
    ```

- 数组遍历

  - 将数组中的每一个元素都获取出来

  - 方法1，for循环（最传统，最灵活，兼容性也好）

  - ```javascript
    for(var i=0; i<arr.length; i++){
        arr[i];
    }
    ```

  - 方法2

  - ```javascript
    for(var i in arr){
        arr[i]
    }
    ```

  - for in也能遍历对象

  - ![image-20200527100617780](C:\Users\zengxiaolong\AppData\Roaming\Typora\typora-user-images\image-20200527100617780.png)

  - for-of遍历

    - ```javascript
      for(var e of arr){
          console.log(e);
      }
      ```

    - 老版本浏览器不支持

  - 

- JS中的数组没有大小限制，在数组中可以存储任意类型任意数量

- 存储大量数据时，数组的性能高于普通的对象

### typeof运算符

typeof用来检查一个值的类型

- 检查一个数字返回'number'
- 检查一个字符串时返回'string'
- 检查布尔值返回'boolean'
- 检查undefined返回'undefined'
- 检查对象或null返回'object'
- 检查函数返回'function'
- 检查数组返回'object'
- 其他对象都是返回'object'
- 检查大整数返回'bigint'（了解）
- 检查Symbol时返回'symbol'（了解）

检查函数返回'function'其他都是返回'object'



# call和apply

![image-20200526214713122](C:\Users\zengxiaolong\AppData\Roaming\Typora\typora-user-images\image-20200526214713122.png)

# instanceof

![image-20200526215902811](C:\Users\zengxiaolong\AppData\Roaming\Typora\typora-user-images\image-20200526215902811.png)

**webstorm里面live Templates(定义输入的快捷方式)**



![image-20200527101905293](C:\Users\zengxiaolong\AppData\Roaming\Typora\typora-user-images\image-20200527101905293.png)

# day10 高阶函数 箭头函数 数组方法

加引号就是调用toString

![image-20200527104046398](C:\Users\zengxiaolong\AppData\Roaming\Typora\typora-user-images\image-20200527104046398.png)

## 高阶函数

如果一个函数的参数是函数，或者函数的返回值是函数，这个函数就称为高阶函数

就是把代码动态的传递到函数里面，不需要把函数写死

将函数作为参数的目的

- 动态的向函数内部传递代码
- 作为参数的函数，由我们定义的，但是没调用，这种函数叫做**回调函数(callback)**
- ocp原则(开闭原则)
  - 一段程序(代码)应该对修改关闭，就是我写完的函数，不希望别人改我的函数，别的地方有可能用这函数，可能导致别的函数不好使了
  - 对更新开放，就是说不能改，可以更新，可以扩展
  - 把匿名函数做为形参简便一些

## 箭头函数

- 箭头函数(=>)

  - 专门用来定义这种作为参数的函数

  - 语法

    - ```javascript
      （[形参..]）=>返回值
      //一般用于简单函数，就是用于回调函数，不要写的太复杂，缺点就是兼容性不太好，ie不兼容
      ```

    - 如果函数只有一个参数，可以省略括号

  - 如果没有参数必须写

  - ![image-20200528111744879](C:\Users\zengxiaolong\AppData\Roaming\Typora\typora-user-images\image-20200528111744879.png)

  - 用的最多的还是 `var fn = (a,b)=>a+b;`，太复杂的不建议用箭头函数

  - 如果返回值是个对象，就不能这样写

  - ![image-20200527143124083](C:\Users\zengxiaolong\AppData\Roaming\Typora\typora-user-images\image-20200527143124083.png)

  - 如果返回值是一个对象字面量，必须在对象外添加()

  - ```javascript
    var fn5 = ()=> ({a:10 , b:33});//这样才能正常返回一个对象
    ```

  - 

- 箭头函数的this，这里的this就是window

- ![image-20200527143337456](C:\Users\zengxiaolong\AppData\Roaming\Typora\typora-user-images\image-20200527143337456.png)

- ```javascript
  (a,b)=>a+b//标准语法
  a => a+10//如果箭头函数只有一个形参，可以省略()
  () =>30+10//没有形参，()不能省略
  () =>{//如果函数体比较复杂， 可以使用代码块{}
      var a = 10;
      var b = 20;
        return a+b;
  }
  () =>({a:10,b:33})//如果返回值是一个对象字面量，字面量外部必须加()
  ```

- 

- 这里的fn7是函数形式调用的，但是this却是Object

- ![image-20200527143514632](C:\Users\zengxiaolong\AppData\Roaming\Typora\typora-user-images\image-20200527143514632.png)

- 所以箭头函数的this不由它自己的调用方式决定，而是由外部作用域决定，会根据外层作用域改变，没有自主决定权

变量在作用域链上，属性在原型链上，变量是沿着作用域链找

![image-20200527145701931](C:\Users\zengxiaolong\AppData\Roaming\Typora\typora-user-images\image-20200527145701931.png)



![image-20200527151050171](C:\Users\zengxiaolong\AppData\Roaming\Typora\typora-user-images\image-20200527151050171.png)

JS中的作用域被称为词法作用域，在哪定义的，作用域就是哪里，和调用没关系

**没事可以看看文档多做做练习**

修改器方法会对原数组造成破坏

```javascript
.pop//删除并返回数组的最后一个元素,并且返回删除的元素
.push// 在数组的末尾增加一个或多个元素，并返回数组的新长度。
.shift//删除并返回数组的第一个元素。
.unshift// 在数组的开头增加一个或多个元素，并返回数组的新长度。
arr.concat()//用来将多个数组合并为一个数组，该方法不会影响到原数组，将结果存储到新数组返回
join()//将数组中所有元素连接为一个字符串
语法：
数组.join();
//它需要一个字符串作为参数，这个字符串会作为元素的连接符
//如果不知道参数，默认使用逗号作为连接符

```

```javascript
indexoOf()//查看数组里的元素的第一次出现的位置，数组里的元素可以是字符也可以是数字
lastIndexOf()//从最后一个元素向前找
```

参数

- 第一个是要查询的元素

- 第二个是查询的起始位置

- 返回值

  - 如果找到了元素，则返回元素第一次出现的索引

  - 如果没找到就返回-1

    

```javascript
slice(开始位置，结束位置)//抽取当前数组中的一段元素组合成一个新数组
```

参数

- 第一个参数，截取开始的位置

- 第二个参数，截取的结束位置，如果省略第二个参数，会一直截取到最后

  

```javascript
splice()//在任意位置给数组添加或删除任意个元素，这是破坏性的方法，调用后会影响原来的数组，这是多功能的
数组.splice(开始索引，删除数量)
替换元素  数组.splice(开始索引，删除数量，新元素，)
指定位置插入新元素 arr.splice(插入位置，0，新元素，新元素)
```



参数

- 第一个参数表示删除起始位置
- 第二个参数表示删除元素个数
- 第三个参数表示要添加的新元素
- 返回值是被删的元素

### forEach()

也是用来遍历数组的方法

- 需要一个回调函数作为参数
- 回调函数会执行多少次，数组里有几个元素就会执行几次
- 每次调用时都会将一个元素的信息传递进函数
- 可以通过定义参数来获取信息
- 回调函数汇总一共会接收到三个参数
  - 第一个参数：当前元素的值
  
  - 第二个参数：当前元素的索引
  
  - 第三个参数：被遍历的数组
  
  - ```javascript
     var arr = ['流星','2','3','45','454','31','67'];
     arr.forEach(element =>console.log(element));//返回的是数组里每个元素
      
    ```
  
  - 

### for-in循环

```javascript
 
        var objArr = ['奥特曼','忍者神龟','悟空']
        //用for in循环遍历数组
        for(var i in objArr){
            console.log(objArr[i]);
        }

        //创建一个对象
        var obj = {
            name:'周杰伦',
            age:48,
            gender:'男'
            };
        //用for-in遍历对象
        for(var n in obj){
            console.log(obj[n]);
        }
```



## 数组方法

### 删除、添加元素

```javascript
      var arr = ['周杰伦','那英','王力宏','孙悟空']

       //打印数组最后一个元素
       console.log(arr[arr.length-1]);
       
       //检查一个对象是否是一个数组
       console.log(Array.isArray(arr));

       //删除数组中最后一个元素
       console.log(arr.pop());

       //添加元素,返回的是索引
       console.log(arr.push('张三儿','李四儿'));
       
        //删除并返回数组第一个元素
        console.log(arr.shift());

        //在数组开头增加元素，返回数组最新长度
        console.log(arr.unshift('李四儿','张三儿'));
```

### 合并数组

```javascript
   var arr = ['孙悟空', '猪八戒', '沙和尚', '唐僧'];
        var arr2 = ['牛魔王','红孩儿','铁扇'];
        var arr3 = ['二郎神', '白龙马'];

        //把arr2和arr3合并成一个数组
        var result = arr.concat(arr2,arr3,'哈哈');

        //将arr数组连接成一个字符串
        result = arr.join(''+'，');	

        //查看元素第一次所在位置
        arr = ['a','c','b','d','e','f','a','c','a'];
        result = arr.indexOf('c');
        result = arr.lastIndexOf('c');

        console.log(result);
```

### 截取数组

```javascript
    var arr = ['孙悟空', '猪八戒', '沙和尚', '唐僧'];
        //slice(起始位置,截止位置)，不包括截止位置
        var result = arr.slice(1,3);

        //splice(起始位置，删除个数，要添加的新元素)
        //删除索引为0，个数一个，添加'牛魔王',等于把孙悟空换成牛魔王
        var result = arr.splice(0,1,'牛魔王');

        //
        console.log(arr);
```

### forEach

```javascript
   var arr = ['孙悟空', '猪八戒', '沙和尚', '唐僧'];
        arr.forEach(function(value,index,arr){
            console.log(value,index,arr);
        })

        arr.forEach(((value,index,array) => console.log(array)));
        
```

### 反转数组

```javascript
var arr = [1, 2, 3, 4, 5];
        //创建新数组用来放反转后的元素
        var newArr = [];
        //遍历原数组所有元素
        for (var i = arr.length - 1; i >= 0; i--) {
            newArr[newArr.length] = arr[i];
        }
        console.log(newArr);
```

### 二维、三维数组

```javascript
        var arr = [[1,2,3],[4,5,6],[7,8,9]]
        console.log(arr[2][1]);

        //三维数组
       var arr2=[[[1,2],[3,4]],[[5,6],[7,8]]]
            console.log(arr2[0][1])


    var arr3 = [[[1,2,3],[10,11,12]],[[4,5,6],[13,14,15]],[[7,8,9],[16,17,18]]];
    console.log(arr3[2][1]);
```



**作业**

1.数组去重练习

2.every(); 	some()	filter()	map() 	reduce()	reverse()	sort()预习整理

## every()

every()方法测试一个数组内的所有元素是否都能通过某个指定函数的测试。它返回一个布尔值。只要有一个不满足条件就返回false，其实是在foreatch基础上做的

用来检查数组中的每一个元素是否都符合条件

需要一个回调函数作为参数，**相当于一个与运算**

```javascript
//判断数组中大于=10的元素
function isBigEnough(element, index, array) {
  return element >= 10;
}
[12, 5, 8, 130, 44].every(isBigEnough);   // false
[12, 54, 18, 130, 44].every(isBigEnough); // true

//用箭头函数写法
[12, 5, 8, 130, 44].every(x => x >= 10); // false
[12, 54, 18, 130, 44].every(x => x >= 10); // true
```



## some() 

some() 方法测试数组中至少有1个元素通过了被提供的函数测试。它返回的是一个Boolean类型的值。

 用来检查数组中是否有元素符合条件**相当于或运算**

```javascript
const array = [1, 2, 3, 4, 5];

// checks whether an element is even，检查元素是否是偶数
const even = (element) => element % 2 === 0;

console.log(array.some(even));
```



## filter()

filter()方法创建一个新的数组，用来从数组中筛选出所有的符合条件的元素

**注意：** filter() 不会对空数组进行检测。

**注意：** filter() 不会改变原始数组。

```javascript
var ages = [32, 33, 16, 40];

function checkAdult(age) {
    return age >= 18;
}
console.log(ages.filter(checkAdult));
```



## map()

map()方法返回一个新数组，数组中的元素为原始数组元素调用函数处理的后值。 简单来说就是根据原来的数组生成新数组
map()方法按照原始数组元素顺序依次处理元素。 



```javascript
语法
array.map(function(currentValue,index,arr), thisValue)

arr = [3,4,5,3,4,5];
 var arr = [3,4,5,6,7,8];
        //每一原加10输出
        var result = arr.map(function(b){
            //遍历数组
            for(var i=0; i<arr.length; i++){
                console.log(arr[i]+10);
                
            }
        })

//用来对数组中的每一个元素做一个操作，返回一个新数组
		arr = [3,4,5,6,7,8];
        var result = arr.map(function (a) {
            if(a % 2===0){
                return a ** 2;
            }else{
                return a;
            }
        });
```



## reduce() 

reduce() 方法接收一个函数作为累加器，数组中的每个值（从左到右）开始缩减，最终计算为一个值。需要回调函数作为参数，参数有两个

- 第一个参数表示累加的结果
- 第二个参数表示当前的元素

reduce() 可以作为一个高阶函数，用于函数的 compose。

```js
		//课堂案例
		arr = [3,4,5,6,7,8];
        result = arr.reduce(function (a, b) {
            return a + b;
        });

        console.log(result);

//文档案例
        array.reduce(function(total, currentValue, currentIndex, arr), initialValue)
        arr = [3,23,4,5,6];
        var result = arr.reduce(function(a,b)){
        return a+b;
           }
        console.log(return)
```

## reverse()反转数组

对数组的元素反转

```javascript
 var arr = [1,2,3,4,5,6,7];

arr.reverse();
```



## sort()

对数组的元素进行排序。在排序是默认按照Unicode编码进行排序的

即使数组中的元素是数组，也是这做的

比字母是没有问题的

如果希望按照数字的大小排序，可以自己通过回调函数来指定排序规则

sor()中的回调函数用来指定元素的排序规则，它会被多次调用，每次调用时会传递数组中的两个元素作为参数

可以定义两个参数来接收元素，两个元素具体是谁不确定，但能确定的是a在数组中位于b的后面

只适用于新版的Chrome

![image-20200529110800332](C:\Users\zengxiaolong\AppData\Roaming\Typora\typora-user-images\image-20200529110800332.png)

sort会根据回调函数的返回值来决定两个元素是否交换位置

- 如果返回的是负值，两个元素会交换位置
- 如果返回的是正值，两个位置元素不变
- 如果返回a-b就返回升序排列
- 如果返回b-a就返回降序排列

在其他浏览器中，规则和Chrome完全相反，但是使用时没有任何区别

### sort方法总结

```javascript
		//原理
		// arr.sort(function (a, b) {
        //     //b,a
        //     // // 希望小的数字在前
        //     // if(a > b){
        //     //     // 后边的数字大于前边的数字
        //     //     return 1;
        //     // }else if(a === b){
        //     //     //两个数字相等
        //     //     return 0;
        //     // }else{
        //     //     // 后边的数字小
        //     //     return -1;
        //     // }
        //
        //
        //     // 希望大的数字在前
        //     if(a > b){
        //         // 后边的数字小于前边的数字
        //         return -1;
        //     }else if(a === b){
        //         //两个数字相等
        //         return 0;
        //     }else{
        //         // 后边的数字小
        //         return 1;
        //     }
        //
        // });
				↓↓
                ↓↓
                ↓↓
                ↓↓   
		arr = [3,1,2,4,5,6,8,9,7,10];
		arr.sort(function (a, b) {
        // 如果返回a-b，则表示数字升序排列
        // return a - b;
        // 如果返回b-a，则表示数字降序排列
            return b - a;
        });

        console.log(arr+'');
```



# 0528补课 函数和对象，返回值，this指向

原始类型（值类型）：Number、String、Boolean、Null、Undefined

对象类型（引用类型）：Object、Function、Array

## 关于对象

- 狭义的对象：Object
- 广义的对象：一切皆对象，包括Function、Array、String、Boolean、Number，自定义对象

## 对象和构造函数

- 对象是构造函数的实例，构造函数是对象的抽象
  - 构造函数决定了类型
  - 构造函数描述对象
  - 系统有很多定义好的构造函数
    - Object、Function、Array、String、Boolean、Number

每new一次都会在内存中开辟一个内存空间

## 原型总结

- 每个对象都有一个原型，对象的原型仍然是一个对象
- 当我们使用对象中某个属性的时候，如果对象不存在，会去对象的原型找也可以说对象会继承原型的属性
- 对象的原型仍然是个对象，原型作为一个对象也有自己的原型，一直到最顶部一个没有原型的对象，组成了原型链
- 当我们使用对象中某个属性的时候，如果对象不存在，会去对象的原型去找，如果还没有会继续在原型的原型找，一直找到原型链的结束，找不到返回undefined

找对象的属性，找不到返回undefined，找原型的原型找不到返回null

**数组的构造函数是Array**



# 冒泡排序

![image-20200528194358541](C:\Users\zengxiaolong\AppData\Roaming\Typora\typora-user-images\image-20200528194358541.png)

```javascript
 var arr = [23,12,45,58,3,6];
        //冒泡排序
        for(var i =0; i <= arr.length-1; i++){
            //外层表示循环的轮数
            for(var j =0 ; j<= arr.length-1-i ;j++){
                //内层表示每轮循环的次数，同时表示数组下标
                //判断如果前面的数大于后面的就调换位置
                if(arr[j] > arr[j+1]){
                    //定义一个变量用来保存交换位置的元素
                    var wrap = arr[j];
                    arr[j] = arr[j+1];
                    arr[j+1] = wrap;
                }
            }
        }
        console.log(arr);
```



# 0529 函数 伪数组 递归

## 伪数组

除了this，在函数内部还存在着一个隐含的参数arguments，是一个类数组对象（伪数组）

在数组里面的方法就不能在这里用 了

调用函数时，传递的所有实参都被存储在了arguments中

arguments[0]表示第一个实参

通过arguments即使不定义形参也可以使用实参



```javascript
//创建一个函数可以用来计算任意数字的和
function sum(){
    //创建一个变量存储结果
    var result = 0;
    //遍历arguments
    for(var i =0; i<arguments.length; i++){
        result += arguments[i]
    }
    return result;
}
```

### callee

它表示包含了一个属性callee，callee就表示当前正在调用的函数，不用管函数的名字，改名字也不会 影响

![image-20200530091524297](C:\Users\zengxiaolong\AppData\Roaming\Typora\typora-user-images\image-20200530091524297.png)



 ## 剩余参数rest

定义形参时，可以在参数列表的最后...rest，形式的参数

```javascript
function fn(a,b,...c){
    
}
```

形参前跟着...表示参数是剩余参数，剩余参数必须写在参数列表最后，所有的没有形参对应的实参都会保存到剩余参数中

这种参数叫做剩余参数

剩余参数本身就是一个数组，专门用来存储剩余的参数



## this——call 和apply

call()

当调用函数的call方法时，函数会立即执行，相当于调用整个函数

通过call方法调用函数时，可以通过它的第一个参数来指定函数的this

apply()也是函数对象的方法，作用和call差不多

apply的实参是写在[]里面，call是直接写

call在向函数传递实参时，参数是一个一个传递的

apply在向函数传递实参时，参数是存储在一个数组中传递的

它们的主要作用是修改this指向

call对箭头函数的this没有影响

```javascript
 function fn(a,b){
            console.log('函数执行',this);
            console.log('a=',a);
            console.log('b=',b);
        }

        var obj = {
            t:fn
        }
        fn.call(window,2,3)//改变this指向window，(改变this的指向,实参...)
        // fn.apply(window,[2,3]);//改变this指向指向window，（改变this的指向,[实参]）
```



### bind

bind()用于为函数绑定一个this

```javascript
 var obj = {name:'孙悟空'}

        function fn(a, b) {
            console.log('fn执行了，this是：',this);
            console.log(a, b);
        }
        var newFn = fn.bind(obj, 123, 456);
        newFn();
```



- 该方法需要通过函数对象调用，调用后并不会立即调用函数，而是返回一个新的函数对象
- 当我们通过新的函数对象来调用函数时，实际上就是在调用fn
- 只是此时fn中的this已经被写死了
- 这个表示底层代码
- ![image-20200529142602713](C:\Users\zengxiaolong\AppData\Roaming\Typora\typora-user-images\image-20200529142602713.png)
- 参数
  - 第一个参数是this
  - 第二个以后的参数是函数执行的实参
- 通过bind()获取的函数，其this和实参已经提前绑定好了，无法再传递新的参数

要传数组给形参，要在数组前面加**...**，这样数组的第一个元素会成为第一个参数，第二元素会成为第二个参数，以此类推

如果将数组中的值赋值给指定的三个变量，可以这样写

![image-20200529144827203](C:\Users\zengxiaolong\AppData\Roaming\Typora\typora-user-images\image-20200529144827203.png)

对象解构也可以这样用

![image-20200529145224745](C:\Users\zengxiaolong\AppData\Roaming\Typora\typora-user-images\image-20200529145224745.png)

解构对象时，如果不是以var开头，必须用()括起来

### this总结

**1、普通函数调用的时候this 是window**

 **2、方法当中调用 this 是这个方法的对象**

**3、构造函数调用的时候 this是准备实例化的对象**

**4、事件的回调函数，this指的就是事件源**

**5、call和apply 方法 this可以自己指定**

**普通函数和构造函数的区别**

- **调用的时候才知道是普通函数还是构造函数**

**this不同  返回值不同**

## 解构赋值

```javascript
 		// function fn(a,b,c){
        //     console.log('a=',a);
        //     console.log('b=',b);
        //     console.log('c=',c);
        // }

        // var arr= [10,20,30];
        // fn(...arr);


        // arr = [10, 20, 30, 40, 50, 60, 70];
        // // var [a,b,c] = arr;
        // var a,b,c;

        // [a,b,...c] = arr;
        // console.log(a, b, c);//[30, 40, 50, 60, 70]

        var obj = {name:'孙悟空', age:'18', gender:'男'};
        var {name, age, gender} = obj;

        console.log(name, age, gender);   

	//交换两个变量的值
	var a=10,b=20
    var temp;
	temp = a;
	a = b;
	b = temp;
	
	//用解构赋值交换两个变量的值
	var a=10,b=20
    [a,b]=[b,a]
```



## 递归

- 简单理解就是在函数里面调用自己
- 这种就相当于死循环，上限999次，这种函数就是递归
- ![image-20200529152336945](C:\Users\zengxiaolong\AppData\Roaming\Typora\typora-user-images\image-20200529152336945.png)



通过递归来计算任意数的阶乘

- **递归的核心思想就是化整为零，将一个大问题拆分为一个小问题**
- 两个条件缺一不可

  - 基线条件，设置递归的终止条件，只要写递归，先写这个		 
  - ![image-20200529154626991](C:\Users\zengxiaolong\AppData\Roaming\Typora\typora-user-images\image-20200529154626991.png)
  - 递归条件，规定了如何对问题进行拆分
  - ![image-20200529154706787](C:\Users\zengxiaolong\AppData\Roaming\Typora\typora-user-images\image-20200529154706787.png)

- 递归的功能和循环类似，都是可以用来反复执行某段代码的
- 相对循环来说，递归没有循环的性能好，递归每调一次函数就会产生作用域，并且大部分解析器都会限制递归执行的次数
- 递归轻易不要写，写不好就会写成死循环
- 相比于循环，递归的逻辑更容易理解
- 一般情况下，开发中递归不是我们的首选，甚至我们应该尽量避免使用递归，就相当于css里的impotent

## 递归版本的阶乘计算

```javascript
 // 递归版本的阶乘计算
        function jieCheng2(n) {
            //判断n是否等于1
            // 基线条件，设置递归的终止条件
            if(n === 1){
                return 1;
            }
            //如果n大于1，例如n=6
            //6! = 6 * 5!  n! = n * (n-1)!
            //递归条件，规定了如何对问题进行拆分
            return n * jieCheng2(n-1);
        }
       // console.log(jieCheng2(10))



       // 创建一个函数，用来求一个数幂运算（使用递归）
       // 6^6 = 6 * 6^5
       // 6^5 = 6 * 6^4
       function pow(num, times) {
            //设置基线条件（递归的停止）
           if(times === 1){
               // 要计算num的1次幂，直接返回num
               return num;
           }else if(times === 0){
               return 1;
           }

           //设置递归条件（拆分问题）
           return num * pow(num, times-1);
       }

        console.log(pow(2, 10));
```

# 0530 闭包

闭包指可以访问到外部作用域中变量的函数

每调用一次就会产生新的闭包，闭包和闭包之间是相互独立的

闭包是什么时候消失的？

- 直到内部函数被垃圾回收后才消失

次案例中inner就是闭包

![image-20200530113831084](C:\Users\zengxiaolong\AppData\Roaming\Typora\typora-user-images\image-20200530113831084.png)



这种是高阶函数，把内部函数作为返回值返回

![image-20200530114020996](C:\Users\zengxiaolong\AppData\Roaming\Typora\typora-user-images\image-20200530114020996.png)

闭包就是用来藏一些见不得人的东西

**编写闭包的三个条件**

- 函数的嵌套，只有函数嵌套才有作用域嵌套，才会有闭包
- 在内部函数中引用外部函数的变量
- 将内部函数作为返回值返回
- ![image-20200530115602866](C:\Users\zengxiaolong\AppData\Roaming\Typora\typora-user-images\image-20200530115602866.png)
- 此时的times只能被inner访问到
- 如果觉得这种麻烦也可以写匿名函数
- ![image-20200530115802908](C:\Users\zengxiaolong\AppData\Roaming\Typora\typora-user-images\image-20200530115802908.png)
- 

## 对象的复制

用slice截取数组里的元素

改一个对另一个没有影响

浅复制表示只对对象中的属性进行一个复制，只复制第一层

**浅复制**只会复制对象本身，不会复制对象的对象

**深复制**不仅复制对象本身，也复制对象的属性

Object.assign()用来将一个或多个对象中的属性复制到另一个对象中

- 第一个参数：目标对象
- 第二及以后的参数：表示被复制的对象



## 内建对象

就是在ES标准里定义的对象

## 日期对象

Date对象

- JS中所有的关于时间信息都需要通过Date对象来表示

创建一个Date对象

```javascript
var d = new Date();
```

如果直接使用new Date()创建时间对象，它会默认创建一个表示代码执行时刻的对象，也就是当前时间

如果希望创建一个指定的时间对象，需要传递一个字符串来指定时间

![image-20200530160752017](C:\Users\zengxiaolong\AppData\Roaming\Typora\typora-user-images\image-20200530160752017.png)

### getFullYear

获取当前Date()对象年份信息(四位)

### getMonth()

获取当前对象Date()的月份信息

0表示1月

1表示2月

。。。

### getDate

获取当前Date对象是几日

### getDay

获取周几，取值范围从0到6，0表示周日，1表示周一



### getTime()获取时间

用来获取当前日期对象的时间戳

时间戳从格林威治标准时间的1970年1月1日0时0分0秒，到当前时间所经历的毫秒数

时间必须有参照物，比如2020年是相对公元0年

### Date.now()

当前时间的时间戳

# 0531预习 Math String 正则



![image-20200530164606208](C:\Users\zengxiaolong\AppData\Roaming\Typora\typora-user-images\image-20200530164606208.png)

## Math

是一个内置对象，它拥有一些数学常数属性和数学函数方法。`Math` 不是一个函数对象。

语法

```javascript
Math.PI//圆周率，一个圆的周长和直径之比，约等于 `3.14159`
Math.sqrt() //平方根
Math.floor()//向下取整，往小了取
Math.ceil()//向上取整，往大了取
parseInt也能取整，但最好别用，因为这是专门对付字符串的，要先转换为字符串再取整
Math.round()//四舍五入
Math.max()//求出一系列数字中最大值
Math.min()//求出一系列数字中最小值
Math.abs()//绝对值
Math.pow(数字，几次方)//求xx的次方
Math.random()//求随机数（伪随机数），用四舍五入的方式取整，可以取0-任何数的
		//求 a - b 之间的随机整数
		console.log(Math.floor(Math.random()*(b - a + 1) + a));
        //四舍五入的方法
        console.log(Math.round(Math.random()*(b-a)+a));



```

## String 字符串方法

- 字符串的所有实例方法，都可以通过基本数据类型字符串去调用

- 字符串的本质就是一个字符数组

- ```javascript
  var str='Hello'==>['H','e','l','l','o']
  ```

- 

```javascript
 //创建一个字符串
        var str = 'djiWERzzGENFxxdrtbc23460983232';
        //indexOf获取字符串中字符的下标
        console.log(str.indexOf('2',2));

        //split将字符串拆分为数组返回，传空串能把字符转换成一个字符一个字符的数组，需要一个字符串作为参数
        console.log(str.split('',12))

        //slice截取指定子串
        console.log(str.slice(2,5))//第一个参数是开始的位置，第二个参数是结束的位置

        //substr截取指定长度的子串
        console.log(str.substr(2,5));//这个方法未来可能被移出掉，被substring代替

        //substring截取指定位置的子串
        console.log(str.substring(4,1));//先比较两个参数的大小之后，决定起始位置和结束位置，不能是负值，如果是负值自动充值为0，它会自动交换位置
        console.log(str.substring(2,4));

        //toLowerCase转换小写
        console.log(str.toLowerCase());

        //toUpperCase转换大写
        console.log(str.toUpperCase());

        //获取字符串自己
        console.log(str.valueOf());
        //把字符串转换成字符串
        console.log(str.toString());

        //charAt获取指定位置的字符串返回
        console.log(str.charAt(8));
		//如果该位置没有字符返回空串
	
        //指定位置返回Unicode码
        console.log(str.charCodeAt(8));

        //concat，连接两个或者多个字符串生成新的字符串,作用相当于+
        
        console.log(arr1.concat('hello','哈喽'));
	
		
        //查找字符串中字符的索引
        var str = 'hello how are you are a are'
         console.log(str.indexOf('are'));//10，第一次出现的索引位置
         console.log(str.lastIndexOf('are'));//24，表示最后一次出现的索引位置
 
        console.log(str.localeCompare(2))//比较大小，0代表相等  1代表原串大 -1代表原串小

		endsWith()//检查字符串是否是以指定内容结束
        
        startsWith()//检查字符串是否是指定内容开始

		//trim()去除字符前后两端的空格
		//trimEnd()去除后边的空格
		//trimRight()去除后边的空格
		//下面两个是一样的
		//trimStart()去除前边的空格
		//trimLeft()去除前边的空格
		//tirm对ie8 9 10 兼容问题，完全不用处理，这些浏览器太老了，除非新版本ie不兼容才处理

		// charAt()根据索引获取特定位置的字符
		//charCodeAt()根据索引获取指定位置字符的字符编码
		//String.fromCharCode()根据编码返回字符
		//repeat()将数组打印多少遍
        result = str.repeat(10);

		//查找结尾有没有某字符
		var str = 'hello';
        console.log(str.endsWith('o'));
        //查找开头有没有某字符
        console.log(str.startsWith('h'));
```

**对字符串操作的方法越多，对数据的操作方法就多**

- 比如说有时候要做数据的交换，一个公司有很多系统，a系统往b系统发送数据

  - ```javascript
    var data = 'sunwukong @-@ swk@hgs.com'
    //字符串中的分隔符，就从a系统发到b系统，b系统收到的是字符串，就可以直接用split拆分，得到的就是一个数组
    ```

  - 

## regexp 正则表达式

所有的语言都支持正则表达式，只是语法不同

爬虫爬到的是源码，实际上就是字符串

计算机根据正则表达式来检查一个字符是否符合规则

获取将子字符串中符合规则的内容提取出来

正则表达式是个对象

```javascript
var 变量 = new RegExp('正则表达式'，'匹配模式')
```

严格区分大小写

在构造函数可以传递一个匹配模式作为第二个参数

- 可以是
  - i 	忽略大小写
  - g    全局匹配模式

正则表达式的方法：

- test()
  - 使用这个方法可以检查字符串是否符合正则表达式规则
    - 符合返回true，不符合返回false
- 举例
- ![image-20200531155111436](C:\Users\zengxiaolong\AppData\Roaming\Typora\typora-user-images\image-20200531155111436.png)

构造函数的方式有点麻烦



使用字面量创建正则表达式

**语法**

- var 变量 = /正则表达式/匹配模式
- 使用字面量的方式简单
- 使用构造函数更加灵活

**|**表示或者的意思，找两个或者多个元素中的一个，满足就返回true

检查字符串中是否有字母，如果不想写太多的**|**可以用**[]**来代替，[]也是表示或的关系

**[a-z]**表示a到z的任意的小写字母

**[A-z]**表示任意字母

**[^...]**表示除了。。。

### test()

- 用来检查一个字符串是否符合正则表达式，符合返回true，不符合返回false

### split()

- split跟join是相反的，join是把数组中的元素拼接成一个字符串，split是把字符串拆分成一个数组

- 方法中可以传递一个正则表达式作为参数，这样方法会根据正则表达式去拆分字符串，比如把数字里面的字母全部拆分就可以这样写

- ```javascript
  var 变量 = 变量.split(/[A-z]/)
  ```

- 这个方法即使不指定全局匹配，也会全都拆分

### search()  

- 可以搜索字符串中是否含有指定内容

- 如果搜索到指定内容，返回的是字符的索引，如果没搜索到返回-1

- 它可以接受一个正则表达式作为参数，然后会根据正则表达式去检索字符串

- 只会查找第一个，即使设置全局查找也没用

- ```javascript
  var str = 'hello abc how aec are afc you';
          //获取字符串中字符的索引，如果没有返回-1
          var result = str.search('you');//14
          // var result = str.search('ha')//-1
          //获取abc或者aec或者afc
          var result = str.search(/a[bef]c/g);//只会查找第一个，设置全局也没用
          console.log(result);
  ```

- 

### match()  

- 可以根据正则表达式，从一个字符串中符合条件的内容提取出来
- 默认情况下只会找到第一个符合要求的内容，找到就会停止
- 我们可以设置正则表达式为全局匹配模式，这样就可以匹配到所有内容
- 可以为一个正则表达式设置多个匹配模式，顺序无所谓

![image-20200531204949644](C:\Users\zengxiaolong\AppData\Roaming\Typora\typora-user-images\image-20200531204949644.png)

- match()会将匹配到的内容封装到一个数组中返回，即使只查到一个结果，放到数组里面更方便，没找到返回null

- 也可以把一大段字母里面的邮箱提取出来，或者数字，QQ号。。

- **简单来说就是可以在一堆没有规则的内容中把有规则的内容提取出来**

- ```javascript
  //match，把字符串中的字母提取出来
          var str = '1a2b3b4d5k6kA6BD3D2J2';
          var result = str.match(/[a-z]/gi);//在全局查找，忽略大小写
          console.log(typeof result);//object
          console.log( result);
  ```

- - 

### replace()

- 可以将字符串中指定内容替换为新的内容，需要两个参数
  - 被替换的内容
  - 新的内容
  
- 如果有相同的字符，默认值替换第一个

- 被替换的内容也可以写正则表达式，如果需要替换所有的需要指定一个全局模式g

- ```javascript
   		 //replace，替换字符串中指定的内容
          var str = '1a2b3b4d5k6kA6BD3D2J2';
          var result = str.replace('2','@-@');
          console.log(result);
  
    		//替换字符串中所有相同的字符
          var str = '1a2a3a4a5a6aA6aD3a2a2';
          var result = str.replace(/a/g,'^_^');
          console.log(result);
  
          //替换任意字母
          var str = '1a2a3a4a5a6aA6aD3a2a2';
          var result = str.replace(/[a-z]/gi,'^_^');
          console.log(result);
  
          //把字符串中的字母都删掉，可以把新字符写成空串
          var str = '1a2a3a4a5a6aA6aD3a2a2';
          var result = str.replace(/[a-z]/gi,'');
          console.log(result);
  ```

### .exec()

是正则表达式的方法，去字符串中匹配跟正则表达式符合的东西作用和match类似不同点在于它是正则的方法，而match是字符串的方法

同时exec()一次值会匹配一个结果，即使设置了全局匹配也是一样

执行一次匹配一次，再执行一次匹配第二个结果，一直匹配到没有结果就返回null

支持用()分组

![image-20200603085541824](C:\Users\zengxiaolong\AppData\Roaming\Typora\typora-user-images\image-20200603085541824.png)



### 正则表达式贪婪模式

- 通过量词去匹配内容，尽可能多的去匹配

  - 可以在量词后面写问号关闭贪婪模式

  - ```javascript
     //创建一个正则表达式
            // 正则表达式贪婪模式，通过量词去匹配内容，它会尽可能多的去匹配
            // 可以通过在量词后边写?，来关闭贪婪模式
            var reg = /ab+?/;
            reg = /ab*?/;
            reg = /ab??/;
     ```
  
  
  ```javascript
        // console.log(reg.test('abb'));
    
        var str = 'abbbcc';
    
        var result = str.match(reg);
    
        // console.log(result[0]);
    
        str = 'dasda13715433267fsgfdgafs13867545679dfasfsdfasf';
        var phoneReg = /1[3-9][0-9]{9}/g;
        // result = str.match(phoneReg);
    
        /*
            exec() 是正则表达式的方法，用来从字符串中匹配内容
                作用和match类似，不同点在于它是正则的方法，match是字符串的方法
                同时exec() 一次只会匹配一个结果，即使你设置全局匹配
         */
         phoneReg = /1[3-9]([0-9]{5})([0-9]{4})/g;
         result = phoneReg.exec(str);
         console.log(result[1]);//71543
  ```
  
    
  
            str = `<div>
    <h2>HTML DOM 树</h2>
    <img src="/i/ct_htmltree.gif" alt="HTML DOM Node Tree" />
    </div>`;
  
            // 编写正则表达式，提取出字符串中图片的路径
            reg = /src="(.+?)"/;
          result = reg.exec(str);
        
            console.log(result[0]);//src="/i/ct_htmltree.gif"
    ```
  
  - 
    ```

### 量词

- 通过量词可以设置一个内容出现的次数

- **{n}正好出n次**

- **{m,n}出现m到n次**

- **{m,}m次以上**

- **+ 表示至少出现一次，相当于{1,}**

- **\*表示0个或多个，相当于{0，}**

- **？表示0个或1个，相当于{0,1}**

- 

- 量词只对它前面的内容起作用

- 可以用()为正则表达式分组

- ![image-20200602102710573](C:\Users\zengxiaolong\AppData\Roaming\Typora\typora-user-images\image-20200602102710573.png)

- 这样的不会相互影响

- ![image-20200602102816516](C:\Users\zengxiaolong\AppData\Roaming\Typora\typora-user-images\image-20200602102816516.png)

- ![image-20200602103018742](C:\Users\zengxiaolong\AppData\Roaming\Typora\typora-user-images\image-20200602103018742.png)

- 

  - ```javascript
    var reg = /(ab){3}/;//这个表示ab出现3次
    var reg = /ab{1,3}/;//这个表示出现1次到3次
    var reg = /ab+c/;
    var reg = /ab*c/;
    var reg = /ab?c/;
    console.log(reg.test());
    ```

  - 

- 语法
  
  - var 变量=/查找的内容{次数}/；
  
- 检查字符串中开头的字符
  - **^** 表示开头,语法
    - `var reg = /^.../`
  - $表示结尾，语法
    - `var reg = /...$/`
  
- 如果同时使用^和$表示开头结尾都是一个字符，必须完全符合正则表达式 

### 正则语法练习

```javascript
        var reg = /^bbb$/;
        var result = reg.test('bbb');//true
        result =reg.test('b');//false
        reult = reg.test('bb');//false
        reult = reg.test('bbb');//false


        console.log(result);

        /*
            量词
                - 量词用来指定字符出现的次数
                {n} 字符正好出现n次
                {n,} 表示n次以上（大于等于n）
                {n,m} 表示n-m次

                + 表示1次以上，相当于{1,}
                * 表示0次或多次
                ? 表示0次或1次

                量词只对它的前一位字符起作用
         */

         //创建一个字符正好是2次的正则
        //  var reg = /^b{2}$/;
        //  //创建一个字符出现0-1次的正则
         reg =/^b?$/
        //  var result = reg.test('bb');//true
        result = reg.test('bb');//false
        result = reg.test('b');//true
        result = reg.test('');//true

        //创建一个字符出现0次以上的正则
        reg = /^b*$/
        result = reg.test('');//true，0次
        result = reg.test('bbbbbbbbbbb');//true，0次以上

        //创建一个字符出现1次以上的正则
        reg = /b+/;
        result = reg.test('b');
        result = reg.test('bbbbbbbbbbb');
        
        //中括号里面的是一个整体
        reg = /^a[bcdefg]+$/;
        result = reg.test('abcdefg'); //true
        result = reg.test('ab'); //true
        result = reg.test('ac'); //true
        result = reg.test('afg'); //true

        //检查一个字符串是否出现了1次以上的ab
        reg = /^(ab)+$/;
        result = reg.test('ababab'); //true
        result = reg.test('abb'); //false

        reg = /^a(b|e)c$/; // 等价于 /^a[be]c$/
        result = reg.test('abc');//true
        result = reg.test('aec');//true
        result = reg.test('xxxaec');//false
        result = reg.test('abec');//false

        console.log(result);
```

### 手机号的正则

```javascript
/*
            创建一个正则表达式，可以用来检查一个字符串是否是一个手机号

            1 3 843436188

            1开头  第二位3-9任意数字  任意数字9位结尾
            ^1      [3-9]          [0-9]{9}$

            ^1[3-9][0-9]{9}$
         */

        var phoneReg = /^1[3-9][0-9]{9}$/;

        console.log(phoneReg.test('13843436188'));
        console.log(phoneReg.test('1384343618'));
        console.log(phoneReg.test('1184343618'));
        console.log(phoneReg.test('1184343618889'));
        console.log(phoneReg.test('23843436188'));
```

### 邮件的正则

<img src="C:\Users\zengxiaolong\AppData\Roaming\Typora\typora-user-images\image-20200601231629687.png" alt="image-20200601231629687" style="zoom: 200%;" />

<img src="C:\Users\zengxiaolong\AppData\Roaming\Typora\typora-user-images\image-20200601231721951.png" alt="image-20200601231721951" style="zoom: 150%;" />

### 转义字符

检查字符串中是否有**.**

**.表示任意字符**

在主轴表达式中使用\作为转义字符

\.表示单纯的.

\\\表示一个斜杠

注意：使用构造函数时，由于它的参数是一个字符串，而\是字符串中转义字符

如果要使用\则需要使用\\\来代替

**\w**	

- 任意字母、数字，_

**\W**

- 除了字母、数字、下划线

**\d**

- 任意数字

**\D**

- 除了数字

**\s**

- 空格

**\S**

- 除了空格

**\b**

- 单词边界

**\B**

- 除了单词边界

  - ```javascript
      reg = /\bchild\b/;// \b就是单词边界
      reg = /\bchild\b/;
            result = reg.test('abcchildren'); // false
            result = reg.test('child'); // true
            result = reg.test('hello child'); // true
      
     //创建一个正则表达式，检查一个字符串中是否含有child这个单词
            reg = /\bchild\b/;
            // result = reg.test('abcchildren'); // false
            // result = reg.test('child'); // true
      
            // result = reg.test('hello child'); // true
            result = reg.test('  child  ');// true
      
            reg = /child/;
            result = reg.test('abcchildren');//true
            result = reg.test('child');//true
      
            console.log(result);
      
      		//用户输入用户名，去除多余空格
            //获取用户输入的信息
            var userName=prompt('请输入用户名');
            console.log('---' +userName +'---')
      
            //将用户输入的空格替换成空串
             userName= userName.replace(/^\s+|\s+$/g,'');
      
            console.log('---' +userName +'---')
    ```


获取用户输入信息，去除信息两遍没注意输入的空格

```javascript
str = str.replace(/^\s*/,'')//*表示开头，空格，0个或者多个，替换成空串，就把开头的空格删除了
```

去掉开头或者结尾的空格

![image-20200602142043240](C:\Users\zengxiaolong\AppData\Roaming\Typora\typora-user-images\image-20200602142043240.png)





### JSON

可能JS和JAVA数据交互

```javascript
var obj={name:'孙悟空',age:18,gender:'男'}；//把这个发给JAVA
```

现在希望这个对象让Java也认识

字符串是所有语言都认识的

**编辑器的配置文件就是JSON写的**

最佳方式将对象转化成字符串的形式

JSON（JavaScript Object Notation)

- JS的对象表示法

- JSON实际上就是一个字符串，它的语法格式和JS对象的语法基本上是一致的，通过JSON表示的对象可以在任意语言中使用

- 传到什么语言就可以变成什么语言的对象

- **注意两点**

  - 格式非常严格，属性名必须是双引号
  - 最后一个属性后边不能再有逗号

- JSON的语法和JS对象的语法基本一样，不同点在于

  - JSON中属性名必须加引号，而且必须是双引号
  - JSON中的字符串也必须使用双引号，其他特点跟JS是一样的

- JSON的两种类

  - JSON对象{}
  - JSON数组[]

- JSON工具类，用来操作JSON数据的

- 将一个JSON字符串转换为JS对象(数组)

  - parse将JSON转换成js对象(数组)

  ![image-20200602152513426](C:\Users\zengxiaolong\AppData\Roaming\Typora\typora-user-images\image-20200602152513426.png)

  - JSON.stringify()，把对象或者数组变成字符串

![image-20200602152731921](C:\Users\zengxiaolong\AppData\Roaming\Typora\typora-user-images\image-20200602152731921.png)

JSON支持的属性的类型

- 数字
- 字符串(使用双引号)，单引号不一定是字符串，但是双引号一定是字符串
- 布尔值
- 空值(null)
- 对象
- 数组
- ![image-20200602153429853](C:\Users\zengxiaolong\AppData\Roaming\Typora\typora-user-images\image-20200602153429853.png)

只支持最普通的对象，不支持函数

通过JSON来完成对象的深复制

![image-20200602154619497](C:\Users\zengxiaolong\AppData\Roaming\Typora\typora-user-images\image-20200602154619497.png)

一般情况下不用手动写JSON，除非写配置文件

#### JSON练习



```javascript
		//把一个对象转成字符串
        var json = '{"name":"孙悟空", "age":18, "gender":"男", "haha":null, "abc":{}, "bcd":[]}';
        //把一个数组转成字符串
        var jsonArr = '[2,3,5,3]';
        

        console.log(json);
        console.log(typeof json);
        console.log(jsonArr);
        console.log(typeof jsonArr);

  /*
            JSON 工具类，用来操作JSON数据的
                JSON.parse() 用来将一个JSON转换为JS对象（数组）
                JSON.stringify() 用来将一个JS对象（数组）转换为一个JSON字符串
         */
         //把JSON字符串转成对象
         var objJson= JSON.parse(json);
        //把JSON字符串转成数组
        var arrJson = JSON.parse(jsonArr);

         console.log(objJson);
         console.log(arrJson);

         //把对象转成字符串
        var obj= JSON.stringify(objJson);
         //把数组转成字符串
         var arr = JSON.stringify(arrJson);

        //  var result = strJson;
         result = arr;
         console.log(arr);

         //创建一个数组里面放对象
         var arr = [
            {name:"孙悟空", age:18, gender:"男"},
            {name:'猪八戒', age:28, gender:'男'},
            {name:'沙和尚', age:38, gender:'男'}
        ];

        //把数组转成字符串
        var arrStr = JSON.stringify(arr);

        // console.log(arrStr);

        var arr2 = [{name:'孙悟空'},{name:'猪八戒'}];
        //对arr2浅复制
        var arr3 = arr2.slice();
        // console.log(arr3);
        //把arr3第一个属性值改为哈哈
        arr3[0].name = '哈哈';
        console.log(arr2[0].name);

          // 可以通过JSON来完成对象的深复制
          var arr3 = JSON.parse(JSON.stringify(arr2));

        arr3[0].name = '哈哈';
        console.log(arr2[0].name);
```



# 0601 复习 闭包，对象复制，日期对象

- 冒泡排序(bubble)
  - 原理：反复的比较相邻的两个元素的大小，然后根据需要进行交换位置
  - 性能比较差，不使用元素较多的情况
- 快速排序
  - 原理
  - 性能

## 闭包

- 就是可以访问到外部函数作用域变量的内部函数

  - 1.必须要有函数的嵌套

  - 2.内层函数必须要引用外层函数中的变量

  - 3.将内层函数作为返回值返回

  - ```javascript
    function outer(){
    	var a=10;
    	function inner(){
    		console.log(a)
        }
        return inner;
    }
    var fn = outer();
    ```

  - 特点

    - 闭包在外部函数调用时创建
    - 外部函数每调用一次就产生一个闭包
    - 当内部函数都被垃圾回收闭包就会销毁
    - 应用闭包主要是为了不希望外部访问的变量

## 对象的复制（拷贝）

- 浅复制
  - 浅复制表示只复制对象的自身，不赋值对象的属性
  - 性能比较好
  - 数组的浅复制
    - slice()
  - 对象的浅复制
    - assign()
- 深复制
  - 深复制不仅会复制对象自身，也会复制对象的属性，甚至是属性的属性
  - 性能差

## 日期对象(Date)

- 在JS中，所有和时间相关信息都由Date对象来表示

- 创建日期对象

  - 创建一个档期日期对象

  - ```javascript
    var d = new Date();
    ```

  - 创建一个指定的日期对象

  - ```javascript
    var d = new Date('月份/日/年份 时：分：秒')//这种格式在不同浏览器兼容性不一样，这种格式基本上是完美的，真正开发的时候还是要多测试目标浏览器是否支持
    ```

  - 对象方法

  - getFullYear()——获取当前日期对象的年份

  - getMonth()——获取月份的索引，0是1月，1是2月。。。

  - getDay()——周几

  - getTime()

    - 获取当前日期对象的时间戳
    - 时间戳指从1970年1月1日0时0分0秒到现在时刻所经历的毫秒数
    - 在计算机底层所有的实际都是通过时间戳表示的
    - 时间戳还是挺常用的，1毫秒生成一个，就意味着重复的概率低，经常用来生成一些随机的ID
      - 比如网购的订单号是唯一的，不能重复，如果做一个自增的订单号，能确保订单号不重复，但是不安全，主要是会泄漏商业机密
      - 订单计算的时候不可能光用时间戳，比如双十一短时间内会生成很多订单，就有可能重复

  - Date.now()——类方法

    - 涉及到原型，成为实例方法

    - 涉及到类（函数对象）中的方法称为类方法（静态方法），类方法直接通过类（函数对象）调用

    - 用来直接获取到当前时间的时间戳

    - ```javascript
        function MyClass() {
        
              }
        
              /*
                  添加到原型（prototype）中方法被称为实例方法，
                      需要通过实例对象来调用
                  var mc = new MyClass();
                  mc.t1();
        
               */
              MyClass.prototype.t1 = function () {
        
              };
        
              /*
                  直接添加到类（函数对象）中的方法称为类方法（静态方法），
                      类方法直接通过类（函数对象）调用
                      MyClass.t2()
               */
              MyClass.t2 = function () {
        
              };
      ```

# 0601 正课==>0531预习

## Math

和其他的类不同，Math并不是一个构造函数，也就是无法通过new来创建Math的实例

Math表示的是数学，在Math对象存储了一组数学运算的常量和方法

这些常量和方法可以直接通过Math来访问

**这种类称为工具类，不用创建实例，属性和方法直接存到对象本身里面**

### 包装类

在JS中，给我们提供了三个包装类

- String()

- Number()

- Boolean()

  - 这三个包装类可以用于创建出一个基本数据类型的对象

  - 对象类型的数字具有原始数字的所有功能，并且它可以直接存储属性和方法

  - 但是在开发中，绝对不能这样使用

  - ```javascript
    var c = 10;
    var d = new Number(10)
    ```

  - 比较对象形式基本数据时，比较的是对象的内存地址

  - 可以通过new Number() 、new String()、  new Boolean()来创建一个基本数据的对象，但是千万不要这么用

  - 当我们调用一个基本数据类型的属性或方法时，由于值中并不具备属性和方法，所有JS的引擎会临时通过包装类来将其转换为对象，然后通过该对象调用属性或方法

  - 对null和undefined调用toString会报错，因为没有包装类
  
- 因为包装类的存在我们可以通过数值调用Number的实例方法，通过字符串调用String类型的实例方法，通过布尔值调用Boolean类型的实例方法
  
    - 比如这里是四个对象，临时通过包装类把基本数据转换的对象调用，调用完就没了，这是给浏览器用的
    - ![image-20200601111902097](C:\Users\zengxiaolong\AppData\Roaming\Typora\typora-user-images\image-20200601111902097.png)
    
  - 这就意味着，可以直接通过值来调用其包装类的方法，

```javascript
       	 //基本数据类型
        var a = 10;
        //创建一个对象
        var b = {};

        //给基本数据类型添加属性
        a.name = '周杰伦';
        a.age = 32;
        console.log(a.name,a.age);//undefined undefined
        console.log(a.toString);

        //创建一个实例对象
        var d = new Number(10);
        console.log(d);//Number {10}
        //给实例对象添加属性
        d.name = '彭于晏';
        d.age = 38;
        console.log(d.name,d.age);//彭于晏 38
        console.log(d+33);//43

        var f = new Number(33);
        var g = new Number(33);
        //比较实例对象，比较的是内存地址
        console.log(f===g);//false


		
```

# 0602 DOM

## DOM

Document Object Model文档对象模型，通过DOM可以使用JS对网页修改

**文档**就是整个网页

**对象**，表示将网页中的每一个部分都转换成一个对象

标签，属性，文字，注释。。。网页里面所有的东西在DOM里转换成对象

转换成对象的好处就是，操作网页纯粹面向对象

**模型**(DOM树)是用来表示对象与对象之间的关系

- 关系明确了，就可以通过一个对象找到其他对象

![image-20200602161916100](C:\Users\zengxiaolong\AppData\Roaming\Typora\typora-user-images\image-20200602161916100.png)

![image-20200603091522350](C:\Users\zengxiaolong\AppData\Roaming\Typora\typora-user-images\image-20200603091522350.png)

模型非常清楚的体现了节点与节点之间的关系

## 节点

是构成网页最基本的东西，网页的每个部分都可以称为节点

都是节点，但是类型不同

- 文档节点，代表整个网页
- 元素节点
  - 所有的标签都是元素节点
- 文本节点
  - 标签中的文字就属于文本节点，很少主动获取文本节点，比如button中间的字
- 属性节点
  - 标签中的属性
  - 比如
    - ![image-20200603091907863](C:\Users\zengxiaolong\AppData\Roaming\Typora\typora-user-images\image-20200603091907863.png)
    - 

![image-20200602162518307](C:\Users\zengxiaolong\AppData\Roaming\Typora\typora-user-images\image-20200602162518307.png)

```html
button按钮

```

在js中浏览器已经给我们提供了document对象，代表整个网页，可以直接使用

`getElementById`通过ID找对象，是document的方法，通过这个方法可以根据元素的id属性获取一个元素

修改btn的innerHTML属性，修改btn内部的HTML代码

## 事件(event)

事件是指用户和浏览器的交互瞬间

 在网页中，点击，缩放，点击键盘，移动鼠标...一切的操作都是事件

可以在事件来对事件做一些处理，对其进项响应

设置事件响应的方式一

- 可以通过在元素的事件属性中设置js代码的形式来响应事件，这种形式虽然跟HTML耦合，但也可以用，不建议大量使用

- ![image-20200602165136878](C:\Users\zengxiaolong\AppData\Roaming\Typora\typora-user-images\image-20200602165136878.png)

- 现在的事件是属性值呈现的，点击了才会触发

- **文档里面的事件参考就是DOM**网址：

  https://developer.mozilla.org/zh-CN/docs/Web/Events

  获取要设置事件的对象

  为元素对应的事件属性设置响应函数形式来处理事件，这也称为回调函数，浏览器调用的

  ![image-20200602165946971](C:\Users\zengxiaolong\AppData\Roaming\Typora\typora-user-images\image-20200602165946971.png)

# 0603 DOM

## DOM查询

网页的加载是从上到下的顺序一行一行加载，如果把script写在body上面，它会优先于body加载

load事件表示自愿加载，当自愿加载完毕后事件会触发

编写DOM相关的代码，有两个编写位置

​	1.编写在body标签最后（优先选择，这样能让网页加载稍微快些，不过区别不大，用哪种都行）

​	2.编写在windo.onload函数内部，可以保证正常操作dom对象

Collection——类数组，所有符合条件的元素都会一起返回

input是自结束标签，没有内部的HTML标签

读取一个元素的属性，想读什么属性就**.什么**

class读不出来

- 元素.属性名
- name属性  元素.name
- value属性  元素.value
- id属性  元素.id
- class属性   元素.className

修改属性

- 元素.属性名=属性值

表单项才有name属性，这个主要对于表单的

`getElementsByClassName()`用于根据元素class属性值来获取一组元素节点对象

`document.querySelector()`

- 可以根据选择器的字符串去页面中查询元素
- 会返回满足要求的第一个元素

`document.querySelectoAll()`

- 根据选择器来获取一组元素节点对象



属性节点成不了父节点也成不了子节点

ie8以下的浏览器不会将空白节点当成子节点



```javascript
getElementsByName()//根据元素的name属性来获取一组元素节点对象
innerHTML//可以用来查看和设置元素内部的HTML代码

getElementsByTagName()//用于根据标签名来获取一组元素节点对象
document.all//返回的是一个数组，即将被放弃的属性，可以用getElementsByClassName代替

`document.documentElement`获取页面的根元素，也就是html

`document.body`获取body元素

`.childNodes`是元素的属性，可以用来获取当前元素的所有子节点
`children`是元素的属性，用来获取当前元素的子元素

`firstChild`获取元素的第一个子节点，也包括空白的文本节点，如果前面有空白，获取的也是空白

`lastChild`最后一个子节点

`firstElementChild`获取当前元素的第一个子元素

`lastElementChild`获取当前元素的最后一个子元素

`parentNode`用来获取一个元素的父节点，主要是元素

`innerText`获取标签内部的文本内容，自动去除html标签，不仅可以读取，还可以改

`previousSibling`获取当前元素的前一个兄弟节点 

`previousElementSibling`获取当前元素的前一个兄弟元素

方法很多，弥补了css的短板，css找不到父元素

`nextSibling`获取当前元素的下一个兄弟节点

`nextElementSibling`获取当前元素的下一个兄弟元素
`value`就是文本框里写的内容

`nodeValue`获取文本节点中的文字，这种方式比较麻烦，比较古老，可以体现出程序员的经验

```



Element元素对象的属性和方法

- 根据标签名获取指定元素的后代元素

- ![image-20200605095706725](C:\Users\zengxiaolong\AppData\Roaming\Typora\typora-user-images\image-20200605095706725.png)

- 获取当前元素的第一个子节点

  - ```javascript
    ele.firstChild
    ```

- 获取当前元素的最后一个节点

- ```javascript
  ele.lastChild
  ```

- 获取当前元素的第一个/最后一个子元素

  - ```javascript
    ele.fistElementChild
    ele.lastElementChild
    ```

- 

- ![image-20200605101136123](C:\Users\zengxiaolong\AppData\Roaming\Typora\typora-user-images\image-20200605101136123.png)

![image-20200603163155460](C:\Users\zengxiaolong\AppData\Roaming\Typora\typora-user-images\image-20200603163155460.png)

### DOM查询练习

```javascript
	//定义一个函数，用来解决绑定代码重复的问题
			/*
				参数：
					id 要绑定单击事件的按钮的id
					callback 事件的响应函数
			 */
			function myClick(id, callback){
				var btn = document.getElementById(id);
				btn.onclick = callback;
			}

			window.onload = function () {

				//为id为btn01的按钮绑定一个单击响应函数
				//获取按钮对象
				var btn01 = document.getElementById('btn01');
				// 为其绑定单击响应函数
				btn01.onclick = function () {
					// getElementById()用来根据id属性来获取一个元素
					// 查找#bj节点
					var bj = document.getElementById('bj');
					// innerHTML 可以用来查看和设置元素内部的html代码
					alert(bj.innerHTML);
				};

				// 为btn02绑定一个单击响应函数
				var btn02 = document.getElementById('btn02');
				btn02.onclick = function () {
					// 查找所有li节点
					// getElementsByTagName() 用于根据标签名来获取一组元素节点对象
					// 返回是一个类数组对象，所有符合条件的元素都会一起返回
					var lis = document.getElementsByTagName('li');
					// 遍历数组
					for(var i=0; i<lis.length; i++){
						alert(lis[i].innerHTML);
					}
				};

				//为id为btn03的按钮绑定一个单击响应函数
				var btn03 = document.getElementById('btn03');
				btn03.onclick = function () {
					// 查找name=gender的所有节点
					// getElementsByName() 根据元素的name属性来获取一组元素节点对象
					var inps = document.getElementsByName('gender');
					// 遍历inps
					for(var i=0; i<inps.length; i++){
						// 获取自结束标签的innerHTML，会返回空串
						// alert(inps[i].innerHTML);

						/*
							读取一个元素的属性：
								元素.属性名
								例子：
									name属性 元素.name
									value属性 元素.value
									id属性   元素.id
								特殊：
									class属性  元素.className

							修改属性：
								元素.属性名 = 属性值
						 */
						// alert(inps[i].className);
						alert(inps[i].value);
					}

				};


				//为btn04绑定一个单级响应函数
				var btn04 = document.getElementById('btn04');
				btn04.onclick = function () {

					// 获取id为city的节点
					var city = document.getElementById('city');
					// 查找#city下所有li节点
					var li = city.getElementsByTagName('li');
					// li = document.querySelectorAll('#city li');
					alert(li.length);
				};

				// 为btn05绑定一个单击响应函数
				var btn05 = document.getElementById('btn05');
				btn05.onclick = function () {
					// 获取id为city的元素
					var city = document.getElementById('city');
					// 返回#city的所有子节点
					// childNodes 是元素的属性，可以用来获取当前元素的所有子节点
					// childNodes会返回当前元素的所有子节点（包括元素和文本）
					// IE8以下的浏览器不会将空白的文本节点当成子节点
					var cns = city.childNodes;

					//遍历cns
					// for(var i=0; i<cns.length; i++){
					// 	alert(cns[i]);
					// }
					// alert(cns.length);

					/*
						children 是元素的属性，用来获取当前元素的子元素
					 */
					var cr = city.children;
					alert(cr.length);
				};

				// 为id为btn06的按钮绑定一个单击响应函数
				myClick('btn06', function () {
					// 获取id为phone的元素
					var phone = document.getElementById('phone');
					// 返回#phone的第一个子节点
					// firstChild用于获取元素的第一个子节点（包括空白的文本节点）
					// lastChild 用于获取当前元素的最后一个子节点
					// firstElementChild 用来获取当前元素的第一个子元素
					// lastElementChild 用来获取当前元素的最后一个子元素
					var fc = phone.firstChild;
					var fec = phone.firstElementChild;

					alert(fec);
				});


				myClick('btn07',function () {
					//获取id为北京元素
					var bj = document.getElementById('bj');
					// 返回#bj的父节点
					// parentNode 用来获取一个元素的父节点
					var pn = bj.parentNode;
					// innerText用来获取标签内部的文本内容，会自动去除html标签
					alert(pn.innerText);
				});

				myClick('btn08',function () {
					// 获取id为android的元素
					var and = document.getElementById('android');
					// 返回#android的前一个兄弟节点
					// previousSibling 用来获取当前元素的前一个兄弟节点
					// previousElementSibling 用来获取当前元素的前一个兄弟元素
					// nextSibling 获取当前元素的下一个兄弟节点
					// nextElementSibling 获取当前元素的下一个兄弟元素

					var prev = and.previousSibling;
					prev = and.previousElementSibling;
					// and.nextElementSibling
					alert(prev);
				});

				// 返回#username的value属性值
				myClick('btn09',function () {
					// 获取id为username的元素
					var um = document.getElementById('username');
					alert(um.value);
				});

				// 设置#username的value属性值
				myClick('btn10',function () {
					var um = document.getElementById('username');
					um.value = "老刘可真帅啊！";
				});

				// 返回#bj的文本值
				myClick('btn11',function () {
					// 获取id为bj的元素
					var bj = document.getElementById('bj');
					// alert(bj.innerHTML);
					// alert(bj.innerText);
					// bj.innerHTML = '深圳';

					// 获取bj的第一个子节点
					// var fc = bj.firstChild;
					// 文本节点的nodeValue，表示的是文本节点中的文字
					// alert(fc.nodeValue);
					alert(bj.firstChild.nodeValue);

				});

			};

		</script>
	</head>
	<body>
		<div id="total">
			<div class="inner">
				<p>
					你喜欢哪个城市?
				</p>

				<ul id="city">
					<li id="bj">北京</li>
					<li>上海</li>
					<li>东京</li>
					<li>首尔</li>
				</ul>

				<br>
				<br>

				<p>
					你喜欢哪款单机游戏?
				</p>

				<ul id="game">
					<li id="rl">红警</li>
					<li>实况</li>
					<li>极品飞车</li>
					<li>魔兽</li>
				</ul>

				<br />
				<br />

				<p>
					你手机的操作系统是?
				</p>

				<ul id="phone">
					<li>IOS</li>
					<li id="android">Android</li><li>Windows Phone</li></ul>
			</div>

			<div class="inner">
				gender:
				<input class="haha" type="radio" name="gender" value="male" >
				Male
				<input class="haha" type="radio" name="gender" value="female">
				Female
				<br>
				<br>
				name:
				<input type="text" name="name" id="username" value="abcde">
			</div>
		</div>
		<div id="btnList">
			<div><button id="btn01">查找#bj节点</button></div>
			<div><button id="btn02">查找所有li节点</button></div>
			<div><button id="btn03">查找name=gender的所有节点</button></div>
			<div><button id="btn04">查找#city下所有li节点</button></div>
			<div><button id="btn05">返回#city的所有子节点</button></div>
			<div><button id="btn06">返回#phone的第一个子节点</button></div>
			<div><button id="btn07">返回#bj的父节点</button></div>
			<div><button id="btn08">返回#android的前一个兄弟节点</button></div>
			<div><button id="btn09">返回#username的value属性值</button></div>
			<div><button id="btn10">设置#username的value属性值</button></div>
			<div><button id="btn11">返回#bj的文本值</button></div>
		</div>
```



#### 作业

做一个京东或者小米的轮播的布局

```html
 <style>
        .container{
            width: 1200px;
            height: 460px;
            position: absolute;
            top: 100px;
            left: 0;
            right: 0;
            bottom: 0;
            margin: 0 auto;
        }
        img{
            position: absolute;
            top: 0px;
            left: 0px;            
            width: 1200px;
            height: 460px;
        }
        /* 设置左箭头 */
        .container .prev{
            width: 41px;
            height: 69px;
            background-image: url(./img/icon-slides.png) ;
            position: absolute;
            top:50%;
            margin-top: -35px;
		    background-position-x: -84px;
        }
        /* 设置移入左箭头 */
        .container .prev:hover{
            background-position-x:0px ;
            /* 移入变小手 */
            cursor:pointer;

        }
        /* 设置右箭头 */
        .container .next{
            background-image: url(./img/icon-slides.png);
            width: 41px;
            height: 69px;
            position: absolute;
            top:50%;
            right: 0;
            margin-top: -33px;
            background-position-x:-123px;
        }
        /* 设置右箭头移入 */
        .container .next:hover{
            background-position-x: -41px;
             /* 移入变小手 */
            cursor:pointer;
        }
    </style>
</head>
<body>
    <div class="container">
        <!--轮播图-->
        <img src="./img/mi1.jpg" alt="">
        <!-- 左右按钮 -->
        <div class="prev">  </div>
        <div class="next">  </div>

    </div>
    <script>
        window.onload = function(){
            //获取左右按钮
            var prev = document.querySelector('.prev');
            var next = document.querySelector('.next');
            //测试是否获取到按钮
            // prev.onclick = function(){
            //     alert('我是左按钮');
            // }
            //获取图片标签
            var imgNode = document.querySelector('img');
            //创建一个数组来存储图片路径
            var imgArr = ["./img/mi1.jpg","./img/mi2.jpg","./img/mi3.jpg","./img/mi4.jpg","./img/mi5.jpg"];
            //测试修改src属性修改图片
            // imgNode.src = "./img/mi2.jpg";

            //定义一个变量为当前索引
            var current = 0;

            //给两个按钮绑定单击事件
            prev.onclick = function(){
                //上一张图片自减
                current--;

                //判断索引是否小于0
                if(current < 0){
                    current = imgArr.length-1;
                }
                //修改src属性切换图片
                imgNode.src = imgArr[current];
            }
            next.onclick = function(){
                //下一张图片自增
                current++;
                //判断索引大于索引最大值
                if(current > imgArr.length-1){
                    current = 0 ;
                }
                //修改src属性切换图片
                imgNode.src = imgArr[current];
            }
        }
    </script>
</body>
```



全选全部选

![image-20200603164713050](C:\Users\zengxiaolong\AppData\Roaming\Typora\typora-user-images\image-20200603164713050.png)

```javascript
<body>
  
        你爱好的运动是？<input type="checkbox" id="checkedAllBox" />全选/全不选

        <br />
        
        <input type="checkbox" name="items" value="足球" />足球
        <input type="checkbox" name="items" value="篮球" />篮球
        <input type="checkbox" name="items" value="羽毛球" />羽毛球
        <input type="checkbox" name="items" value="乒乓球" />乒乓球
        <br />
        <button>全选</button>
        <button>全不选</button>
        <button>反选</button>
  
    <script>
        window.onload = function () {
            //获取input
            var inputNode = document.querySelectorAll('input');
            //获取button
            var btn = document.querySelectorAll('button');
            //给第一个按钮绑定单击事件
            btn[0].onclick = function () {
                //遍历复选框
                for (var i = 0; i < inputNode.length; i++) {
                    inputNode[i].checked = true;
                }
            }
            // 全不选
            // 给第二个button绑定单击事件的回调函数
            btn[1].onclick = function () {
                for (var i = 0; i < inputNode.length; i++) {
                    inputNode[i].checked = false;
                }
            }
            // 给第三个button绑定单击事件的回调函数
            btn[2].onclick = function () {
                for (var i = 0; i < inputNode.length; i++) {
                    inputNode[i].checked = !inputNode[i].checked;
                }
            }
        }


    </script>
</body>
//先把需求用自己的语言描述出来
/*
1.点击按钮让四个多选框都选择
2.做任何事完成任何需求，第一件事先找对象，获取四个多选框对象
3.修改对象无非两个方法，要么是调方法，要么改属性，不知道怎么做就看文档API
选框是类数组，可以通过解构把类数组转成数组，再对数组进行操作
*/
```

getElementsByName()返回的是一个实时更新的数组

- 如果在网页中添加新的符合条件的元素，它会自动被添加到数组中

所有的getElement方法都是这个特点，返回的数组是实时更新的

querySelectorAll返回的是一个静态的，不会实时更新


**HTMLCollection是动态的 ，NodeList是静态的**

checked用来匹配单选，多选，下拉框

这里是获取所有name属性为items的值

![image-20200605153037764](C:\Users\zengxiaolong\AppData\Roaming\Typora\typora-user-images\image-20200605153037764.png)

获取所有选中状态的选框



![image-20200605153128638](C:\Users\zengxiaolong\AppData\Roaming\Typora\typora-user-images\image-20200605153128638.png)

这表示总数量和选中的数量相等

![image-20200605153357822](C:\Users\zengxiaolong\AppData\Roaming\Typora\typora-user-images\image-20200605153357822.png)



# 0605 DOM的增删改

```javascript
document.createElement()//创建元素节点
document.createTextNode()//创建文本节点
父节点.appendChild()//添加子节点event
gz.appenChild(txt)//把TXT设置为广州的子节点
父节点.insertBefore(前面节点,后面节点)//将一个节点插入到指定节点前面
父节点.replaceChild(新节点，被替换的旧节点)//使用一个新的节点替换旧的节点
//做什么操作都要先找到父亲
父节点.removeChild()//删除子节点，如果有父节点就用这个
子节点.parentNode.removeChlid(子节点)//自己删自己的节点，如果没有父节点就用这个
也可以通过innerHTML来完成DOM的增删改

```

## this到底是谁

- 根据函数的调用方式不同，this也不同
  - 以函数形式调用时，this是window
  - 以方法形式调用，铜焊丝是调用方法的对象
  - 以构造函数调用时，this是新建的对象
  - 使用call和apply调用时，this是call了和apply的第一个桉树
  - 箭头函数的this，由外层作用域决定
  - 事件响应函数的this，是绑定事件的对象

超链接的默认行为 

![image-20200606092740578](C:\Users\zengxiaolong\AppData\Roaming\Typora\typora-user-images\image-20200606092740578.png)

在表格中，如果不指定tbody，tfoot，thead，浏览器会自动添加，习惯上是table里面写tbody

所以tr的父元素是tbody，而不是table





# 0606

```javascript
修改元素样式
元素.style.样式名
```



```javascript
对象.style.样式名//通过style属性读取的样式也是内联样式
getComputedStyle(要获取样式的元素,要获取的伪元素)//读取元素当前的样式，第二个参数不写或者传nall是一样的，返回值是对象中存存储了当前元素所有生效的样式，无论是样式表里的还是行内样式，谁生效读谁，不兼容ie8
currentStyle//当前样式,只有ie支持，从ie6就开始支持了
```

通过getComputedStyle()读取的样式都是只读的，无法修改

宽度如果不设置，默认值是auto

getComputedStyle()方法只支持ie9以上的浏览器

## 样式相关的属性

```javascript
clientWidth	//可见区域宽度，没有单位（内容区+内边距）

clientHeight //可见区域高度（内容区+内边距）

//以上两个属性返回值就是数字没有单位，可以直接用来计算
```



```javascript
offsetWidth	获取可见框宽度（内容区+内边距+边框）
offsetHeiht 获取可见框高度（内容区+内边距+边框）

offsetParent//获取元素的定位父元素，获取离当前元素最近的开启了定位的祖先元素，如果所有的祖先元素都没有开启定位返回body

offsetLeft//获取当前元素距离定位元素的左侧偏移量
offsetTop//获取当前元素距离定位元素的上侧偏移量
```

![image-20200606151712377](C:\Users\zengxiaolong\AppData\Roaming\Typora\typora-user-images\image-20200606151712377.png)

```javascript
scrollHeight//用来获取元素滚动区域的高度
scrollWidth//用来获取滚动区域的宽度

scrollTop//垂直滚动条的位移
scrollLeft//水平滚动条的位移
当元素的scrollHeight-scrollTop===clientHeight，返回的是true的时候，说明滚动条滚动到底了，如果是小数会导致计算的不准确
scroll事件会在元素的滚动条滚动的时候触发
disabled//禁用
```



# 0608 小米轮播图过渡 事件对象

点击翻页按钮，第一步要做的是隐藏当前显示的图片

创建一个变量是当前显示的图片

过渡效果能用css就不用js，js做出来的性能不好

style是个类数组

## 事件对象

一个问题不知道就问知道的人，同理，想获取鼠标坐标，谁知道鼠标坐标在哪

就是浏览器，那就要找浏览器这个对象

```javascript
.onmousemove//移动事件
(event.clientX,event.clientY)//形参里面传入了X坐标和Y坐标
```

当事件响应函数会在事件触发时由浏览器自动调用，函数并不是我们调的，只是把函数赋值给属性，是浏览器自动调用的

浏览器会在响应函数中传递一个对象作为参数(事件对象)

- 这个对象就是事件对象，在事件对象中，存储了所有的当前事件的相关信息
- 事件对象中存储了当前事件的所有细节
  - 比如键盘的按键被按下
  - 鼠标的按键被按下
  - 鼠标的指针坐标。。。

注意：在ie8及以下浏览器中，事件对象没有座位实参传递，无法通过以下方式来获取事件对象，可以写`window.event`这个属性已经作废了，但是如果要兼容ie8还得这么写

可以通过以下方式来处理event的兼容问题

```javascript
event=event || window.event //这种是为了兼容ie8，现在已经不用这种写法了
```

clientX和clientY获取的都是鼠标指针的坐标，是相对视口

```javascript
pageX和pageY//用来获取鼠标相当于整个页面的坐标，这两个没有正式成为标准
```

```javascript
scrollTop//要用这个距离从documentElement里面调documentElement.scrollTop
```



## 事件的冒泡

当一个后代元素的事件被触发，影响到祖先元素的相同事件被触发，这就是事件的冒泡

冒泡只和网页的结构有关，和表现无关

冒泡的存在实际上简化了开发，所以大部分情况下冒泡都是有利的

但是有些情况我们不希望冒泡存在，可以通过事件对象取消冒泡

```javascript
event.cancelBubble=true//取消事件冒泡,只能取消一个事件的冒泡
event.stopPropagetion()//可以取消多个事件的冒泡
event.preventDefault()//取消默认行为

```

## 事件委派

当需要为多个元素绑定相同事件时，往往面临如下问题：

- 需要绑定多次事件
- 新添加的元素必须重新绑定事件

现在值需要绑定一次事件就可以让所有的元素都拥有该事件，包含现在的元素和未来的元素

可以统一将事件绑定到共同的祖先元素上，这样只需要绑定一次事件就可以使所有的子元素都拥有该事件

事件的target属性，表示是触发事件的对象，其实就是事件的源头，代表当前的对象

```javascript
ev.currentTarget()//就跟this一样的，事件给谁绑定的，它就是谁
```



元素的nodeName属性可以返回标签名

把标签转换成小写判断是否全等于标签名



![image-20200608163721059](C:\Users\zengxiaolong\AppData\Roaming\Typora\typora-user-images\image-20200608163721059.png)

可以在标签中，添加一个data-xxx这种自定义属性，可以在这些属性中，存储一些我们需要的数据

在元素对象中，有一个dataset属性，是一个数据集，在它里边存储了所有通过data-xxx存储的属性

`data`就是用来存数据的，通过对象的dataset把数据取出来

### 小米轮播图过渡效果没用事件委派版本

```javascript
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            list-style: none;
        }

        .container {
            width: 1200px;
            height: 460px;
            position: relative;
            top: 100px;
            left: 0;
            right: 0;
            bottom: 0;
            margin: 0 auto;
        }

        .imgList {
            width: 1200px;
            /* position: relative; */
            left: 0;
            right: 0;
            margin: 100px auto;
        }

        .imgList img.active {
            opacity: 1;
        }

        .imgList img {
            width: 1200px;
            height: 460px;
            float: left;
            position: absolute;
            top: 0;
            transition: all 1s linear;
            opacity: 0;

        }

        /* 设置左箭头 */
        .prev {
            width: 41px;
            height: 69px;
            background-image: url(./img/icon-slides.png);
            position: absolute;
            top: 195px;
            left: 0;
            /* 相对自身偏移 */
            /* transform: translateX(58px); */
            /* 设置自身显示的位置 */
            background-position-x: -83px;
        }

        /* 设置移入左箭头样式 */
        .imgList .prev:hover {
            background-position-x: 0px;
            cursor: pointer;
        }

        /* 设置右箭头 */
        .next {
            width: 41px;
            height: 69px;
            background-image: url(./img/icon-slides.png);
            position: absolute;
            top: 195px;
            right: 0;
            /* 相对自身偏移 */
            /* transform: translateX(-65px); */
            /* 设置自身显示的位置 */
            background-position-x: -123px;
        }

        /* 设置移入右箭头样式 */
        .imgList .next:hover {
            background-position-x: -41px;
            cursor: pointer;
        }

        /* 设置小圆点容器 */
        .iconList {
            position: absolute;
            width: 100px;
            height: 20px;
            right: 20px;
            bottom: 10px;

        }

        .iconList .icon {
            width: 12px;
            height: 12px;
            background-color: #fff;
            float: left;
            border-radius: 50%;
            margin-left: 8px;
        }

        .iconList .icon:hover {
            background-color: #fff;
            cursor: pointer;
        }
        .iconList .icon.active{
            background-color: #000;
            color:#fff;
        }
    </style>
</head>

<body>
    <!-- 创建最外层容器 -->
    <div class="container">
        <!-- 创建图片容器 -->
        <div class="imgList">
            <!-- 五张图片 -->
            <img src="./img/mi1.jpg" class="active" alt="">
            <img src="./img/mi2.jpg" alt="">
            <img src="./img/mi3.jpg" alt="">
            <img src="./img/mi4.jpg" alt="">
            <img src="./img/mi5.jpg" alt="">

            <!-- 左右箭头 -->
            <div class="prev"></div>
            <div class="next"></div>
        </div>
        <!-- 创建小圆点容器 -->
        <ul class="iconList">
            <li class="icon" class="active"></li>
            <li class="icon"></li>
            <li class="icon"></li>
            <li class="icon"></li>
            <li class="icon"></li>
        </ul>
    </div>
    <script>
        //获取img元素节点
        const imgNodes = document.querySelectorAll('img');

        //获取左右箭头
        const prev = document.querySelector('.prev');
        const next = document.querySelector('.next');

        //iconList
        const iconNodes = document.querySelectorAll('.icon')

        //获取container
        // const container = document.querySelector('.container')

        //创建一个变量表示当前索引
        let current = 0;

        //给左箭头绑定单击事件
        prev.onclick = function () {
            current--
            if (current < 0) {
                current = imgNodes.length - 1;

            }
            setPlay();
        }

        //给右箭头绑定单击事件
        next.onclick = function () {
            current++
            if (current > imgNodes.length - 1) {
                current = 0;
            }
            setPlay();
        }
        //过渡函数
        function setPlay() {
            imgNodes.forEach((item, index) => {
                item.classList.remove('active')
                iconNodes[index].classList.remove('active')
            })
            imgNodes[current].classList.add('active');
            iconNodes[current].classList.add('active');
        }
        //小圆点的单击事件
        //遍历每一个小圆点
        iconNodes.forEach((item, index) => {
            //绑定点击事件
            item.onclick = function () {
                current = index;
                setPlay();
            }
        })
    </script>
</body>

</html>
```

### 小米轮播图过渡效果思路

```javascript
/*
        思路
        1.获取所有图片
        2.获取左右按钮
        3.创建当前图片索引的变量
        4.前后翻页的单击事件
        5.获取所有圆点
        6.给所有小圆点绑定单击事件，先遍历
            立即执行函数，给每个小圆点绑定单击事件
        7.创建一个公共函数，用来切换图片，形参语义表示当前小圆点索引
            判断如果当前索引小于0就让伪数组长度-1赋值给当前索引
            否则就等于0
        8.处理导航点的问题
        9.获取当前选中的导航点，前提是在html里面设置一个当前导航点的类名
        10.取消选中状态，可以让当前导航点的类名设置为空串
        11.给当前小圆点设置active这个类
        12.隐藏当前图片
        13.当前图片的所有透明度设为0
        14.保险起见，把层级设置0，设置当前图片索引的层级为0
        15.重置图片当前索引，把小圆点当前索引赋值给图片当前索引
        16.让图片显示，设置当前图片透明度和层级设为1

        */
```

![image-20200609091956332](C:\Users\zengxiaolong\AppData\Roaming\Typora\typora-user-images\image-20200609091956332.png)



![image-20200609102329029](C:\Users\zengxiaolong\AppData\Roaming\Typora\typora-user-images\image-20200609102329029.png)



# 0609 拖拽 鼠标事件 鼠标滚轮事件



addEventListener()
也可以通过 addEventlistener()来为元素绑定事件
addEventListener(type, listener[ useCapture))
**参数:**

- type要监听的事件的字符串,注意这里不需要与o
- Listener回调函数,当事件发生后调用的函数
- recapture 布尔值,是否在捕获阶段触发事件,一般都是 false，false就是冒泡，true就是捕获
  通过 addEventlistener()可以为一个元素的一个事件绑定多个响应函数
  这样当事件被触发时,响应函数会按照事件的绑定顺序依次执行
  该方法不支持IE8及以下的浏览器

```javascript
addEventlistener()//添加事件监听，可以为一个元素的同一个事件绑定多个响应函数，在开发的时候不用担心被别人同名的事件覆盖了
removeEventlistener()//移除元素的事件监听器
```

## 事件的传播

关于事件的传播方向当时两大巨头网景和微软有着不同的理解：

- 网景认为事件应该由外向内传递，事件发生时，应该先从外层元素上的事件，然后向内一层一层传递，这一事件的传播机制，称为事件捕获
- 微软公司认为事件由内向外传递，事件发生时，应该先从内层元素（触发事件的元素）开始，然后一层一层传递，这一事件传播机制，称为事件的冒泡
- 于是W3C将事件整个分成了三个阶段
  - 捕获阶段
    - 事件发生后首先从外层元素向内层元素进行事件的捕获
    - 默认情况下此阶段不会触发事件
    - 如果希望在捕获阶段触发事件，可以将addtEventlistener，第三个参数设为true，这个参数是true就是捕获，这个参数是false就是冒泡
  - 目标阶段
    - 捕获到达触发事件的元素，捕获终止
  - 冒泡阶段
    - 从触发事件的元素开始，向外层开始事件的冒泡

**用事件监听的方法添加事件的时候，如果要删除事件，要保证每一位置都是一模一样，否则删不了，如果要删，必须把函数提出来，第二个参数用同一个函数名字，第三个如果一个是false一个是true也不行**

![image-20200610091955794](C:\Users\zengxiaolong\AppData\Roaming\Typora\typora-user-images\image-20200610091955794.png)

## 拖拽

拖拽的功能

- 当在被拖拽的元素上按下鼠标，功能开始
- 当鼠标移动时，被拖拽的元素跟着鼠标一起懂
- 当鼠标松开是，鼠标固定在当前位置不动

```javascript

```

当鼠标按下时，功能开始，需要元素跟随鼠标移动

button	0是左键，1是滚轮，2是邮件

classList是一个类数组对象，在它里边将元素的每一个class属性都设置为数组中的元素，可以通过该对象来完成各种对class的操作

```javascript
contains()//用来检查classList是否含有某个类，如果有返回true，没有返回false
add()//用来向元素中添加新的class，样式也会一起添加
remove()//移除一个或多个class
replace()//使用一个新的class替换元素的class
toggle()//切换元素指定的class，如果有则删除，没有则添加
offsetX 和 offsetY// 用来获取鼠标指针在当前元素中的位置
```

## 鼠标事件

```javascript
contextmenu//表示右键菜单的事件
```

![image-20200609163809944](C:\Users\zengxiaolong\AppData\Roaming\Typora\typora-user-images\image-20200609163809944.png)

```javascript
preventDefault();//禁止默认行为，也可以禁止右键事件
return false;//也可以禁止默认行为
```

```javascript
mousedown//鼠标按下
mousemove//鼠标移动
mouseup//鼠标松开
//计算元素最终位置=元素起始位置+鼠标距离差（元素距离差）
```



## 鼠标滚轮事件

```javascript
wheel//事件会在鼠标滚动的时候触发
deltaX//获取鼠标横向滚动方向，向左拨或者向右拨，左是负值，右是正值
deltaY//获取鼠标纵向滚动方向，上是负，下是正

```

**注意：自己写的项目要在每个浏览器都测试一下，看看问题出在哪里**

**作业**

练习class属性的版本

拖拽查看车的全景

# 0610 类的操作 键盘事件

js改样式会跟css耦合，不是不能用，尽量少用

在js里修改class属性，间接修改了样式，会导致以前的class消失了，把以前的class重新赋值

这样可以对正则表达式动态的操作![image-20200610103443413](C:\Users\zengxiaolong\AppData\Roaming\Typora\typora-user-images\image-20200610103443413.png)



![image-20200610103620643](C:\Users\zengxiaolong\AppData\Roaming\Typora\typora-user-images\image-20200610103620643.png)

删除一个class就是替换一个空串

拖拽看全景浏览器是有一个懒加载，因为是现加载的，拖一次加载一下，为了解决这个问题，我们对图片进行预加载，只需要创建一个图片标签，然后设置路径，图片就会被预先加载

## 封装函数功能用来添加，检查，移出替换某个类

```javascript
 // 定义一个函数用来检查类中是否含有某个class
            function hasClass(ele, className) {
                // 用构造函数写正则 
                var reg = new RegExp("\\b"+className+"\\b");
                return reg.test(ele.className);
            }

            //定义一个函数用来添加某个类
                function addClass(ele,className){
                    //判断如果元素中没有某个类
                    if(!hasClass(ele,className)){
                        //添加一个类
                        ele.className += ' '+className;
                    }
                }

            //定义一个函数用来移除某个类
            function removeClass(ele,className) {
                var reg = new RegExp("\\s*\\b"+ className +"\\b")//任意数字加单独的className单词
                //将类中符合正则表达式的内容替换成空串
                ele.className = ele.className.replace(reg,'');
            }

            //定义一个函数，如果有某个类就删除，没有就添加
            function toggoleClass(ele,className) {
                //检查元素是否有某个类
                if(hasClass(ele,className)){
                    removeClass(ele,className);
                }else{
                    addClass(ele,className);
                }
            }

            //定义一个函数用来替换某个类
            function repaceClass(ele,oldCls,newCls) {
                // 根据老的类创建正则表达式
                var reg = new RegExp('\\b'+oldCls+'\\b');
                //将某个类中符合正则表达式的内容替换成newCls
                ele.className = ele.className.replace(reg,newCls);
            }
```



## 键盘事件

属性选择器

![image-20200610142850599](C:\Users\zengxiaolong\AppData\Roaming\Typora\typora-user-images\image-20200610142850599.png)

```javascript
keydown//按键按下的时候触发
keyup//按键松开事件
//div这种元素不能绑定键盘按下事件，只能绑定可以获取焦点的元素
//超链接可以获取焦点，通常是给input或者document绑定

```

事件对象中的key属性，表示当前所按的按键

keyCode返回的是按键变好（不区分大小写和换挡，这个现在不推荐使用了）

一个属性不能同事等于两个按键

![image-20200610145630108](C:\Users\zengxiaolong\AppData\Roaming\Typora\typora-user-images\image-20200610145630108.png)

类似于ctrl   alt   shift这种功能按键，在事件对象中都有专门判断的属性

ctrlKey用来判断Ctrl是否按下

altKey用来判断alt是否按下

shiftKey用来判断shift是否按下

这些键要结合和其他键一起使用



恢复本地文件代码没有修改之前的状态

![image-20200610154753363](C:\Users\zengxiaolong\AppData\Roaming\Typora\typora-user-images\image-20200610154753363.png)



## 定时器

![image-20200612090702210](C:\Users\zengxiaolong\AppData\Roaming\Typora\typora-user-images\image-20200612090702210.png)

setTimeout()延时调用，用来设置函数在一定事件后执行

- 第一个参数 要执行的函数
- 第二个参数 间隔的时间（毫秒）

  - 返回值
    - 返回一个唯一的id作为标识，可以通过该id来关闭延时调用
  - clearTimeout（id）关闭延时调用

setInterval()用来设置让一个函数反复执行，就是循环定时器
- 参数
  - 要执行的函数
  - 每次执行的时

- clearInterval()关闭循环定时器

- clearTimeout()关闭setTimeout()定时器

用延时定时器代替循环定时器更灵活，可以用在贪吃蛇

![image-20200612091407494](C:\Users\zengxiaolong\AppData\Roaming\Typora\typora-user-images\image-20200612091407494.png)

轮播图简便写法，在定时器里面设置这个变量

![image-20200610163312528](C:\Users\zengxiaolong\AppData\Roaming\Typora\typora-user-images\image-20200610163312528.png)

![image-20200611102600891](C:\Users\zengxiaolong\AppData\Roaming\Typora\typora-user-images\image-20200611102600891.png)

## 轮播图思路

html部分

- 最外层容器
  - 图片容器
    - 图片
    - 图片
    - 图片
    - 图片
  - 左右箭头
  - 小圆点容器
    - 小圆点
    - 小圆点
    - 小圆点
    - 小圆点

css部分

- 最外层样式相对定位
  - 宽高
  - 相对定位
  - 居中
- 图片容器
- 添加active类的图片透明度opcity：1
- 图片宽高，浮动，绝对定位
- 过渡效果：all 1s  linear(匀速)；
- 透明度：0
- 左右箭头
  - 引入背景图
  - 宽高
  - 绝对
  - 位置
  - 自身显示位置，background-position-x
  - 移入变换自身显示位置，变小手
- 小圆点容器
  - 绝对定位
  - 宽高
  - 位置
- 小圆点
  - 宽高
  - 颜色
  - 浮动
  - 圆角
  - 位置
- 移入小圆点
  - 颜色
  - 变小手

js部分

- 获取图片

- 获取左右箭头

- 获取所有小圆点

- 获取最外层容器

- 获取小圆点容器

- 创建一个变量表示当前索引

- 给最外层绑定单击事件

  - 判断当前事件对象是否等于左按钮
  - 判断当前事件对象是否等于右按钮

- 设置公共切换图片的函数，添加一个类的方法，calssList

  ```javascript
   function setPlay() {
              imgNodes.forEach((item, index) => {
                  item.classList.remove('active')
                  iconNodes[index].classList.remove('active')
              })
              imgNodes[current].classList.add('active');
              iconNodes[current].classList.add('active');
          }
   		//小圆点的单击事件
          // 遍历每一个小圆点
          iconNodes.forEach((item, index) => {
              //绑定点击事件
              item.onclick = function () {
                  current = index;
                  setPlay();
              }
          })
  
          //创建一个循环定时器
          var timeId = setInterval(function () {
              current++;
              if (current > imgNodes.length - 1) {
                  current = 0;
              }
              setPlay();
          }, 2000)
  
          // 给最外层添加鼠标移入事件
          container.addEventListener('mouseenter', function () {
              clearInterval(timeId);
          })
          //给最外层添加鼠标移出事件
          container.addEventListener('mouseleave', function () {
              //鼠标移出继续轮播
              timeId = setInterval(() => {
                  current++;
                  if (current > imgNodes.length - 1) {
                      current = 0;
                  }
                  setPlay();
              }, 2000)
          });
  ```

  

# offsetTop、clientTop、scrollTop、offsetTop各位置属性详解

![img](https://img-blog.csdn.net/20180104085724397)

```javascript
offsetWidth//content+padding+border
clientWidth//content+padding
clientLeft//元素边框宽度
offsetLeft//元素距离定位的祖先元素位置-border，如果没有定位的祖先元素，就是距离根元素的位置
offsetTop//元素距离定位的祖先元素位置-border，如果没有定位的祖先元素，就是距离根元素的位置

offsetX，offsetY//鼠标距离元素的位置
clientX,clientY//鼠标距离视口的位置
pageX//鼠标距离页面的位置
screenX//鼠标距离屏幕的位置

```







# 0612 贪吃蛇 BOM

每移动一下是自身大小，游戏窗口一定是一格整倍数，10倍

![image-20200612092748388](C:\Users\zengxiaolong\AppData\Roaming\Typora\typora-user-images\image-20200612092748388.png)

- 创建最外层窗口game
  - 游戏主窗口stage
    - 创建一个蛇snake
      - 创建蛇的身体snake-body
  - 创建保存游戏信息的窗口info
    - div，score计分的
    - div ，level
    - ![image-20200612093344987](C:\Users\zengxiaolong\AppData\Roaming\Typora\typora-user-images\image-20200612093344987.png)
  - 创建食物food，里面四个div用来换造型
    - div1
    - div2
    - div3
    - div4

**CSS部分**

- 去除默认样式
- 设置外层容器
  - 宽340
  - 高400
  - 背景色#b7d4a8
  - margin：0 auto
  - 边框：10像素，黑色，实线
  - 圆角
- 效果
- ![image-20200612093744227](C:\Users\zengxiaolong\AppData\Roaming\Typora\typora-user-images\image-20200612093744227.png)

- 主窗口
  - 边框2px 黑色
  - 宽高300*300

- 文字应该是跟主窗口一样的
  - 游戏信息
  - 宽300
  - font：bold 20px (字体)courier,(备选字体)monospace
  - 效果
  - ![image-20200612094255285](C:\Users\zengxiaolong\AppData\Roaming\Typora\typora-user-images\image-20200612094255285.png)
  - 弹性盒居中更加便捷，给game开启弹性盒
    - display：flex;
    - 设置主轴排列方向,主轴是纵向，侧轴是横向
      - flex-flow:column
    - align-items:center(设置侧轴上元素的对齐方式)
    - 父元素设置弹性容器，子元素自动就是弹性子元素 了，默认垂直排列，主轴是纵向，如果默认水平排列，主轴就是横向
    - justify-content:space-around（设置主轴上的对齐方式）
    - **忘的东西赶紧复习，弹性盒模型可以适用所用场景**
    - 浮动尽量不用，弹性盒模型不用算尺寸，浮动可能高度塌陷，浮动就要设置两个文字的元素
    - 开启info的弹性盒

蛇移动的时候，不知道蛇头的位置在哪，所以先从尾巴开始移动，从后往前移



## BOM浏览器对象模型

- BOM中为我们提供了一组对象，借助这组对象，我们可以通过js来操作浏览器

- window代表浏览器窗口，全局对象

- Navigator     表示浏览器的信息

- Location    表示浏览器的地址栏信息

  - 可以通过window.locationg或location来对其进行访问
  - ![image-20200612161040444](C:\Users\zengxiaolong\AppData\Roaming\Typora\typora-user-images\image-20200612161040444.png)
  - 它用于获取或设置浏览器的地址栏，操作Location就是操作浏览器地址栏
  - 直接打印它可以获取到地址栏信息
  - 也可以对其修改

  ![image-20200612161314767](C:\Users\zengxiaolong\AppData\Roaming\Typora\typora-user-images\image-20200612161314767.png)

  - 修改后浏览器将会跳转到修改后的地址
    - 通过修改location会产生历史记录，也就是可以回退
  - assign()用来修改location的值，和直接修改location一样,可以用绝对路径，也可以用相对路径
  - replace（）替换，也可以用来跳转页面，使用新的页面替换当前的页面，不会生成历史记录，不能回退
  - location.reload()重新加载，刷新当前页面
  - reload(true)  强制清除缓存刷新页面，这个方法不推荐使用，过时的方法

- History     表示浏览器的历史记录

  - 可以通过window.history或history来对其进行访问
  - 历史记录属于个人隐私，所以js无法直接访问用户的历史记录
    - history.forward()
      - 用来切换的下一页，相当于浏览器向前翻页的按钮
    - history.back()相当于浏览器的回退按钮，往后翻页
    - history.go()跳转到指定页面
      - 1  表示前进1页
      - 2  表示前进2页
      - -1回退1页
      - -2 回退2页

- Screen      表示用户设备屏幕信息

- BOM对象都是window对象的属性，可以通过window对象访问，也可以直接访问

  - ```javascript
    alert(navigator)
    
    ```

  - 

## Navigator

表示浏览器的信息

可以通过window.navigator来访问，或者navigator识别浏览器的信息

Netscape	网景

由于历史原因，Navigator中大部分属性都不能用啦识别浏览器

只剩下一个还有点用的属性userAgent，这个属于等同于浏览器

- userAgent是一个字符串，字符串中包含浏览器的描述信息

可以通过一些IE中独有的对象来判断一个浏览器是不是ie

window.ActiveXObject，这个方法在ie11里是不灵的

对象虽然存在，但是转换成布尔值还是转成false，目的就是伪装