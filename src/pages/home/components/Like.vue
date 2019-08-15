<template>
      <div class="index-like">
          <div class="like-title">
              <span class="iconfont icon-like">&#xe85c;</span>
              <span class="like-left-title">猜你喜欢</span>
          </div> 
          <div class="like-list">
              <div class="like-item">
                  <img class="item-img" src="http://img1.qunarzz.com/sight/p0/1906/ba/ba0ea8a459c73871a3.img.jpg_200x200_29068ad2.jpg" alt="">
                  <div class="item-info">
                      <div class="info-title">
                        隐贤山庄水上乐园
                      </div>
                      <div class="info-apprise">

                      </div>
                      <div class="info-price">
                          <span>￥119</span>起
                      </div>
                      <div class="info-city">
                        东莞
                      </div>
                  </div>
              </div>
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
        .like-left-title
          font-size: .32rem
          line-height .44rem
      .like-list
        padding-left: .24rem
        padding-top: .2rem
        .like-item
          display flex;
          overflow hidden
          height 2rem
          width 100%
          .item-img
            width 2rem
            height 2rem
          .item-info
            flex:1
            padding .1rem
            overflow hidden
            .info-title
              font-size .32rem
              line-height .44rem
              ellipsis()    
              color #212121
              font-family:Arial,"Microsoft Yahei","Helvetica Neue",Helvetica,sans-serif          
</style>
