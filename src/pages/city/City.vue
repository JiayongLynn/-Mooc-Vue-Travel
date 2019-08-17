<template>
    <div class="city">
      <div class="city-left">
        <div class="iconfont back-icon">&#xe624;</div>
      </div>
      <div class="city-title">
        城市选择
      </div>
    </div>
</template>

<script>
export default {
  name: 'City',
}
</script>

<style lang="stylus" scoped>
  @import '~styles/varibles.styl';
  .city
    line-height: .86rem
    display: flex
    background: $bgColor
    color: #fff
    .city-left
      width: .64rem
      float: left
      .back-icon
        text-align:center
        font-size:.36rem
        width .8rem
        height .88rem
    .header-input
      flex:  1
      background :#fff
      height :.62rem
      line-height .62rem
      color:#ccc
      border-radius: .1rem
      margin-top :  .12rem
      margin-left :.2rem
      padding-left :.2rem
    .header-right
      width:  1.24rem
      text-align: center
      font-size :0
      color #fff
      .arrow-icon
        font-size: 0.24rem
        // margin-left :-.04rem
</style>
