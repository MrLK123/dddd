<template>
  <div class="header">
    <div class="header-left">
        <div class="iconfont back-icon">&#xe658;</div>
    </div>
    <div class="header-input"><span class="iconfont">&#xe63c;</span>输入城市/景点/游玩主题</div>
    <div class="header-right">城市<span class="iconfont arrow-icon">&#xe65c;</span> </div>
  </div>
</template>

<script>
export default {
  name: "HomeHeader"
};
</script>

<style lang="stylus" scoped>
@import '~styles/varibles.styl'
.header {
  display: flex;
  color: #fff;
  line-height: 0.86rem;
  background: $bgColor;
}

.header-left 
  width: 0.64rem;
  text-align :center
  float: left;
  .back-icon
     font-size:0.6rem


.header-input {
  flex: 1;
  padding-left:.2rem
  margin:.12rem 0 .12rem .2rem  
  line-height :.62rem
  height: 0.62rem
  background:#fff
  border-radius:.1rem
  color:#ccc
}

.header-right 
  width: 1.26rem;
  float: right;
  text-align :center

   

</style>