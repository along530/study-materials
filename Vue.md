# vue



- 概念：渐进式JS框架
  - 渐进式
    - 自底向外增量开发
- 作用：用来构建用户界面

​    **3. 表达式&语句的区别**

​     **1. 表达式**

​      - 没有分号

​      - 一定会有返回值（返回值可能是undefined）

​     **2. 语句**

​      - 有分号（没有分号，在JS编译时会自动添加分号）

​      - 没有返回值

​     const a = 123 // 语句

​     a // 表达式

​     123 // 表达式

​     a; // 语句

​     function fn() {} // 语句

​     const fn = () => {} // 函数表达式语句

​     fn // 表达式

​     fn() // 表达式

​     fn(); // 语句

​     if (a > 1) {} // 语句

​     a > 1 // 表达式





## 计算属性和监视属性

1. **计算属性**

​    在computed属性对象中定义计算属性的方法

​    在页面中使用{{方法名}}来显示计算的结果

   **2. 监视属性:**

​    通过vm对象的$watch()或watch配置来监视指定的属性

​    当属性变化时, 回调函数自动调用, 在函数内部进行计算

   **3. 计算属性高级:**

​    通过getter/setter实现对属性数据的显示和监视

​    计算属性存在缓存, 多次读取只执行一次getter计算

## new Vue(配置对象)

1. **el 元素**
   获取DOM元素（document.querySelector）

​      或者vm.$mount('#app')

2. **data 数据**
   用来保存模板页面需要使用动态数据（一般数据/非函数数据）

3. **methods 方法**
   用来保存模板页面需要使用函数数据

4. **computed 计算属性**
   用来保存需要计算的属性
   如果有一个属性，需要根据其他属性（data中属性）来计算生成

5. **watch 监视属性**
   监视属性（data中的属性）的变化
   如果有一个属性发生变化，需要做一些特殊操作（发送请求，保存数据...）
   注意：先要定义data中的属性才能监视

## 模板

1. 模板页面 HTML + CSS + JS
2. 模板语法（只出现HTML中）

  - 插值语法（双大括号表达式） {{JS表达式}}
    用来动态展示JS中的数据
    注意：只能用来标签内部，不能作为标签属性

  - **指令语法**
    作为元素标签属性使用

  - **v-model** 用来实现双向数据绑定
    注意：只能用于表单项元素（如：input、textarea、select、checkbox...）

      - 数据可以由Model（js）流向View（模板页面）
      - 当用户输入数据时，数据可以View（模板页面）流向Model（js）
    
  - 简写  **:**

    ```javascript
         <input type="text" value="msg" /> 值就是msg
    
    ​     <input type="text" :value="msg" /> 值会去vm上找
    ```

    

  - **v-bind** 用来实现单向数据绑定
    简写 :

  - **v-on** 用来绑定事件监听
    简写 @

  - **v-if / v-else-if / v-else** 用来切换元素显示/隐藏
    特点：隐藏的话会从DOM树种移除元素

  - **v-show** 用来切换元素显示/隐藏
    特点：隐藏的话会通过display:none隐藏元素
    频繁切换用v-show, 反之v-if

  - **v-for** 遍历数组/对象

    - 需要设置唯一的key

    - 有id用id，没有id再用index

    - ```java
      v-for="(person, index) in persons"//括号可以不写，但是自己要知道，最好写上括号看起来更清晰	
      ```

- 

## 样式处理

如果样式是静态的，就直接写死，只有将来样式会发生动态变化，才会使用下面方案

1. **class**

- string  :class="color"
- obj   :class="{a: isShow, b: !isShow}"
- array :class="['red', green]"

2. **style**
   :style="{fontSize: '30px', color: color}"
   注意：采用小驼峰命名法

## 双向数据绑定

1. 数据可以由Model（js）流向View（模板页面）
2. 当用户输入数据时，数据可以View（模板页面）流向Model（js）

## MVVM

- M Model 数据层
- V View 视图层
- VM ViewModel 视图数据层
  - 通过绑定事件监听和数据绑定的方式来实现双向数据绑定
  - 绑定事件监听：V --> M
  - 数据绑定: M --> V



## 事件处理

绑定监听

- v-on:xxx='fun'
- 简写
  - @xxx='fun'
  - @xxx='fun(参数)'
    - 写函数调用的方法（函数实际上没有调用），此时能接受n个参数
  - 默认事件形参:event
  - 隐含属性对象:$event

事件修饰符

- ```javascript
  .prevent:阻止事件的默认行为 event.preventDefault()
  .stop:停止事件冒泡 event.stopPropagation()
  
```
  
  - 更多事件修饰符:    https://cn.vuejs.org/v2/api/#v-on

按键修饰符

- **.keycode** : 操作的是某个keycode值的健
- **.enter** : 操作的是enter键
- 参考地址:https://cn.vuejs.org/v2/guide/events.html#%E6%8C%89%E9%94%AE%E4%BF%AE%E9%A5%B0%E7%AC%A6

## 表单处理

使用v-model(双向数据绑定)自动收集数据

- text/textarea

- checkbox

- radio

- select

当你选中option时，如果option设置了value属性，那么select收集到的就是value属性

 如果没有value属性，那么select收集到的就是option里面的内容

```javascript
	<select v-model="city">
      <option value="">未选择</option>
      <option v-for="city in cities" :key="city.id" :value="city.id">
        {{city.name}}
      </option>
    </select>
```

> ref 用来获取DOM元素



## Vue实例生命周期

概念:从诞生到死亡整个过程依次经历的函数

- **初始化显示**

  - beforeCreate()

    - 在数据代理之前触发的，所以此时还不能使用data中的数据

      数据代理：将data中的数据代理到this上

  - created()

    - 在数据代理之后触发的，所以此时才可以使用data中的数据

  - beforeMount()

    - 在模板解析之前触发

  - mounted()

    - 在模板解析之后触发，此时才能获取到真正的DOM元素

      注意：如果需要操作DOM，要在mounted和其后才做

      解析成浏览器认识的元素

