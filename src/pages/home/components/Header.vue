<template>
  <div class="header">
    <div class="header-left">
    	<div class="iconfont back-icon">&#xe624;</div>
    </div>
    <div class="header-input">
    	<span class="iconfont">&#xe632;</span>	
    		请输入城市/景点/游玩主题
		</div>
    <router-link to="/city">
      <div class="header-right">
        {{ this.$store.state.city }}
        <span class="iconfont city-icon">&#xe64a;</span>
      </div>
    </router-link>
  </div>
</template>
<script>
export default {
  name: 'HomeHeader',
  props: {
    city: String
  }
}
</script>

<style lang="stylus" scoped>
  @import '~@/assets/css/varibles.styl'
  .header
    display: flex
    line-height: .86rem
    background: $bgColor
    color:#fff
    .header-left
      width: .86rem
      float: left
      .back-icon
      	text-align: center
      	font-size: .4rem
    .header-input
      flex: 1
      height: .64rem
      line-height: .64rem
      margin-top: .12rem
      margin-left: .2rem
      padding-left: .2rem
      background:#fff
      color:#ccc
      border-radius:.1rem
    .header-right
      width: 1.55rem
      float: right
      text-align: center
      color: #fff
      .city-icon
      	margin-left: -.04rem
      	font-size: .24rem
</style>
