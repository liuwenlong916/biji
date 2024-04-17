# 搜索
1. 请求顺序不能保证响应顺序，防抖节流无法保证（间隔太长影响使用）
2. axios取消请求方式解决：cancelToken
3. 汉字输入完成请求：compositionstart 和 compositionend

# element组件重构
```javascript
// 适合已有项目改造，新项目直接使用重命名的组件
import Upload from '@/components/Upload.vue'
ElementUI.OriginalUpload=ElementUI.Upload.name = 'ElOriginalUpload'
Vue.component('ElUpload', Upload)
```
# element popover
1. 组件会创建一个自定义指令 v-popover，el-popover会把使用使用该指令的元素作为参考元素，触发元素
2. 一个popover只能绑定一个指令v-popover，否则只有最后一个绑定的元素会显示popover

# 自定义指令
```javascript
//v-myDirective:arg="value"
inserted(el, binding,vnode){
  console.log(el) // 原生js元素对象 <div>value</div>
  console.log(binding) // {arg:"arg"//可任意值, expression:"value",//变量名 value:"",//变量的值}
  console.log(vnode) // vue中的虚拟dom
}
```
虚拟dom中 context和this一样
