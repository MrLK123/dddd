<template>
    <div class="header">
        <router-link to="/"><div class="iconfont home-back">&#xe658;</div></router-link>
        城市选择
    </div>
</template>

<script>
    export default {
        name:"CityHeader"
    }
</script>

<style  lang='stylus' scoped>
@import '~styles/varibles'
  .header
     position: relative
     line-height:$headerHeight
     height:$headerHeight
     text-align:center
     background:$bgColor
     font-size:.34rem
     color:#fff
     .home-back
        position:absolute
        left:0
        top:0
        width:.64rem
        text-align:center
        font-size:0.6rem
        color:#fff
</style>