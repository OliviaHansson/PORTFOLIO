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
@import '../assets/styles/style.scss';

section {
  @include container(calc(100% - 150px), 0, 0);
  border: 1px solid black;
  padding-left: 150px;
  // display: flex;
  // width: 55%;
  // margin: 0 auto;
  padding-top: 5%;

  h1 {
    font-size: 8em;
    text-shadow: 0px 4px 4px rgba(0, 0, 0, 0.75);
    letter-spacing: 5px;
    overflow: hidden;
    white-space: nowrap;
    // animation: typewriter 4s steps(30, end);
    display: inline-block;
    position: relative;
    // animation-duration: 10s;
    // animation-timing-function: steps(25, end);
    // animation-iteration-count: infinite;
    // text-align: center;

    // &span {
    //   display: block;
    //   padding-left: 200px;
    // }
    &::first-line {
      // color: pink;
      overflow: hidden;
    white-space: nowrap;
    // animation: typewriter 4s steps(30, end);
    display: inline-block;
    position: relative;

    }
        animation: typewriter 2s steps(30);

  }
  h1 span {
    display: block;
    padding-left: 300px;


  }

  
}
@keyframes typewriter {
  from { width: 0%; }
  to { width: 100%; }
  // 0%, 100% {
  //   width: 0;
  // }
  // 20%, 80% {
  //   width: 10.2em;
  // }
}

</style>