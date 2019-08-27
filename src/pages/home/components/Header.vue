<template>
    <div class="header">
      <div class="header-left">
        <div class="iconfont back-icon">&#xe624;</div>
      </div>
      <div class="header-input">
        <span class="iconfont">&#xe632;</span>
        输入城市/景点/游玩主题
      </div>
      <router-link to="/city">
        <div class="header-right">
          <span style="font-size:.3rem">{{this.city}}</span>
          <span class="iconfont arrow-icon">&#xe64a;</span>
        </div>
      </router-link>
    </div>
</template>

<script>
export default {
  name: 'HomeHeader',
  props:{
    city:{
      type:String
    }
  }
}
</script>

<style lang="stylus" scoped>
  @import '~styles/varibles.styl';
  .header
    line-height: .86rem
    display: flex
    background: $bgColor
    color: #fff
    .header-left
      width: .64rem
      float: left
      .back-icon
        text-align:center
        font-size:.4rem
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
        font-size: 0.26rem
        // margin-top: -.34rem
        // margin-left :-.04rem
</style>
