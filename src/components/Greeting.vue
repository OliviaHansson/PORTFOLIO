<template>
  <section>
    <h1>"Hello<span>World"</span></h1>
  </section>
  
</template>
<script>
export default {
  name: 'Greeting'
}
</script>
<style lang="scss" scoped>
section {
  display: flex;
  width: 55%;
  margin: 0 auto;
  padding-top: 5%;

  h1 {
    font-size: 8em;
    text-shadow: 0px 4px 4px rgba(0, 0, 0, 0.75);

    // &span {
    //   display: block;
    //   padding-left: 200px;
    // }
  }
  h1 span {
    display: block;
    padding-left: 300px;


  }

  
}

</style>