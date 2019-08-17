<template>
      <div class="index-like">
          <div class="like-title">
              <span class="iconfont icon-like">&#xe85c;</span>
              <span class="like-left-title">猜你喜欢</span>
          </div> 
          <div class="like-list">
              <div class="like-item" v-for='item in likeList' :key="item.id">
                  <img class="item-img" :src="item.imgUrl" alt="">
                  <div class="item-info">
                      <div class="info-title">
                        {{item.title}}
                      </div>
                      <div class="info-apprise">
                          <Star :rating='item.rating'></Star>
                          <span style='font-size:12px'>{{item.commentTotal}}条评论</span>
                      </div>
                      <div class="info-price">
                          <span class="price">￥{{item.price}}</span>起
                          <span class="info-city">
                           {{item.city}}
                          </span>
                      </div>
                      <div v-if="item.advert" class="info-content">
                          {{item.advert}}
                      </div>
                  </div>
              </div>
              <a href="" class="viewall">查看所有产品</a>
          </div>
      </div>
</template>

<script>
import Star from '../../tools/Star'
export default {
  name: 'HomeLike',
  components: {
    Star
  },
  props:{
    likeList:{
      type:Array
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
        padding-top: .2rem
        .like-item
          display flex;
          overflow hidden
          width 100%
          position relative
          padding:.2rem .2rem
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
              font-family:Arial,"Microsoft Yahei","Helvetica Neue",Helvetica,sans-serif;
              margin-bottom:.1rem
            .info-price
              font-size:.22rem
              margin-top .5rem
              position relative
              .price
                font-size .4rem
                line-height .4rem
                color: #ff8300;
              .info-city
                position absolute;
                right 0;
                bottom 0;
                width 1rem
                ellipsis()
            .info-content
              background: #fff9f9;
              color: #f55;
              font-size: .24rem;
              line-height: .34rem;
              display inline-block
              padding: .04rem .1rem;
              margin-top .3rem
        .like-item:after
          content: " ";   
          border-bottom:1px solid #e0e0e0;
          transform: scaleY(.33333);
          bottom:0;
          position absolute
          width 100%
        .viewall
          display block
          line-height .44rem
          font-size:.32rem
          text-align center
          padding .2rem 0
</style>
