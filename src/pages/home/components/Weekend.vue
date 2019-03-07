<template>
    <div>
        <div class="title">周末去哪儿</div>
        <ul>
            <li class="item border-bottom" v-for="item of list" :key="item.id">
                <img class="item-img" :src="item.imgUrl"/>
                <div class="item-info">
                    <p class="item-title">{{ item.title }}</p>
                    <p class="item-content">{{ item.desc }}</p>
                </div>
            </li>
        </ul>
    </div>
</template>

<script>
export default {
    name: 'HomeWeekend',
    props: {
        list: Array
    }
}
</script>

<style lang="stylus" scoped>
 @import '~@/assets/css/mixins.styl'
.title {
    line-height: .8rem
    text-indent:.2rem
    background: #eee 
}
.item {
    overflow: hidden
    height: 0
    padding-bottom: 55%
}
.item-img {
    width: 100%
}
.item-info {
    padding :.1 rem
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

</style>

