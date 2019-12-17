<template>
  <article>
    <h1>About.</h1>
    <div class="aboutMe fade-in-section is-visible">
      <p class="introducing">
        My name is<span> Olivia Hansson</span> I'm a <span>web developer</span> based in 
        Stcokholm, Sweden. sed do eiusmod tempor incididunt ut labore et dolore. 
        I’m a web developer ipsum dolor sit amet, consectetur adipiscing elit, 
        sed do eiusmod tempor incididunt ut labore et dolore
      </p>
    </div>
    <div class="myMusic">
      <iframe src="https://open.spotify.com/embed/playlist/37i9dQZF1DX0Yxoavh5qJV" 
      width="300" height="250" frameborder="0" allowtransparency="true" 
      allow="encrypted-media">
      </iframe>
    </div>
    
  </article>
</template>
<script>
/* eslint-disable */

export default {
  name: 'about',
  props: ['show'],
  created() {
    console.log('from about component', this.show)
  }
}
</script>
<style lang="scss" scoped>
@import '../assets/styles/style.scss';

article {
  @include container(calc(100% - 300px), 0, 0 150px);
  position: relative;
  text-shadow: 0px 4px 4px rgba(0, 0, 0, 0.25);

  border: 1px solid black;
  height: 120vh;
  // padding: 0 100px;

  // padding-left: 150px;
  display: block;
  .aboutMe {
    border: 3px dotted pink;
    width: 90%;
    // visibility: hidden;
    // animation-play-state: paused;
    animation: fadeInUp 5s ease-in-out;
    // margin: 100px 0;
    .introducing {
      font-size: 1.3em,

   
    }
    span:nth-child(1) {
      font-size: 3em;
      display: block;
      padding-left: 100px;
      color: white;
      margin: 20px 0;
    

    }
    span:nth-child(2) {
      font-size: 1em;
      color: pink;
      background-color: black;
      font-style: italic;
    }
  }
  .myMusic {

    background-color: red;
    position: absolute;
    right: -150px;
    bottom: 50px;
    // margin-right: -80px;
    width: 60%;
    // margin: 50px 0;
    // justify-content: flex-end;
    height: 300px;
    // // float: right;
    // display: flex;
    // justify-content: center;
    // align-items: center;
  }

}

.fade-in-section {
  opacity: 0;
  transform: translateY(20vh);
  visibility: hidden;
  transition: opacity 0.6s ease-out, transform 1.2s ease-out;
  will-change: opacity, visibility;
}
.fade-in-section.is-visible {
  opacity: 1;
  transform: none;
  visibility: visible;
}
@keyframes fadeInUp {
	0% {
		opacity: 0;
	transform: translateY(50px);
	}

	100% {
		opacity: 1;
		transform: translateY(0);
	}
}
// @-webkit-keyframes fadeInUp {
// 	0% {
// 		opacity: 0;
// 		-webkit-transform: translateY(20px);
// 	}	100% {
// 		opacity: 1;
// 		-webkit-transform: translateY(0);
// 	}
// }
</style>