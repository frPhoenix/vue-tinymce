# vue-tinymce
在vue中使用tinymce编辑器


## 放置 tinymce文件
tinymce文件夹下是所有的tinymce编辑器文件，这些文件之间有引用关系，所以不能让webpack将他们编译了。

1. 在vue-cli2中，将tinymce文件夹放置在与`src`文件夹同级`static`文件夹下。在`main.js`文件中这样引用：
```
import '/static/tinymce/tinymce.min.js'
window.tinymce.baseURL = '/static/tinymce'
window.tinymce.suffix = '.min' // 解决报错 Uncaught SyntaxError: Unexpected token < 
```

2. 在vue-cli3中，将tinymce文件夹放置在`public`文件夹下。在`main.js`文件中这样引用：（我这里是这样配置，根据项目配置不同你那里可能需要做相应的改变）
```
import 'tinymce/tinymce.min.js'
window.tinymce.baseURL = '/tinymce'
window.tinymce.suffix = '.min'
```

## 使用`vue-tinymce.vue`组件
`vue-tinymce.vue`文件可任意放置，像使用普通组件一样使用即可