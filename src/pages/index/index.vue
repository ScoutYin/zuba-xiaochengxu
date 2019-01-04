<template>
<div class="container" @click="clickHandle('test click', $event)">
  <div class="header-wrapper">
    <home-header></home-header>
  </div>
  <div class="banner-wrapper">
    <home-banner></home-banner>
  </div>
  <div class="link-entry-wrapper">
    <home-link-entry></home-link-entry>
  </div>
</div>
</template>

<script>
import HomeHeader from './header'
import HomeBanner from './banner'
import HomeLinkEntry from './link-entry'

export default {
  data () {
    return {
      motto: 'Hello World',
      userInfo: {}
    }
  },

  components: {
    HomeHeader,
    HomeBanner,
    HomeLinkEntry
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
  padding: 0;
}
.header-wrapper {
  display: flex;
  align-items: center;
  width: 100%;
  height: 60px;
  background: #fff;
}
.banner-wrapper {
  padding: 10px $aside-padding;
  overflow: hidden;
  width: 100%;
  height: 200px;
  background: #fff;
}
.link-entry-wrapper {
  padding: 0 $aside-padding;
  padding: 10px 0;
  width: 100%;
  height: 100px;
  background: #fff;
}

</style>
