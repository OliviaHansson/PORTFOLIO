<template>
  <nav id="id">
    <p @click="toggleMenu()" :class="{ menuHeading: menuIsOpen}">menu</p>
    <ul>
      <li>about</li>
      <li>work</li>
      <li>resume</li>
    </ul>
  </nav>
</template>
<script>
export default {
  name: 'MenuBar',
  data: function() {
    return {
      menuIsOpen: false
    }
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
    // transform: rotate(-90deg);
    transform-origin: left top;
    &:hover {
      cursor: grab;
    }
    text-shadow: 0px 4px 4px rgba(0, 0, 0, 0.15);
  }
  .menuHeading {
    transform: none;
    color: pink;
  }
  li {
    // display: none;
    margin: 100px 0;
    text-shadow: 0px 4px 4px rgba(0, 0, 0, 0.15);

    &:hover {
      color: red;
    }
  }
}
</style>