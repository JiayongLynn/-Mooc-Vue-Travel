<template>
      <div class="index-like">
          <div class="like-title">
              <span class="iconfont icon-like">&#xe85c;</span>
              <span class="like-left-title">猜你喜欢</span>
          </div>
      </div>
</template>

<script>
export default {
  name: 'HomeLike',
   data () {
     return{

     }
  }
}
</script>

<style lang="stylus" scoped>
  @import '~styles/mixins.styl'

    .index-like
      background-color #ffffff
      margin-top .2rem
      .like-title
        padding:.24rem
        height .44rem
        position relative
        .icon-like
          color #d81e06
        ..like-left-title
          font-size: .32rem
          line-height .44rem
</style>
