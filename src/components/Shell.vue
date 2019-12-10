<template>
  <main class="shell">
    <MenuBar />
    <!-- <iframe src="https://open.spotify.com/embed/playlist/37i9dQZF1DX0Yxoavh5qJV" width="300" height="300" frameborder="0" allowtransparency="true" allow="encrypted-media"></iframe>
    <p class="menu">menu</p> -->
    <Greeting />
    <About />
    <Spin />
  </main>
</template>
<script>
import MenuBar from './MenuBar'
import Greeting from './Greeting'
import Spin from './Spin'
import About from './About'

export default {
  name: 'Shell',
  components: {
    MenuBar,
    Greeting,
    Spin,
    About
  }
}
</script>
<style lang="scss" scoped>
.shell {
  // background-color: #e4dcd1;
  padding: 20px;
  // background-color: #cdd2ce;
  iframe {
    // transform: rotate3d(-1, -1, -1, 0.2turn);
    // transform-origin: left bottom;
    // transform: perspective(800px);
    box-shadow: 11px -12px 5px -2px rgba(191,184,191,1);
    border-radius: 5px;
    animation: fadein 2s;

  }
  .menu {
    &:hover {
      transform: rotate(-90deg);
      transform-origin: left bottom;

    }
  }
}
</style>