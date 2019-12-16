<template>
  <section>
    <h1>Work.</h1>
    <div class="scrollContainer">
      <div class="card">

      </div>
      <div class="card">

      </div>
      <div class="card">

      </div>
      <div class="card">

      </div>
    </div>

  </section>
</template>
<script>
export default {
  name: 'Work'
  
}
</script>
<style lang="scss" scoped>
@import '../assets/styles/style.scss';

section {
  @include container(calc(100% - 100px), 0, 50px);
  height: 100vh;
  border: 1px solid black;
  
  // padding-left: 150px;

  .scrollContainer {
    overflow-x: scroll;
    overflow-y: hidden;
    white-space: nowrap;

    // for ios devices
    // https://codeburst.io/how-to-create-horizontal-scrolling-containers-d8069651e9c6
    -webkit-overflow-scrolling: touch;

    .card {
      display: inline-block;
      border: 1px solid red;
      height: 300px;
      width: 80%;
    }
    
    // /* Hide scrollbar for IE and Edge */
    -ms-overflow-style: none;

    &::-webkit-scrollbar {
      display: none;
    }
    
  }
// .scrollContainer::-webkit-scrollbar {
//     display: none;
// }

// /* Hide scrollbar for IE and Edge */
// .scrollContainer {
//     -ms-overflow-style: none;
// }
}
</style>