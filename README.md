# vue-ueditor-wrap-demo

本项目用于介绍`vue-ueditor-wrap`的使用实例，目前`vue-ueditor-wrap`版本为`3.0.3`。
参考地址： https://haochuan9421.github.io/vue-ueditor-wrap/#/home

## 安装步骤

* 安装组件
  需要在项目目录下执行以下命令，-S 表示写入到package.json文件中。
```
# vue-ueditor-wrap v3 仅支持 Vue 3
npm i vue-ueditor-wrap@3.x -S
# or
yarn add vue-ueditor-wrap@3.x
```
* 下载 UEditor
  
  > 将解压的文件夹重命名为 UEditor 并移动到你项目的静态资源目录下，比如下面是一个由 Vue CLI（v3+）创建的项目，静态资源目录就是 public。

* 注册组件
```
// main.js
import { createApp } from 'vue';
import VueUeditorWrap from 'vue-ueditor-wrap';
import App from './App.vue';

createApp(App).use(VueUeditorWrap).mount('#app');
```
* v-model 绑定数据
```
<vue-ueditor-wrap v-model="msg" :config="editorConfig" editor-id="editor-demo-01"></vue-ueditor-wrap>
```

```
import { ref } from 'vue';

export default {
  setup() {
    const msg = ref('<h2>Hello World!</h2>');
    return {
      msg,
    };
  },
  created() {
    // 更多 UEditor 配置，参考 http://fex.baidu.com/ueditor/#start-config
    this.editorConfig = {
      UEDITOR_HOME_URL: '/UEditor/', // 访问 UEditor 静态资源的根路径，可参考常见问题1
      serverUrl: '//ueditor.szcloudplus.com/cos', // 服务端接口（这个地址是我为了方便各位体验文件上传功能搭建的临时接口，请勿在生产环境使用！！！）
    };
  },
};
```
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
