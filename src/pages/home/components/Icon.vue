    <template>
        <div class="icons">
            <swiper>
                <swiper-slide v-for="(page,index) of pages" :key="index">
                    <div  class="icon" v-for="item of page" :key="item.id"> 
                        <div class="icon-img">
                            <img class="icon-img-content" :src="item.imgUrl" />
                        </div>
                        <p class="icon-desc">{{item.desc}}</p> 
                    </div> 
                </swiper-slide>
             </swiper>
        </div>
    </template>

    <script>
        export default {
            name:"HomeIcon",
            data(){
                return {
                 iconList:[
                     {
                     id:"0001",
                    imgUrl:"http://img1.qunarzz.com/piao/fusion/1803/95/f3dd6c383aeb3b02.png ",
                    desc:"热门景点"
                     },
                     {
                     id:"0002",
                    imgUrl:"http://img1.qunarzz.com/piao/fusion/1804/ff/fdf170ee89594b02.png",
                    desc:"自然风光"
                     },
                     {
                     id:"0003",
                    imgUrl:"http://img1.qunarzz.com/piao/fusion/1803/76/eb88861d78fb9902.png",
                    desc:"植物园"
                     },
                     {
                     id:"0004",
                    imgUrl:"http://img1.qunarzz.com/piao/fusion/1803/6c/9e54a8540fee0102.png",
                    desc:"故宫"
                     },
                     {
                     id:"0005",
                    imgUrl:"http://img1.qunarzz.com/piao/fusion/1803/80/416c6ab3368d1f02.png",
                    desc:"全部玩乐"
                     },
                     {
                     id:"0006",
                    imgUrl:"http://mp-piao-admincp.qunarzz.com/mp_piao_admin_mp_piao_admin/admin/20194/f04285731d7121da1b9028e2bf431695.png",
                    desc:"天梯山"
                     },
                     {
                     id:"0007",
                    imgUrl:"http://img1.qunarzz.com/piao/fusion/1803/bd/9f7b9b2b60c1502.png",
                    desc:"汉牡丹园"
                     },
                     {
                     id:"0008",
                    imgUrl:"http://img1.qunarzz.com/piao/fusion/1803/87/20656da0ac042002.png",
                    desc:"紫金山"
                     },
                     {
                     id:"0009",
                    imgUrl:"http://mp-piao-admincp.qunarzz.com/mp_piao_admin_mp_piao_admin/admin/20193/f85ce21492e4f7896498dc70dc43f8b3.png",
                    desc:"天河山"
                     },
                     {
                     id:"0010",
                    imgUrl:"http://mp-piao-admincp.qunarzz.com/mp_piao_admin_mp_piao_admin/admin/20194/b4511345827006994aa1980a3886f0ac.png",
                    desc:"北京世园"
                     }
                 ]  
                }
            },
            computed:{
                pages(){
                    let pages=[];
                    this.iconList.map((item,index)=>{
                        const page=Math.floor(index/8);
                        if(!pages[page]){
                            pages[page]=[];
                        }
                        pages[page].push(item);
                    })
                    return pages
                }

            }
        }
    </script>

    <style lang="stylus" scoped>
        @import '~styles/varibles.styl'
        @import '~styles/mixins.styl'
        .icons >>> .swiper-container 
            height:0
            padding-bottom:50%
        .icon 
            position:relative
            height:0
            width:25%
            float:left
            padding-bottom:25%
            .icon-img
                box-sizing:border-box
                padding:.1rem
                position: absolute
                left:0
                right:0
                top:0
                bottom:.44rem
                .icon-img-content
                    height:100%
                    display:block
                    margin:0 auto
            .icon-desc
                position:absolute
                text-align:center
                height:.44rem
                line-height:.44rem
                left:0
                right:0 
                bottom:0   
                color:$darkTextColor
                ellipsis()
    </style>