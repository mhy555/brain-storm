## vue2.0升级笔记

el的挂载元素不再支持html、body，需改成css选择器元素。如：
```javascript
new Vue({
  el: '#app',
  template: '<App/>',
  components: { App }
})
```