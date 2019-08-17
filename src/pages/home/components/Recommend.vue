<template>
    <div>
      <div class="weekhot">
          <div class="hot-title">
              <span class="iconfont icon-hot">&#xe64b;</span>
              <span class="hot-left-title">本周热门榜单</span>
              <a href="" class="hot-all-list">全部榜单<span class="iconfont">&#xe602;</span></a>
          </div>
          <div class="swipper-hot">
              <swiper :options="swiperOption">
                <!-- slides -->
                <swiper-slide v-for="Item in RecommandList" v-bind:key="Item.id">
                  <div class="hot-swipper-item">
                      <div class="hot-top">
                        <img style="width:100%" v-if="Item.top == 1" src="http://img1.qunarzz.com/piao/fusion/1710/ab/159673b63e6ca702.png" alt="">
                        <img style="width:100%" v-if="Item.top == 2" src="http://img1.qunarzz.com/piao/fusion/1710/2d/36d0c4adaebbbc02.png" alt="">
                        <img style="width:100%" v-if="Item.top == 3" src="http://img1.qunarzz.com/piao/fusion/1710/67/edc47ffef9e96b02.png" alt="">
                      </div>
                      <div class="item-img">
                          <img :src="Item.imgUrl" alt="">
                      </div>
                      <div class="item-title">
                          {{Item.title}}
                      </div>
                      <div class="item-desc">
                        <span class="price">￥<em class="price-num">{{Item.price}}</em></span>起
                      </div>
                  </div>
                  <!-- <img class="swipe-img" :src='Item.imgUrl' alt=""> -->
                </swiper-slide>
                <!-- 滚动条 -->
                <!-- <div class="swiper-scrollbar"   slot="scrollbar"></div> -->
              </swiper>
          </div>
      </div>
    </div>
</template>

<script>
export default {
  name: 'Recommend',
  props:{
    RecommandList:{
      type:Array
    }
  },
   data () {
    return {
      swiperOption:{
        slidesPerView: 3.4,
        spaceBetween: 0,
        freeMode: true,
        slidesOffsetBefore : 10
      }
    }
  }
}
</script>

<style lang="stylus" scoped>
  @import '~styles/mixins.styl'

    .weekhot
      background-color #ffffff
      margin-top .2rem
      .hot-title
        padding:.24rem
        height .44rem
        position relative
        .icon-hot
          color #d81e06
        .hot-left-title
          font-size: .32rem
          line-height .44rem
        .hot-all-list
          right 0.6rem
          line-height .44rem
          position absolute
          font-size: .24rem
          color #616161
      .swipper-hot >>> .swipper-container
        padding-left: .24rem
      .swipper-hot
        width:100%
        height:0
        padding-bottom:41%
        .hot-swipper-item
          width 2rem
          .hot-top
            position:absolute;
            width:.84rem;
            height:.4rem
          .item-img
            width 2rem
            height 0
            padding-bottom 100%
          .item-img>img
            width 100%
          .item-title
            margin-top .12rem
            font-size .24rem
            text-align center
            line-height .32rem
            ellipsis()
          .item-desc
            font-size .24rem
            line-height .36rem
            color #212121
            text-align center
            .price
              color #ff8300
              .price-num
                font-size .28rem
</style>
