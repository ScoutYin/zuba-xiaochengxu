<template>
<div class="home-banner">
  <swiper>
    <swiper-item
      class="home-banner-item"
      v-for="(item, index) in bannerList"
      :key="index"
    >
      <img :src="item" class="home-banner-img">
    </swiper-item>
  </swiper>
</div>
</template>

<script>
export default {
  name: 'HomeBanner',
  data () {
    return {
      bannerList: [
        'https://cdn.baletoo.cn/Uploads/bnanerImageUrl/1/290/oss_5c2497f0c4f9f.jpg'
      ]
    }
  }
}
</script>

<style lang="scss">
.home-banner {
  height: 100%;
  ._swiper {
    height: 100%;
  }
  &-item {
    border-radius: 20px;
  }
  &-img {
    width: 100%;
  }
}
</style>
