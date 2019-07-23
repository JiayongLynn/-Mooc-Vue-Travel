<template>
<div class='wrapper'>
    <swiper :options="swiperOption">
    <!-- slides -->
    <swiper-slide v-for="Item in swiperList" v-bind:key="Item.id">
      <img class="swipe-img" :src='Item.imgUrl' alt="">
    </swiper-slide>
    <!-- Optional controls -->
    <div class="swiper-pagination"  slot="pagination"></div>
  </swiper>
</div>
</template>

<script>
export default {
  name: 'HomeSwiper',
  data () {
    return {
      swiperOption: {
        pagination: {
          el: '.swiper-pagination',
        },
        loop: true
      },
      swiperList: [{
        id: '0001',
        imgUrl: 'http://mp-piao-admincp.qunarzz.com/mp_piao_admin_mp_piao_admin/admin/20197/f6d5d4cc342b18bc90a83bd3291e035f.jpg_750x200_654a09cf.jpg'
      }, {
        id: '0002',
        imgUrl: 'http://mp-piao-admincp.qunarzz.com/mp_piao_admin_mp_piao_admin/admin/20193/d7bbc21db442366a882e04ddc984669a.jpg_750x200_85e640d9.jpg'
      }, {
        id: '0003',
        imgUrl: 'http://mp-piao-admincp.qunarzz.com/mp_piao_admin_mp_piao_admin/admin/20194/8f7bcfbd2ccdd8aaa116799a39c812c9.jpg_750x200_c41c49fb.jpg'
      }]
    }
  }
}
</script>

<style lang="stylus"  scoped>
  .wrapper >>> .swiper-pagination-bullet-active
      background #fff
  .wrapper
    overflow:hidden
    width:100%
    height:0
    padding-bottom:31.25%
    .swipe-img
      width :100%
</style>
