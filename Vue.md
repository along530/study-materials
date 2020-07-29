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
  - 隐含属性对戏:$event

事件修饰符

- ```javascript
  .prevent:阻止事件的默认行为 event.preventDefault()
  .stop:停止事件冒泡 event.stoppropagation()
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

ref 用来获取DOM元素



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

transitiong组件：对显示/隐藏的元素，添加过渡transition/动画animation效果，animation可以指定中间过渡的时间，效果，精细的控制运动轨迹

taansition原生并没有这个标签，是Vue产生的

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

-  transition组件：

  ​     在操作显示/隐藏的元素，添加一个过渡transition/动画animation效果

  

  ​     显示 -> 隐藏 leave

  ​      开始阶段：v-leave

  ​      过渡阶段: v-leave-active

  ​      结束阶段: v-leave-to

  

  ​     隐藏 -> 显示 enter

  ​      开始阶段：v-enter

  ​      过渡阶段: v-enter-active

  ​      结束阶段: v-enter-to

## 过滤器

理解过滤器

 功能: 对要显示的数据进行特定格式化后再显示

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
date要处理的数据
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

自定义局部指令热点:只能当前实例对象使用

定义全局指令通过Vue.derective()

**常用内置指令**

   v-if : 如果为true, 当前标签才会输出到页面

   v-else: 如果为false, 当前标签才会输出到页面

   v-show : 通过控制display样式来控制显示/隐藏

   v-for : 遍历数组/对象

   v-on : 绑定事件监听, 一般简写为@

​    @click.once="handleClick"

   v-bind : 强制绑定解析表达式, 可以省略v-bind

​    简写 :

   v-model : 双向数据绑定

   v-text : 更新元素的 textContent(相当于innerText)

   v-html : 更新元素的 innerHTML

   v-once : 元素只会渲染一次，后续渲染无效（性能优化）

   v-cloak : 防止闪现表达式, 与css配合: [v-cloak] { display: none }

## 插件 plugin

Vue插件:扩展Vue的功能

- 扩展Vue全局功能,通过Vue直接使用
  - Vue.filter/Vue.directive
- 扩展Vue局部功能,通过实例对象使用

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

   1). 简单的说: key是虚拟DOM对象的标识, 在更新显示时key起着极其重要的作用

   2). 详细的说: 当列表数组中的数据发生变化生成新的虚拟DOM后, React进行新旧虚拟DOM的diff比较

​     a. key没有变

​       item数据没变, 直接使用原来的真实DOM

​       item数据变了, 对原来的真实DOM进行数据更新

​     b. key变了

​       销毁原来的真实DOM, 根据item数据创建新的真实DOM显示(即使item数据没有变)

  \2. key为index的问题

   1). 添加/删除/排序 => 产生没有必要的真实DOM更新 ==> 界面效果没问题, 但效率低

   2). 如果item界面还有输入框 => 产生错误的真实DOM更新 ==> 界面有问题

   注意: 如果不存在添加/删除/排序操作, 用index没有问题

  \3. 解决:

   使用item数据的标识数据作为key, 比如id属性值



  \4. 结论：

   \1. 能用id作为key属性就用id

   \2. 什么时候能用index?

​    \- 没有id

​    \- 往数组最后面进行操作（添加/删除）



外部文件需要:

- Vue.sue(插件) 注册插件

- 引入插件

插件定义成函数,内部会去判断插件是函数类型还是对象类型

为什么用id作为唯一的key属性,这是服务器后端生成的,能用id尽量用id

- 虚拟DOM,diff算法

- 第一次渲染dom树
- 第二次渲染dom树,更改数据重新渲染,生成新的dom树,跟第一个dom树比较
- 把差异统一更新,重新渲染,性能更加高效
- 相同层级的子元素做了优化

index应用场景

- 遍历的元素往后面添加

**结论**:能用id尽量用id,没有id可能要自己创造id,一般情况下浏览器可能不会提示,但是自己要知道

## 组件

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
      - 从绝对路径调用resolve,public
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

