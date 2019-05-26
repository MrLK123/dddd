<template>
    <div>
        <city-header></city-header>
        <city-seach></city-seach>
        <city-list :cities="cities" :letter="letter" :hotCities="hotCities"></city-list>
        <city-alphabet @change="handlerChange"  :cities="cities"></city-alphabet>
    </div>
</template>

<script>
import axios from 'axios'
import CityHeader from './components/Header'
import CitySeach from './components/Seach'
import CityList from './components/List'
import CityAlphabet from './components/Alphabet'
    export default {
        name:'City',
        components:{CityHeader,CitySeach,CityList,CityAlphabet},
        data(){
            return {
                hotCities:[],
                cities:{},
                letter:''
            }
        },
        methods:{
            handlerChange(letter){
                this.letter=letter
            }
        },
        mounted(){
            axios.get("/api/city.json").then(res=>{
                res=res.data;
                if(res.ret && res.data){
                    const data=res.data;
                     this.hotCities=data.hotCities;
                     this.cities=data.cities;
                }
               
            })
        }
    }
</script>

<style  scoped>

</style>