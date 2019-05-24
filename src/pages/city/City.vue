<template>
    <div>
        <city-header></city-header>
        <city-seach></city-seach>
        <city-list></city-list>
        <city-alphabet></city-alphabet>
    </div>
</template>

<script>
import CityHeader from './components/Header'
import CitySeach from './components/Seach'
import CityList from './components/List'
import CityAlphabet from './components/Alphabet'
    export default {
        name:'City',
        components:{CityHeader,CitySeach,CityList,CityAlphabet}
    }
</script>

<style  scoped>

</style>