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
  data() {
    return {
      swiperOption: {
          pagination:'.swiper-pagination',
          loop:true
      },
      swiperList:[
          {
              id:'0001',
              imgUrl:"https://img1.qunarzz.com/p/tts3/1710/d8/9e2349a941d6e702.jpg_r_640x420x90_2210a8d3.jpg"
          },
          {
              id:'0002',
              imgUrl:"https://img1.qunarzz.com/vs_ceph_vs_tts/5207cb6b-40b5-43c2-ae22-3d5ab44ef334.jpg_r_640x420x90_2c48378b.jpg"
          }
      ]
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