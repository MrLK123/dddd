<template>
  <div id="app">
    <keep-alive exclude="Detail">
      <router-view/>
    </keep-alive>
    <!-- <Echarts/> -->
  </div>
</template>

<script>

import Echarts from './pages/echarts/Echarts'
export default {
  name: 'App',
  components:{Echarts},
}
</script>

<style>

</style>
