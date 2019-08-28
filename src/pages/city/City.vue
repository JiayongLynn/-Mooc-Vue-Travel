<template>
  <div class="city">
    <city-header></city-header>
    <city-search></city-search>
    <city-list :citylist='cityList' :hotcityList='hotcityList'></city-list>
    <city-alaphet :citylist='cityList'></city-alaphet>
  </div>
 
</template>

<script>
import CityHeader from './components/Header'
import CitySearch from './components/Search'
import CityList   from './components/List'
import CityAlaphet from './components/Alaphet'
import axios         from 'axios'

export default {
  name: 'City',
  components: {
    CityHeader,
    CitySearch,
    CityList,
    CityAlaphet
  },
  data(){
    return{
      cityList:{},
      hotcityList:[]
    }
  },
  methods:{
    getCityData(){
      axios.get('/api/city.json')
      .then(this.getCityInfo);
    },
    getCityInfo(res){
        if(res.data.ret && res.data.data){
            let data = res.data.data;
            this.cityList = data.cities;
            this.hotcityList = data.hotCities;
        }
    }

  },
  mounted(){
    this.getCityData();
  }
}
</script>

<style lang="stylus" scoped>

</style>
