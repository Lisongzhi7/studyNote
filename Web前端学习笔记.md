# Web前端学习笔记

## 1.vue学习笔记

### 1.1.Vue-cli项目创建

#### 第一步：在项目文件夹里面右键打开命令行窗口，输入创建Vue命令

```bash
vue init webpack test
```

> 注意：test是项目名称

### 1.2.Vue基础测试

#### 基本的标签

* v-mode

* v-for

* v-if

* v-show

* 动态class

* 生命周期的几个方法

* data是什么

* method

  



## 2.Html学习笔记

### 2.1.常用的标签

``` html
<ul>  <li>  <a>  <p>  <input>  <br>  <div>  <td>  <title>  <var>  <q>  <option>  <link>  <i> <font>
```

#### 2.1.2伪类选择器

``` html
:link-表示普通的链接（没访问过的链接）
例如：a:link{
      color:yellowgreen;
}
:visited-表示访问过的链接，浏览器是通过历史记录来判断一个链接是否访问过，由于涉及到用户的隐私问题，所以使用visited伪类只能设置字体的颜色
例如：a:visited{
      color:red;
}
:hover-伪类表示鼠标移入的状态
例如：a:hover{
      color:skyblue;
}
:active-表示的是超链接被点击的状态
例如：a:active{
      color:black;
}
```

### 2.2.HTML的语法规范

HTML中不区分大小写，一般我们使用小写
HTML中的注释不能嵌套
HTML标签必须结构完整，要么成对出现，要么自结束标签
HTML标签中的属性必须有值，且值必须加引号（双引号和单引号都可以）

### 2.3.常用快捷键

ctrl+d 复制行
ctrl+x 删除行
ctrl+/ 单行注释
ctrl+shift+/ 块注释
Ctrl+R 替换文本
Ctrl+F 查找文本
Ctrl+Shift+Space 自动补全代码
Shift+F6 重构-重命名
Ctrl+E 最近打开的文件
Ctrl+H 显示类结构图
Ctrl+Q 显示注释文档
Alt+F1 查找代码所在位置
Alt+1 快速打开或隐藏工程面板
Ctrl+Alt+ left/right 返回至上次浏览的位置
F2 或Shift+F2 高亮错误或警告快速定位

### 2.4.超链接

​	使用a标签来创建一个超链接，属性：hred：指向链接跳转的目标地址（相对路径/完整地址；都可以）
​	a标签中的target属性可以用来指定打开链接的位置
​		可选值：
​			_self,表示在当前窗口打开
​			_blank,在新的窗口中打开链接

### 2.5.路由

例如：<router-link to"/home"></router-link>,在目录下的src目录中建立一个router目录文件，创建一个index.js，在里面写                                          

``` html
  import Vue from 'vue'
               import Router from 'vue-router'     
importHomefrom'@/components/home/Home' 
              Vue.use(Router)                                     
  export default new Router({
  routes:[
    {
      path: '/',
      name: 'Home',
      component: Home
    },
    {
      path: '/home',
      name: 'Home',
      component: Home
    }]                                                                                                                                                                           }）
```



### 2.6.阿里云图标继承

把喜欢的文件下载解压，复制到src目录下的assets下的icon（注意：icon目录需自己创建），然后在main.js文件里面引入iconfont.css（即：import '@/assets/icon/iconfont.css'）,现在就可以引用阿里云图标了，但是必须添加iconfont类，例如：`<i class="iconfont icontuding(图钉)"></i>`

### 2.7.卡片的弹出，渐入效果

需下载npm install aos --save插件，可直接使用npm下载
效果例如：

``` html
<div data-aos="fade-up"(运动效果)
     data-aos-duration="3000"(运行时间)>
</div>
```



### 2.8.v-if语句

``` html
<div v-if="showNav" class="fd-head"></div>                    
<div v-if="!showNav" class="fd-head"></div>
```



``` javascript
 data() {
        return {
            showNav:true
        }
    },                                                                                   mounted() {
        window.addEventListener('scroll', this.handleScroll)
    },
    methods:{

        handleScroll () {
            let scrollTop = window.pageYOffset || document.documentElement.scrollTop || document.body.scrollTop;
            if(scrollTop > 100){
                this.showNav = true;
            }else if(scrollTop < 100) {
                this.showNav = false;
            }
        },
    },
```

### 2.9.v-for语句

``` html
<div v-for="(item,index) of list"  class="zuo">
                        <div class="zuo-head">
                            <div class="zuo-head-one" :class="omgColor(index)"><span>{{ item.name }}</span></div>
                        </div>
                        <div class="zuo-bottom">
                            <div class="zuo-bottom-desc">
                                <span>{{ item.desc }}</span>
                            </div>
                        </div>
                    </div>
```

