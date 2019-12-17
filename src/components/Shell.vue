<template>
  <main class="shell">
    <MenuBar :activateLink="setActive" />
    <!-- <iframe src="https://open.spotify.com/embed/playlist/37i9dQZF1DX0Yxoavh5qJV" width="300" height="300" frameborder="0" allowtransparency="true" allow="encrypted-media"></iframe>
    <p class="menu">menu</p> -->
    <Greeting />
    <About :show="isShown" id="about"  />
    <Work id="work" />
    <Resume id="cv" />
    <Spin />
  </main>
</template>
<script>
/* eslint-disable */

import MenuBar from './MenuBar'
import Greeting from './Greeting'
import Spin from './Spin'
import About from './About'
import Work from './Work'
import Resume from './Resume'

export default {
  name: 'Shell',
  components: {
    MenuBar,
    Greeting,
    Spin,
    About,
    Work,
    Resume
  },
  data: function() {
    return {
      isShown: [],
      setActive: []
    }
  },
  methods: {
    scroll(e) {
      const about = document.getElementById('about').getBoundingClientRect()
      const work = document.getElementById('work').getBoundingClientRect()

      // const aboutPosition = about.getBoundingClientRect()
      // const workPosition = work.getBoundingClientRect()
      // console.log(about)
      if ( about.top < window.innerHeight && about.bottom > 0 ) {
        this.isShown = 'about'
        this.setActive = 'about'
        console.log(this.isShown)
      }


      // const cont = document.getElementById('work')
      // const rect = cont.getBoundingClientRect()

      // const top = rect.top
      // console.log(top)
    }
  },
  created() {
    window.addEventListener('scroll', this.scroll)
  },
  destroyed() {
    window.removeEventListener('scroll', this.scroll)
  }

}
</script>
<style lang="scss" scoped>
.shell {
  // background-color: #e4dcd1;
  padding: 0 150px;
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