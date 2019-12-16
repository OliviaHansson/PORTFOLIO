<template>
  <section>
    <h1>RESUME.</h1>
  </section>
</template>
<script>
export default {
  name: 'Resume'
  
}
</script>
<style lang="scss" scoped>
@import '../assets/styles/style.scss';

section {
  @include container(calc(100% - 100px), 0, 50px);
  border: 1px solid black;
  height: 80vh;

  // padding-left: 150px;
}
</style>