<template>
  <div class="wrapper">
    <div class="landingFirstPart">
     <div>
        <img class="logo" src="https://www.globalemergencypreparedness.org/wp-content/uploads/2020/04/logo.png" />
        <div style="height:20px"></div>
        <div class="headline">
            <div class="headlineSecondText">the future of</div> <div class="headlineThirdText">Emergency</div>
        </div>
     </div>
    </div>
    <div class="headlineFirstText">innovating</div>
    <div class="landingSecondPart">
      <div class="imgContainer">
        <img src="../images/world.gif" />
      </div>
    </div>
    

  </div>
</template>

<script>
import anime from 'animejs/lib/anime.es.js';

export default {
  name: 'LandingPage',
  components: {
  },
  mounted(){
    console.log('anime',anime);
    let textEndingPosition = document.querySelector('.headline').getBoundingClientRect();
    console.log('textEndingPosition',textEndingPosition)
    const textAnimation = anime.timeline({ 
      autoplay: true,
      delay: 500,
      easing: 'easeInOutQuad'
    });
    textAnimation
    .add({
      targets: '.logo',
      scale: [0, 1],
      duration: 200
    }).  
    add({
      targets: '.headlineFirstText',
      keyframes: [
          {opacity:1,top: textEndingPosition.top-25,left: textEndingPosition.left+10}             
      ],
       duration: 2000,
       loop: false
    }).add({
      targets: '.headlineSecondText',
      opacity: [0, 1],
      top:20,
      duration: 300
    }).add({
      targets: '.headlineThirdText',
      opacity: [0, 1],
      top:20,
      duration: 300
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
    justify-content:center;
    width:100%;
    color:white;
    position:relative;
    padding-left:3rem;
  }
  .headline{
    font-size:2.8rem;
    text-transform:uppercase;
    
  }
  .headlineFirstText{
    display:inline;
    position:absolute;
    opacity:0;
    right:0;
    top:50%;
    transform:translateY(-50%);
    font-size:2.8rem;
    text-transform:uppercase;
  }
  .headline>div:nth-child(1){
    padding:1.2rem;
    font-size:1.8rem;
  }
  .headlineThirdText{
    color:#ff0000;
  }
  .landingFirstPart{
    flex:1;
    height:100%;
    display:flex;
    align-items:center;
    justify-content:center;
    text-align:center;
    margin-bottom:100px;
  }
  .landingFirstPart img{
    margin:0 0 3rem 0;
  }
  .landingSecondPart{
    flex:1;
    background-image: url(../images/world.gif);
    height:100%;
    background-repeat: no-repeat;
    background-size: cover;
  }
  .imgContainer{
     width:1000px;
     height:100%;
  }
  .imgContainer img{
      width:100%;
      height:120%;
      background-size:cover;
    }
</style>
