<template>
<div class="container" @click="clickHandle('test click', $event)">
  <home-header></home-header>
  <div class="banner-wrapper">
    <home-banner></home-banner>
  </div>
</div>
</template>

<script>
import HomeHeader from './header'
import HomeBanner from './banner'

export default {
  data () {
    return {
      motto: 'Hello World',
      userInfo: {}
    }
  },

  components: {
    HomeHeader,
    HomeBanner
  },

  methods: {
    bindViewTap () {
      const url = '../logs/main'
      wx.navigateTo({ url })
    },
    getUserInfo () {
      // 调用登录接口
      wx.login({
        success: () => {
          wx.getUserInfo({
            success: (res) => {
              this.userInfo = res.userInfo
            }
          })
        }
      })
    },
    clickHandle (msg, ev) {
      console.log('clickHandle:', msg, ev)
    }
  },

  created () {
    // 调用应用实例的方法获取全局数据
    this.getUserInfo()
  }
}
</script>

<style lang="scss" scoped>

.container {
  padding: 0 $aside-padding;
}
.banner-wrapper {
  margin-top: 20px;
  overflow: hidden;
  width: 100%;
  height: 200px;
}

</style>
