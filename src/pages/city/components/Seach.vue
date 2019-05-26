<template>
    <div>
        <div class="search">
            <input v-model="keyword" type="text" class="search-input" placeholder="输入城市名称或拼音"/>
        </div>
        <div class="search-content" ref="search" v-show="keyword">
            <ul>
                <li class="search-item border-bottom" @click="handleCityClick(item)" v-for="item in list" :key="item.name">{{item}}</li>
            </ul>
            <ul>
                <li class="search-item border-bottom" v-show="show" >没有搜索到匹配项</li>
            </ul>
        </div>
    </div>
</template>

<script>
import Bscorll from 'better-scroll';
import { mapMutations } from 'vuex'
import { clearTimeout, setTimeout } from 'timers';
    export default {
        name:"Citysearch",
        props:{
            cities:Object
        },
        methods:{
            handleCityClick(city){
                this.changeCity(city);
                this.$router.push("/")
            },
            ...mapMutations(['changeCity'])
        },
        data(){
            return {
                list:[],
                keyword:'',
                timer:null
            }
        },
        computed:{
            show(){
                return !this.list.length
            }
        },
        watch:{
            keyword(){
                if(this.timer){
                    clearTimeout(this.timer)
                }
                if(!this.keyword){
                    this.list=[];
                    return;
                }
                this.timer=setTimeout(()=>{
                    const resolt=[];
                    for (let i in this.cities){
                        this.cities[i].forEach(item=>{
                            if(item.name.includes(this.keyword) || item.spell.includes(this.keyword)){
                                resolt.push(item.name);
                            }
                        })
                    }
                    this.list=resolt;
                },100)
            }
        },
        mounted(){
            this.scorll=new Bscorll(this.$refs.search)
        }
    }
</script>

<style  lang='stylus' scoped>
@import '~styles/varibles'
  .search
    padding:.1rem
    line-height: .72rem
    background: $bgColor
    color:#666
    .search-input
        width:100%
        height 0.62rem
        line-height: .62rem
        text-align:center
        border-radius:.06rem
        box-sizing:border-box
        padding:0 .2rem
  .search-content
    z-index:1
    overflow: hidden
    position: absolute 
    top:1.78rem
    left:0
    right:0
    bottom:0
    background: #eeeeee
    .search-item
        background:#fff
        line-height:.64rem
        padding-left:.2rem
        color:#666

</style>


