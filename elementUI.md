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

# el-select icon
嵌套在table内部时，会导致高度变小，icon未居中
解决方案：行加高，或 size='mini'
