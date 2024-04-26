
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

# 动态img
src传入动态值时需要使用require，

# filter
filter 内部方法this不指向组件实例，需要用到外部属性，需传入
```javascript
filters:{
  filter:(val)=>{
    return val
  }
}

```
