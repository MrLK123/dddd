<template>
    <div>
      <home-header :city='city'></home-header>
      <home-swiper :swiperList='swiperList'></home-swiper>
      <home-icon :iconList="iconList"></home-icon>
      <home-recommond :recommondList="recommondList"></home-recommond>
      <home-weekend :weekendList="weekendList"></home-weekend>
    </div>
</template>

<script>
import HomeHeader from './components/Header';
import HomeSwiper from './components/Swiper';
import HomeIcon from './components/Icon';
import HomeRecommond from './components/Recommond';
import HomeWeekend from './components/Weekend';
import axios from 'axios'
export default {
    name:"Home",
    components:{HomeHeader,HomeSwiper,HomeIcon,HomeRecommond,HomeWeekend},
    data(){
      return {
        city:'',
        swiperList:[],
        iconList:[],
        recommondList:[],
        weekendList:[]
      }
    },
    created(){
      axios.get("/api/index.json").then(this.getHomeInfo);
    },
    methods:{
      getHomeInfo(res){
        if(res.data.ret){
          const data=res.data.data
          this.city=data.city
          this.swiperList=data.swiperList
          this.iconList=data.iconList
          this.recommondList=data.recommondList
          this.weekendList=data.weekendList
        }
      }
    }
}
</script>

<style scoped>

</style>