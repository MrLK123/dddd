<template>
    <div id="myChart" ref="myChart"></div>   
 </template>
 <style>
     #myChart {
         width: 400px;
         height: 600px;
         margin: 20px auto;
         border: 1px solid #CCC
     }
 </style>
 <script>
 import axios from 'axios'
//  引入完整的echarts
import echarts from './echartBar'
import  theme from './theme'

export default {
  name: 'hello',
  data() {
    return {
      msg: 'Welcome to Your Vue.js App'
    }
  },
  mounted() {
    this.drawLine();
  },
  methods: {
    drawLine() {
       
      // 基于准备好的dom，初始化echarts实例
      let myChart =  echarts.init(this.$refs.myChart,theme)
      myChart.showLoading();
axios.get('/api/data.json').then(res=>{
  setTimeout(()=>{
        myChart.hideLoading();
    myChart.setOption(res.data);
  },4000)
}
);
      // 绘制图表
      
    }
  }
}
 </script>