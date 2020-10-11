<template>
  <div class="wrapper">
    <div class="a">
      <div class="headlineText">
        <span>Project</span>
      </div>
    </div>
    <div class="b">
      <div class="imgContainer">
        <img src="../images/happy.svg" />
      </div>
    </div>
  </div>
</template>

<script>
import anime from 'animejs/lib/anime.es.js';

export default {
  name: 'Projects',
  components: {
  },
  mounted(){
    console.log('anime',anime);

    const textAnimation = anime.timeline({ 
      autoplay: true,
      delay: 500,
      easing: 'easeInOutQuad'
    });

    textAnimation.add({
      targets: '.headlineText span',

      
      opacity: [0, 1],
      duration: 500
    }).add({
      targets: '.headlineText div',
      translateY: ['-40px', 0],
      opacity: [0, 1],
      duration: 1000,
      delay:0
    })
  },
  destroyed(){
      console.log('ok')
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style>

  .wrapper{
    background:#212b32;
    height:100vh;
    display:flex;
    align-items:center;
    width:100%;
    color:white;
      padding-left:3rem;
  }
  .headlineText{
    font-size:2.8rem;
    font-weight:100;
  }
  .headlineText *{
      padding:.5rem 0;
      display:inline-block;
  }
  .a{
    flex:1;
  }
  .b{
    flex:1;
    display:flex;
    justify-content:center;
  }
  .imgContainer{
    width:100%;
  }
  .imgContainer img{
      width:100%;
    }
</style>