``` javascript
data() {
        return {
            list: [{
                name: 'HTML',
                desc: '从学校开始就接触HTML，发现了它的乐趣，就很喜欢，可能自己没事的时候都会去瞧上一瞧，爱钻研，遇见不会的都会想去把它了解到，记在自己的笔记上'
            },{
                name: 'Vue',
                desc: '刚开始接触的时候可能会有很多的不了解，但是通过自己的学习，课余时间的自学，慢慢的发现其好处，这一框架我本人也是十分喜欢（仅代表我的个人观点）'
            },{
                name: '读书',
                desc: '书是良药，刘向说："书犹药也，善读可以医愚"书是益友，臧克家说："读过一本书，像交了一位益友；书是窗户，高尔基说："每一本书，都在我面前打开了一扇窗户'
            },],
        }
```





## 3.CSS学习笔记(w3school里有详细介绍)

### 3.1.样式设置

##### 3.1.1：CSS用于控制页面中的元素样式

##### 3.1.2：CSS优先级：!important/style/id/css从前到后

##### 3.1.3：阴影设置：box-shadow: 0 15px 35px rgba(50, 50, 93, .1), 0 5px 15px rgba(0, 0, 0, .07);

##### 3.1.4：圆角设置：border-radius:5px

##### 3.1.5：项目属性：order：stretch（默认值）：轴线占满整个交叉轴

##### 3.1.6：img标签：object-fit: cover用于控制图片的填充方式；属性值为：cover表示适配div图片大小

##### 3.1.7：writing-mode控制文字的排列方向；属性值为：vertical-rl垂直排列

##### 3.1.8：calc用于计算宽高；例如：height: calc(300px - 80px)



### 3.2.flex布局方式

#### 3.2.1：flex-direction（排列方向）

​	该属性用于项目的排列方向
​	属性值为：row表示从左到右排列
​	属性值为：row-reverse表示从右到左排列
​	属性值为：column表示从上到下排列
​	属性值为：column-reverse表示从下到上排列

#### 3.2.2：align-content（换行后的对齐方式）

​	该属性定义多根轴线的对齐方式
​	该属性值为：flex-start：与交叉轴的起点对齐
​	该属性值为：flex-end：与交叉轴的终点对齐
​	该属性值为：center：与交叉轴的中点对齐
​	该属性值为：space-between：与交叉轴两端对齐，轴线之间的间隔平均分布
​	该属性值为：space-around：每根轴线两侧的间隔都相等。所以，轴线之间的间隔比轴线与边框的间隔大一倍
​	该属性值为：stretch（默认值）：轴线占满整个交叉轴

#### 3.2.3：align-items（垂直对齐）

​	该属性用于垂直方向的对齐
​	属性值为：center表示垂直方向居中对齐
​	属性值为： flex-start表示垂直方向顶对齐
​	属性值为：flex-end表示垂直方向底部对齐

####  3.2.4：justify-content（水平对齐）

​	该属性用于水平方向的对齐
​	属性值为：center表示水平方向居中对齐
​	属性值为：flex-start表示水平方向左对齐
​	属性值为：flex-end表示水平方向右对齐
​	属性值为：space-between表示两端对齐

#### 3.2.5：flex-wrap（换行）

​	该属性用于换行
​	属性值为：nowrap表示默认，不换行
​	属性值为：wrap表示换行，第一行在上方
​	属性值为：wrap-nowrap表示换行，第一行在下方

### 3.3.行类元素与块级元素的区别

#### 3.3.1：行内元素

​	在众多行内元素中，最常使用的是span，另外行内元素还包括img、a、big、small、sub、sup、strong、u、button(属性默认为display：inline-block)
​	行内元素的特点：相邻的行内元素不换行，设置宽高无效，margin设置仅左右方向有效，上下无效，padding设置上右下左都有效。水平方向上padding-left，padding-right，margin-left，margin-right都有边距效果，但是垂直方向上padding-top、padding-bottom、margin-top、margin-bottom都不会产生边距效果。

#### 3.3.2:块级元素

​	块级元素最具有代表性的就是div，其余的有p、h1~h6、table、ul、li、ol、等等以及H5新增的属性header、section、aside、footer等等。
​	块级元素的特点，能够自动换行开启新的一行，能够设置宽高，margin和padding对上下左右四个方向设置均有效。
​		行内块级元素，元素排列在一行，不会自动换行，可设置宽度和高度以及外边距和内边距的所有样式。

#### 3.3.3:行类元素与块级元素之间的互转

​	display:inline;转换为行内元素
​	display:block;转换为块级元素
​	display:inline-block;转换为行内块级元素

### 3.4.路径

#### 3.4.1：相对路径

​	指相对于当前资源所在目录的位置
​	可以用../来返回一级目录，返回几级目录就写几个../

