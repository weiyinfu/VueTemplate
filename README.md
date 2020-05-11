一套简单的Vue模板
# 特点
* 支持多个页面，是否使用单页面用户自己决定，便于调试
* 集成了typescript
* 考虑到库的压缩，可以把vue、axios、elementUI等库放在外部加以引用，避免打包之后文件过大
* 支持webpack条件配置，使用条件语法可以灵活区分运行环境和生产环境，可读性好
* 比较完善的webpack配置

# 简介
现有的Vue模板大都是针对单页面应用的，单页面应用不利于调试特定组件。本模板支持生成多个页面。  
运行webpack时，webpack会自动扫描pages下的所有.vue文件，为每个.vue文件生成两个文件：
* HTML文件
* JS文件

其中，HTML文件的模板就是此目录下的index.html，JS文件的模板就是此目录下的main.js，本模板使用的模板为handlebars。HTML会生成到dist目录下，js会生成到gen目录下。这两个文件的名字与.vue文件同名但后缀名不同。  

# 目录结构
文件夹
* components：组件目录
* pages：页面目录
* dist：webpack生成的目录
* gen：存放根据模板生成的代码
* static：存放无需打包的公共资源
