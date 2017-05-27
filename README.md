前言
======================
  vue
##  项目描述

* 这是一个简单个人博客项目

##  项目运行（nodejs 6.0+）
---------------------------------------
## 克隆到本地

 *  git clone git@github.com:Chenchangsheng1990/Personal-Blog-vue.js.git

# 安装依赖

* npm install or cnpm install 

# 开启本地服务器localhost:8088
npm run dev

# 发布环境
* npm run build

* npm run build --report
##  路由
```
应用包括下面7个路由

/welcome 首页,个人信息简单介绍；
/music QQ音乐内地歌曲排行;
/movie 电影排行页面，调用豆瓣API，并且采用滚动加载；
/news 新浪新闻，调用新浪新闻API。
/story 鬼故事列表页面，调用API
/picture 
/me 个人简历页面，链接到giehub个人resume

##项目结构
.
├── build // vue-cli 自带的配置文件
│   ├── build.js
│   ├── check-versions.js
│   ├── dev-client.js
│   ├── dev-server.js
│   ├── utils.js
│   ├── webpack.base.conf.js
│   ├── webpack.dev.conf.js
│   └── webpack.prod.conf.js
├── config  // vue-cli 自带的配置文件
│   ├── dev.env.js
│   ├── index.js
│   └── prod.env.js
├── dist
│	├──static
│	│	├──	ccs
│	│	├──	img
│	│	├──	js
│	│	├──	favicon.ico
│	│	├──	iconfont.js
│	│	└──	public.css
│	│	
│	└──index.html
├── index.html
├── node-proxy  // node 转发API请求，解决跨域问题
│   └── index.js
├── src
│   ├── assets
│   │   ├── menus
│	│	│	└── user.jpg
│   │   ├── music
│	│	│	└── blur.jpg
│   │   └── welcome 
│	│		├──	imccs.jpg
│	│		└── welcome.jpg 
│   ├── components
│   │   ├── View
│	│	│	└── View.jpg
│   │   ├── Load.vue
│	│	├── Me.vue
│	│	├──	Menus.vue
│	│	├── Movie.vue
│	│	├── Music.vue
│	│	├── News.vue
│	│	├── Picture.vue
│	│	├── Story.vue
│   │   └── Welcome.vue
│	├── router.js // 路由
│	│	└──index.js
│	├──	App.vue
│   └── main.js // 入口文件
├── static
├── .babelrc
├──	.editorconfig
├──	.eslintignore
├──	.eslintrc.js
├──	.postcssrc.js
├──	index.html
├── package.json
└── README.md


## 参考文档
> - [vue官网](http://cn.vuejs.org/)
> - [vue-loader](https://router.vuejs.org/)# Personal-Blog-vue.js
