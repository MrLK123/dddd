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
import { mapState } from 'vuex';
export default {
    name:"Home",
    components:{HomeHeader,HomeSwiper,HomeIcon,HomeRecommond,HomeWeekend},
    data(){
      return {
        lastCity:"",
        swiperList:[],
        iconList:[],
        recommondList:[],
        weekendList:[]
      }
    },
    created(){
        this.lastCity=this.city;
       this.getHomeInfo();
    },
    computed:{
       ...mapState(['city'])  
    },
    methods:{
      getHomeInfo(){
         axios.get("/api/index.json?page="+this.city).then(this.getHomeInfoSucc);
      },
      getHomeInfoSucc(res){
        if(res.data.ret){
          const data=res.data.data
          this.swiperList=data.swiperList
          this.iconList=data.iconList
          this.recommondList=data.recommondList
          this.weekendList=data.weekendList
        }
      }
    },
    activated(){
      if(this.lastCity !== this.city){
        this.lastCity=this.city;
        this.getHomeInfo();
      }
    }
}
</script>

<style scoped>

</style>