<template>
  <div class="header">
    <div class="header-left">
        <div class="iconfont back-icon">&#xe658;</div>
    </div>
    <div class="header-input"><span class="iconfont">&#xe63c;</span>输入城市/景点/游玩主题</div>
    <router-link to="/city"><div class="header-right">{{this.doCity}}<span class="iconfont arrow-icon">&#xe65c;</span> </div></router-link>
  </div>
</template>

<script>
import { mapState,mapGetters } from 'vuex'
export default {
  name: "HomeHeader",
  computed:{
    ...mapState(['city']),
    ...mapGetters(['doCity'])
  }
};
</script>

<style lang="stylus" scoped>
@import '~styles/varibles.styl'
.header {
  display: flex;
  color: #fff;
  line-height:$headerHeight
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
  min-width: 1.06rem;
  padding:0 .14rem
  float: right;
  text-align :center
  color:#fff
</style>