- **更新状态**

  - beforeUpdate
    - 在更新之前触发，实际上数据已经更新了
  - updated()
    - 在更新之后触发，实际上数据已经更新了
    - 只要触发data里面的数据就会触发

- **卸载销毁vue实例:**

  - ```javascript
    this/vm.$destroy()
    ```

  - beforeDestroy 在卸载之前

  - destroyed  在卸载之后

 **重要的生命周期：**

**created / mounted**   (数据代理之后/模板解析之后)

- 发送ajax请求

- 设置定时器

- 绑定特殊事件等一次性任务

**destroyed**

- 做一些收尾工作

- 取消ajax请求

- 清除定时器

- 解绑特殊事件等收尾工作

> data的数据要用于动态展示
>
> 如果要在实例对象上定义数据，但是又不用数据展示，直接定义在this上

## 过渡动画 transition

元素从一个位置到另一个位置的过渡效果

transitiong组件：对显示/隐藏(v-if/vishow)的元素，添加过渡transition/动画animation效果，animation可以指定中间过渡的时间，效果，精细的控制运动轨迹

transition原生并没有这个标签，是Vue产生的

**1.vue动画的理解**

​    操作css的trasition或animation

​    vue会给目标元素添加/移除特定的class

**2.基本过渡动画的编码**

​    1). 在目标元素外包裹<transition name="xxx">

​    2). 定义class样式

​     1>. 指定过渡样式: transition

​     2>. 指定隐藏时的样式: opacity/其它

3. **过渡的类名**

​    xxx-enter-active: 指定显示的transition

​    xxx-leave-active: 指定隐藏的transition

​    xxx-enter: 指定隐藏时的样式

- transition组件：

  ​     在操作显示/隐藏的元素，添加一个过渡transition/动画animation效果

  

  ​     显示 -> 隐藏 leave

  ​      开始阶段：v-leave

  ​      过渡阶段: v-leave-active

  ​      结束阶段: v-leave-to

  

  ​     隐藏 -> 显示 enter

  ​      开始阶段：v-enter

  ​      过渡阶段: v-enter-active

  ​      结束阶段: v-enter-to

  可以通过<transition name='fade'></transition> 来修改类型的前缀

  

## 过滤器

理解过滤器

 功能: 对要显示的数据进行特定格式化后再显示,文本/时间

**注册过滤器**

- 全局过滤器(所有组件都能使用)
  
  - ```
    Vue.filter(名称, function (value, ...args) {})
    ```
- 局部过滤器(只有当前组件能够使用)
  
  - ```
    new Vue({ filters: { 名称: function (value, ...args) {} } })
    ```
  
  - 

 注意: 并没有改变原本的数据, 可是产生新的对应的数据

计算属性只能处理数组或者对象数据

 处理时间js库

- moment

- dayjs

- date-fns



2. 编码

 1). 定义过滤器

  ```javascript
Vue.filter(filterName, function(value[,arg1,arg2,...]){

   进行一定的数据处理

   return newValue

  })
  ```



 2). 使用过滤器

```javascript
<div>{{myData | filterName}}</div>
<div>{{myData | filterName(arg)}}</div>
data要处理的数据
format过滤器函数
```

​    最终会调用 format(date) 得到返回值，显示返回值

局部过滤器：格式化文本/时间

只能当前实例对象vm/this使用

## 指令

自定义两个指令

- 功能类型v-text  更新元素的 textContent(相当于innerText)

key是指令名称,value是要做的事

expression 表达式

binding代表指令信息

- 指令名称 name rawName
- 表达式 expression value

自定义局部指令特点:只能当前实例对象使用

定义全局指令通过Vue.derective()

**常用内置指令**

   v-if : 如果为true, 当前标签才会输出到页面,如果隐藏就是彻底干掉dom元素

   v-else: 如果为false, 当前标签才会输出到页面

   v-show : 通过控制display样式来控制显示/隐藏

   v-for : 遍历数组/对象

   v-on : 绑定事件监听, 一般简写为@

​    @click.once="handleClick" :一次性绑定

   v-bind : 强制绑定解析表达式, 可以省略v-bind    简写 **:**

   v-model : 双向数据绑定

   v-text : 更新元素的 textContent(相当于innerText)

   v-html : 更新元素的 innerHTML

   v-once : 元素只会渲染一次，后续渲染无效（性能优化）

   v-cloak : 防止闪现表达式, 与css配合: [v-cloak] { display: none }

修饰符:

- event.preventDefault()(取消默认事件)

- event.stopPropagation()(阻止冒泡)

**自定义指令**

- 全局指令
  - Vue.directive('指令名称',function(el,binding){})
    - el 绑定指令的DOM元素
    - binding 指令的所有信息
- 局部指令
  - new Vue({directives:{指令名称:function(el,binding){}}})
  - ![image-20200731085351159](C:\Users\zenghao\AppData\Roaming\Typora\typora-user-images\image-20200731085351159.png)

## 插件 plugin

Vue插件:扩展Vue的功能

- 扩展Vue全局功能,通过Vue直接使用
  - Vue.filter/Vue.directive
- 扩展Vue局部功能,通过实例对象使用

用法

- 定义插件文件 xxx.js
- function xxx(Vue){扩展Vue功能}

使用/插件

- Vue.ues(插件)
- 注意:必须先注册插件,再new VUe()

语法

- 定义成对象
- 定义成函数

引用myPlugin插件时,内部会调用install方法

扩展局部功能要写在原型上

- $mount() 
- $destroy()

扩展其他功能

- 自定义过滤器

