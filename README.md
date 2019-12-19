一套简单的Vue模板
# 特点
* 支持多页面，便于调试
* 一套灵活通用的webpack配置
* 支持webpack条件配置，灵活区分运行环境和生产环境

# 简介
现有的Vue模板大都是针对单页面应用的，单页面应用不利于调试特定组件。本模板支持生成多个页面。  
运行webpack时，webpack会自动扫描pages下的所有.vue文件，为每个.vue文件生成两个文件：
* HTML文件
* JS文件

其中，HTML文件的模板就是此目录下的index.html，JS文件的模板就是此目录下的main.js，本模板使用的模板为handlebars。HTML会生成到dist目录下，js会生成到gen目录下。这两个文件的名字与.vue文件同名但后缀名不同。  
gen目录中的文件内容如下：
```js
import ElementUI from "element-ui"
import Vue from "vue"
import VueRouter from "vue-router"
import component from "../pages/Index.vue"

Vue.use(ElementUI)
Vue.use(VueRouter)
new Vue({
  el: "#app",
  render(createElement) {
    return createElement(component)
  }
})
```
生成的HTML文件内容如下：
```html
<html>
  <head>
    <title>Megvii ANN&Cluster Laboratory</title>
    <meta charset="UTF-8" />
    <link rel="icon" href="favicon.ico" type="image/x-icon" />
    <link rel="shortcut icon" href="favicon.ico" type="image/x-icon" />
  </head>

  <body>
    <div id="app"></div>
  </body>
  <link href="https://cdn.bootcss.com/font-awesome/4.7.0/css/font-awesome.min.css" rel="stylesheet" />
  <script src="Index.js"></script>
</html>
```

# 目录结构
文件夹
* components：组件目录
* pages：页面目录
* dist：webpack生成的目录
* gen：存放此模板生成的代码
* lib：存放js库
* public：存放无需打包的公共资源

文件
* common.less：公共的样式配置
* index.html：HTML模板
* main.js:JS模板
