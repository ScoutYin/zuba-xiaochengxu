<template>
<div class="home-header">
  <div class="home-header-location">
    <van-icon name="dingwei"></van-icon>
      <span>杭州</span>
  </div>
  <div class="home-header-search">
    <van-search
      :value="searchValue"
      placeholder="你想住在哪儿"
      @change="handleChange"
    >
    </van-search>
  </div>
</div>
</template>

<script>
export default {
  name: 'HomeHeader',

  methods: {
    handleChange (value) {
      console.log('搜索值', value)
    }
  }
}
</script>

<style lang="scss">
.home-header {
  padding: 0 $aside-padding;
  display: flex;
  align-items: center;
  width: 100%;

  &-location {
    margin-right: 12px;
  }
  &-search {
    flex: 1;
    .van-search {
      border-radius: 50rpx;
      background: #f2f2f2;
    }
    .van-cell {
      background: transparent;
    }
    .van-icon {
      color: #999;
    }
  }
}
</style>
