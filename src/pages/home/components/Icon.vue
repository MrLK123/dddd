    <template>
        <div class="icons">
            <swiper :options="swiperOption">
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
            props:{
                iconList:Array
            },
            data(){
                return {
                    swiperOption:{
                        autoplay:false
                    }
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
        .icons
            margin-top:.2rem
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