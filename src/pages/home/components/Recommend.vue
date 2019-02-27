<template>
    <div>
        <div class="title">热销推荐</div>
        <ul>
            <li class="item border-bottom" v-for="item of recommend" :key="item.id">
                <img class="item-img" :src="item.img"/>
                <div class="item-info">
                    <p class="item-title">{{ item.title }}</p>
                    <p class="item-content">{{ item.content }}</p>
                    <p class="item-price">{{ item.price }}</p>
                </div>
            </li>
        </ul>
    </div>
</template>

<script>
export default {
    name: 'HomeRecommend',
    data () {
        return {
            recommend: [{
                id: '01',
                img: 'http://img1.qunarzz.com/sight/p0/1901/a6/a6569d2d53c6c637a3.water.jpg_200x200_f135cf7f.jpg',
                title: '东部华侨城茶溪谷',
                content: '东部华侨城茶溪谷东部华侨城茶溪谷东部华侨城茶溪谷',
                price: '￥89.9'
            }, {
                id: '02',
                img: 'http://img1.qunarzz.com/sight/p0/1508/2e/d9363ce50a88c8c5ff5a138c67687cd4.water.jpg_200x200_1c15c8f5.jpg',
                title: '深圳野生动物园',
                content: '深圳野生动物园深圳野生动物园深圳野生动物园',
                price: '￥69.9'
            }, {
                id: '03',
                img: 'http://img1.qunarzz.com/sight/p0/1812/49/4946928832260941a3.water.jpg_200x200_1790001b.jpg',
                title: '锦绣中华民俗村',
                content: '锦绣中华民俗村锦绣中华民俗村锦绣中华民俗村',
                price: '￥36.9'
            }]
        }
    }
}
</script>

<style lang="stylus" scoped>
 @import '~@/assets/css/mixins.styl'
.title {
    margin-top: .2rem
    line-height: .8rem
    text-indent:.2rem
    background: #eee 
}
.item {
    display: flex
    height: 2.0rem
    overflow: hidden
}
.item-img {
    height: 1.8 rem
    width: 1.8 rem
    padding: .1 rem
}
.item-info {
    flex : 1
    padding :.1 rem
    min-width :0
}
.item-title {
    line-height : .6 rem
    font-size : .32rem
    ellipsis() 
}
.item-content {
    line-height : .4 rem
    color :#ccc
    ellipsis()
}
.item-price {
    margin-top :.2 rem 
    color :#ff9300
    padding : 0.1 rem
    font-size :.48 rem
}

</style>

