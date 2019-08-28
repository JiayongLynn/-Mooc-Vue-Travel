<template>
   <div class="list" ref='wrapper'>
     <div>
        <div class="area">
          <div class='title border-topbottom'>当前城市</div>
          <div class="button-list">
              <div class="warpper-button">
                  <div class="button">
                        东莞
                  </div>
              </div>
          </div>
        </div> 
        <div class="area">
          <div class='title border-topbottom'>热门城市</div>
          <div class="button-list">
              <div class="warpper-button" v-for="item of hotcityList" :key="item.id">
                  <div class="button">
                        {{item.name}}
                  </div>
              </div>
          </div>
        </div> 
        <div class="area" v-for="(item,key) of citylist" :key="key">
          <div class='title border-topbottom'>{{key}}</div>
          <div class="item-list" v-for="cityitem of item" :key='cityitem.id'>
              <div class="item border-bottom">
                  {{cityitem.name}}
              </div>
          </div>
        </div>
      </div>
    </div> 
</template>

<script>
import Bscroll from 'better-scroll'
export default {
  name: 'CityList',
  props:{
      citylist:{
          type:Object
      },
      hotcityList:{
          type:Array
      }
  },
  mounted(){
    this.scroll = new Bscroll(this.$refs.wrapper);
  }
}
</script>

<style lang="stylus" scoped>
  @import '~styles/varibles.styl';
  .list
    position absolute
    top 1.58rem
    left 0
    right 0
    bottom 0
    overflow hidden
    .border-topbottom
      &:before
        border-color: #ccc
      &:after
        border-color: #ccc
    .border-bottom
      &:before
        border-color: #ccc
        
    .title
      background #eeeeee
      line-height .5rem
      font-size .26rem
      color #000
      padding  .05rem 0 .05rem .3rem

    .button-list
      overflow hidden
      padding .1rem .6rem .1rem .1rem
      .warpper-button
        float left
        width 33.3%
        .button
          text-align center
          padding .1rem 0
          border .02rem solid #ccc
          border-radius: .06rem
          margin .1rem
    .item-list
      .item
        line-height .76rem
        padding-left .2rem
</style>