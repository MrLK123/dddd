<template>
        <ul class="list">
            <li 
               class="item" 
               v-for="item in letters" 
               :ref="item"
               :key="item" 
               @click="handleClick"
               @touchstart="handleTouchStart"
               @touchmove="handleTouchMove"
               @touchend="handleTouchEnd"
            >{{item}}</li>
        </ul>
    
</template>

<script>
import { clearTimeout, setTimeout } from 'timers';
    export default {
        name:"Alphabet",
        props:["cities"],
        data(){
            return {
                touchStatus:false,
                startY:"",
                timer:null
            }
        },
        updated(){
            this.startY=this.$refs["A"][0].offsetTop+89;
        },
        methods:{
            handleClick(e){
                this.$emit("change",e.target.innerText)
            },
            handleTouchStart(){
                this.touchStatus=true;
            },
            handleTouchMove(e){
               
                if(this.touchStatus){
                    if(this.timer){
                        clearTimeout(this.timer);
                    }
                    this.timer=setTimeout(()=>{
                        const touchY=e.touches[0].clientY-this.startY;
                        const index=Math.floor(touchY/20);    
                        if(index>=0 && index<=this.letters.length){
                            this.$emit("change",this.letters[index])
                             }
                        }
                    ,16)
                    }
            },
            handleTouchEnd(){
                this.touchStatus=false;
            }
        },
        computed:{
            letters(){
                let letters=[];
                for(let i in this.cities){
                    letters.push(i);
                }
                return letters;
            }
        }
    }
</script>

<style lang="stylus" scoped>
@import '~styles/varibles'
   .list
      display:flex
      flex-direction:column
      justify-content:center
      text-align:center
      position:absolute
      right:0
      bottom:0
      width:.4rem
      top: 1.78rem
      color:$bgColor
      .item
         line-height: .4rem
</style>