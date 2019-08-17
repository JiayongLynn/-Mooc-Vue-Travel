<template>
<div class='wrapper'>
    <swiper :options="swiperOption" v-if="showSwipper">
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
  props:{
    swiperList:{
      type:Array
    }
  },
  data () {
    return {
      swiperOption: {
        pagination: {
          el: '.swiper-pagination'
        },
        loop: true
      }
    }
  },
  computed:{
      showSwipper(){
        return this.swiperList.length;
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
    padding-bottom:26.7%
    .swipe-img
      width :100%
</style>