- ```javascript
  Vue.filter("timeFormat", function (
      value,
      formatStr = "YYYY-MM-DD HH:mm:ss"
    ) {
      return dayjs(value).format(formatStr);
    });
  ```

- 

- 自定义指令

- ```javascript
  Vue.directive('upper-case', function (el, binding) {
     el.textContent = binding.value.toUpperCase();
   })
  ```

## key

 面试题:

   1). react/vue中的key的作用/内部原理

   2). 为什么列表的key尽量不要用index

  \1. 虚拟DOM的key的作用?

   1). **简单的说**: key是虚拟DOM对象的标识, 在更新显示时key起着极其重要的作用

   2). **详细的说:** 当列表数组中的数据发生变化生成新的虚拟DOM后, React进行新旧虚拟DOM的diff比较

​     a. key没有变

​       item数据没变, 直接使用原来的真实DOM

​       item数据变了, 对原来的真实DOM进行数据更新

​     b. key变了

​       销毁原来的真实DOM, 根据item数据创建新的真实DOM显示(即使item数据没有变)

2. **key为index的问题**

   1). 添加/删除/排序 => 产生没有必要的真实DOM更新 ==> 界面效果没问题, 但效率低

   2). 如果item界面还有输入框 => 产生错误的真实DOM更新 ==> 界面有问题

   注意: 如果不存在添加/删除/排序操作, 用index没有问题

  \3. 解决:

   使用item数据的标识数据作为key, 比如id属性值



**在哪里使用**

- v-for遍历的时候,遍历的每一项元素需要添加一个唯一的key属性

使用时注意

- key的值能用id用id

- 什么时候用index

  - 没有id可以跟后台协商返回一个id,因为数据库一般都会有id
  - 是往数组后面添加/删除




外部文件需要:

- Vue.use(插件) 注册插件

- 引入插件

插件定义成函数,内部会去判断插件是函数类型还是对象类型

为什么用id作为唯一的key属性,这是服务器后端生成的,能用id尽量用id

- 虚拟DOM,diff算法

- 第一次渲染DOM树
- 第二次渲染DOM树,更改数据重新渲染,生成新的**DOM**树,跟第一个DOM树比较
- 把差异统一更新,重新渲染,性能更加高效
- 相同层级的子元素做了优化

index应用场景

- 遍历的元素往后面添加

**结论**:能用id尽量用id,没有id可能要自己创造id,一般情况下浏览器可能不会提示,但是自己要知道

## 组件

概念:包含特定用户界面功能的代码集合体(HTML+css+js)

什么是模块:只有js

将来开发都是基于组件开发的,如果多个组件中有公共的js代码, 就提取封装成一个js模块,组件中再引入模块使用

使用组件

- 定义组件构造函数
  - const VueComponent = Vue.extend({组件配置对象})
- 注册组件
  - 全局组件
    - Vue.component(组件名称,组件构造函数)
  - 局部组件
    - new VUe({components:{组件名称:组件配置对象}})
    - ![image-20200731090357661](C:\Users\zenghao\AppData\Roaming\Typora\typora-user-images\image-20200731090357661.png)

- 使用组件
  - <组件名称></组件名称>

全局组件

局部组件

如果data是对象,直接使用,如果data是函数,会调用函数使用其返回值

template里面写组件的html代码

## cli 脚手架

devtool 用来增强调试的

compress  压缩

npm i webpack-dev-server -D

static/media/ 表示静态的位置

limit:8*1024  小于这个值的就转化成base64

html-webpack-plguin插件下载

vue loader网站下载编译vue的loader

babel-core

copy-plugin

extensions:[] 数组里面的内容可以省略,自动补全文件扩展名

ignore:[ ]j忽略

## 搭建脚手架流程

引入path模块

引入html-webpack-plugin组件,需要先下载

引入VueLoaderPlugin

引入CopyPlugin

module.exports

- entry

- output

  - 文件名

- module

  - rules[]

  - - test匹配.css结尾的

    - 规则use[]

      

    - 匹配图片

    - url-loader

    - options

      - base64位8*1024
      - name:''  (静态路径)

    - 

    - 匹配.html结尾

    - html-loader

    - options

      - 复制官网

      

    - 匹配.vue结尾

    - vue-loader

      

    - 匹配.js结尾

    - babel-loader

- (module外面)

- plugins[ ]

  - new HtmlWebpackPlugin 组件
    - 处理根目录下面的public里面的index.html文件
  - new VueLoaderPlugin()
  - new CopyPlugin
    - patterns[]{}
      - 从绝对路径resolve方法,public
      - 到绝对路径内存里面的dist
      - globOptions:{}
        - ignore忽略index.html

- (plugins外面)

- 模式:开发环境

- 增强调试devtool:"eval-cheap-module-source-map"

```javascript
devServer:{
设置dist文件
端口号
域名
自动打开服务器
压缩
}
resolve:{

自动补全文件扩展名 .js .vue .json
extensions[]
}
```

> hot:true 开启HMR功能,提升打包性能
>
> include 包含
>
> exclude 排除
>
> 复制文件的时候在文件夹复制,在vscode复制会卡死
>
> main.js是打包的入口文件
>
> 必须要有根标签<div></div>,否则报错

## 定义Vue 的组件

- 组件名称采用大驼峰命名法
- 后缀名 .vue
- 默认情况下,都有一个公共应用组件:App.vue
  - 是最大的,最外层组件
- 组件内部有三个代码块
  - template 写html代码
    - 必须只有一个根标签
  - script  写js代码
    - 默认暴露出去一个配置对象(data/methods/filters/computed/watch),用es6模块化
  - style  写css代码

