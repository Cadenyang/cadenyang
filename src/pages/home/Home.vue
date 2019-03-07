<template>
  <div>
    <home-header :city="city"></home-header>
    <home-swiper :list="imgList"></home-swiper>
    <home-icons :list="iconList"></home-icons>
    <home-recommend :list="recommendList"></home-recommend>
    <home-weekend :list="weekendList"></home-weekend>
  </div>
</template>
<script>
import HomeHeader from './components/Header'
import HomeSwiper from './components/Swiper'
import HomeIcons from './components/Icons'
import HomeRecommend from './components/Recommend'
import HomeWeekend from './components/Weekend'
import axios from 'axios'

export default {
  name: 'Home',
  components: {
    HomeHeader,
    HomeSwiper,
    HomeIcons,
    HomeRecommend,
    HomeWeekend
  },
  data () {
    return {
      city: '',
      imgList: [],
      iconList: [],
      recommendList: [],
      weekendList: []
    }
  },
  mounted () {
    this.getHomeInfo()
  },
  methods: {
    getHomeInfo() {
      axios.get('/api/index.json').then(response => {
        const res = response.data
        if(res.data && res.success == true){
            this.city = res.data.city
            this.imgList = res.data.imgList
            this.iconList = res.data.iconList
            this.recommendList = res.data.recommendList
            this.weekendList = res.data.weekendList
        }
      })
    }
  }
}
</script>
<style>
</style>
