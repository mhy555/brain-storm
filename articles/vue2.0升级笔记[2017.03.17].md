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

- 迁移过程中，如果还需在1.0版本下开发，注意重新npm install 一下，以免node module 中引用的还是2.0的vue。
- $refs不是响应的，无法在computed中监听到变化并更新。
- 现在在**组件**上使用 `v-on` 只会监听自定义事件（组件用 `$emit` 触发的事件）。如果要监听根元素的原生事件，可以使用 `.native` 修饰符

