# dbvue

> A Vue.js project

## Build Setup

``` bash
# install dependencies
npm install

# serve with hot reload at localhost:8080
npm run dev

# build for production with minification
npm run build

# build for production and view the bundle analyzer report
npm run build --report
```

For detailed explanation on how things work, checkout the [guide](http://vuejs-templates.github.io/webpack/) and [docs for vue-loader](http://vuejs.github.io/vue-loader).


豆瓣电影vue项目文档

1. npm init vue webpack-simple <文件名>
2. npm install  //下载依赖项
3. css、img静态文件放在static文件夹中，注意静态文件的路径问题
4. 把index.html整个放到当前文件夹的index.html
5. 把这个index.html的body里面的东西全部放到App.vue的template里面
6. 规划组件，划分模块
7. 将app.vue划分模块，在components中新建模块   如bottom.vue  top.vue  
8. 每个模块代码  template  script  style
9. 暴露bottom模块  export default{
   name:bottom//给最外面的div加上class  footer
}
10 . 将模块引入到App.vue 
	
`

	<template>
	  <top></top>
	  <bottom></bottom>
	</template>
	<script>
	  import footer from “./components/footer”
	  components:{
	    Top,//解构赋值 top：top,
	    bottom
	  }
	</script>
	<style></style>

11 . 配置路由

	路由下面 index.js

	在app.vue里面击加上 `<router></router>`
	
	a标签改成 `<router-link to="/"><router-link>`，vue规范

	在定义路径规则的时候，如果你给它提供了一个name属性，则可以在后续使用这条路径规则的时候，直接引用。
	<router-link to="{name: 'user', params: {userId: 1}">Home</router-link>

12 . 数据请求  axois  插件vue-jsonp
 		
	npm install --save vue-jsonp（同时开启两个npm，cmder）
	查看文档npm docs vue-jsonp	
	使用查看文档

	通过vue-jsonp请求数据-什么时候请求？ 生命周期---created（发送请求）---mounted（渲染数据）
	created:function(){
		getDate();
	}


	`

	methods:{
		getDate:
	}

`	注意组件中的data用函数
	注意函数中的this的指向