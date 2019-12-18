<template>
  <main class="shell">
    <MenuBar :activateLink="isShown" />
    <!-- <iframe src="https://open.spotify.com/embed/playlist/37i9dQZF1DX0Yxoavh5qJV" width="300" height="300" frameborder="0" allowtransparency="true" allow="encrypted-media"></iframe>
    <p class="menu">menu</p> -->
    <Greeting />
    <About :visible="this.isShown === 'about'" id="about"  />
    <Work :visible="this.isShown === 'work'" id="work" />
    <Resume :visible="this.isShown === 'cv'" id="cv" />
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
      isShown: '',
      setActive: ''
    }
  },
  methods: {
    scroll(e) {
      // if(this.isShown !== '') {
      //   this.isShown = ''
      // }

      // const about = document.getElementById('about').getBoundingClientRect()
      // const work = document.getElementById('work').getBoundingClientRect()
      // const cv = document.getElementById('cv').getBoundingClientRect()

      let active = ''
      const sections = [
        'about',
        'work',
        'cv'
      ]

      sections.map(section => {
        const element = document.getElementById(section).getBoundingClientRect()
        if (element.top < window.innerHeight / 2) {
          active = section
          console.log(active)
        }
      })
      
      if (active !== this.isShown) {
        this.isShown = active
        // console.log(active !== '' ? active + ' is now active!' : 'no active section!')
      }

      // if (about.top < window.innerHeight && about.bottom > 0) {
      //   console.log('about is on screen')
        
        
      //   if (this.isShown !== 'about') {
      //     this.isShown = 'about'
      //     this.setActive = 'about'
      //     console.log('WE MAKE ABOUT THE ACTIVE ONE')
      //   }


      // } else {
      //   if (this.isShown !== '') {
      //     this.isShown = ''
      //     console.log('lets remove all active sections')
      //   }
      // }

      // } else if (this.isShown !== '') {
      //   console.log('buu')
      //   this.isShown = ''
      // }
    }
  },
  created() {
    window.addEventListener('scroll', this.scroll)
  },
  mounted() {
    this.scroll()
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