>  HtmlWebpackPlugin会自动引入打包生成的js文件和css文件
>
>  所有模块要用的东西都要引入
>
>  主文件 main.js 引入相关的依赖 new Vue将APP组件渲染到页面
>
>  index.html是写容器元素
>
>  APP.vue是写组件的
>
>  以后写内容都是在src目录里面写
>
>  csoped 确保样式在当期组件生效
>
>  路径别名@assets/xx/xx

注册组件的时候一般采用大驼峰,最终使用时采用前两个

![image-20200731112730974](C:\Users\zenghao\AppData\Roaming\Typora\typora-user-images\image-20200731112730974.png)

 问题一：样式没办法正常显示

  原因：最新的css-loader是4.x.x版本，不能实现

  解决：要使用css-loader 3.x.x的版本

   npm i css-loader@3 -D



 问题二：当你修改JS代码，触发 CopyPlugin 的功能

  原因：会覆盖打包生成的html（ignore没有效果） 

   copy-webpack-plugin 6.x.x

  解决： 要使用copy-webpack-plugin 5.x.x的版本

   npm i copy-webpack-plugin@5 -D 

>  全局样式，所有组件都生效 
>
>  问题：如果其他组件有相同的样式，就会覆盖
>
>  解决：scoped
>
>  让样式只在当前组件生效
>
>  devtools 用于调试vue开发者工具
>
>  main.js主文件里面的变化很少
>
>  运行js代码要关闭其他运行的js文件,否则端口号冲突
>
>  如果复制的时候丢包,把node_modules删掉,重新下npm i
>
>  一定要有根标签,否则报错
>
>  APP是Add是父子关系,跟List也是父子关系
>
>  render函数内部会帮你注册App组件,渲染#app容器内部去
>
>  用户名、评论数据就是data
>
>  props(标签属性)方案,父组件给子组件传递动态数据
>
>  - 默认props属性组件不接收,如果需要接收的话,需要手动声明接收
>  - 里面写要声明接收的属性
>  - key 接收的属性
>  - value 接收属性值的类型 Array
>  - 组件实例对象上就会添加一个属性comments,值为父组件传过来的值
>
>  mounted()组件挂载完毕的函数,
>
>  submit事件
>
>  - 按钮的type类型就是submit
>  - 点击按钮就会触发form表单的submit事件

- 接收一个参数createElement,具有模板编译能力
- 使用简单
- 打包体积更小

拆分组件

- 功能
- 变化

## 组件化开发重要事项

- **拆分组件**
  - 根据页面功能或变化来拆分
    - App
    - CommentAdd
    - CommentList
    - CommentDel
- **实现静态组件**
  - 只有html+css,没有js
  - 实现:从小到大,从上到下,从左到右



- **实现动态组件**

  - 要不要定义data

    - 要看用户界面有没有变化

  - data定义成什么值

    - 数据列表展示：

    - ```javascript
      comments: [{id: 1, name: 'xxx', content: 'yyy'}, {id: 2}, {id: 3}]
      ```

    - 

- **数据定义在哪个组件,看数据由哪些组件需要**

  - 数据展示
  - 更新数据的功能
  - 如果数据只有单个组件要,就定义在单个组件内部
  - 如果数据由多个组件要,就定义在公共的父组件/祖先组件,优先考虑父组件
  - 数据源只能有一个,不能定义多个数据

- 实现功能

  - 先实现数据的动态展示

  - 再实现其他功能,就是操作数据功能,(添加,修改,删除)

  -  数据源在哪里（App），操作数据的方法就定义在哪里（App）？

     App组件将操作数据的方法传给CommentAdd，CommentAdd通过调用方法从而更新App组件数据

- 组件通信的方法

  - props

  - 适用于父组件通信

  -  父 --> 子

      传递非函数数据，子组件直接使用

     子 --> 父

      父给子传递函数数据，子组件调用函数传递数据，父组件就能接收到了

  - 注意:props传递的数据只读不修改

  - 用法

    - ```javascript
        1. 父组件 在子组件标签定义属性和值
          <CommentList :comments="comments"/>
          
        2. 子组件声明接受props
          props: {
            comments: Array
          },  
        
          props: ["comment"]
      ```

    - 

      

    - 子组件实例对象上就会添加响应的属性,就可以直接使用了



> 数据源在App,就在App里面写删除的逻辑
>
> 取名字尽量避免关键字,可以简写
>
> 计算属性优先级高于watch,并且不能做异步操作
>
> computed计算属性不能做异步操作
>
> watch可以做异步操作 
>
> 组件挂载完毕就会触发mounted
>
> 计算属性可以重写属性的get方法和set方法
>
> localStorag 永久存储在磁盘



## 数据动态展示

![image-20200801200718955](C:\Users\zenghao\AppData\Roaming\Typora\typora-user-images\image-20200801200718955.png)

main.js ,基本模板,很少变化

- 引入vue 
- 引入App
- 关闭生产提示
- 渲染到页面,挂载到#app容器

复制静态页面的html和css两个文件

测试静态页面有没有出来

三个组件TodoFooder,TodoHeader,TodoList

每个组件放入响应的相应的html代码,

父组件引入子组件,并且引入哪个组件就要注册哪个组件,

- App是header,list,footer的直接父组件,结构是todo-container结构
  
- list是item是直接父组件,list里面是todo-main结构		
  
- item里面是li结构

- header里面的todo-header结构

- 

- 每个选项都有三个属性

  ![image-20200801202939762](C:\Users\zenghao\AppData\Roaming\Typora\typora-user-images\image-20200801202939762.png)

**App组件**

todos定义在App里面,因为多个组件要用

- data
  - return对象
    - todos[id,content]

props给TodoList传递数据

- 使用TodoList组件

- 收集数据:todos='todos'

methods

- addTodo,传入要添加的todo
  - 实例对象的todos首位添加({id:this.id++ ,...todo})
    - (...todo展开一个对象到新对象中,新对象中有id属性,也有todo上面的属性)
  - id初始值:xx

