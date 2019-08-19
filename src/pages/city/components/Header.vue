<template>
   <div class="city-header">
      <div class="city-left">
        <div class="iconfont back-icon">&#xe624;</div>
      </div>
        <h2 class="city-title">城市选择</h2>      
   </div>
</template>

<script>
export default {
  name: 'Header',
}
</script>

<style lang="stylus" scoped>
  @import '~styles/varibles.styl';
  .city-header
    background: $bgColor
    color: #fff
    height .86rem
    .city-left
      width: .64rem
      position absolute
      left 0
      display inline-block
      .back-icon
        text-align:center
        font-size:.36rem
        width .8rem
        height .86rem
        line-height .86rem
    .city-title
      font-size:.32rem
      text-align center
      line-height .86rem
  .city:after
      content: " ";   
      border-bottom:1px solid #e0e0e0;
      transform: scaleY(.33333);
      bottom:0;
      position absolute
      width 100%
</style>