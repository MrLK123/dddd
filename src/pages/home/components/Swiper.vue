<template>
  <div class="wrapper">
    <swiper :options="swiperOption">
      <swiper-slide v-for="item of swiperList" :key="item.id">
        <img 
          class="swiper-img"
          :src="item.imgUrl"
        >
      </swiper-slide>
      <div class="swiper-pagination" slot="pagination"></div>
    </swiper>
  </div>
</template>
<script>
export default {
  name: "HeaderSwiper",
  props:{
    swiperList:Array
  },
  data() {
    return {
      swiperOption: {
          pagination:'.swiper-pagination',
          loop:true,
          autoplay:3000
      }
    };
  }
};
</script>

       
<style lang="stylus" scoped>
  .wrapper >>>.swiper-pagination-bullets
     bottom:2.3rem
    .wrapper >>>.swiper-pagination-bullet
     background :#fff
  .wrapper
      width:100%
      overflow:hidden
      height:0
      padding-bottom:40%
      background :#ccc
   .swiper-img
       width:100%
</style>