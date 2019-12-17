<template>
  <nav id="id">
    <p @click="toggleMenu()" :class="{ menuHeading: menuIsOpen}">menu</p>
    <ul>
      <li :class="{ listHeading: menuIsOpen}">about.</li>
      <li :class="{ listHeading: menuIsOpen}">work.</li>
      <li :class="{ listHeading: menuIsOpen}">resume.</li>
    </ul>
  </nav>
</template>
<script>
/* eslint-disable */

export default {
  name: 'MenuBar',
  props: ['activateLink'],
  data: function() {
    return {
      menuIsOpen: false
    }
  },
  mounted() {
    console.log('from menu component',this.activateLink)
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
  }
}
</style>