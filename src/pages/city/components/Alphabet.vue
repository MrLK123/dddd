<template>
        <ul class="list">
            <li class="item">A</li>
            <li class="item">A</li>
            <li class="item">A</li>
            <li class="item">A</li>
            <li class="item">A</li>
            <li class="item">A</li>
            <li class="item">A</li>
            <li class="item">A</li>
            <li class="item">A</li>
            <li class="item">A</li>
            <li class="item">A</li>
            <li class="item">A</li>
            <li class="item">A</li>
        </ul>
    
</template>

<script>
    export default {
        name:"Alphabet"
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