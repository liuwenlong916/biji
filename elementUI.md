# element组件重构
```javascript
// 适合已有项目改造，新项目直接使用重命名的组件
import Upload from '@/components/Upload.vue'
ElementUI.OriginalUpload=ElementUI.Upload.name = 'ElOriginalUpload'
Vue.component('ElUpload', Upload)
```
# popover指令
1. 组件会创建一个自定义指令 v-popover，el-popover会把使用使用该指令的元素作为参考元素，触发元素
2. 一个el-popover元素只能绑定一个指令v-popover，否则只有最后一个绑定的元素会显示popover
   
# el-popper
默认append-to-body，未包含在<div id='app'></div>内，所以 deep(>>>) 深度设置样式无效。

el-select、el-date-picker 的选项底层逻辑和popper一样

## 解决方法
1. 设置append-to-body=false
2. 删除scoped

# el-select icon
嵌套在table内部时，会导致高度变小，icon未居中
解决方案：行加高，或 size='mini'


# el-table
选中项被删除，刷新列表后，需手动清空选中项 clearSelection()
