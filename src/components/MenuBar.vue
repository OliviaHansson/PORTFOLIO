<template>
  <nav id="id">
    <p @click="toggleMenu()" :class="{ menuHeading: menuIsOpen}">menu</p>
    <ul>
      <li id="aboutMenu" :class="{ listHeading: menuIsOpen}">about.</li>
      <li id="workMenu" :class="{ listHeading: menuIsOpen}">work.</li>
      <li id="cvMenu" :class="{ listHeading: menuIsOpen}">resume.</li>
    </ul>
  </nav>
</template>
<script>
/* eslint-disable */

export default {
  name: 'MenuBar',
  props: ['activateLink'],
  // props: {
  //   activateLink: {
  //     type: ,
  //     default: false
  //   }
  // },
  watch: { 
    activateLink: function(newVal, oldVal) { // watch it
      const about = document.getElementById('aboutMenu')
      const work = document.getElementById('workMenu')
      const cv = document.getElementById('cvMenu')

      about.classList.remove('test')
      work.classList.remove('test')
      cv.classList.remove('test')

      switch(newVal) {
        case 'about':
          about.classList.add('test')
          break
        case 'work':
          work.classList.add('test')
          break
        case 'cv':
          cv.classList.add('test')
          break
      }

      console.log('Prop changed: ', newVal, ' | was: ', oldVal)
    }
  },
  data: function() {
    return {
      menuIsOpen: false,
      isActive: this.activateLink
    }
  },
  created() {},
  mounted() {
    console.log('from menu component',this.isActive)
  },
  methods: {
    toggleMenu() {
      this.menuIsOpen = !this.menuIsOpen
    }
  }
}
</script>
<style lang="scss" scoped>
#id {
  // border: 1px solid black;
  height: 100vh;
  width: 10vw;
  position: fixed;
  z-index: 1;
  left: 0;
  top: 0;
  padding-left: 20px;
  padding-top: 100px;
  font-size: 1.2em;

  // p {
  //   font-size: 1.5em;
  //   margin: 120px 0;

  //   // &:first-child {
  //   //   margin-top: 0;
  //   // }
  // }
  p:first-child {
    // margin-top: 40px;
    font-size: 1.7em;
    // color: red;
    transition-property: transform;
    transform: rotate(-90deg);
    transform-origin: left top;
    text-shadow: 0px 4px 4px rgba(0, 0, 0, 0.15);

    &:hover {
      cursor: grab;    
      // transform: rotate(180);
    }
  }
  .menuHeading {
    color: pink;
    transform: rotate(-90deg);
    animation-name: test;
    animation-duration: 2s;
    animation-fill-mode: forwards;
    // animation-direction: reverse;
  }
  .listHeading {
    display: block;
    animation-name: test;
    animation-duration: 2s;
    transform-origin: left top;

  }
  .activeLink {
    border-bottom: 2px solid black;
  }
  @keyframes test {
    from {transform: rotate(-90deg); opacity: 0%;}
    to {transform: rotate(0deg); opacity: 100%;}
  }
  li {
    display: none;
    margin: 100px 0;
    text-shadow: 0px 4px 4px rgba(0, 0, 0, 0.15);

    &:hover {
      color: red;
    }
  a:link {
    text-decoration: none;
    color: black;
  }

  a:visited {
    text-decoration: none;
        color: black;

  }

  // a:hover {
  //   text-decoration: underline;
  //       color: black;

  // }

  a:active {
    text-decoration: underline;
    color: red;

  }
  }
}
.test {
  color: red;
}
</style>