<template>
    <div class="weekend">
        <h2 class="weekend-title">周末去哪儿</h2>
        <div class="weekend-list">
             <div class="weekend-item" v-for="item in weekList" :key="item.id">
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
    props:{
        weekList:{
            type:Array
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