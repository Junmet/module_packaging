# module_packaging

## Project setup
```
npm install
```

### Compiles and hot-reloads for development
```
npm run serve
```

### Compiles and minifies for production
```
npm run build
```

### Lints and fixes files
```
npm run lint
```

### Customize configuration
See [Configuration Reference](https://cli.vuejs.org/config/).


## 封装tabs
使用规范：
```
<tabs currentIndex="1" @changeIndex="changeIndexHandler">
    <tab label="tab1" index="1">
        <div>内容1</div>
    </tab>
    <tab label="tab2" index="2">
        <div>内容2</div>
    </tab>
    <tab label="tab3" index="3">
        <div>内容3</div>
    </tab>
</tabs>
```

渲染规范
```
<ul>
    <li>tab1</li>
    <li>tab2</li>
    <li>tab3</li>
</ul>
<div>
    <div>内容1</div>
    <div>内容2</div>
    <div>内容3</div>
</div>
```
template -> render进行渲染

组件说明：
> 当currentIndex的值等于tab的index值时就是被选中状态（高亮），label为tab栏的显示文本 ，@changeIndex为事件绑定