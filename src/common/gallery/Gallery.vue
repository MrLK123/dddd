<template>
    <div class="container" @click="handleClick">
        <div class="wrapper" >
            <swiper :options="swiperOptions"     >
                <swiper-slide v-for="(item,index) in imgs" :key="index">
                    <img 
                    class="swiper-img"
                    :src="item"
                    >
                </swiper-slide>            
                <div class="swiper-pagination" slot="pagination"></div>
            </swiper>
        </div>
    </div>
</template>

<script>
    export default {
        name:"Gallery",
        props:{
            imgs:{
                type:Array,
                default (){
                    return [];
                }
            }
        },
        methods:{
            handleClick(){
                this.$emit('close')
            }
        },
        data(){
            return {
                swiperOptions:{
                    autoplay:false,
                    pagination:".swiper-pagination",
                    paginationType:"fraction",
                    loop:true,
                    observeParents:true,
                    observer:true
                   
                }
            }
        }
    }
</script>

<style lang="stylus" scoped>
    .container >>> .swiper-container
        overflow:inherit
    .container
        position:fixed
        z-index:9
        top:0
        left:0
        right:0
        bottom:0
        background:#000
        display:flex
        flex-direction:column
        justify-content:center
        .wrapper
            background:#fff
            .swiper-img
                width:100%
        .swiper-pagination
            bottom:-.8rem
            color:#fff
           
          
           
</style>