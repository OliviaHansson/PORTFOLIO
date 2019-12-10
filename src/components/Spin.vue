<template>
  <article>
    <img src="../assets/Spin2.png" alt="">
  </article>
</template>
<script>
export default {
  
}
</script>
<style lang="scss" scoped>
article {
  position: relative;
  img {
    position: fixed;
    width: 200px;
    z-index: 1;
    right: 0;
    bottom: 0;
    animation: spin 20s linear infinite;

    &:hover {
      animation: none;
    }
  }

}
@keyframes spin {
  0% { transform: rotate(0deg); }
  100% { transform: rotate(360deg); }
}

</style>