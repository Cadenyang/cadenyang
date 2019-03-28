<template>
    <div>
        <city-header></city-header>
        <city-search></city-search>
        <city-list :hot="hotCities" :cities="allCities"></city-list>
        <city-alphabet :cities="allCities"></city-alphabet>
    </div>
</template>
<script>
import CityHeader from './components/Header'
import CitySearch from './components/Search'
import CityList from './components/List'
import CityAlphabet from './components/Alphabet'
import axios from 'axios'

export default {
    name: 'City',
    components: {
        CityHeader,
        CitySearch,
        CityList,
        CityAlphabet
    },
    data () {
        return {
            hotCities: [],
            allCities: {}
        }
    },
    mounted () {
        this.getCityInfo()
    },
    methods: {
        getCityInfo () {
            axios.get('/api/city.json').then(response => {
                const res = response.data
                if(res.data && res.success == true){
                    this.hotCities = res.data.hotCities
                    this.allCities = res.data.cities
                    // this.iconList = res.data.iconList
                    // this.recommendList = res.data.recommendList
                    // this.weekendList = res.data.weekendList
                }
            })
        }
    }
}
</script>
<style>

</style>

