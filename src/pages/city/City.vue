<template>
    <div>
        <city-header></city-header>
        <city-search></city-search>
        <city-list :hot="hotCities" :cities="allCities" :letter="letter"></city-list>
        <city-alphabet :cities="allCities" @change="handleChange"></city-alphabet>
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
            allCities: {},
            letter: ''
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
                }
            })
        },
        handleChange (letter) {
            this.letter = letter
        }
    }
}
</script>
<style>

</style>

