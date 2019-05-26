<template>
    <div>
        <div class="banner">
            <img  @click="handleTrigger" class="banner-img" :src="bannerImg" />
            <div class="banner-info">
                <div class="banner-title">{{sightName}}</div>
                <div class="banner-number"> <span class="iconfont banner-icon">&#xe623;</span>{{galleryImg.length}}</div>
            </div>
        </div>
        <fade-animation>
            <common-gallery @close="handleTrigger" :imgs="galleryImg" v-show="showGallery"></common-gallery>
        </fade-animation>
    </div>
</template>

<script>
    import CommonGallery from 'common/gallery/Gallery';
    import FadeAnimation from 'common/fade/FadeAnimation'
    export default {
        name:"Banner",
        props:{
            galleryImg:Array,
            sightName:String,
            bannerImg:String
        },
        data(){
            return {
                showGallery:false
               
            }
        },
        methods:{
            handleTrigger(){
                this.showGallery=!this.showGallery;
            }
        },
        components:{CommonGallery,FadeAnimation}
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