**TodoList**

- 内部要接收一下props :[]

- 使用TodoItem组件,遍历todos,key属性,把遍历的todo传给TodoItem

**TodoItem组件**

- 通过标签属性接收,todo

- span标签里面插值语法,向页面展示todo.content
- li标签
  - 绑定mouseenter ="isShow = true"
  - 绑定mouseleave = "isShow = false"
  - :class="{'item-bg':isShow }"(有可能有,有可能没有,看true和false)
- data
  - return对象
    - isDelBtnShow 默认false不显示
- button标签v-show="isShow "默认不显示
- style标签
  - .item-bg{黑色,.5(透明度)}

**TodoHeader组件**

- input
  - 收集数据-->v-model="content"
  - 绑定按键事件的enter触发事件="handleEnter"
- data函数里面return一个对象
  - content初始化为空
- methods
  - handleEnter
    - 定义content,实例对象.content.去除两边空格
    - 判断如果没有content
      - 弹出""
      - return
- 接收App的数据"addTodo"
- 调用实例对象的addTodo方法传一个对象,里面有content(目的是更新父组件里面的数据)
- 实例对象的content清空
- 

> 更新App里面的todos数据,页面就会发生变化



<img src="C:\Users\zenghao\AppData\Roaming\Typora\typora-user-images\image-20200801215941642.png" alt="image-20200801215941642" style="zoom:150%;" />

isCheck在后面,会覆盖前面的todo里面的的isCheck

![image-20200801220255883](C:\Users\zenghao\AppData\Roaming\Typora\typora-user-images\image-20200801220255883.png)

把返回的新数组交给this.todos去更新,这时候this.todos去更新就会更新成一个新数组

![image-20200801221405803](C:\Users\zenghao\AppData\Roaming\Typora\typora-user-images\image-20200801221405803.png)

这个相当于一个只读属性

![image-20200801221733640](C:\Users\zenghao\AppData\Roaming\Typora\typora-user-images\image-20200801221733640.png)

统计isCheck 的数量

![image-20200801223206706](C:\Users\zenghao\AppData\Roaming\Typora\typora-user-images\image-20200801223206706.png)

修改item的时候就是决定了footer里面的get方法,然后footer里面的set的方法又会影响item的值

![image-20200801230853681](C:\Users\zenghao\AppData\Roaming\Typora\typora-user-images\image-20200801230853681.png)

如果没有值就给一个空数组,返回值是一个json字符串,还需要JSON.parse转成js数组对象,将来读取数据就会从本地去加载

![image-20200801232032640](C:\Users\zenghao\AppData\Roaming\Typora\typora-user-images\image-20200801232032640.png)

这里是将id变成唯一的id

![image-20200802181851635](C:\Users\zenghao\AppData\Roaming\Typora\typora-user-images\image-20200802181851635.png)

class有可能有,有可能没有,它的值看isShow是true还是false

![image-20200802182119945](C:\Users\zenghao\AppData\Roaming\Typora\typora-user-images\image-20200802182119945.png)

过滤的是整个元素

![image-20200802182147553](C:\Users\zenghao\AppData\Roaming\Typora\typora-user-images\image-20200802182147553.png)

不会修改原数组,要重新赋值,这样原数组才会发生变化





> 刷新的时候要保存todos,需要持久化存储,localstorage
>
> 要运行的文件名字要跟webpack入口文件一致,要运行哪个就改哪个文件的名字

**props传输数据**

![image-20200803090012943](C:\Users\zenghao\AppData\Roaming\Typora\typora-user-images\image-20200803090012943.png)



## 0803 vue自定义事件

绑定事件

- on
- once

触发事件

- emit(事件名,事件回调函数接收的参数)

解绑

- off(事件名,事件回调函数)

实例对象上面的东西就要加$

ref

- 给普通html标签绑定ref,最终就会获取DOM元素
- 给组件标签绑定ref,最终获取组件实例对象

![image-20200803092513463](C:\Users\zenghao\AppData\Roaming\Typora\typora-user-images\image-20200803092513463.png)

```javascript
mounted(){
    this.$refs.child.$on('aaa',this.事件回调)
}
这两种写法是等价的
<aaa @事件名 = '事件回调'/>
```



_events保存了自定义事件

this实际上是组件的实例对象

VueComponents是Vue组件构造函数

Vue原型对象所有实例都可以访问

![image-20200803105431008](C:\Users\zenghao\AppData\Roaming\Typora\typora-user-images\image-20200803105431008.png)

实现任意组件通信,全局事件总线EventBus

程序从上到下执行,因为最开始newVue产生vm,让所有组件都能使用

> 哪个组件需要数据展示就把数据定义在哪个组件
>
> mounted里面绑定事件
>
> 绑定事件就要解绑,避免多个组件绑定的事件冲突
>
> created,mounted
>
> 绑定事件,发请求

> 属性只要添加一次，一定考虑初始化4个生命周期函数
>
> 必须在 mounted 之前（mouted之前是子组件渲染，子组件要使用）
>
>  所以在beforeCreate绑定$bus属性，希望越早绑定越好
>
>  this就是vm
>
> 

在这里触发四个子组件

![image-20200803191959643](C:\Users\zenghao\AppData\Roaming\Typora\typora-user-images\image-20200803191959643.png)

## 插槽slot

![image-20200803151450953](C:\Users\zenghao\AppData\Roaming\Typora\typora-user-images\image-20200803151450953.png)

**默认插槽**

父组件,双标签

slot标签里面写什么就看父组件怎么传了

只能渲染到一个位置

**命名插槽/具名插槽**

可以将标签内容分别渲染到子组件不同位置



**作用域插槽**

特点:能够接收子组件传递过来的数据

每一个组件都有自己的作用域,要渲染的数据必须要定义在当前组件中

