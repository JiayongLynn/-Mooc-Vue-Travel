<template>
  <div class="city">
    <city-header></city-header>
    <city-search></city-search>
    <city-list></city-list>
    <city-alaphet></city-alaphet>
  </div>
 
</template>

<script>
import CityHeader from './components/Header'
import CitySearch from './components/Search'
import CityList   from './components/List'
import CityAlaphet from './components/Alaphet'
export default {
  name: 'City',
  components: {
    CityHeader,
    CitySearch,
    CityList,
    CityAlaphet
  },
}
</script>

<style lang="stylus" scoped>

</style>
