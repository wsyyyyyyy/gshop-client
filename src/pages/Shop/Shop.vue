<!--  -->
<template>
  <div>
    <!-- 商家头部 -->
    <ShopHeader/>

    <!-- 三个tab选项 -->
    <div class="tab">
      <div class="tab-item">
        <router-link to="/shop/goods">点餐</router-link>
      </div>
      <div class="tab-item">
        <router-link to="/shop/ratings">评价</router-link>
      </div>
      <div class="tab-item">
        <router-link to="/shop/info">商家</router-link>
      </div>
    </div>

    <!-- 显示子路由 -->
    <router-view/>

  </div>
</template>

<script>
// 子组件
import ShopHeader from '../../components/ShopHeader/ShopHeader.vue'

export default {
  data () {
    return {
    };
  },

  mounted() {
    // 发请求获取数据
    this.$store.dispatch('getShopInfo')
  },

  components: {
    ShopHeader
  },

  computed: {},

  methods: {}
}

</script>

<style lang='stylus' rel='stylesheet/stylu'>
  @import "../../common/stylus/mixins.styl"
  .tab
    height 40px
    line-height 40px
    background #fff
    bottom-border-1px(rgba(7, 17, 27, 0.1))
    .tab-item
      float left
      width: 33.33333%
      text-align center
      font-size 14px
      color rgb(77, 85, 93)
      a
        display block
        position relative
        &.router-link-active
          color #02a774
          &::after
            content ''
            position absolute
            left 50%
            bottom 1px
            width 35px
            height 2px
            transform translateX(-50%)
            background #02a774
</style>