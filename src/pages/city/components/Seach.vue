<template>
    <div class="seach">
        <input type="text" class="seach-input" placeholder="输入城市名称或拼音"/>
    </div>
</template>

<script>
    export default {
        name:"CitySeach"
    }
</script>

<style  lang='stylus' scoped>
@import '~styles/varibles'
  .seach
    padding:.1rem
    line-height: .72rem
    background: $bgColor
    color:#666
    .seach-input
        width:100%
        height 0.62rem
        line-height: .62rem
        text-align:center
        border-radius:.06rem
        box-sizing:border-box
        padding:0 .2rem
</style>


