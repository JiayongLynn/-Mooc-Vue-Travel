<template>
    <ul class="alaphet-list">
       <li class="item" v-for="item of alaphetList" :key="item" 
       @click="handleChange"
       @touchstart='handleTouchStart'
       @touchmove='handleTouchMove'
       @touchend='handleTouchEnd'
       :ref="item"
       >
          {{item}}
       </li>
    </ul>
</template>

<script>
export default {
  name: 'CityAlaphet',
  props:{
      citylist:{
          type:Object
      },
  },
  data(){
     return{
        touchStatus:false
     }
  },
  computed:{
     alaphetList(){
        const alaphet = [];
        for(let i in this.citylist){
           alaphet.push(i);
        }
        return alaphet;
     }
  },
  methods:{
     handleChange(event){
        this.$emit('jumpArea',event.target.innerText);
     },
     handleTouchStart(){
        this.touchStatus = true;
     },
     handleTouchMove(event){
        if(this.touchStatus){
           const StartY = this.$refs['A'][0].offsetTop;
           const SlideY = event.touches[0].clientY - 79;
           const index = Math.floor((SlideY - StartY)/20);
           if(index >= 0 && index < this.alaphetList.length){
            this.$emit('jumpArea',this.alaphetList[index]);
           }
        }
     },
     handleTouchEnd(){
        this.touchStatus = false;
     }
  }
}
</script>

<style lang="stylus" scoped>
  @import '~styles/varibles.styl';
    .alaphet-list
      position absolute
      top 1.58rem
      right 0
      bottom 0
      width .4rem
      display  flex 
      flex-direction column
      justify-content center
      .item
        line-height .44rem
        text-align center
        color $bgColor
</style>