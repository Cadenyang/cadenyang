<template>
    <div>
        <div class="title">热销推荐</div>
        <ul>
            <router-link tag="li" class="item border-bottom" v-for="item of list" :key="item.id" :to="'/detail/' + item.id">
                <img class="item-img" :src="item.imgUrl"/>
                <div class="item-info">
                    <p class="item-title">{{ item.title }}</p>
                    <p class="item-content">{{ item.contentStart }}{{ item.title }}{{ item.contentEnd }}</p>
                    <p class="item-price">{{ item.price }}</p>
                </div>
            </router-link>
        </ul>
    </div>
</template>

<script>
export default {
    name: 'HomeRecommend',
    props: {
        list: Array    
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

