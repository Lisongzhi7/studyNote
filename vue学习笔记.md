# vue学习笔记









## git 学习笔记

克隆项目

```bash
 git clone https://github.com/Lisongzhi7/vue-demo.git
```

代码提交

```bash
 # 文件加入到版本管理
 git add .
 # 本地提交
 git commit -m "项目初始化"
 # 推送到远端
 git push
 
 
 git pull
 
 
```



## Html学习笔记

### 常用标签

```html
<html></html>
<body></body>
<h1>
    
</h1>
<h2>
    
</h2>
<ui>
<li></li></ui>
<p>
    
</p>
<span></span>
<div class="">
    
</div>
<br>
<table>
    
</table>
<img>

```



## vue学习笔记

* 全局安装vue

```bash
npm install vue-cli -g
```

* 安装vue-cli

```bash
cnpm install vue-cli -g
```

* 创建项目

```bash
vue init webpack
```

* 项目运行

```bash
npm run dev
```









## 备忘录

### markdown常见语法

`# 表示一级标题`

代码使用` ``` html表示`

引用使用`> 表示`

# 学习路线

* vue
* vue-cli
* vue-router
* git
* markdown
* css3
* html5
* webpack
* 

```javascript
let name = "zhanfsan";
let age = 12

let student = {
    name: "",
    age: "",
    sex: ""
}
let lisizhi = {
     name: "lisongzhi",
    age: "13",
    sex: "nan"，
    aa: 
}

let zhangsan = {
     name: "zhangsan",
    age: "131",
    sex: "3123"
}
let studes[lisizhi, zhangsan]

let s = [{},{}]

let article = [
    {
        title： "",
        time: "",
        author: "",
        desc: "",
        tags: [
            name: "",
            Color: "",
            num: 12
        ]
    },
         {
        title： "",
        time: "",
        author: "",
        desc: "",
        tags: [
            name: "",
            Color: "",
            num: 12
        ]
    }
]




let tag = [
    {
        name: "",
        num: ""
    }
]

```

## axios使用

> 这个是Vue项目中用于请求后端数据的一个框架。

### 使用方法

#### 第一步：安装

```bash
npm install axios -S
```

#### 第二步：新建index.js用于封装请求

在Vue项目的src下面新建api目录，在api目录里面新建index.js文件，文件内容如下：

```javascript
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

## 字体的引用

### 引用方法

### 第一步：

在Vue项目的static中建立一个文件夹font，用于存储自带字体以外的字体

### 例如：

Alibaba-PuHuiTi-Bold.otf

Alibaba-PuHuiTi-Heavy.otf

Alibaba-PuHuiTi-Light.otf

Alibaba-PuHuiTi-Medium.otf

Alibaba-PuHuiTi-Regular.otf

### 第二步：

在JaveScript中引入字体

``` javascript
@font-face {
    font-family:'Alibaba-PuHuiTi-Medium';
    src: url('/static/font/Alibaba-PuHuiTi-Medium.otf') format('truetype');
}
@font-face {
    font-family:'Alibaba-PuHuiTi-Bold';
    src: url('/static/font/Alibaba-PuHuiTi-Bold.otf') format('truetype');
```

### 第三步：

在CSS当中应用font-family代码

``` css
font-family: "Alibaba-PuHuiTi-Medium";
font-family: 'Alibaba-PuHuiTi-Bold';
```

