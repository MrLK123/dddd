<template>
    <div class="list" ref="wrapper">
       <div>
            <div class="area">
            <div class="title border-topbottom">当前城市</div>
            <div class="button-list">
                <div class="button-wrapper" ><div class="button">北京</div></div>

            </div>
        </div>
        <div class="area">
            <div class="title border-topbottom">热门城市</div>
            <div class="button-list">
                <div class="button-wrapper" v-for="item in hotCities" :key="item.id" ><div class="button">{{item.name}}</div></div>
            </div>
        </div>
        <div class="area" v-for="(item,key) in cities" :key="key" :ref="key">
            <div class="title border-topbottom">{{key}}</div>
            <div class="item-list" v-for="list in item" :key="list.id">
                <div class="item border-bottom" >{{list.name}}</div>
            </div>
        </div>
       </div>
    </div>
</template>

<script>
    import Bscroll from 'better-scroll'
    export default {
        name:"CityList",
        props:['cities','hotCities','letter'],
        mounted(){
            this.scroll=new Bscroll(this.$refs.wrapper);
        },
        watch:{
            letter(){
                if(this.letter){
                    const ele=this.$refs[this.letter][0];
                    this.scroll.scrollToElement(ele);
                }
            }
        }
    }
</script>

<style lang="stylus" scoped>
    .list
        overflow: hidden
        position:absolute
        top:1.78rem
        left:0
        right:0
        bottom:0 
        .border-topbottom
        &:before
            border-color:#ccc
        &:after
            border-color:#ccc
        .border-bottom
        &:before
            border-color:#ccc
        &:after
            border-color:#ccc
    .title
            line-height: .56rem
            font-siez:.26rem
            padding-left:.2rem
            background: #eeeeee
            color:#666
        .button-list
            overflow: hidden
            padding:.1rem .6rem .1rem .1rem
            .button-wrapper
                width:33.3%
                float: left 
                .button
                    margin:.1rem 
                    text-align:center
                    border:.02rem solid #cccccc
                    padding:.1rem 0
                    border-radius: .06rem
        .item-list
            .item
                line-height: 0.76rem
                padding-left: .2rem

</style>