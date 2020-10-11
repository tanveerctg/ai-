<template>
  <swiper class="swiper" :options="swiperOption">
    <swiper-slide>
     <LandingPage />
    </swiper-slide>

    <swiper-slide>
     <Contact/>
    </swiper-slide>

    <swiper-slide>
     <Projects/>
    </swiper-slide>

    <div class="swiper-pagination" slot="pagination"></div>
    <!-- <div class="swiper-button-prev" slot="button-prev"></div>
    <div class="swiper-button-next" slot="button-next"></div>
    -->
  </swiper>
</template>

<script>
  import { Swiper, SwiperSlide } from 'vue-awesome-swiper'
  import LandingPage from  '../components/LandingPage'
  import Contact from  '../components/Contact'
  import Projects from  '../components/Projects'
  import "swiper/css/swiper.css";

  export default {
    name: 'Home',
    title: 'Autoplay',
    components: {
      Swiper,
      SwiperSlide,
      LandingPage,
      Contact,
      Projects
    },
    data() {
      return {
        swiperOption: {
          spaceBetween: 30,
          centeredSlides: true,
          autoplay: {
            delay: 15000,
            disableOnInteraction: false
          },
          pagination: {
            el: '.swiper-pagination',
            clickable: true
          },
          navigation: {
            nextEl: '.swiper-button-next',
            prevEl: '.swiper-button-prev'
          }
        }
      }
    }
  }
</script>

<style>

  .swiper{
    height:100vh;
  }
  .swiper-slide{
    display:flex;
    justify-content:center;
    align-items:center;
  }
</style>