#### 3.4.2：绝对路径

​	绝对路径就是你的主页上的文件或目录在硬盘上真正的路径。





## 4.Git学习笔记

### 4.1.github项目创建

#### 第一步：GitHub创建项目

登录`GitHub`网页，点击+，选择`new repository`创建项目，输入项目名称，例如`vue-demo`，勾选`public`或者`private`，其中`public`表示该项目所有人都能看到，`private`表示该项目仅仅只有自己能看到，勾选`Add a README file`，最后点击` create repository`完成项目的创建。

#### 第二步：将GitHub上新创建的项目克隆到本地电脑上

在本地电脑需要放项目的文件夹里面右键菜单，选择git bash here，打开窗口，输入下面的克隆命令

```bash
git clone https://github.com/Lisongzhi7/vue-demo.git
```

> 注意：https://github.com/Lisongzhi7/vue-demo.git表示的是GitHub上的项目地址。



## 5.Axios学习笔记

### 第一步：安装

``` bash
npm install axios -S
```

### 第二步：新建index.js用于封装请求

在Vue项目的src下面新建api目录，在api目录里面新建index.js文件，文件内容如下：

``` javascript
import axios from 'axios'
let http = axios.create({
    baseURL: 'http://luokangyuan.com:8852/',
    withCredentials: false,
    headers: {
        'Content-Type': 'application/x-www-form-urlencoded;charset=utf-8'
    },
    transformRequest: [function (data) {
        let newData = '';
        for (let k in data) {
            if (data.hasOwnProperty(k) === true) {
                newData += encodeURIComponent(k) + '=' + encodeURIComponent(data[k]) + '&';
            }
        }
        return newData;
    }]
});

function apiAxios(method, url, params, response) {
    http({
        method: method,
        url: url,
        data: method === 'POST' || method === 'PUT' ? params : null,
        params: method === 'GET' || method === 'DELETE' ? params : null,
    }).then(function (res) {
        response(res);
    }).catch(function (err) {
        response(err);
    })
}

export default {
    get: function (url, params, response) {
        return apiAxios('GET', url, params, response)
    },
    post: function (url, params, response) {
        return apiAxios('POST', url, params, response)
    },
    put: function (url, params, response) {
        return apiAxios('PUT', url, params, response)
    },
    delete: function (url, params, response) {
        return apiAxios('DELETE', url, params, response)
    }
}
```

> 备注：baseURL是请求的服务器基本地址；

### 第三步：在main.js中引入axios

```bash
import Api from './api/index.js';
Vue.prototype.$api = Api;
```

### 第四步：在Vue组件中使用Axios请求数据

```javascript
this.$api.get(`/api/v1/article/${this.current}/${this.size}`,null, (res) => {
    if (res) {
        this.list = res.data.records;
        this.total = res.data.total;
    }
})
```

## 6.字体的引用学习笔记

### 引用方法

#### 第一步：在Vue项目的static中建立一个文件夹font，用于存储自带字体以外的字体

##### 例如字体：

``` javascript
Alibaba-PuHuiTi-Bold.otf

Alibaba-PuHuiTi-Heavy.otf

Alibaba-PuHuiTi-Light.otf

Alibaba-PuHuiTi-Medium.otf

Alibaba-PuHuiTi-Regular.otf
```

#### 第二步：在JaveScript中引入字体

``` javascript
@font-face {
    font-family:'Alibaba-PuHuiTi-Medium';
    src: url('/static/font/Alibaba-PuHuiTi-Medium.otf') format('truetype');
}
@font-face {
    font-family:'Alibaba-PuHuiTi-Bold';
    src: url('/static/font/Alibaba-PuHuiTi-Bold.otf') format('truetype');
```

#### 第三步：在CSS当中应用font-family代码

``` css
font-family: "Alibaba-PuHuiTi-Medium";
font-family: 'Alibaba-PuHuiTi-Bold';
```



## 7.Js回到顶部效果学习笔记

#### 实现原理

利用a标签回到顶部的链接，href=”javascript:;”是用来阻止a标签的默认行为。

##### 第一步：hetml代码

``` html
<a href="javascript:;" id="return_top" title="回到顶部">返回顶部</a>
```

##### 第二步：css代码（始终固定在屏幕右下角）

``` css
#return_top{
    width:40px; 
    height:40px;
    position:fixed; 
    right:25px; 
    bottom:10px; 
    display:none; 
    background-color: #FFFFFF;
}
```

##### 第三步：JavaScript代码

