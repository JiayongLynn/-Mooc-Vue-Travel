<template>
   <div class="list">
      <div class="area">
        <div class='title border-bottom'>当前城市</div>
        <div class="button-list">
            <div class="warpper-button">
                <div class="button">
                      东莞
                </div>
            </div>
        </div>
      </div> 
       <div class="area">
        <div class='title border-bottom'>热门城市</div>
        <div class="button-list">
            <div class="warpper-button">
                <div class="button">
                      东莞
                </div>
            </div>
             <div class="warpper-button">
                <div class="button">
                      东莞
                </div>
            </div>
             <div class="warpper-button">
                <div class="button">
                      东莞
                </div>
            </div>
             <div class="warpper-button">
                <div class="button">
                      东莞
                </div>
            </div>
             <div class="warpper-button">
                <div class="button">
                      东莞
                </div>
            </div>
             <div class="warpper-button">
                <div class="button">
                      东莞
                </div>
            </div>
             <div class="warpper-button">
                <div class="button">
                      东莞
                </div>
            </div>
        </div>
      </div> 
       <div class="area">
        <div class='title border-bottom'>A</div>
        <div class='title border-bottom'>B</div>
        <div class='title border-bottom'>C</div>
        <div class='title border-bottom'>D</div>
        <div class='title border-bottom'>E</div>
        <div class='title border-bottom'>F</div>
        <div class='title border-bottom'>G</div>
      </div> 
   </div>
</template>

<script>
export default {
  name: 'CityList',
}
</script>

<style lang="stylus" scoped>
  @import '~styles/varibles.styl';
    .border-bottom
      &:before
        border-color: #ccc
      &:after
        border-color: #ccc
    .title
      background #eeeeee
      line-height .44rem
      font-size .26rem
      color #666
      padding-left .3rem
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
</style>