<template>
  <div class="icons">
    <swiper :options="swiperOption">
      <!-- slides -->
      <swiper-slide v-for="page in pages" :key="page.id">
          <div class="icon" v-for="Item in page" v-bind:key="Item.id">
            <div class='iconImg'>
              <img class="iconImg-img" :src='Item.imgUrl' alt="">
            </div>
            <p class="icon-desc">{{Item.desc}}</p>
          </div>
      </swiper-slide>
      <!-- Optional controls -->
    <div class="swiper-pagination"  slot="pagination"></div>

    </swiper>
  </div>
</template>

<script>
export default {
  name: 'HomeIcons',
  props:{
    iconList:{
      type:Array
    }
  },
  data () {
    return {
      swiperOption: {
        pagination: {
          el: '.swiper-pagination'
        }
        // loop: true
      }
    }
  },
  computed: {
    pages() {
      const pages = [];
      this.iconList.forEach((item,index)=>{
        const page = Math.floor(index / 8);
        if(!pages[page]){
          pages[page] = []
        }
        pages[page].push(item)
      })
      return pages
    }
  }
}
</script>

<style lang='stylus' scoped>
  @import '~styles/varibles.styl'
  @import '~styles/mixins.styl'
  .icons >>> .swiper-container
    height 0
    padding-bottom 50%
  .icons
    background-color #fff
    .icon
      float: left
      width:  25%
      padding-bottom: 25%
      position relative
      height 0
      overflow hidden
      .iconImg
        position absolute
        top: .25rem
        left: 0
        right: 0
        bottom 0
        box-sizing: border-box
        height: 1.1rem
        .iconImg-img
          height  100%
          display block
          margin 0 auto
      .icon-desc
        position absolute
        left 0
        right 0
        bottom 0
        height .44rem
        line-height .44rem
        color $darkTextColor
        text-align center
        ellipsis()
</style>
