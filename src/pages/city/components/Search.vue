<template>
    <div>
        <div class="search">
            <input v-model="keyword" class="search-input" type="text" placeholder="输入城市名或拼音">
        </div>
        <div class="search-content" ref='search' v-show="keyword">
            <ul>
                <li class="search-item border-bottom" v-for="item in list" :key="item.id">{{item.name}}</li>
                <li class="search-item border-bottom" v-show='hasNoData'>没有找到数据</li>
            </ul>
        </div>
    </div>
</template>

<script>
import Bscoll from 'better-scroll'
export default {
    name:'Search',
    props:{
        cityList:Object
    },
    data(){
        return{
            keyword:"",
            list:[],
            timer:null,
        }
    },
    watch:{
        keyword(){
            if(this.timer){
                clearTimeout(this.timer);
            }
            if(!this.keyword){
                this.list = [];
                return;
            }
            this.timer = setTimeout(()=>{
                const result =[];
                for(let i in this.cityList){
                    this.cityList[i].forEach((value) => {
                        if(value.spell.indexOf(this.keyword)>-1 || value.name.indexOf(this.keyword)>-1){
                            result.push(value);
                        }
                    });
                }
                this.list = result;
            },100)
        }
    },
    mounted(){
        this.scroll  = new Bscoll(this.$refs.search)
    },
    computed:{
        hasNoData(){
            return !this.list.length;
        }
    }
}
</script>

<style lang="stylus" scoped>
  @import '~styles/varibles.styl';
    .search
        background: $bgColor
        color: #fff
        height .72rem
        padding 0 .1rem
        .search-input
          width 100%
          height .62rem
          line-height .62rem
          text-align center
          border-radius .06rem
          color #666
          box-sizing:border-box
          padding 0 .1rem
    .search-content
        position absolute
        top 1.58rem
        bottom  0
        left 0
        right 0
        z-index 1
        background #eee
        overflow hidden
        .search-item
           line-height .62rem
           padding-left .2rem
           color #666
           background #fff
</style>