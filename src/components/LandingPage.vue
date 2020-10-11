<template>
  <div class="wrapper">
    <div class="landingFirstPart">
     <div class="textContainer">
        <img class="logo" src="https://www.globalemergencypreparedness.org/wp-content/uploads/2020/04/logo.png" />
        <div style="height:20px"></div>
        <div class="headline">
            <div class="headlineSecondText">the future of</div> <div class="headlineThirdText">Emergency</div>
        </div>
     </div>
    </div>
    <span class="headlineFirstText">innovating</span>
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
    let textContainer = document.querySelector('.textContainer').getBoundingClientRect();
    console.log('textContainer',textContainer)
    setTimeout(()=>{
    let textEndingPosition = document.querySelector('.headline').getBoundingClientRect();
    const textAnimation = anime.timeline({ 
      easing: 'easeInOutQuad'
    });
    textAnimation
    .add({
      targets: '.logo',
      scale: [0, 1],
      duration: 300
    }).  
    add({
      targets: '.headlineFirstText',
      keyframes: [
          {opacity:1,top: textEndingPosition.top-25,left: textEndingPosition.left+10}             
      ],
       duration: 1500,
       loop: false
    }).add({
      targets: '.headlineSecondText',
      opacity: [0, 1],
      duration: 300
    }).add({
      targets: '.headlineThirdText',
      opacity: [0, 1],
      duration: 300
    })
    },10)
   

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
    box-sizing: border-box;
    padding-left:2rem;
  }
  .logo{
    width:102%;
  }
  .headline{
    font-size:3rem;
    text-transform:uppercase;
    padding-top:25px; 
  }
  .headlineFirstText{
    display:inline-block;
    position:absolute;
    opacity:0;
    right:0;
    top:50%;
    transform:translateY(-50%);
    text-transform:uppercase;
    font-size:3rem;
    padding-top:40px; 
  }
  .headline>div:nth-child(1){
    padding:1.2rem;
    font-size:1.9rem;
  }
  .headlineThirdText{
    color:#ff0000;
  }
  .landingFirstPart{
    flex:1;
    height:100%;
    text-align:center;
    position:relative;
  }
  .textContainer{
    position:absolute;
    left:50%;
    top:30%;
    transform:translate(-50%,-30%);
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