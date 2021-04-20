<template>
  <img alt="Vue logo" src="./assets/logo.png">
  <HelloWorld msg="Welcome to Your Vue.js App" />
  <vue-ueditor-wrap v-model="msg" :config="editorConfig" editor-id="editor-demo-01"></vue-ueditor-wrap>
</template>

<script>
import { ref } from 'vue';
import HelloWorld from './components/HelloWorld.vue'

export default {
  name: 'App',
  components: {
    HelloWorld
  },
  setup () {
    const msg = ref('<h2>Hello World!</h2>');
    return {
      msg,
    };
  },
  created () {
    // 更多 UEditor 配置，参考 http://fex.baidu.com/ueditor/#start-config
    this.editorConfig = {
      UEDITOR_HOME_URL: '/UEditor/', // 访问 UEditor 静态资源的根路径，可参考常见问题1
      serverUrl: '//ueditor.szcloudplus.com/cos', // 服务端接口（这个地址是我为了方便各位体验文件上传功能搭建的临时接口，请勿在生产环境使用！！！）
    };
  },
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