或者引入使用

数据对于组件必须是可见的

```vue
<!-- 
v-slot:title="slotProps"
      v-slot 指令
      v-slot:title 给当前插槽取一个名称。叫做title
      v-slot:title="slotProps" 接受子组件slot标签传递过来的数据slotProps
    slotProps是一个对象，对象里面包含了 slot标签 的数据
 -->
<template v-slot:title="slotProps">
  <h1>hello {{title}} {{slotProps.num}}</h1>
</template> 

<!-- 简写 -->
<template #title="slotProps">
    <h1>hello {{ title }} {{ slotProps.num }}</h1>
  </template>

<!-- 
    #title="{ num }" 解构赋值语法，提取所有slot属性中的num
  -->
```



> v-slot:标签名字 简写#
>
> 如果传数据可以用props或者事件总线,如果传标签就用插槽

## 消息订阅(subscribe)与发布(publish)

App订阅方

A发布方



# 组件的通信

1. 传递的数据是只读不修改
2. 数据源在哪，更新数据的方法就定义在哪，谁要用就把更新方法传给谁

## props

1. 适用于父子组件通信
   父 --> 子
   传递非函数数据，子组件直接使用
   子 --> 父
   父给子传递函数数据，子组件调用函数传递数据，父组件就能接收到了
2. 用法：
3. 父组件 在子组件标签定义属性和值
   <CommentList :comments="comments"/>

4. 子组件声明接受 props
   props: ["comment"],


```javascript
props: {
  comments: Array
},

props: {
  person: {
    // 必选属性
    type: Object, // 值的类型是对象
    required: true, // 必须的
  },
  name: {
    // 可选属性
    type: String,
    default: "tom", // 默认值
  },
  age: {
    type: Number,
    required: true,
    // 检查属性的函数
    // val就是属性的值
    validator(val) {
      console.log("validator()", val);
      return val > 18;
      // return true; // 返回true代表校验通过
      // return false; // 返回false代表校验失败，就会报错
    },
  },
}
```

3. 子组件实例对象上就会添加相应的属性，就可以通过 this 使用了

## 自定义事件

适用场景：子组件向父组件通信

1. 绑定自定义事件

<Child @addPerson="addPerson"/>

或

<Child ref="child"/>
mounted() {
  // 绑定事件
  this.$refs.child.$on('addPerson', this.addPerson);
},
beforeDestroy() {
  // 解绑事件
  this.$refs.child.$off('addPerson', this.addPerson);
},

2. 触发自定义事件

this.\$emit('addPerson', xxx)

3. 自定义事件 API

- xxx.\$on(事件名称, 事件回调函数); 绑定持续性事件
- xxx.\$once(事件名称, 事件回调函数); 绑定一次性事件
- xxx.\$emit(事件名称, ...args); 触发事件
- xxx.\$off(事件名称, 事件回调函数); 解绑事件

4. 特点
   给 A 组件绑定自定义事件，就只有 A 组件可以触发，其他组件不行
   所以只能父子组件通信，默认不能跨层级通信

## 总结组件间通信

组件关系：父子 / 祖孙 / 兄弟

1. props
   适用于父子组件通信
   父 --> 子 传递一般数据
   子 --> 父 传递函数数据

- 使用
  - 父组件通过标签属性传递动态数据 <A :xxx="xxx" />
  - 子组件需要声明接受属性（三种方式）
  - 子组件通过 this 直接访问使用
- 注意：数据只读不修改

2. 自定义事件
   适用于子 --> 父通信（一般不用）

3. 全局事件总线（自定义事件加强版）
   适用于祖孙 / 兄弟组件通信

- 使用

  - 首先将全局事件总线对象（vm）定义到 Vue 的原型对象上

    - 为了所有实例对象都能够使用

    ```
    new Vue({
      beforeCreate() {
        Vue.prototype.$bus = this;
      }
    })
    ```

  - 接受数据方：绑定自定义事件

  ```
  mounted() {
    this.$bus.$on(eventName, callback);
  },
  beforeDestroy() {
    // 注意 callback 必须和绑定事件的 callback 一致
    this.$bus.$off(eventName, callback);
  }
  ```

  - 发送数据方：触发自定义事件

  ```
  this.$bus.$emit(eventName, arg1, arg2...)
  ```

4. pubsub 消息订阅发布机制（本质上就是自定义事件）
   适用于祖孙 / 兄弟组件通信（一般不用）

5. 插槽
   适用于父子组件通信
   前面 4 种手段都是通信动态数据
   而插槽通信是带动态数据的标签

父 --> 子 通信是带动态数据的标签
子 --> 父 通信是动态数据

- 默认插槽

```
父组件 A：
<B>
  <!-- h1就是要传给子组件B的内容 -->
  <h1>{{title}}</h1>
</B>
子组件 B：
<!-- 使用父组件传递过来的标签数据 -->
<slot></slot>
```

- 命名插槽 / 具名插槽

```
父组件 A：
<B>
  <template slot="header">
    <h1>{{title}}</h1>
  </template>

  <template v-slot:header>
    <h1>{{title}}</h1>
  </template>

  <template #header>
    <h1>{{title}}</h1>
  </template>
</B>
子组件 B：
<slot name="header"></slot>
```

- 作用域插槽

```
父组件 A：
<B>
  <template v-slot:header="slotProps">
    <h1>{{title}}</h1>
    <p>{{slotProps.num}}</p>
  </template>

  <template #header="{ num }">
    <h1>{{title}}</h1>
    <p>{{num}}</p>
  </template>
</B>
子组件 B：
<slot name="header" :num="num"></slot>
```

6. vuex(将来学~)

![image-20200803194735371](C:\Users\zenghao\AppData\Roaming\Typora\typora-user-images\image-20200803194735371.png)



## vue ajax

