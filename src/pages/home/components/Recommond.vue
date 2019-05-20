<template>
    <div>
        <div class="title">今日推荐</div>
        <ul>
            <li v-for="item of filterItem" :key="item.id" class="item border-bottom">
                <img class="item-img" :src="item.imgUrl">
                <div class="item-info">
                    <p class="item-title">{{item.title}}</p>
                    <p class="item-desc">{{item.desc}}</p>
                    <button class="item-button">查看详情</button>
                </div>
            </li>
        </ul>
        <div v-if="page==5" class="item-more" @click="allItem">查看所有产品</div>
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
                        imgUrl:"http://img1.qunarzz.com/sight/p27/201211/06/0932693bbebc5cf293835fbb.jpg_200x200_dc6b6d13.jpg",
                        desc:"浪漫秦皇岛，浪漫的乐岛海洋王国",

                    },
                    {
                        id:"0002",
                        title:"圣蓝海洋公园",
                        imgUrl:"http://img1.qunarzz.com/sight/p0/1505/bb/bb29191753da43e9.water.jpg_200x200_68979539.jpg",
                        desc:"浪漫秦皇岛，圣蓝海洋公园",
                        
                    },
                    {
                        id:"0003",
                        title:"渔岛",
                        imgUrl:"http://img1.qunarzz.com/sight/p0/1707/68/6857311108984e5ea3.img.jpg_200x200_86426f1e.jpg",
                        desc:"浪漫秦皇岛，钓鱼岛是中国的",
                        
                    },
                    {
                        id:"0004",
                        title:"南戴河",
                        imgUrl:"http://img1.qunarzz.com/wugc/p60/201307/17/1152bf39dd8d844793835fbb.jpg_200x200_633b19fd.jpg",
                        desc:"浪漫秦皇岛，浪漫南戴河",
                        
                    },
                    {
                        id:"0005",
                        title:"渔岛·菲奢尔海景温泉",
                        imgUrl:"http://img1.qunarzz.com/sight/p0/1612/52/52395bcad168baa3.water.jpg_200x200_da526cd0.jpg",
                        desc:"浪漫秦皇岛，浪漫渔岛·菲奢尔海景温泉",
                        
                    },
                    {
                        id:"0006",
                        title:"天下第一关（山海关）",
                        imgUrl:"http://img1.qunarzz.com/sight/p27/201211/06/0932693bbebc5cf293835fbb.jpg_200x200_dc6b6d13.jpg",
                        desc:"浪漫秦皇岛，浪漫的乐岛海洋王国",

                    },
                    {
                        id:"0007",
                        title:"圣蓝海洋公园",
                        imgUrl:"http://img1.qunarzz.com/sight/p0/1505/bb/bb29191753da43e9.water.jpg_200x200_68979539.jpg",
                        desc:"浪漫秦皇岛，圣蓝海洋公园",
                        
                    },
                    {
                        id:"0008",
                        title:"渔岛",
                        imgUrl:"http://img1.qunarzz.com/sight/p0/1707/68/6857311108984e5ea3.img.jpg_200x200_86426f1e.jpg",
                        desc:"浪漫秦皇岛，钓鱼岛是中国的",
                        
                    },
                    {
                        id:"0009",
                        title:"南戴河",
                        imgUrl:"http://img1.qunarzz.com/wugc/p60/201307/17/1152bf39dd8d844793835fbb.jpg_200x200_633b19fd.jpg",
                        desc:"浪漫秦皇岛，浪漫南戴河",
                        
                    },
                    {
                        id:"0010",
                        title:"渔岛·菲奢尔海景温泉",
                        imgUrl:"http://img1.qunarzz.com/sight/p0/1612/52/52395bcad168baa3.water.jpg_200x200_da526cd0.jpg",
                        desc:"浪漫秦皇岛，浪漫渔岛·菲奢尔海景温泉",
                        
                    },
                    {
                        id:"0011",
                        title:"天下第一关（山海关）",
                        imgUrl:"http://img1.qunarzz.com/sight/p27/201211/06/0932693bbebc5cf293835fbb.jpg_200x200_dc6b6d13.jpg",
                        desc:"浪漫秦皇岛，浪漫的乐岛海洋王国",

                    },
                    {
                        id:"0012",
                        title:"圣蓝海洋公园",
                        imgUrl:"http://img1.qunarzz.com/sight/p0/1505/bb/bb29191753da43e9.water.jpg_200x200_68979539.jpg",
                        desc:"浪漫秦皇岛，圣蓝海洋公园",
                        
                    },
                    {
                        id:"0013",
                        title:"渔岛",
                        imgUrl:"http://img1.qunarzz.com/sight/p0/1707/68/6857311108984e5ea3.img.jpg_200x200_86426f1e.jpg",
                        desc:"浪漫秦皇岛，钓鱼岛是中国的",
                        
                    },
                    {
                        id:"0014",
                        title:"南戴河",
                        imgUrl:"http://img1.qunarzz.com/wugc/p60/201307/17/1152bf39dd8d844793835fbb.jpg_200x200_633b19fd.jpg",
                        desc:"浪漫秦皇岛，浪漫南戴河",
                        
                    },
                    {
                        id:"0015",
                        title:"渔岛·菲奢尔海景温泉",
                        imgUrl:"http://img1.qunarzz.com/sight/p0/1612/52/52395bcad168baa3.water.jpg_200x200_da526cd0.jpg",
                        desc:"浪漫秦皇岛，浪漫渔岛·菲奢尔海景温泉",
                        
                    }
                ]
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