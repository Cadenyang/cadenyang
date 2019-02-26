
<template>
    <div class="swiper-container">
        <swiper :options="swiperOption">
        <swiper-slide v-for="item of imgList" :key="item.id">
            <img class="swiper-img" :src="item.imgUrl" >
        </swiper-slide>
        <div class="swiper-pagination"  slot="pagination"></div>
        </swiper>
    </div>
</template>
    
<script>
export default {
    name: 'HomeSwiper',
    data() {
        return {
            swiperOption: {
                pagination:'.swiper-pagination',
                loop: true,
                autoplay:1500
            },
            imgList: [{
                id: '01',
                imgUrl: 'http://mp-piao-admincp.qunarzz.com/mp_piao_admin_mp_piao_admin/admin/20191/f3b6ae9446056f5501f2497f1058b253.jpg_750x200_7608aa31.jpg'
            },{
                id: '02',
                imgUrl: 'http://mp-piao-admincp.qunarzz.com/mp_piao_admin_mp_piao_admin/admin/20192/70f9002b859d6e765533ced2df18db50.jpg_750x200_83cfeb88.jpg'
            },{
                id: '03',
                imgUrl: 'http://img1.qunarzz.com/piao/fusion/1809/61/44400d6591891202.jpg_750x200_7565a05c.jpg'
            }]
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
    height:0;
    padding-bottom:25%
    background:#eee
}
.swiper-img {
    width:100%
}

</style>
