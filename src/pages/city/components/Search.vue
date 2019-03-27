<template>
    <div class="search">
        <input type="text" class="search-input" placeholder="请输入城市或者拼音"/>
    </div>
</template>
<script>
export default {
    name: 'CitySearch'
}
</script>
<style lang="stylus" scoped>
    @import '~@/assets/css/varibles.styl'
    .search {
        height: .72rem
        padding: 0 .1rem
        background: $bgColor
    }
    .search-input {
        box-sizing: border-box
        width: 100%
        height: .62rem
        line-height: .62rem
        text-align: center
        padding: 0 .2rem
        border-radius: .06rem
        color:#666
    }
</style>

