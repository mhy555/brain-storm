## vue2.0升级笔记

- el的挂载元素不再支持html、body，需改成css选择器元素。如：
```javascript
new Vue({
  	el: '#app',
  	template: '<App/>',
  	components: { App }
})
```

- import vue 的时候，vue会import进vue.common.js，需在webpack中配置alia，将vue绑定到vue.js上。
```javascript
resolve: {
	alias: {
		'vue': 'vue/dist/vue.js'
	}
},
```
Vue 最早会打包生成三个文件，一个是 runtime only 的文件 vue.common.js，一个是 compiler only 的文件 compiler.js，一个是 runtime + compiler 的文件 vue.js。(ref: http://jiongks.name/blog/code-review-for-vue-next/)
