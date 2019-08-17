<template>
    <div class='home'>
      <home-header :city="city"></home-header>
      <home-swiper :swiperList="swiperList"></home-swiper>
      <home-icons :iconList="iconList"></home-icons>
      <home-recommend :RecommandList="recommandList"></home-recommend>
      <home-like :likeList="likeList"></home-like>
      <home-weekend :weekList="weekList"></home-weekend>
    </div>
</template>

<script>
import HomeHeader    from './components/Header'
import HomeSwiper    from './components/Swiper'
import HomeIcons     from './components/Icons'
import HomeRecommend from './components/Recommend'
import HomeLike      from './components/Like'
import HomeWeekend   from './components/Weekend'
import axios         from 'axios'
export default {
  name: 'Home',
  components: {
    HomeHeader,
    HomeSwiper,
    HomeIcons,
    HomeRecommend,
    HomeLike,
    HomeWeekend
  },
  data(){
    return{
      city:'',
      swiperList:[],
      iconList:[],
      recommandList:[],
      likeList:[],
      weekList:[]
    }
  },
  methods:{
    getHomeData(){
       axios.get('/api/index.json')
          .then(this.getHomeInfo)
    },
    getHomeInfo(res){
      res = res.data;
      if(res.ret && res.data){
          let data = res.data;
          this.city = data.city;
          this.swiperList = data.swiperList;
          this.iconList = data.iconList;
          this.recommandList = data.RecommendList;
          this.likeList = data.likeList;
          this.weekList = data.weekList;
      }
    }
  },mounted(){
    this.getHomeData();
  }
}
</script>

<style lang="stylus">
  .home
    background-color #f5f5f5
</style>
