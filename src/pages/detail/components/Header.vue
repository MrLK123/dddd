<template>
    <div>
        <router-link v-show="showAbs" tag="div" to='/'  class="abs-header"><div class="iconfont abs-header-back">&#xe658;</div></router-link>
       <div v-show="!showAbs" :style="fiexdStyle" class="fixed-header">  <router-link  to="/"><div class="iconfont fixed-header-back">&#xe658;</div></router-link>景点详情</div>
    </div>
</template>

<script>
    export default {
        name:"DetailHeader",
        data(){
            return{
                showAbs:true,
                fiexdStyle:{
                    opacity:0
                }
            }
        },
        methods:{
            handleScroll(){
                const top=document.documentElement.scrollTop;
               if(top<60){
                   this.showAbs=true
               }else{
                   let opacity=top/160>1?1:top/160;
                   this.fiexdStyle={opacity}
                   this.showAbs=false
               }
            }
        },
        activated(){
            window.addEventListener("scroll",this.handleScroll);
        }
    }
</script>

<style lang="stylus" scoped>
@import '~styles/varibles'
    .abs-header 
        position:absolute
        top:.2rem
        left:.2rem
        width:.8rem
        height: 0.8rem
        border-radius: 0.4rem
        line-height: .8rem
        text-align:center
        background:rgba(0,0,0,0.7)
        .abs-header-back
            color:#fff
            font-size:.6rem
    .fixed-header
        position:fixed
        top:0;
        left:0
        right:0
        line-height:$headerHeight
        height:$headerHeight
        background:$bgColor
        text-align:center
        color:#fff
        font-size: .34rem
        .fixed-header-back
            position:absolute
            left:0
            top:0
            font-size:.64rem
            width:.64rem
            text-align:center
            color:#fff
</style>