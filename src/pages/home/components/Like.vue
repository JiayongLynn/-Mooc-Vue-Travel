<template>
      <div class="index-like">
          <div class="like-title">
              <span class="iconfont icon-like">&#xe85c;</span>
              <span class="like-left-title">猜你喜欢</span>
          </div> 
          <div class="like-list">
              <div class="like-item" v-for='item in itemList' :key="item.id">
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
   data () {
     return {
      itemList: [{
        id: '0001',
        imgUrl: 'http://img1.qunarzz.com/sight/p0/1906/ba/ba0ea8a459c73871a3.img.jpg_200x200_29068ad2.jpg',
        title:'隐贤山庄水上乐园',
        rating:3,
        commentTotal:7,
        price:79,
        city:'东莞市',
        advert:'🔥好评如潮，小伙伴热推景点~'
      }, {
        id: '0002',
        imgUrl: 'http://img1.qunarzz.com/sight/p0/1603/1d/1d756648039bf30f90.water.jpg_250x250_18d11102.jpg',
        title:'东莞香市动物园',
        rating:5,
        commentTotal:4959,
        price:110,
        city:'东莞',
      }, {
        id: '0003',
        imgUrl: 'http://img1.qunarzz.com/sight/p0/1511/34/34170b200db08a5a90.img.jpg_200x200_cc3130fd.jpg',
        title:'隐贤山庄',
        rating:5,
        commentTotal:8737,
        price:159,
        city:'东莞市',
        advert:'帅的人都去过了😎，你还等什么~'
      },{
        id: '0004',
        imgUrl: 'http://img1.qunarzz.com/sight/p0/1902/7a/7ac34ad6cc6e7497a3.img.jpg_200x200_939e55b1.jpg',
        title:'东莞龙凤山庄影视渡假村',
        rating:1,
        commentTotal:6847,
        price:68,
        city:'东莞市',
        advert:'东莞本月收藏Top5╰(￣▽￣)╭'
      },{
        id: '0005',
        imgUrl: 'http://img1.qunarzz.com/sight/p0/1905/af/af4f95f579ee43b1a3.water.jpg_200x200_9fdbf80f.jpg',
        title:'东莞观音山旅游风景区',
        rating:2,
        commentTotal:8737,
        price:38.9,
        city:'东莞市',
      },{
        id: '0006',
        imgUrl: 'http://img1.qunarzz.com/sight/p0/1602/a2/a2db6aea3707663a90.img.jpg_250x250_f06fcda4.jpg',
        title:'梦幻百花洲',
        rating:5,
        commentTotal:5126,
        price:48,
        city:'东莞市',
      },{
        id: '0007',
        imgUrl: 'http://img1.qunarzz.com/sight/p0/1607/6c/6ce376cd5775ce6fb4.img.jpg_200x200_7ed7ce79.jpg',
        title:'虎英水上乐园（原棕榈谷水城）',
        rating:5,
        commentTotal:692,
        price:75,
        city:'东城',
        advert:'享受刺激有趣的水上活动'
      },{
        id: '0008',
        imgUrl: 'http://img1.qunarzz.com/sight/p0/1603/bf/bfd3325186a7160590.water.jpg_200x200_6cd3d3dd.jpg',
        title:'华南mall欢笑天地',
        rating:5,
        commentTotal:626,
        price:59.9,
        city:'东莞市',
      },{
        id: '0009',
        imgUrl: 'http://img1.qunarzz.com/sight/p0/1907/41/41daff4e8ec5a1e9a3.img.jpg_200x200_7caaf33c.jpg',
        title:'东莞华南Mall-哈尔滨冰雪大世界',
        rating:5,
        commentTotal:297,
        price:39.9,
        city:'南城区',
      },{
        id: '0010',
        imgUrl: 'http://img1.qunarzz.com/sight/p0/201303/04/9de745ece9f1135cc8d65eac.jpg_200x200_a454f2b7.jpg',
        title:'水濂山',
        rating:5,
        commentTotal:226,
        price:12.7,
        city:'东莞市',
        advert:'岭南古韵，山水迷人，人与自然的天体之峰'
      },{
        id: '0011',
        imgUrl: 'http://img1.qunarzz.com/sight/p0/201301/21/844438b21540e06ec8d65eac.jpg_200x200_38d5ba2f.jpg',
        title:'东莞植物园（原绿色世界）',
        rating:0,
        commentTotal:12,
        price:48,
        city:'东莞市',
      },{
        id: '0012',
        imgUrl: 'http://img1.qunarzz.com/sight/p0/1505/a9/a90bda513f0123a8.water.jpg_200x200_f257a313.jpg',
        title:'南社明清古建筑群',
        rating:5,
        commentTotal:1041,
        price:24.8,
        city:'茶山',
      }]
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
