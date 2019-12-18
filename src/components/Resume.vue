<template>
  <article :class="{'active': visible}">
    <h1>RESUME.</h1>
  </article>
</template>
<script>
export default {
  name: 'Resume',
  props: {
    visible: {
      type: Boolean,
      default: false
    }
  }
}
</script>
<style lang="scss" scoped>
@import '../assets/styles/style.scss';

article {
  @include container(calc(100% - 100px), 0, 50px);
  border: 1px solid black;
  height: 80vh;

  // padding-left: 150px;
}
</style>