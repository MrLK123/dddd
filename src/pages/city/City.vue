<template>
    <div>
        <city-header></city-header>
        <city-seach></city-seach>
    </div>
</template>

<script>
import CityHeader from './components/Header'
import CitySeach from './components/Seach'
    export default {
        name:'City',
        components:{CityHeader,CitySeach}
    }
</script>

<style  scoped>

</style>