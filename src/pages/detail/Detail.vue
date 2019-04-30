<template>
    <div>
        <detail-banner
            :sightName="sightName"
            :bannerImg="bannerImg"
            :bannerImgs="gallaryImgs"           
        ></detail-banner>
        <detail-header></detail-header>
        <div class="content">
            <detail-list :list="list"></detail-list>
        </div>
    </div>
</template>

<script>
import DetailBanner from './components/Banner'
import DetailHeader from './components/Header'
import DetailList from './components/List'
import axios from 'axios';

export default {
    name: 'Detail',
    components: {
        DetailBanner,
        DetailHeader,
        DetailList
    },
    data () {
        return {
            sightName: '',
            bannerImg: '',
            gallaryImgs: [],
            list: []
        }
    },
    methods: {
        getDetailInfo () {
           axios.get('/api/detail.json', {
               params: {
                   id: this.$route.params.id
               }
           }).then(response => {
               const res = response.data
               if( res.success == true){
                   this.sightName = res.data.sightName
                   this.bannerImg = res.data.bannerImg
                   this.gallaryImgs = res.data.gallaryImgs
                   this.list = res.data.categoryList
               }
           })
        }
    },
    mounted () {
        this.getDetailInfo()
    }
}
</script>

<style lang="stylus" scoped>
.content {
    height: 50rem
}
</style>



