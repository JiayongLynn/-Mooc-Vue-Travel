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
                <swiper-slide v-for="Item in swiperList" v-bind:key="Item.id">
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
   data () {
    return {
      swiperOption:{
        slidesPerView: 3.4,
        spaceBetween: 0,
        freeMode: true,
        slidesOffsetBefore : 10
      },
      swiperList: [{
        id: '0001',
        imgUrl: 'http://img1.qunarzz.com/sight/p0/1511/34/34170b200db08a5a90.img.jpg_250x250_02eb6e72.jpg',
        title:'隐贤山庄',
        price:79,
        top:1
      }, {
        id: '0002',
        imgUrl: 'http://img1.qunarzz.com/sight/p0/1603/1d/1d756648039bf30f90.water.jpg_250x250_18d11102.jpg',
        title:'东莞香市动物园',
        price:109,
        top:2
      }, {
        id: '0003',
        imgUrl: 'http://img1.qunarzz.com/sight/p0/1902/7a/7ac34ad6cc6e7497a3.img.jpg_250x250_94a5f69e.jpg',
        title:'东莞龙凤山庄影视渡假村',
        price:68,
        top:3
      },{
        id: '0004',
        imgUrl: 'http://img1.qunarzz.com/sight/p0/1905/af/af4f95f579ee43b1a3.water.jpg_250x250_5d79e709.jpg',
        title:'东莞观音山旅游风景区',
        price:38.9
      },{
        id: '0005',
        imgUrl: 'http://img1.qunarzz.com/sight/p0/1607/6c/6ce376cd5775ce6fb4.img.jpg_250x250_b7361b12.jpg',
        title:'虎英水上乐园（原棕榈谷水城）',
        price:75
      },{
        id: '0006',
        imgUrl: 'http://img1.qunarzz.com/sight/p0/1602/a2/a2db6aea3707663a90.img.jpg_250x250_f06fcda4.jpg',
        title:'梦幻百花洲',
        price:51.2
      },{
        id: '0007',
        imgUrl: 'http://img1.qunarzz.com/sight/p0/1906/ba/ba0ea8a459c73871a3.img.jpg_250x250_42d709b8.jpg',
        title:'隐贤山庄水上乐园',
        price:74
      },{
        id: '0008',
        imgUrl: 'http://img1.qunarzz.com/sight/p0/1507/52/0e7cb0d161c785b41bab3664bf8c692a.water.jpg_250x250_45f0a538.jpg',
        title:'水濂山乐民游艺园',
        price:12.8
      },{
        id: '0009',
        imgUrl: 'http://img1.qunarzz.com/sight/p0/1603/bf/bfd3325186a7160590.water.jpg_250x250_995db565.jpg',
        title:'华南mall欢笑天地',
        price:12.8
      },{
        id: '0010',
        imgUrl: 'http://img1.qunarzz.com/sight/p0/1806/f5/f56a5d7c095aed73a3.img.jpg_250x250_48babef3.jpg',
        title:'水濂山乐民游艺园',
        price:54.9
      }]
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