>  只要发请求,数据就定义在data里面,因为发完请求之后一定用来展示
>
> axios返回值是promise对象
>
> 跨域:只有客户端并且是ajax请求,才有跨域问题
>
> 改了webpack配置要重启webpack
>
> 正向代理是开发阶段
>
> 反向代理是上线阶段
>
> 要往子组件传递内容用插槽的 时候就用双标签
>
> 引用数据类型转布尔值一定是true

![image-20200804091409968](C:\Users\zenghao\AppData\Roaming\Typora\typora-user-images\image-20200804091409968.png)

![image-20200804091824869](C:\Users\zenghao\AppData\Roaming\Typora\typora-user-images\image-20200804091824869.png)

这两步看似前后顺序执行,其实运行很快,几乎同时执行

![image-20200804101833071](C:\Users\zenghao\AppData\Roaming\Typora\typora-user-images\image-20200804101833071.png)

这些都是普通http请求

**users page**

四个状态:

v-if 文字  

else-if  loading  

else-if  users  

else  error(失败状态)

![image-20200804111452443](C:\Users\zenghao\AppData\Roaming\Typora\typora-user-images\image-20200804111452443.png)

# vuex

![image-20200804141223390](C:\Users\zenghao\AppData\Roaming\Typora\typora-user-images\image-20200804141223390.png)

**集中管理所有组件状态,简单来说就是管理data数据的**

Vue Components :vue组件

集中管理在state里面,将状态数据渲染到Vue Components

Actions触发更新数据的行为,主要作用就是发送ajax的,会做一些异步操作

- 包含n个用来间接修改state的方法对象

Dispatch分发

Backend Api 后端Api

Mutations 真正更新数据的方法

- 包含n个用来直接修改state的方法对象

State 更新状态数据

Devtools 检测数据的变化,记录了数据变化的日志

Vue Components得到最新的数据显示



![image-20200804141715111](C:\Users\zenghao\AppData\Roaming\Typora\typora-user-images\image-20200804141715111.png)

也可以直接调用Mutations  更新

```vue
const mutations = {
    yyy (state, {data1}) { //元数据,要更新的数据
        // 更新state的某个属性
    }
}
```



> **&位运算符,进行二进制的位运算**
>
> store对象,上面有所有的状态数据和更新状态数据的方法
>
> store对象
>
>  \*  就有所有的状态数据和更新状态数据的方法
>
>  \*  store.state / store.getters
>
>  \*  store.dispatch('xxx')
>
> INCREMENT是Mutations 里面的方法,用来更新state里面的数据
>
> action函数的第二个参数就是dispatch传入的第二个参数
>
> mutation函数的第二个参数就是commit函数的第二个参数
>
> 在更新之前要做操作就通过action
>
> 如果action中只有调用commit方法,就应该直接更新
>
> 如果action中需要做一些其他事情(发送ajax请求),就应该间接更新

```vue
state,      // 等同于 `store.state`，若在模块中则为局部状态
rootState,  // 等同于 `store.state`，只存在于模块中
commit,     // 等同于 `store.commit`
dispatch,   // 等同于 `store.dispatch`
getters,    // 等同于 `store.getters`
rootGetters // 等同于 `store.getters`，只存在于模块中
```

![image-20200804164549501](C:\Users\zenghao\AppData\Roaming\Typora\typora-user-images\image-20200804164549501.png)

```vue
mapState(['xxx'])会将对象展开,作为属性添加到computed中
作用:将vuex中的state映射成组件的计算属性,最终使用起来简单点
```

![image-20200804165241070](C:\Users\zenghao\AppData\Roaming\Typora\typora-user-images\image-20200804165241070.png)

![image-20200804170114283](C:\Users\zenghao\AppData\Roaming\Typora\typora-user-images\image-20200804170114283.png)

 \* store对象

 \*  就有所有的状态数据和更新状态数据的方法

 \*  store.state 访问vuex状态数据

 \*  store.getters 访问vuex计算属性数据

 \*  store.dispatch('xxx') 触发action函数

 \*  store.commit('xxx') 触发mutation函数

你在组件中使用 `this.$store.dispatch('xxx')` 分发 action，或者使用 `mapActions` 辅助函数将组件的 methods 映射为 `store.dispatch` 调用（需要先在根节点注入 `store`）：

```js
import { mapActions } from 'vuex'

export default {
  // ...
  methods: {
    ...mapActions([
      'increment', // 将 `this.increment()` 映射为 `this.$store.dispatch('increment')`

      // `mapActions` 也支持载荷：
      'incrementBy' // 将 `this.incrementBy(amount)` 映射为 `this.$store.dispatch('incrementBy', amount)`
    ]),
    ...mapActions({
      add: 'increment' // 将 `this.add()` 映射为 `this.$store.dispatch('increment')`
    })
  }
}
```

**vuex优化**

main.js

```javascript
引入vue模块/App模块/./store

new Vue构造函数,

- 将App渲染到页面
  - 往Vue实例对象注入store
  - 挂载到app容器中
```

App.vue

```vue
<template>
	根标签
	页面显示count  oddOrEven
	下拉列表select标签,需要双向绑定
	+和-按钮绑定单机事件,值为"INCREMENT", "DECREMENT"两个方法,需要传入data数据里面定义的初始值
	increment if odd和increment async按钮绑定单机事件,值为"incrementIfOdd", "incrementAsync",传入data数据里面定义的初始值
</template>
<script>
	从vuex统一引入mapState, mapGetters, mapActions, mapMutations
    data数据里面定义数据初始化为1
    将vuex中的state映射成组件的计算属性，通过this直接使用'count'
    将vuex中的getters映射成组件的计算属性，通过this直接使用'oddOrEven'
    将vuex中的action映射成组件的方法，通过this直接使用"incrementIfOdd", "incrementAsync",
     将vuex中的mutition映射成组件的方法,通过this直接使用"INCREMENT", "DECREMENT"
     
</script>
```

