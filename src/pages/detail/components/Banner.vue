<template>
    <div>
        <div class="banner" @click="handleShowGarray">
            <img class="banner-img" src="http://img1.qunarzz.com/sight/p0/1409/19/adca619faaab0898245dc4ec482b5722.jpg_600x330_f922b488.jpg" />
            <div class="banner-info">
                <div class="banner-title">故宫(AAAAA景区)</div>
                <div class="banner-number"><span class="iconfont banner-icon">&#xe692;</span>80</div>
            </div>
        </div>
        <common-gallary :imgs="imgs" v-show="showGarray" @close="handleCloseGallary"></common-gallary>
    </div>
</template>
<script>
import CommonGallary from 'common/gallary/Gallary'

export default {
    name: 'DetailBanner',
    data () {
        return {
            showGarray: false,
            imgs: [ 'http://img1.qunarzz.com/wugc/p238/201306/16/d9090c728fed64eb93835fbb.jpg_r_800x800_7329a802.jpg',
                    'http://img1.qunarzz.com/sight/p0/1501/af/af47583adca3f972.water.jpg_r_800x800_5a57e1fe.jpg',
                    'http://img1.qunarzz.com/sight/p0/1410/e3/73da8d3e19cdc41c1932d4fcd22ec792.water.jpg_r_800x800_7f96ccf9.jpg',
                    'http://img1.qunarzz.com/wugc/p238/201306/16/d9090c728fed64eb93835fbb.jpg_r_800x800_7329a802.jpg',
                    'http://img1.qunarzz.com/sight/p0/1501/af/af47583adca3f972.water.jpg_r_800x800_5a57e1fe.jpg',
                    'http://img1.qunarzz.com/sight/p0/1410/e3/73da8d3e19cdc41c1932d4fcd22ec792.water.jpg_r_800x800_7f96ccf9.jpg'
                  ]
        }
    },
    methods: {
        handleShowGarray () {
            this.showGarray = true
        },
        handleCloseGallary () {
            this.showGarray = false
        }
    },
    components: {
        CommonGallary
    }
}
</script>

<style lang="stylus" scoped>
.banner {
    position: relative
    overflow: hidden
    height: 0
    padding-bottom: 55.3%
}
.banner-img {
    width: 100%
}
.banner-info {
    display: flex
    position: absolute
    left: 0
    right: 0
    bottom: 0
    line-height: .6rem
    color:#fff
    background-image: linear-gradient(top, rgba(0, 0, 0, 0), rgba(0, 0, 0, 0.8))
}
.banner-title {
    flex: 1
    font-size: .35rem
    padding: 0 .2rem
}
.banner-number {
    height: .35rem
    line-height: .35rem
    margin-top: .15rem
    padding: 0 .3rem
    border-radius: .2rem
    background: rgba(0, 0, 0, .8)
    font-size: .35rem 
}
.banner-icon {
    font-size: .35rem
    margin-right: .1rem
}
</style>


