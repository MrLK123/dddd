<template>
    <div>
        <div class="title">今日推荐</div>
        <ul>
            <router-link tag="li" :to="'/detail/'+item.id" v-for="item of filterItem" :key="item.id" class="item border-bottom">
                <img class="item-img" :src="item.imgUrl">
                <div class="item-info">
                    <p class="item-title">{{item.title}}</p>
                    <p class="item-desc">{{item.desc}}</p>
                    <button class="item-button">查看详情</button>
                </div>
            </router-link>
        </ul>
        <div v-if="page==5" class="item-more" @click="allItem">查看所有产品</div>
    </div>
</template>

<script>
    export default {
        name:"HomeRecommond",
        props:{
            recommondList:Array
        },
        data(){
            return {
                page:5
            }
        },
        methods:{
            allItem(){
               this.page=this.recommondList.length
            }
        },
        computed:{
            filterItem(){
             return this.recommondList.filter((item,index)=>{
                    if(index < this.page)
                    return item
                    })
            }
        }
    }
</script>

<style lang="stylus" scoped>
@import '~styles/mixins.styl'
  .title
    text-indent:.2rem
    margin-top:.2rem
    line-height:.8rem
    background :#eee
  .item
    display:flex
    .item-img
        width:1.9rem
        height:1.9rem
        padding:.2rem
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
        .item-button
            margin-top:.46rem
            padding:.2rem
            background #ff9300
            padding:0 .1rem
            border-redius:.06rem
.item-more
    color:#09f
    text-align:center
    line-height:.8rem
</style>