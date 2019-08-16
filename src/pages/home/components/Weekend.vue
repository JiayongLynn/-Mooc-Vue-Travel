<template>
    <div class="weekend">
        <h2 class="weekend-title">周末去哪儿</h2>
        <div class="weekend-list">
             <div class="weekend-item" v-for="item in dataList" :key="item.id">
                 <img class="item-img" :src="item.img" alt="">
                  <div class="item-info">
                    <p class="info-title">{{item.title}}</p>
                    <p class="info-desc">{{item.desc}}</p>
                 </div>
             </div>
            
        </div>
    </div>
</template>

<script>
export default {
    name:'weekend',
    data(){
        return{
            dataList:[
                {
                    id:1,
                    img:'http://img1.qunarzz.com/sight/source/1507/d9/2ddc7652fdba16.jpg_r_640x214_5e62f1a3.jpg',
                    title:'深圳周边游',
                    desc:'远离城市拥堵，去周边开启清新假期吧。'
                },{
                    id:2,
                    img:'http://img1.qunarzz.com/sight/source/1811/15/66f14e0fd6fbb.jpg_r_640x214_5d69f21d.jpg',
                    title:'清远周边逛',
                    desc:'人人都有一双发现美的眼睛，身边的事物最熟悉不过，那你可曾发现了被人遗漏的美？'
                },{
                    id:3,
                    img:'http://img1.qunarzz.com/sight/source/1811/b8/5d599bbdcf8b57.jpg_r_640x214_2ee055e3.jpg',
                    title:'浮在海上的绿洲',
                    desc:'南国滨海之城，避寒胜地，有暖暖的阳光，海风习习，吃着海鲜逛逛老街多惬意啊'
                },{
                    id:4,
                    img:'http://img1.qunarzz.com/sight/source/1505/4b/d04aa63b1b0ab3.jpg_r_640x214_a3a9c5b6.jpg',
                    title:'东莞打卡',
                    desc:'东莞，向往一座城，不需要理由'
                },{
                    id:5,
                    img:'http://img1.qunarzz.com/sight/source/1602/88/bf120edeaea383.jpg_r_640x214_f8591f7b.jpg',
                    title:'欢乐长隆',
                    desc:'世界欢乐汇聚长隆，这里拥有多个大型游乐设备和精彩的演出，和小伙伴们一起感受刺激的体验'
                }
            ]
        }
    }
}
</script>

<style lang="stylus" scoped>
  @import '~styles/mixins.styl'
    .weekend-title
        padding-left .24rem
        line-height .8rem
    .weekend-item
        margin-bottom .1rem
        background #fff
      .item-img
        width 100%
      .item-info
        padding:.14rem .2rem .2rem .2rem
        .info-title
         font-size .28rem
         line-height .48rem
         padding-right 1.4rem
         color #212121
         ellipsis()
        .info-desc
         color #616161
         padding-right 1.4rem
         font-size .24rem
         ellipsis()

</style>