``` javas
<script type="text/javascript">
//      回到顶部效果
        window.onload = function(){
            var obtn = document.getElementById('return_top');  //获取回到顶部按钮的ID
            var clientHeight = document.documentElement.clientHeight;   //获取可视区域的高度
            var timer = null; //定义一个定时器
            var isTop = true; //定义一个布尔值，用于判断是否到达顶部
        
            window.onscroll = function(){         //滚动条滚动事件
        
                //获取滚动条的滚动高度
                var osTop = document.documentElement.scrollTop || document.body.scrollTop; 
        
                if(osTop >= clientHeight){  //如果滚动高度大于可视区域高度，则显示回到顶部按钮
                        obtn.style.display = 'block';
                }else{         //否则隐藏
                    obtn.style.display = 'none';
                }
        
                //主要用于判断当 点击回到顶部按钮后 滚动条在回滚过程中，若手动滚动滚动条，则清除定时器
                if(!isTop){     
                    clearInterval(timer);
                }
                isTop = false;
            }

            obtn.onclick = function(){    //回到顶部按钮点击事件
                //设置一个定时器
                timer = setInterval(function(){
                    //获取滚动条的滚动高度
                    var osTop = document.documentElement.scrollTop || document.body.scrollTop;
                    //用于设置速度差，产生缓动的效果
                    var speed = Math.floor(-osTop / 6);
                    document.documentElement.scrollTop = document.body.scrollTop = osTop + speed;
                    isTop =true;  //用于阻止滚动事件清除定时器
                    if(osTop == 0){
                        clearInterval(timer);
                    }
                },30);
            }
        }
    </script>
```



## 8.动态Class学习笔记

### 用途

可以用来改变已经固定的卡片颜色与时间轴的左右分布

#### 例如

``` html
//时间轴的左分布 <div class="zuo-name"（//盒子名字） :class（动态css）="{'fd-left-card'（命名的名字） : index % 2 != 0}"（index从0开始算，不等于0不变，等于0改变）>
```

### 动态class（卡片颜色的改变）

#### 例如

``` html
<div class="zuo-head">
      <div class="zuo-head-one" :class="omgColor(index)"><span>{{ item.name }}</span></div>
 </div>
```

``` javascript
methods:{
    omgColor(index){
            return `bagColor${index +1}`
}
```



翻转属性

``` css
transform:rotate(7deg(多少度数));
```



## 9.div浮动样式学习笔记

``` html
<div data-aos="fade-up"
     data-aos-duration="3000">
</div>//向上浮动
<div data-aos="fade-down"
     data-aos-easing="linear"
     data-aos-duration="1500">
</div>//向下浮动
<div data-aos="fade-right"
     data-aos-offset="300"
     data-aos-easing="ease-in-sine">
</div>//向右浮动
<div data-aos="fade-left"
     data-aos-anchor="#example-anchor"
     data-aos-offset="500"
     data-aos-duration="500">
</div>//向左浮动
//更多详情可查看：https://michalsnik.github.io/aos/
```

## 10.JavaScript学习笔记

### 常用内置指令

#### v:text：更新元素的 textContent

#### v-html：更新元素的 innerHTML

#### v-if ：如果为 true，当前标签才会输出到页面

#### v-else：如果为 false，当前标签才会输出到页面

#### v-show：通过控制display样式来控制显示/隐藏

#### v-for：遍历数组/对象

#### v-on：绑定监听事件，一般简写为@

#### v-bind：强制绑定解析表达式，可以省略v-bind

#### v-model：双向数据绑定

#### ref：为某个元素注册一个唯一表示，vue对象通过$els属性访问这个元素对象

#### v-cloak：使用它防止闪现表达式，与css配合：[v-cloak] {display：none}

#### 组件的含义：相当于是一个局部功能界面， 局部功能界面里面相关的所有资源都是组件的组成部分（即功能模块）











## 随手记录知识点

### markdown常见语法

`# 表示一级标题`

代码使用` ``` html表示`

引用使用`> 表示`

Vue打包 `npm run build`

![https://badgen.net/badge/14444/24444/blue](https://badgen.net/badge/14444/24444/blue)示例

https://badgen.net/badge/14444/24444/blue
14444换成左侧文字，24444换成右侧问题  blue是颜色
生成后 复制u'r'l到typora 
语法是  ![]()
![https://badgen.net/badge/14444/24444/blue](https://badgen.net/badge/14444/24444/blue)

[ ]：数组

{ }：对象

ipconfig：查找ip

### 定义变量

let

### 鼠标移动放大缩小效果

```
.kapian:hover{
    animation: kapian 3s infinite;
    cursor: pointer;
}
@keyframes kapian {  /*定义关键帧、scaleDrew是需要绑定到选择器的关键帧名称*/
    0%{
        transform: scale(1);  /*开始为原始大小*/
    }
    25%{
        transform: scale(1.1); /*放大1.1倍*/
    }
    50%{
        transform: scale(1);
    }
    75%{
        transform: scale(1.1);
    }
}
注意：kapian是命名的名称
```

