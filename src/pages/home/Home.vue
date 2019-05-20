<template>
    <div>
      <home-header></home-header>
      <home-swiper></home-swiper>
      <home-icon></home-icon>
      <home-recommond></home-recommond>
      <home-weekend></home-weekend>
    </div>
</template>

<script>
import HomeHeader from './components/Header';
import HomeSwiper from './components/Swiper';
import HomeIcon from './components/Icon';
import HomeRecommond from './components/Recommond';
import HomeWeekend from './components/Weekend';
export default {
    name:"Home",
    components:{HomeHeader,HomeSwiper,HomeIcon,HomeRecommond,HomeWeekend}
}
</script>

<style scoped>

</style>