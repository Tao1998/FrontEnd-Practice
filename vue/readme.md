## VUE

### vue 生命周期

- beforeCreate 创建实例之间，只有简单实例，没有data\methods

- created 加载数据，在dom前

- beforeMount 创建虚拟dom

- mounted 挂载真实dom

### v-model

本质是一个语法糖

```html
<input v-model="message" placeholder="edit me"></input>
```

等价于

```html
<input v-bind:value="message" v-on:input="message=$event.target.value"></input>
```

### Virtual DOM

在视图渲染之前，把写好的template模板先编译成VNode并缓存下来，等到数据发生变化需要重新渲染时，对比VNode，根据有差异的VNode创建真实DOM节点再插入到视图中，最终完成一次视图更新

### Diff 算法

对比新旧虚拟DOM，找出更改的虚拟节点，更新对应的真实节点，而不更新其他数据没变的节点

性能对比：

- 使用虚拟DOM算法的损耗计算： 总损耗 = 虚拟DOM增删改+（与Diff算法效率有关）真实DOM差异增删改+（较少的节点）排版与重绘
- 直接操作真实DOM的损耗计算： 总损耗 = 真实DOM完全增删改+（可能较多的节点）排版与重绘

### 渲染

用户写的模板 模板编译 render函数 VNode patch 视图

### vue-router

**hash**

通过url后面的hash实现路由，hash

**history**

通过`window.history`的两个API `pushState`,`replaceState`
