
<template>
    <div class="swiper-container">
        <swiper :options="swiperOption" v-if="showSwiper">
        <swiper-slide v-for="item of list" :key="item.id">
            <img class="swiper-img" :src="item.imgUrl" >
        </swiper-slide>
        <div class="swiper-pagination"  slot="pagination"></div>
        </swiper>
    </div>
</template>
    
<script>
export default {
    name: 'HomeSwiper',
    props: {
        list: Array
    },
    data() {
        return {
            swiperOption: {
                pagination:'.swiper-pagination',
                loop: true,
                autoplay:1500
            }
        }
    },
    computed: {
        showSwiper() {
            return this.list.length
        }
    }
}
</script>

<style lang="stylus" scoped>
.swiper-container >>> .swiper-pagination-bullet-active{
    background: white
}
.swiper-container{
    overflow:hidden
    width:100%
    height:25px;
    padding-bottom:25%
    background:#eee
}
.swiper-img {
    width:100%
}

</style>