index.js

```javascript
引入vue模块/vuex插件(先下载)/
定义state对象集中管理数据,初始值0,用来集中式管理多个组件共享的状态数据（普通data数据）
定义计算属性getters,
    定义oddOrEven方法,传入state,state里面的值判断是否被2整除或者位运算'xx&1',true是偶数,false是奇数

定义actions对象
	incrementIfOdd方法传入两个参数,第一个参数为commit方法和state方法,第二个参数为dispatch传入的第二个参数
	incrementAsync方法传入两个参数,第一个参数为commit,第二个为dispatch传入的第二个参数,一般定义为number
定义mutations对象
	INCREMENT方法传入两个参数,第一个为数据状态state,第二个为commit函数的第二个参数payload(也可以写number)
		stat里面的内容+=payload
	DECREMENT传入两个参数,第一个为数据状态state,第二个为commit函数的第二个参数payload(也可以写number)
		stat里面的内容-=payload
定义store对象,值为new Vuex.Store({}),里面有所有的状态数据和更新状态数据的方法,现在用到的是 state,actions,mutations,getters,
   把store暴露出去
```



> 组件化和模块化是可以共存的
>
> 只要有计算属性,一定有data里面的一个属性发生变化,触发计算属性的变化 
>
> 只要修改state,getters自然就变了

**user page 用vuex完成**

> vuex里面要管理的users,还要定义一个isLoading
>
> 切换loading的状态,时刻都要考虑这个考虑,但凡发请求都要考虑loading状态,也要交给vuex管理
>
> 在actions里面发请求,要想办法切换loading
>
> 请求成功和失败也要定义在vuex里面

引入mapState

在计算属性中

- 映射四个属性

actions里面

- 定义search方法

引入axios

mutations中

- REQUESTING方法,将state上面的isf改为false,isl改为true

## vue-router

路由就是点击组件,页面地址变了,但是没有更新

![image-20200805112228639](C:\Users\zenghao\AppData\Roaming\Typora\typora-user-images\image-20200805112228639.png)

> key是路径,value是组件
>
> 需要下载vue-rourer
>
> redirect 重定向

![image-20200805114811406](C:\Users\zenghao\AppData\Roaming\Typora\typora-user-images\image-20200805114811406.png)



\

??????????????????????????????????

![image-20200805125632370](C:\Users\zenghao\AppData\Roaming\Typora\typora-user-images\image-20200805125632370.png)

"isFirstView", "isLoading", "users", "error"

![image-20200805132534585](C:\Users\zenghao\AppData\Roaming\Typora\typora-user-images\image-20200805132534585.png)

## 前端路由

用来开发SPA应用

- 单页面应用
- 特点:
  - 点击路由链接不会刷新页面,不会发送请求
  - 更新浏览器地址,更新局部页面(组件)
- 路由,每一个路由就是一个访问地址,有一个回调函数来处理它
  - 一种简单的映射关系,key-value
  - key:路由路径 path
  - value 路由组件 component
- vue-router
  - 配置
    - 
  - 使用

> 一个地址对应一个相应的路由组件
>
> <router-view></router-view>根据地址变化显示相应的组件
>
> children是home的子路由
>
> **" "** 相当于根路由,里面写/就是补充父路由路径
>
> App里面<router-view>只能显示一级路由组件,一级路由组件里面的<router-view>才能显示二级路由组件
>
> props传参比较抽象,但是是最好用的
>
> 练完了可以把todo改造成vuex类型
>
> VueRouter是路由器,routes是路由,路由器是用来管理路由的
>
> find()找到就停了
>
> created用来发送请求,设置定时器等一次性任务,mounted用来绑定事件	

![image-20200805161721565](C:\Users\zenghao\AppData\Roaming\Typora\typora-user-images\image-20200805161721565.png)

不写/就会自动把父路由匹配上去

![image-20200805163419803](C:\Users\zenghao\AppData\Roaming\Typora\typora-user-images\image-20200805163419803.png)

查询字符串

![image-20200805164803879](C:\Users\zenghao\AppData\Roaming\Typora\typora-user-images\image-20200805164803879.png)

这样传参不容易出错

![image-20200805174825505](C:\Users\zenghao\AppData\Roaming\Typora\typora-user-images\image-20200805174825505.png)

```vue
<router-link></router-link> 用来取代 a 标签

​       特点：

​        1. 点击不会刷新页面，也不会发送请求

​        2. 只会更新浏览器地址 path



​       以下两个样式，当你选中router-link生效

​        exact-active-class 

​         默认值：router-link-exact-active 

​        active-class 

​         默认值：router-link-active



​      <router-view></router-view> 

​       根据 浏览器地址 path 的变化，加载相应的组件显示

​       注意：需要加载的组件要在router配置中写好
```

![image-20200805182314204](C:\Users\zenghao\AppData\Roaming\Typora\typora-user-images\image-20200805182314204.png)

只要是前面的路径开头的,后面任意地址都行,就可以加载detail组件

![image-20200805183216801](C:\Users\zenghao\AppData\Roaming\Typora\typora-user-images\image-20200805183216801.png)

一旦注入,在实例对象上就会多this.$route和this.$router

![image-20200805183441807](C:\Users\zenghao\AppData\Roaming\Typora\typora-user-images\image-20200805183441807.png)

这是params里面的东西

![image-20200805184427986](C:\Users\zenghao\AppData\Roaming\Typora\typora-user-images\image-20200805184427986.png)

newValue就是$route

![image-20200805184900233](C:\Users\zenghao\AppData\Roaming\Typora\typora-user-images\image-20200805184900233.png)

一旦更新detail属性,页面就会重新渲染成最新的内容

