<template>
  <div id="app">
    <Shell />
  </div>
</template>

<script>
import Shell from './components/Shell.vue'

export default {
  name: 'app',
  components: {
    Shell
  },
}
</script>

<style lang="scss">
@import './assets/styles/style.scss';
 
body {
  margin: 0;
  padding: 0;
  background-color: #DBD5CA;
  scroll-behavior: smooth;

}
#app {
  // mainFont
  font-family: $mainFont;
  letter-spacing: 1px;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  /*text-align: center;
  color: #2c3e50; 
  margin-top: 60px;  */

  ul {
    padding: 0;

    li{
      list-style-type: none;
    }
  }
}
</style>
