<template>
    <div>
        <div class="title">周末去哪浪</div>
        <ul>
            <li v-for="item of recommondList" :key="item.id" class="item border-bottom">
                <img class="item-img" :src="item.imgUrl">
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
        name:"HomeRecommond",
        data(){
            return {
                page:5,
                recommondList:[
                    {
                        id:"0001",
                        title:"天下第一关（山海关）",
                        imgUrl:"http://img1.qunarzz.com/sight/source/1812/58/ebdb4ae5c789be.jpg_r_640x214_21321088.jpg",
                        desc:"浪漫秦皇岛，浪漫的乐岛海洋王国",

                    },
                    {
                        id:"0002",
                        title:"圣蓝海洋公园",
                        imgUrl:"http://img1.qunarzz.com/sight/source/1810/22/b036f54d85ea22.jpg_r_640x214_3e6eb1bb.jpg",
                        desc:"浪漫秦皇岛，圣蓝海洋公园",
                        
                    },
                    {
                        id:"0003",
                        title:"渔岛",
                        imgUrl:"http://img1.qunarzz.com/sight/source/1507/82/06e79c5f8d6e7.jpg_r_640x214_5e63707e.jpg",
                        desc:"浪漫秦皇岛，钓鱼岛是中国的",
                        
                    },
                    {
                        id:"0004",
                        title:"南戴河",
                        imgUrl:"http://img1.qunarzz.com/sight/source/1810/22/b036f54d85ea22.jpg_r_640x214_3e6eb1bb.jpg",
                        desc:"浪漫秦皇岛，浪漫南戴河",
                        
                    },
                    {
                        id:"0005",
                        title:"渔岛·菲奢尔海景温泉",
                        imgUrl:"http://img1.qunarzz.com/sight/source/1810/22/b036f54d85ea22.jpg_r_640x214_3e6eb1bb.jpg",
                        desc:"浪漫秦皇岛，浪漫渔岛·菲奢尔海景温泉",
                        
                    }
                ]
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