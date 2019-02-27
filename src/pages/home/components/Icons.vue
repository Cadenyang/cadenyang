<template>
  <div class="icons">
    <swiper :options="swiperOption">
      <swiper-slide v-for="(page, index) of pages" :key="index">
        <div class="icon" v-for="item of page" :key="item.id">
          <div class="icon-img">
            <img class="icon-img-content" :src="item.img">
          </div>
          <p class="icon-content">{{ item.content }}</p>
        </div>
      </swiper-slide> 
    </swiper>    
  </div>

</template>

<script>
export default {
    name: "HomeIcons",
    data () {
      return {
        swiperOption: {
          autoplay:false
        },
        iconList: [{
          id: '01',
          img: 'http://img1.qunarzz.com/piao/fusion/1803/95/f3dd6c383aeb3b02.png',
          content: '热门景点'
        }, {
          id: '02',
          img: 'http://img1.qunarzz.com/piao/fusion/1804/5a/13ceb38dcf262f02.png',
          content: '一日游'
        }, {
          id: '03',
          img: 'http://img1.qunarzz.com/piao/fusion/1804/ff/fdf170ee89594b02.png',
          content: '深圳必游'
        }, {
          id: '04',
          img: 'http://img1.qunarzz.com/piao/fusion/1803/50/26ffa31b56646402.png',
          content: '海洋馆'
        }, {
          id: '05',
          img: 'http://img1.qunarzz.com/piao/fusion/1803/76/eb88861d78fb9902.png',
          content: '动植物园'
        }, {
          id: '06',
          img: 'http://img1.qunarzz.com/piao/fusion/1803/bd/9f7b9b2b60c1502.png',
          content: '踏青赏花'
        }, {
          id: '07',
          img: 'http://img1.qunarzz.com/piao/fusion/1803/a6/6d97515091789602.png',
          content: '世界之窗'
        }, {
          id: '08',
          img: 'http://img1.qunarzz.com/piao/fusion/1803/e7/d108f17143b40f02.png',
          content: '三月特惠'
        }, {
          id: '09',
          img: 'http://img1.qunarzz.com/piao/fusion/1803/b6/37560ece9c62b502.png',
          content: '东部华侨城'
        }]
      }
    },
    computed: {
      pages () {
        const pages = []
        this.iconList.forEach((item,index)=>{
          const page = Math.floor( index / 8)
          if(!pages[page]){
            pages[page] = []
          }
          pages[page].push(item)
        })
        return pages
      }
    }
}
</script>

<style lang="stylus" scoped>
 @import '~@/assets/css/varibles.styl'
 @import '~@/assets/css/mixins.styl'
.icons >>> .swiper-container {
  height: 0;
  padding-bottom:50%
}
.icons {
  margin-top: .1rem
}
.icon {
  position:relative
  overflow: hidden;
  float: left;
  width: 25%;
  height: 0;
  padding-bottom:25%;
}
.icon-img {
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  bottom: .44rem;
  box-sizing: border-box;
  padding: .1rem
}
.icon-img-content {
  display:block;
  margin: 0 auto;
  height:100%
}
.icon-content {
  position: absolute;
  left: 0;
  right: 0;
  bottom:0;
  height :.44rem;
  line-height :.44rem;
  color :$textColor
  text-align:center;
  ellipsis()
}

</style>


