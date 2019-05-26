<template>
  <div id="app">
    <router-view/>
    <!-- <Echarts/> -->
  </div>
</template>

<script>
import Echarts from './pages/echarts/Echarts'
export default {
  name: 'App',
  components:{Echarts}
}
</script>

<style>

</style>
