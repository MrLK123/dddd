<template>
    <div>
        <div class="title">周末去哪浪</div>
        <ul>
            <li v-for="item of weekendList" :key="item.id" class="item border-bottom">
                <div class="item-img-wrapper">
                <img class="item-img" :src="item.imgUrl">
                </div>
                <div class="item-info">
                    <p class="item-title">{{item.title}}</p>
                    <p class="item-desc">{{item.desc}}</p>
                </div>
            </li>
        </ul>
        
    </div>
</template>

<script>
    export default {
        name:"Weekend",
        props:{
            weekendList:Array
        },
        data(){
            return {
                page:5
            }
        }
    }
</script>

<style lang="stylus" scoped>
@import '~styles/mixins.styl'
  .title
    text-indent:.2rem
    line-height:.8rem
    background :#eee
.item-img-wrapper
    overflow: hidden
    height:0
    padding-bottom:37.09%
    .item-img
        width:100%
.item-info
    padding:.2rem
    min-width:0
    flex:1
    .item-title
        ellipsis()
        line-height:.54rem
        font-size:.32rem
    .item-desc
        ellipsis()
        line-height:.4rem
        color:#ccc
</style>