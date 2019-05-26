<template>
    <div>
        <div class="banner">
            <img  @click="handleTrigger" class="banner-img" src="//img1.qunarzz.com/sight/p0/1902/37/3766884ef42171ffa3.img.jpg_600x330_71e0584e.jpg" />
            <div class="banner-info">
                <div class="banner-title">北京世界园艺博览会</div>
                <div class="banner-number"> <span class="iconfont banner-icon">&#xe623;</span>199</div>
            </div>
        </div>
        <common-gallery @close="handleTrigger" :imgs="imgs" v-show="showGallery"></common-gallery>
    </div>
</template>

<script>
    import CommonGallery from 'common/gallery/Gallery';
    export default {
        name:"Banner",
        data(){
            return {
                showGallery:false,
                imgs:["http://img1.qunarzz.com/sight/p0/201301/09/db8f3d2e54e643f793835fbb.jpg_350x240_1bc55c88.jpg ","http://img1.qunarzz.com/sight/p0/1902/84/84696f368bbec10da3.img.jpg_350x240_3a0fefe8.jpg"]
            }
        },
        methods:{
            handleTrigger(){
                this.showGallery=!this.showGallery;
            }
        },
        components:{CommonGallery}
    }
</script>

<style lang="stylus" scoped>
    .banner
        position: relative
        overflow: hidden
        height:0
        padding-bottom: 55%
        .banner-img
            width:100%

        .banner-info
            display:flex
            position:absolute
            height:.6rem
            left:0
            right:0
            bottom:0
            color:#fff
            background:linear-gradient(top,rgba(0,0,0,0),rgba(0,0,0,.8))
            .banner-title
                flex:1
                font-size: 0.32rem
                padding:0 .2rem
            .banner-number
                height:.32rem
                line-height: .32rem
                margin-left:.4rem
                border-radius:.2rem
                padding:0 .4rem
                font-size:.24rem
                background:rgba(0,0,0,0.6)
                .banner-icon
                    font-size:.24rem
</style>