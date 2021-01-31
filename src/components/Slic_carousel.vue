<template>
  <VueSlickCarousel  v-bind="settings" >
    <div class="carousel_item"
      v-for="img in slicImg"
      :key="img.id"
    >
        <img :src="require('/src/assets/images/pompons/'+ img.name)" alt="img">
    </div>
  </VueSlickCarousel>
</template>

<script>
import VueSlickCarousel from 'vue-slick-carousel'
import 'vue-slick-carousel/dist/vue-slick-carousel.css'
// optional style for arrows & dots
import 'vue-slick-carousel/dist/vue-slick-carousel-theme.css'

export default {
name: "Slic_carousel",

  components: {
    VueSlickCarousel
  },

  data(){
    return {
      slicImg: [
        {name: "bk_black.png"},
        {name: "bl_blue.png"},
        {name: "cs_cerise.png"},
        {name: "gn_green.png"},
        {name: "iv_ivary.png"},
        {name: "lb_light_blue.png"},
        {name: "ld_lavender.png"},
        {name: "ll_lilac.png"},
        {name: "mt_mint.png"},
        {name: "og_orange.png"},
        {name: "ph_peach.png"},
        {name: "pk_pink.png"},
        {name: "pr_purple.png"},
        {name: "rd_red.png"},
        {name: "wh_white.png"},
        {name: "yw_yellow.png"}
      ],
      settings: {
        arrows: false,
        dots: false,
        autoplay: true,
        autoplaySpeed: 2000,
        slidesToShow: 1,


      }
    }
  }
}
</script>

<style lang="scss" scoped>
    .carousel_item {
      img {
        width: 30rem;
        margin: 0 auto;
      }
    }

    //for mobile only
    @media all and (max-width:599px){
      .carousel_item {
        img {
          width: 15rem;
          margin: 0 auto;
        }
      }
    }

</style>